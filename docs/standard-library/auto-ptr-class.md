---
title: Класс auto_ptr
ms.date: 11/04/2016
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
ms.openlocfilehash: 7e652b18b723e2a58c1f4673baf180a14db93477
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834782"
---
# <a name="auto_ptr-class"></a>Класс auto_ptr

Заключает в оболочку интеллектуальный указатель вокруг ресурса, что гарантирует, что ресурс будет удален автоматически, когда точка управления выходит за пределы блока.

Более мощный класс `unique_ptr` имеет более высокий приоритет, чем `auto_ptr`. Дополнительные сведения см. в разделе [Класс unique_ptr](../standard-library/unique-ptr-class.md).

Дополнительные сведения о `throw()` и об обработке исключений см. в статье [Спецификации исключений](../cpp/exception-specifications-throw-cpp.md).

## <a name="syntax"></a>Синтаксис

```cpp
class auto_ptr {
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```

### <a name="parameters"></a>Параметры

*right*\
`auto_ptr`, из которого необходимо получить существующий ресурс.

*ptr*\
Указатель, указанный для замены сохраненного указателя.

## <a name="remarks"></a>Примечания

Шаблон класса описывает смарт-указатель, называемый `auto_ptr` , для выделенного объекта. Указатель должен быть либо null, либо обозначать объект, выделенный **`new`** . `auto_ptr` передает право владения, если сохраненное значение присваивается другому объекту (Он заменяет сохраненное значение после перемещения с пустым указателем.) Деструктор для `auto_ptr<Type>` удаления выделенного объекта. `auto_ptr<Type>` гарантирует, что выделенный объект автоматически удаляется при выходе точки управления за пределы блока даже с использованием созданного исключения. Не следует создавать два объекта `auto_ptr<Type>`, владеющих одним объектом.

