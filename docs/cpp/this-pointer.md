---
title: 'Указатель :::no-loc(this):::'
description: :::no-loc(this):::Указатель является созданным компилятором указателем на текущий объект в нестатических функциях-членах.
ms.date: 01/22/2020
f1_keywords:
- :::no-loc(this):::_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- 'pointers, to :::no-loc(class)::: instance'
- ':::no-loc(this)::: pointer'
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- ':::no-loc(this):::'
- ':::no-loc(class):::'
- ':::no-loc(struct):::'
- ':::no-loc(union):::'
- ':::no-loc(sizeof):::'
- ':::no-loc(const):::'
- ':::no-loc(volatile):::'
ms.openlocfilehash: c851beaba7fe1091ffd7827714f90307303058c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225830"
---
# <a name="no-locthis-pointer"></a>Указатель :::no-loc(this):::

**`:::no-loc(this):::`** Указатель является указателем, доступным только в нестатических функциях-членах **`:::no-loc(class):::`** **`:::no-loc(struct):::`** типа, или **`:::no-loc(union):::`** . Он указывает на объект, для которого вызывается функция-член. Статические функции-члены не имеют **`:::no-loc(this):::`** указателя.

## <a name="syntax"></a>Синтаксис

```cpp
:::no-loc(this):::
:::no-loc(this):::->member-identifier
```

## <a name="remarks"></a>Примечания

**`:::no-loc(this):::`** Указатель объекта не является частью самого объекта. Он не отражается в результате выполнения **`:::no-loc(sizeof):::`** инструкции для объекта. При вызове нестатической функции-члена для объекта компилятор передает адрес объекта в функцию в виде скрытого аргумента. Например, при вызове следующей функции

```cpp
myDate.setMonth( 3 );
```

может интерпретироваться как:

```cpp
setMonth( &myDate, 3 );
```

Адрес объекта доступен в функции-члене в качестве **`:::no-loc(this):::`** указателя. Большинство **`:::no-loc(this):::`** используемых указателей являются неявными. Он является юридическим, хотя и ненужным, для использования явной **`:::no-loc(this):::`** ссылки на члены :::no-loc(class)::: . Например:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   :::no-loc(this):::->month = mn;      // are equivalent
   (*:::no-loc(this):::).month = mn;
}
```

Выражение **`*:::no-loc(this):::`** обычно используется для возврата текущего объекта из функции-члена:

```cpp
return *:::no-loc(this):::;
```

**`:::no-loc(this):::`** Указатель также используется для защиты от самостоятельной ссылки:

```cpp
if (&Object != :::no-loc(this):::) {
// do not execute in cases of self-reference
```

> [!NOTE]
> Поскольку **`:::no-loc(this):::`** указатель не является изменяемым, присваивания **`:::no-loc(this):::`** указателю не допускаются. Более ранние реализации C++ позволяли назначать **`:::no-loc(this):::`** .

Иногда **`:::no-loc(this):::`** указатель используется напрямую, например для управления самостоятельными ссылочными данными :::no-loc(struct)::: Урес, где требуется адрес текущего объекта.

## <a name="example"></a>Пример

```cpp
// :::no-loc(this):::_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

:::no-loc(class)::: Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( :::no-loc(const)::: Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( :::no-loc(const)::: Buf &otherbuf )
{
    if( &otherbuf != :::no-loc(this)::: )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *:::no-loc(this):::;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-no-locthis-pointer"></a>Тип :::no-loc(this)::: указателя

**`:::no-loc(this):::`** Тип указателя можно изменить в объявлении функции с помощью **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** ключевых слов и. Чтобы объявить функцию, имеющую один из этих атрибутов, добавьте ключевые слова после списка аргументов функции.

Рассмотрим пример.

```cpp
// type_of_:::no-loc(this):::_pointer1.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

В приведенном выше коде объявляется функция-член, `X` в которой **`:::no-loc(this):::`** указатель обрабатывается как **`:::no-loc(const):::`** указатель на **`:::no-loc(const):::`** объект. Можно использовать сочетания параметров *ОПС-mod-list* , но они всегда изменяют объект, на который указывает **`:::no-loc(this):::`** указатель, а не сам указатель. В следующем объявлении объявляется функция `X` , в которой **`:::no-loc(this):::`** указатель является **`:::no-loc(const):::`** указателем на **`:::no-loc(const):::`** объект:

```cpp
// type_of_:::no-loc(this):::_pointer2.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

Тип **`:::no-loc(this):::`** в функции-члене описан в следующем синтаксисе. *Список «ОПС-квалификатор»* определяется на основе декларатора функции-члена. Это может быть **`:::no-loc(const):::`** или **`:::no-loc(volatile):::`** (или). * :::no-loc(class)::: -Type* — это имя :::no-loc(class)::: :

[*ОПС-квалификатор-List*] * :::no-loc(class)::: -тип* ** \* :::no-loc(const)::: :::no-loc(this)::: **

Иными словами, **`:::no-loc(this):::`** указатель всегда является :::no-loc(const)::: указателем. Его нельзя назначить.  **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** Квалификаторы или, используемые в объявлении функции члена, применяются к :::no-loc(class)::: экземпляру, на **`:::no-loc(this):::`** который указывает указатель в области этой функции.

В следующей таблице приведены дополнительные сведения о том, как работают эти модификаторы.

### <a name="semantics-of-no-locthis-modifiers"></a>Семантика :::no-loc(this)::: модификаторов

|Модификатор|Значение|
|--------------|-------------|
|**`:::no-loc(const):::`**|Не удается изменить данные элемента; не удается вызвать функции члена, которые не являются **`:::no-loc(const):::`** .|
|**`:::no-loc(volatile):::`**|Данные элементов загружаются из памяти при каждом доступе к ним; отключает некоторые оптимизации.|

Передача **`:::no-loc(const):::`** объекта в функцию-член, которая не имеет значение, является ошибкой **`:::no-loc(const):::`** .

Аналогично, также возникает ошибка передачи **`:::no-loc(volatile):::`** объекта в функцию-член, которая не является **`:::no-loc(volatile):::`** .

Функции-члены, объявленные как **`:::no-loc(const):::`** не могут изменять данные элементов — в таких функциях **`:::no-loc(this):::`** указатель является указателем на **`:::no-loc(const):::`** объект.

> [!NOTE]
> Con :::no-loc(struct)::: OR и де :::no-loc(struct)::: or нельзя объявлять как **`:::no-loc(const):::`** или **`:::no-loc(volatile):::`** . Однако они могут вызываться для **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** объектов или.

## <a name="see-also"></a>См. также статью

[Ключевые слова](../cpp/keywords-cpp.md)
