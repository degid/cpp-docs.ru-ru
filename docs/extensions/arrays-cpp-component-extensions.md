---
title: Массивы (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
helpviewer_keywords:
- array keyword [C++]
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
ms.openlocfilehash: ecd8425bf7bcc9772d7b1327add79b89aea629a7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182244"
---
# <a name="arrays-ccli-and-ccx"></a>Массивы (C++/CLI и C++/CX)

Тип `Platform::Array<T>` в C++/CX или ключевое слово **array** в C++/CLI объявляет массив указанного типа и начальное значение.

## <a name="all-platforms"></a>Все платформы

Массив должен быть объявлен с помощью модификатора дескриптора объекта (^) после закрывающей угловой скобки (>) в объявлении.
Количество элементов массива не является частью типа. Одна переменная массива может ссылаться на массивы разных размеров.

В отличие от стандартной версии C++, индексация не идентична арифметическим операциям над указателями и не коммутативна.

Дополнительные сведения о массивах см. в следующих разделах:

- [Практическое руководство. Использование массивов в C++/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)

- [Списки аргументов переменной длины (...) (C++/CLI)](variable-argument-lists-dot-dot-dot-cpp-cli.md)

## <a name="windows-runtime"></a>Среда выполнения Windows

Массивы являются членами пространства имен `Platform`. Они могут быть только одномерными.

### <a name="syntax"></a>Синтаксис

В первом примере синтаксиса используется агрегатное ключевое слово **ref new**, чтобы выделить память для массива. Во втором примере объявляется локальный массив.

```cpp
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]

[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*qualifiers*<br/>
(Необязательно) Один или несколько из следующих спецификаторов класса хранения: [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [static](../cpp/static-members-cpp.md).

*array-type*<br/>
Тип переменной массива. Допустимые типы: основные типы и классы среды выполнения Windows, ссылочные классы и структуры, классы и структуры значений, а также собственные указатели (`type*`).

*rank*<br/>
(Необязательно) Получает число измерений массива. Должен иметь значение 1.

*identifier*<br/>
Имя переменной массива.

*initialization-type*<br/>
Тип значений, которые инициализируют массив. Как правило *array-type* и *initialization-type* относятся к одному типу. Однако типы могут быть разными, если есть преобразование из *initialization-type* в *array-type*. Например, если *initialization-type* получен из *array-type*.

*initialization-list*<br/>
(Необязательно) Разделенный запятыми список инициализирующих элементы массива значений в фигурных скобках. Например, если *rank-size-list* имеет значение `(3)`, т. е. объявляется одномерным массивом из 3 элементов, *initialization-list* может иметь вид `{1,2,3}`.

### <a name="remarks"></a>Примечания

Во время компиляции с помощью `__is_ref_array(type)` можно определить, является ли тип массивом с подсчетом ссылок. Подробные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

### <a name="examples"></a>Примеры

В следующем примере создается одномерный массив из 100 элементов.

```cpp
// cwr_array.cpp
// compile with: /ZW
using namespace Platform;
ref class MyClass {};
int main() {
   // one-dimensional array
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);
   My1DArray[99] = ref new MyClass();
}
```

## <a name="common-language-runtime"></a>Среда CLR

### <a name="syntax"></a>Синтаксис

В первом примере синтаксиса используется ключевое слово **gcnew**, чтобы выделить память для массива. Во втором примере объявляется локальный массив.

```cpp
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]

[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*qualifiers*<br/>
(Необязательно) Один или несколько из следующих спецификаторов класса хранения: [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [static](../cpp/static-members-cpp.md).

*array-type*<br/>
Тип переменной массива. Допустимые типы: основные типы и классы среды выполнения Windows, ссылочные классы и структуры, классы и структуры значений, собственные указатели (`type*`) и собственные типы POD.

*rank*<br/>
(Необязательно) Получает число измерений массива. Значение по умолчанию — 1; максимальное число — 32. Каждое измерение массива само является массивом.

*identifier*<br/>
Имя переменной массива.

*initialization-type*<br/>
Тип значений, которые инициализируют массив. Как правило *array-type* и *initialization-type* относятся к одному типу. Однако типы могут быть разными, если есть преобразование из *initialization-type* в *array-type*. Например, если *initialization-type* получен из *array-type*.

*rank-size-list*<br/>
Разделенный запятыми список размеров каждого измерения массива. Если задан параметр *initialization-list*, компилятор может определить размер каждого измерения, и тогда параметр *rank-size-list* можно опустить.

*initialization-list*<br/>
(Необязательно) Разделенный запятыми список инициализирующих элементы массива значений в фигурных скобках. Или разделенный запятыми список вложенных элементов *initialization-list*, инициализирующих элементы в многомерном массиве.

Например, если *rank-size-list* имеет значение `(3)`, т. е. объявляется одномерным массивом из 3 элементов, *initialization-list* может иметь вид `{1,2,3}`. Если параметр *rank-size-list* имеет значение `(3,2,4)`, т. е. объявляется трехмерным массивом с 3 элементами в первом измерении, 2 элементами во втором и 4 элементами в третьем, то параметр *initialization-list* может иметь вид `{{1,2,3},{0,0},{-5,10,-21,99}}`.

### <a name="remarks"></a>Примечания

**Массив** находится в пространстве имен [Platform, default, and cli Namespaces](platform-default-and-cli-namespaces-cpp-component-extensions.md).

Как и в стандартной версии C++, индексы массива начинаются от нуля, и массив индексируется с помощью квадратных скобок ([]). В отличие от стандартной версии C++, индексы многомерного массива указываются в списке индексов каждого измерения вместо набора операторов квадратных скобок ([]) для каждого измерения. Например, *идентификатор*[*индекс1*, *индекс2*] вместо *идентификатор*[*индекс1*][*индекс2*].

Все управляемые массивы являются производными от `System::Array`. Любой метод или свойство `System::Array` может применяться непосредственно к переменной массива.

При создании массива указателей на управляемый класс элементы массива инициализируются нулем.

При создании массива, тип элементов которого является типом значения `V`, к каждому элементу массива применяется конструктор по умолчанию для `V`. Дополнительные сведения см. в разделе [Эквиваленты собственным типам C++ в .NET framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).

Во время компиляции с помощью `__is_ref_array(type)` можно определить, является ли тип массивом среды CLR. Подробные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере создается одномерный массив из 100 элементов и трехмерный массив с 3 элементами в первом измерении, 5 элементами во втором и 6 элементами в третьем.

```cpp
// clr_array.cpp
// compile with: /clr
ref class MyClass {};
int main() {
   // one-dimensional array
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);
   My1DArray[99] = gcnew MyClass();

   // three-dimensional array
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);
   My3DArray[0,0,0] = gcnew MyClass();
}
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
