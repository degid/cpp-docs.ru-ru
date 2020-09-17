---
title: '&lt;ios&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ios>
- ios/std::<ios>
helpviewer_keywords:
- ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
ms.openlocfilehash: 8ba03e5ab5dd90a6f29e08b01576803a00f0bd24
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845488"
---
# <a name="ltiosgt"></a>&lt;ios&gt;

Определяет несколько основных типов и функций при работе с потоками ввода-вывода. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода-вывода. Его редко приходится включать напрямую.

## <a name="requirements"></a>Требования

**Заголовок**: \<ios>

**Пространство имен:** std

> [!NOTE]
> \<ios>Библиотека использует `#include <iosfwd>` инструкцию.

## <a name="remarks"></a>Примечания

Существует большая группа функций — манипуляторы. Манипулятор, объявленный в, \<ios> изменяет значения, хранящиеся в объекте аргумента класса [ios_base](../standard-library/ios-base-class.md). Другие манипуляторы выполняют действия с потоками, управляемыми объектами типа, производного от этого класса, например специализацией одного из шаблонов классов [basic_istream](../standard-library/basic-istream-class.md) или [basic_ostream](../standard-library/basic-ostream-class.md). Например, [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) очищает флаг формата `ios_base::skipws` в объекте `str` , который может иметь один из этих типов.

Вы можете также вызвать манипулятор путем вставки его в поток вывода или извлечения из потока ввода благодаря специальным операциям вставки и извлечения, доступным для классов, производных от `ios_base`. Пример:

```cpp
istr>> noskipws;
```

вызывает [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**).

## <a name="members"></a>Элементы

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[iOS](../standard-library/ios-typedefs.md#ios)|Поддерживает класс ios из старой библиотеки iostream.|
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|Поддерживает внутренние операции.|
|[streampos](../standard-library/ios-typedefs.md#streampos)|Содержит текущее положение указателя буфера или указателя файла.|
|[данные streamsize](../standard-library/ios-typedefs.md#streamsize)|Определяет размер потока.|
|[виос](../standard-library/ios-typedefs.md#wios)|Поддерживает класс wios из старой библиотеки iostream.|
|[встреампос](../standard-library/ios-typedefs.md#wstreampos)|Содержит текущее положение указателя буфера или указателя файла.|

### <a name="manipulators"></a>Манипуляторы

|Имя|Описание|
|-|-|
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Указывает, что переменные типа [bool](../cpp/bool-cpp.md) отображаются как **`true`** или **`false`** в потоке.|
|[уменьшение](../standard-library/ios-functions.md#dec)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 10.|
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Устанавливает флаги объекта `ios_base` в соответствии с форматом отображения значений с плавающей запятой, принятым по умолчанию.|
|[fixed](../standard-library/ios-functions.md#fixed)|Устанавливает режим отображения чисел с плавающей запятой в нотации фиксированного десятичного формата.|
|[hex](../standard-library/ios-functions.md#hex)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 16.|
|[свертывания](../standard-library/ios-functions.md#hexfloat)|
|[internal](../standard-library/ios-functions.md#internal)|Устанавливает режим выравнивания знака числа по левому краю, а самого числа — по правому краю.|
|[слева](../standard-library/ios-functions.md#left)|Устанавливает режим добавления левого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.|
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Устанавливает режим отображения переменных типа [bool](../cpp/bool-cpp.md) в потоке в виде 1 или 0.|
|[ношовбасе](../standard-library/ios-functions.md#noshowbase)|Отключает отображение основания нотации, в которой отображается число.|
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Отображает только целую часть числа с плавающей запятой, дробная часть которого равна нулю.|
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Устанавливает режим отображения положительных чисел без обязательного знака.|
|[noskipws](../standard-library/ios-functions.md#noskipws)|Устанавливает режим чтения пробелов потоком ввода.|
|[наунитбуф](../standard-library/ios-functions.md#nounitbuf)|Устанавливает режим использования буфера выходных данных и обработки данных при заполнении буфера.|
|[прописные буквы](../standard-library/ios-functions.md#nouppercase)|Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в нижнем регистре.|
|[октября](../standard-library/ios-functions.md#oct)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 8.|
|[Правильно](../standard-library/ios-functions.md#right)|Устанавливает режим добавления правого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.|
|[экспоненциаль](../standard-library/ios-functions.md#scientific)|Устанавливает режим отображения чисел с плавающей запятой с использованием экспоненциального представления.|
|[showbase](../standard-library/ios-functions.md#showbase)|Включает отображение основания нотации, в которой отображается число.|
|[showpoint](../standard-library/ios-functions.md#showpoint)|Отображает целую часть числа с плавающей запятой и цифры справа от десятичной запятой даже в том случае, если дробная часть равна нулю.|
|[showpos](../standard-library/ios-functions.md#showpos)|Устанавливает режим отображения положительных чисел с обязательным знаком.|
|[skipws](../standard-library/ios-functions.md#skipws)|Устанавливает режим игнорирования пробелов потоком ввода.|
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Устанавливает режим обработки выходных данных при наличии данных в буфере.|
|[верхний регистр](../standard-library/ios-functions.md#uppercase)|Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в верхнем регистре.|

### <a name="error-reporting"></a>Отчет об ошибках

|Имя|Описание|
|-|-|
|[io_errc](../standard-library/ios-functions.md#io_errc)||
|[is_error_code_enum](../standard-library/ios-functions.md#is_error_code_enum)||
|[iostream_category](../standard-library/ios-functions.md#iostream_category)||
|[make_error_code](../standard-library/ios-functions.md#make_error_code)||
|[make_error_condition](../standard-library/ios-functions.md#make_error_condition)||

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[basic_ios](../standard-library/basic-ios-class.md)|Шаблон класса описывает хранилище и функции-члены, общие для входных потоков (класса Template [basic_istream](../standard-library/basic-istream-class.md)) и потоков вывода (шаблона класса [basic_ostream](../standard-library/basic-ostream-class.md)), которые зависят от параметров шаблона.|
|[fpos](../standard-library/fpos-class.md)|Шаблон класса описывает объект, который может хранить всю информацию, необходимую для восстановления произвольного индикатора положения файла в любом потоке.|
|[ios_base](../standard-library/ios-base-class.md)|Этот класс описывает хранилище и функции-члены общие для обоих потоков (ввода и вывода), не зависящих от параметров шаблона.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
