---
title: Класс vector&lt;bool&gt;
ms.date: 11/04/2016
f1_keywords:
- vector<bool>
- vector/std::vector::flip
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
ms.openlocfilehash: 24a18197c6b335172b88d2db37e8ac7ed57f58b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845423"
---
# <a name="vectorltboolgt-class"></a>Класс vector&lt;bool&gt;

`vector<bool>`Класс является частичной специализацией [вектора](../standard-library/vector-class.md) для элементов типа **`bool`** . Он имеет распределитель для базового типа, используемого специализацией, который обеспечивает оптимизацию пространства путем хранения одного **`bool`** значения на бит.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Примечания

Поведение данной специализации шаблона класса аналогично поведению класса vector, за исключением различий, указанных в данной статье.

Операции, которые работают с **`bool`** типом, соответствуют значениям в хранилище контейнера. Параметр `allocator_traits::construct` не используется для создания данных значений.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_pointer](#const_pointer)|Typedef для итератора `const_iterator`, который может применяться как указатель константы на логический элемент `vector<bool>`.|
|[const_reference](#const_reference)|Typedef для **`bool`** . После инициализации данный объект не проверяет наличие обновлений исходного значения.|
|[pointer](#pointer)|Typedef для итератора `iterator`, который может применяться как указатель на логический элемент `vector<bool>`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[flip](#flip)|Обращает все биты в `vector<bool>`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `vector<bool>`.|
|[operator&#91;&#93;](#op_at)|Возвращает смоделированной ссылку на элемент `vector<bool>` в указанную позицию.|
|`at`|Функция аналогична функции неспециализированного [вектора](../standard-library/vector-class.md):: at, за исключением того, что в ней используется прокси-класс [vector \<bool> :: Reference](#reference_class). См. также [operator[]](#op_at).|
|`front`|Функция аналогична функции неспециализированного [вектора](../standard-library/vector-class.md):: Front, за исключением того, что в ней используется прокси-класс [vector \<bool> :: Reference](#reference_class). См. также [operator[]](#op_at).|
|`back`|Функция аналогична функции неспециализированного [вектора](../standard-library/vector-class.md):: Back, за исключением того, что в ней используется прокси-класс [vector \<bool> :: Reference](#reference_class). См. также [operator[]](#op_at).|

### <a name="proxy-class"></a>Прокси-класс

|Имя|Описание|
|-|-|
|[\<bool>класс ссылки Vector](#reference_class)|Класс, действующий как прокси для моделирования поведения `bool&`, объекты которого могут предоставлять ссылки на элементы (одиночные биты) в пределах объекта `vector<bool>`.|

## <a name="requirements"></a>Требования

**Заголовок**: \<vector>

**Пространство имен:** std

## <a name="vectorboolconst_pointer"></a><a name="const_pointer"></a> Vector \<bool> :: const_pointer

Тип, описывающий объект, который можно использовать в качестве константного указателя на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef const_iterator const_pointer;
```

## <a name="vectorboolconst_reference"></a><a name="const_reference"></a> Vector \<bool> :: const_reference

Тип, описывающий объект, который можно использовать в качестве константной ссылки на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения и примеры кода см. в разделе [vector&lt;bool&gt;::reference::operator=](#reference_operator_eq).

## <a name="vectorboolflip"></a><a name="flip"></a> Vector \<bool> :: переворот

Реверсирует все биты в `vector<bool>`.

```cpp
void flip();
```

### <a name="example"></a>Пример

```cpp
// vector_bool_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha; // format output for subsequent code

    vector<bool> vb = { true, false, false, true, true };
    cout << "The vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vb.flip();

    cout << "The flipped vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="vectorbooloperator"></a><a name="op_at"></a> Vector \<bool> ::operator[]

Возвращает смоделированной ссылку на элемент `vector<bool>` в указанную позицию.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Параметры

*POS*\
Позиция элемента `vector<bool>`.

### <a name="return-value"></a>Возвращаемое значение

Объект [vector \<bool> :: Reference](#reference_class) или [vector \<bool> :: const_reference](#const_reference) , содержащий значение индексированного элемента.

Если заданная позиция больше или равна размеру контейнера, результат не определен.

### <a name="remarks"></a>Примечания

Если вы компилируете с набором _ITERATOR_DEBUG_LEVEL, то при попытке получить доступ к элементу за пределами вектора возникает ошибка времени выполнения.  Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

В этом примере кода показано правильное использование `vector<bool>::operator[]` и две распространенные ошибки кода, которые заносятся в комментарий. Эти ошибки вызывают ошибки, так как адрес `vector<bool>::reference` объекта, который `vector<bool>::operator[]` возвращает значение, не может быть выполнен.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;
    vector<bool> vb;

    vb.push_back(true);
    vb.push_back(false);

    //    bool* pb = &vb[1]; // conversion error - do not use
    //    bool& refb = vb[1];   // conversion error - do not use
    bool hold = vb[1];
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;

    // Note this doesn't modify hold.
    vb[1] = true;
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;
}
```

## <a name="vectorboolpointer"></a><a name="pointer"></a> Vector \<bool> ::p оинтер

Тип, описывающий объект, который можно использовать в качестве указателя на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef iterator pointer;
```

## <a name="vectorboolreference-class"></a><a name="reference_class"></a>\<bool>класс Vector:: Reference

`vector<bool>::reference`Класс является прокси-классом, предоставляемым [ \<bool> классом Vector](../standard-library/vector-bool-class.md) для имитации `bool&` .

### <a name="remarks"></a>Примечания

Необходима смоделированная ссылка, поскольку C++ изначально не допускает прямых ссылок на биты. `vector<bool>` использует только один бит на элемент, ссылку на который можно создать с помощью данного класса прокси. Однако моделирование ссылки является незавершенным, поскольку определенные назначения не являются допустимыми. Например, поскольку адрес `vector<bool>::reference` объекта не может быть получен, следующий код, использующий [ \<bool> оператор Vector::operator&#91;&#93;](#op_at) , неверен:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="vectorboolreferenceflip"></a><a name="reference_flip"></a> вектор \<bool> :: Reference:: переворот

Инвертирует логическое значение элемента [вектора \<bool> ](../standard-library/vector-bool-class.md) , на который указывает ссылка.

```cpp
void flip();
```

#### <a name="example"></a>Пример

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

### <a name="vectorboolreferenceoperator-bool"></a><a name="reference_operator_bool"></a> Vector \<bool> :: Reference:: оператор bool

Обеспечивает неявное преобразование из `vector<bool>::reference` в **`bool`** .

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Логическое значение элемента \<bool> объекта Vector.

#### <a name="remarks"></a>Примечания

Объект `vector<bool>` невозможно изменить при помощи данного оператора.

### <a name="vectorboolreferenceoperator"></a><a name="reference_operator_eq"></a> Vector \<bool> :: Reference::operator=

Присваивает биту логическое значение или значение, которое содержит элемент со ссылкой.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка на элемент, значение которого должно быть присвоено биту.

*val*\
Логическое значение, которое должно быть присвоено биту.

#### <a name="example"></a>Пример

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="vectorboolswap"></a><a name="swap"></a> Vector \<bool> :: swap

Статическая функция-член, которая обменивает два элемента логических векторов ( `vector<bool>` ) с помощью класса прокси [vector \<bool> :: Reference](#reference_class).

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Элемент, который должен быть заменен *правым* элементом.

*right*\
Элемент, который должен быть заменен *левым* элементом.

### <a name="remarks"></a>Примечания

Данная перегрузка поддерживает специальные прокси-требования `vector<bool>`. [vector::swap](../standard-library/vector-class.md) имеет те же функции, что и одноаргументная перегрузка `vector<bool>::swap()`.

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