Вы можете передать объект `auto_ptr<Type>` по значению в виде аргумента в вызове функции. `auto_ptr` не может быть элементом любого контейнера стандартной библиотеки. Вы не можете надежно управлять последовательностью объектов `auto_ptr<Type>` с помощью контейнера стандартной библиотеки C++.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[auto_ptr](#auto_ptr)|Конструктор для объектов типа `auto_ptr`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[element_type](#element_type)|Этот тип является синонимом для параметра шаблона `Type`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[get](#get)|Эта функция-член возвращает сохраненный указатель `myptr`.|
|[отпускании](#release)|Этот член заменяет сохраненный указатель `myptr` на пустой указатель и возвращает сохраненный ранее указатель.|
|[reset](#reset)|Эта функция-член вычисляет выражение `delete myptr`, но только если значение сохраненного указателя `myptr` изменяется после вызова функции. Затем она заменяет сохраненный указатель на *ptr*.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_eq)|Оператор присваивания, который передает право владения от одного объекта `auto_ptr` другому.|
|[operator*](#op_star)|Оператор удаления ссылки для объектов типа `auto_ptr`.|
|[operator->](#op_arrow)|Оператор для разрешения доступа к членам.|
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|Приводит из одного вида `auto_ptr` в другой вид `auto_ptr`.|
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|Приводит из `auto_ptr` в `auto_ptr_ref`.|

### <a name="auto_ptr"></a><a name="auto_ptr"></a> auto_ptr

Конструктор для объектов типа `auto_ptr`.

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>Параметры

*ptr*\
Указатель на объект, который инкапсулирует `auto_ptr`.

*right*\
Объект `auto_ptr` для копирования конструктором.

#### <a name="remarks"></a>Примечания

Первый *конструктор сохраняет* входные `myptr` и сохраняемые указатели на выделенный объект. Второй конструктор передает права собственности на указатель, хранящийся *справа*, сохраняя *право*. [выпуск](#release) в `myptr` .

Третий конструктор ведет себя так же, как и второй, за исключением того, что он хранит `right` . `ref`. `release` в `myptr` , где `ref` — это ссылка, хранящаяся в `right` .

Конструктор шаблона ведет себя так же, как второй конструктор, при условии, что указатель на `Other` может быть неявно преобразован в указатель на `Type` .

#### <a name="example"></a>Пример

```cpp
// auto_ptr_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

void function ( auto_ptr<Int> &pi )
{
   ++( *pi );
   auto_ptr<Int> pi2( pi );
   ++( *pi2 );
   pi = pi2;
}

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   cout << pi->x << endl;
   function( pi );
   cout << pi->x << endl;
}
```

```Output
Constructing 00311AF8
5
7
Destructing 00311AF8
```

### <a name="element_type"></a><a name="element_type"></a> element_type

Этот тип является синонимом для параметра шаблона `Type`.

```cpp
typedef Type element  _type;
```

### <a name="get"></a><a name="get"></a> get

Эта функция-член возвращает сохраненный указатель `myptr`.

```cpp
Type *get() const throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Сохраненный указатель `myptr` .

#### <a name="example"></a>Пример

```cpp
// auto_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      x = i;
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;
   };

   int x;

};

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   pi.reset( new Int( 6 ) );
   Int* pi2 = pi.get ( );
   Int* pi3 = pi.release ( );
   if (pi2 == pi3)
      cout << "pi2 == pi3" << endl;
   delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="operator"></a><a name="op_eq"></a> operator=

Оператор присваивания, который передает право владения от одного объекта `auto_ptr` другому.

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>Параметры

*right*\
Объект типа `auto_ptr`.

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект типа `auto_ptr<Type>`.

#### <a name="remarks"></a>Примечания

Присваивание вычисляет выражение `delete myptr` , но только в том случае, если сохраненный указатель `myptr` изменяется в результате назначения. Затем он передает права собственности на указатель, хранящийся *справа*, сохраняя *право*. [выпуск](#release) в `myptr` . Функция возвращает __ \* this__.

#### <a name="example"></a>Пример

Пример использования оператора Member см. в разделе [auto_ptr](#auto_ptr).

### <a name="operator"></a><a name="op_star"></a> operator

Оператор удаления ссылки для объектов типа `auto_ptr`.

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект типа `Type` , которому принадлежит указатель.

#### <a name="remarks"></a>Примечания

Оператор косвенного обращения возвращает `*`[get](#get). Следовательно, сохраненный указатель не должен быть пустым.

#### <a name="example"></a>Пример

Пример использования функции члена см. в разделе [auto_ptr](#auto_ptr).

### <a name="operator-gt"></a><a name="op_arrow"></a> operator&gt;

Оператор для разрешения доступа к членам.

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Член объекта, `auto_ptr` которому принадлежит.

#### <a name="remarks"></a>Примечания

Оператор выбора возвращает [Get](#get) `( )` , поэтому элемент *AP*в выражении ->  **member** ведет себя так же, как ( *AP*). **Get**()) — > **элемент**, где *AP* — это объект класса `auto_ptr` \< **Type**> . Следовательно, сохраненный указатель не должен иметь значение NULL и `Type` должен быть классом, структурой или типом объединения с `member` элементом.

#### <a name="example"></a>Пример

Пример использования функции члена см. в разделе [auto_ptr](#auto_ptr).

### <a name="operator-auto_ptrltothergt"></a><a name="op_auto_ptr_lt_other_gt"></a> Оператор auto_ptr &lt; другой&gt;

Приводит из одного вида `auto_ptr` в другой вид `auto_ptr`.

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Оператор приведения типа возвращает `auto_ptr` \< **Other**> ( ** \*this**).

#### <a name="example"></a>Пример

```cpp
// auto_ptr_op_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;
int main()
{
   auto_ptr<int> pi ( new int( 5 ) );
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;
}
```

### <a name="operator-auto_ptr_refltothergt"></a><a name="op_auto_ptr_ref_lt_other_gt"></a> Оператор auto_ptr_ref &lt; другой&gt;

Приводит из `auto_ptr` в `auto_ptr_ref`.

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Оператор приведения типа возвращает **auto_ptr_ref** \< **Other**> ( ** \*this**).

#### <a name="example"></a>Пример

```cpp
// auto_ptr_op_auto_ptr_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer
    // f(ciap);
    f(iap); // compiles, but gives up ownership of pointer

            // here, iap owns a destroyed pointer so the following is bad:
            // *iap = 5; // BOOM

    cout << "main exiting\n";
}
```

```Output
~C:  2
main exiting
~C:  1
```

### <a name="release"></a><a name="release"></a> отпускании

Этот член заменяет сохраненный указатель `myptr` на пустой указатель и возвращает сохраненный ранее указатель.

```cpp
Type *release() throw();
```

#### <a name="return-value"></a>Возвращаемое значение

Ранее сохраненный указатель.

#### <a name="remarks"></a>Примечания

Этот член заменяет сохраненный указатель `myptr` на пустой указатель и возвращает сохраненный ранее указатель.

#### <a name="example"></a>Пример

```cpp
// auto_ptr_release.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="reset"></a><a name="reset"></a> reset

Функция-член вычисляет выражение `delete myptr` , но только в том случае, если значение сохраненного указателя `myptr` изменяется в результате вызова функции. Затем она заменяет сохраненный указатель на `ptr`.

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>Параметры

*ptr*\
Указатель, заданный для замены сохраненного указателя `myptr` .

#### <a name="example"></a>Пример

```cpp
// auto_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

## <a name="see-also"></a>См. также раздел

[Класс unique_ptr](../standard-library/unique-ptr-class.md)
