---
title: Функции &lt;new&gt;
ms.date: 11/04/2016
f1_keywords:
- new/std::get_new_handler
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: 6b51a5bcbb9c90370cef1391d4020862d2e2cefd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212180"
---
# <a name="ltnewgt-functions"></a>Функции &lt;new&gt;

## <a name="get_new_handler"></a><a name="get_new_handler"></a>get_new_handler

```cpp
new_handler get_new_handler() noexcept;
```

### <a name="remarks"></a>Примечания

Возвращает текущий `new_handler`.

## <a name="launder"></a><a name="launder"></a>лаундер

```cpp
template <class T>
    constexpr T* launder(T* ptr) noexcept;
```

### <a name="parameters"></a>Параметры

*ptr*\
Адрес байта в памяти, в котором содержится объект, тип которого аналогичен *T*.

### <a name="return-value"></a>Возвращаемое значение

Значение типа *T \* * , указывающее на X.

### <a name="remarks"></a>Примечания

Также называется барьером оптимизации указателя.

Используется как константное выражение, если значение его аргумента может использоваться в константном выражении. Байт хранилища можно получить с помощью значения указателя, указывающего на объект, если в хранилище, занятом другим объектом, — объект с аналогичным указателем.

### <a name="example"></a>Пример

```cpp
struct X { const int n; };

X *p = new X{3};
const int a = p->n;
new (p) X{5}; // p does not point to new object because X::n is const
const int b = p->n; // undefined behavior
const int c = std::launder(p)->n; // OK
```

## <a name="nothrow"></a><a name="nothrow"></a>nothrow

Предоставляет объект, который будет использоваться в качестве аргумента для **`nothrow`** версий **`new`** и **`delete`** .

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Примечания

Объект используется в качестве аргумента функции для соответствия типу параметра [std::nothrow_t](../standard-library/nothrow-t-structure.md).

### <a name="example"></a>Пример

См. разделы [operator new](../standard-library/new-operators.md#op_new) и [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) с примерами использования `std::nothrow_t` в качестве параметра функции.

## <a name="set_new_handler"></a><a name="set_new_handler"></a>set_new_handler

Устанавливает пользовательскую функцию, которая будет вызываться при сбое **оператора New** при попытке выделить память.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>Параметры

*пнев*\
`new_handler`Устанавливаемый объект.

### <a name="return-value"></a>Возвращаемое значение

0 для первого вызова и предыдущее `new_handler` при последующих вызовах.

### <a name="remarks"></a>Примечания

Функция сохраняет *Пнев* в статическом новом указателе [обработчика](../standard-library/new-typedefs.md#new_handler) , который он обслуживает, а затем возвращает значение, сохраненное ранее в указателе. Новый обработчик используется [оператором new](../standard-library/new-operators.md#op_new)(**size_t**).

### <a name="example"></a>Пример

```cpp
// new_set_new_handler.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;
void __cdecl newhandler( )
{
   cout << "The new_handler is called:" << endl;
   throw bad_alloc( );
   return;
}

int main( )
{
   set_new_handler (newhandler);
   try
   {
      while ( 1 )
      {
         new int[5000000];
         cout << "Allocating 5000000 ints." << endl;
      }
   }
   catch ( exception e )
   {
      cout << e.what( ) << endl;
   }
}
```

```Output
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
The new_handler is called:
bad allocation
```
