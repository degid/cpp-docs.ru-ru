---
title: Расширения Майкрософт для языков C и C++
ms.date: 06/14/2018
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
ms.openlocfilehash: 77f2ed64a0c816d84e67f66b664141581a9fad51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231511"
---
# <a name="microsoft-extensions-to-c-and-c"></a>Расширения Майкрософт для языков C и C++

Visual C++ расширяет стандарты ANSI C и ANSI C++ следующим образом.

## <a name="keywords"></a>Keywords

Добавлено несколько ключевых слов. В списке в [ключевых словах](../../cpp/keywords-cpp.md)ключевые слова с двумя символами подчеркивания являются Visual C++ расширениями.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Вне класса определение статических константных целочисленных элементов (или enum)

В стандарте (**/Za**) необходимо сделать неклассическое определение для членов данных, как показано ниже:

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

В параметре **/Ze**определение вне класса является необязательным для статических, константных целочисленных и постоянных элементов данных enum. Инициализаторы в классе могут иметь только целочисленные типы и перечисления, являющиеся статическими и const. выражение инициализации должно быть константным выражением.

Чтобы избежать ошибок, когда в файле заголовка содержится определение вне класса и файл заголовка включается в несколько исходных файлов, используйте [selectany](../../cpp/selectany.md). Пример:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>Приведения

Компилятор C++ и компилятор C поддерживают следующие типы приведений, отличных от ANSI:

- Преобразования, отличные от ANSI, для создания l-значений. Пример:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > Это расширение доступно только на языке C. Можно использовать следующую стандартную форму ANSI C в коде C++, чтобы изменить указатель так, как если бы он был указателем на другой тип.

   Предыдущий пример можно переписывать следующим образом для соответствия стандарту ANSI C.

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- Не-ANSI приведение указателя функции к указателю на данные. Пример:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   Чтобы выполнить такое же приведение и обеспечить совместимость с ANSI, можно привести указатель функции к типу, `uintptr_t` прежде чем присвоить его указателю данных:

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>Списки аргументов переменной длины

Компилятор C++ и компилятор C поддерживают декларатор функции, который задает переменное число аргументов, за которыми следует определение функции, предоставляющую тип.

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>Однострочные комментарии

Компилятор C поддерживает однострочные комментарии, которые вводятся с помощью двух символов косой черты (//):

```C
// This is a single-line comment.
```

## <a name="scope"></a>Область

Компилятор C поддерживает следующие функции, связанные с областью действия.

- Переопределение внешних элементов как статических:

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- Использование немягких переопределений typedef в пределах одной области действия:

   ```C
   typedef int INT;
   typedef int INT;
   ```

- Деклараторы функций имеют область действия файла:

   ```C
   void func1()
   {
       extern int func2( double );
   }
   int main( void )
   {
       func2( 4 );    //  /Ze passes 4 as type double
   }                  //  /Za passes 4 as type int
   ```

- Использование переменных области блока, которые инициализируются с помощью неконстантных выражений:

   ```C
   int clip( int );
   int bar( int );
   int main( void )
   {
       int array[2] = { clip( 2 ), bar( 4 ) };
   }
   int clip( int x )
   {
       return x;
   }
   int bar( int x )
   {
       return x;
   }
   ```

## <a name="data-declarations-and-definitions"></a>Объявления и определения данных

Компилятор C поддерживает следующие функции объявления и определения данных.

- Смешанные символьные и строковые константы в инициализаторе:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- Битовые поля, имеющие базовые типы, отличные от **`unsigned int`** или **`signed int`** .

- Деклараторы, у которых нет типа:

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- Неразмерные массивы в качестве последнего поля в структурах и объединениях:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- Безымянные (анонимные) структуры:

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- Безымянные (анонимные) объединения:

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- Безымянные члены:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>Встроенные функции с плавающей запятой

Компилятор x86 C++ и компилятор C поддерживают встроенное создание функций,,,,,,, `atan` `atan2` `cos` `exp` `log` `log10` `sin` `sqrt` и `tan` при указании **/Oi** . Для компилятора C соответствие ANSI потеряно, если используются эти встроенные функции, так как они не задают `errno` переменную.

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Передача параметра указателя, не являющегося константой, в функцию, которая принимает ссылку на параметр-указатель const

Это расширение для C++. Этот код будет компилироваться с параметром **/Ze**:

```cpp
typedef   int   T;

const T  acT = 9;      // A constant of type 'T'
const T* pcT = &acT;   // A pointer to a constant of type 'T'

void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'
{
   rpcT = pcT;
}

T*   pT;               // A pointer to a 'T'

void func ()
{
   func2 ( pT );      // Should be an error, but isn't detected
   *pT   = 7;         // Invalidly overwrites the constant 'acT'
}
```

## <a name="iso646h-not-enabled"></a>ISO646. H не включено

В разделе **/Ze**необходимо включить iso646.h, если нужно использовать текстовые формы следующих операторов:

- && (и)

- &= (and_eq)

- & (BITAND)

- &#124; (bitor)

- ~ (соблюдается)

- ! недостаточно

- ! = (not_eq)

- &#124;&#124; (или)

- &#124;= (or_eq)

- ^ (XOR)

- ^ = (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Адрес строкового литерала имеет тип const char [], а не const char (*) []

В следующем примере выводится `char const (*)[4]` в режиме **/Za**, но в параметре `char const [4]` **/Ze**.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>См. также раздел

- [/ZA,/Ze (Отключение расширений языка)](za-ze-disable-language-extensions.md)
- [Параметры компилятора MSVC](compiler-options.md)
- [Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
