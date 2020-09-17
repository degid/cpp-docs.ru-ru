---
title: '&lt;valarray&gt;'
ms.date: 11/04/2016
f1_keywords:
- <valarray>
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
ms.openlocfilehash: 9d2f3097637b3708c16f3048a34dd32b7f6fd80b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840145"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Определяет шаблон класса valarray и многочисленные вспомогательные шаблоны и функции классов.

## <a name="requirements"></a>Требования

**Заголовок:**\<valarray>

**Пространство имен:** std

> [!NOTE]
> \<valarray>Библиотека использует инструкцию "#include <initializer_list>".

## <a name="remarks"></a>Примечания

Эти шаблоны и функции классов допускаются необычные широты в интересах повышения производительности. В частности, любой возвращаемый функцией тип `valarray<T1>` может возвращать объект другого типа T2. В этом случае любая функция, принимающая один или несколько аргументов типа, `valarray<T2>` должна иметь перегрузки, принимающие произвольные сочетания этих аргументов, каждый из которых заменен аргументом типа T2.

## <a name="members"></a>Элементы

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[abs](../standard-library/valarray-functions.md#abs)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны абсолютному значению элементов входного valarray.|
|[acos](../standard-library/valarray-functions.md#acos)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арккосинусу элементов входного valarray.|
|[asin](../standard-library/valarray-functions.md#asin)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арксинусу элементов входного valarray.|
|[atan](../standard-library/valarray-functions.md#atan)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арифметическому значению арктангенса элементов входного valarray.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Возвращает valarray, элементы которого равны арктангенсу декартовых компонентов, заданных сочетанием констант и элементов массивов valarray.|
|[begin](../standard-library/valarray-functions.md#begin)||
|[cos](../standard-library/valarray-functions.md#cos)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны косинусу элементов входного valarray.|
|[cosh](../standard-library/valarray-functions.md#cosh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому косинусу элементов входного valarray.|
|[end](../standard-library/valarray-functions.md#end)||
|[exp](../standard-library/valarray-functions.md#exp)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны натуральной экспоненте элементов входного valarray.|
|[log](../standard-library/valarray-functions.md#log)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны натуральному логарифму элементов входного valarray.|
|[log10](../standard-library/valarray-functions.md#log10)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны десятичному логарифму элементов входного valarray.|
|[pow](../standard-library/valarray-functions.md#pow)|Обрабатывает элементы входных объектов valarray и констант, возвращая массив valarray, элементы которого равны основанию, заданному элементами входного valarray, или константу, возведенную в степень, заданную элементами входного valarray или константой.|
|[sin](../standard-library/valarray-functions.md#sin)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны синусу элементов входного valarray.|
|[sinh](../standard-library/valarray-functions.md#sinh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому синусу элементов входного valarray.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны квадратному корню элементов входного valarray.|
|[swap](../standard-library/valarray-functions.md#swap)||
|[tan](../standard-library/valarray-functions.md#tan)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны тангенсу элементов входного valarray.|
|[tanh](../standard-library/valarray-functions.md#tanh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому тангенсу элементов входного valarray.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/valarray-operators.md#op_neq)|Проверяет, не равны ли соответствующие элементы двух одинаковых по размеру valarray или не равны ли все элементы valarray указанному значению типа элемента valarray.|
|[operator%](../standard-library/valarray-operators.md#op_mod)|Возвращает остаток от деления соответствующих элементов двух одинаковых по размеру valarray или от деления valarray на указанное значение типа элемента valarray или от деления указанного значения на valarray.|
|[operator&](../standard-library/valarray-operators.md#op_amp)|Получает результат применения побитовой операции `AND` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[operator&&](../standard-library/valarray-operators.md#op_amp_amp)|Получает результат применения логической операции `AND` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента valarray.|
|[operator>](../standard-library/valarray-operators.md#op_gt)|Проверяет, больше ли элементы одного valarray, чем элементы одинакового по размеру valarray либо больше или меньше ли все элементы valarray, чем указанное значение типа элемента valarray.|
|[operator>=](../standard-library/valarray-operators.md#op_gt_eq)|Проверяет, больше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.|
|[operator>>](../standard-library/valarray-operators.md#op_gt_gt)|Сдвигает вправо биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.|
|[operator<](../standard-library/valarray-operators.md#op_lt)|Проверяет, меньше ли элементы одного valarray, чем элементы одинакового по размеру valarray или больше ли либо меньше ли все элементы valarray, чем указанное значение.|
|[operator<=](../standard-library/valarray-operators.md#op_lt_eq)|Проверяет, меньше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.|
|[operator<<](../standard-library/valarray-operators.md#op_lt_lt)|Сдвигает влево биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.|
|[operator*](../standard-library/valarray-operators.md#op_star)|Получает результат поэлементного умножения соответствующих элементов двух одинаковых по размеру valarray или умножения valarray и указанного значения типа элемента valarray.|
|[operator+](../standard-library/valarray-operators.md#op_add)|Получает результат поэлементной суммы соответствующих элементов двух одинаковых по размеру valarray или суммы valarray и указанного значения типа элемента valarray.|
|[operator-](../standard-library/valarray-operators.md#operator-)|Получает результат поэлементного вычитания соответствующих элементов двух одинаковых по размеру valarray или вычитания valarray и указанного значения типа элемента valarray.|
|[operator/](../standard-library/valarray-operators.md#op_div)|Получает результат поэлементного деления соответствующих элементов двух одинаковых по размеру valarray или деления valarray на указанное значение типа элемента valarray.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|Проверяет, равны ли соответствующие элементы двух одинаковых по размеру valarray или равны ли все элементы valarray указанному значению типа элемента valarray.|
|[operator^](../standard-library/valarray-operators.md#op_xor)|Получает результат применения побитовой эксклюзивной операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[operator&#124;](../standard-library/valarray-operators.md#op_or)|Получает результат применения побитовой операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[operator||](../standard-library/valarray-operators.md#op_lor)|Получает результат применения логической операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента valarray.|

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[Класс gslice](../standard-library/gslice-class.md)|Служебный класс, используемый для определения многомерных срезов valarray.|
|[Класс gslice_array](../standard-library/gslice-array-class.md)|Внутренний, вспомогательный шаблон класса, поддерживающий общие объекты-срезы путем предоставления операций между массивами подмножества, определенными общим срезом valarray.|
|[Класс indirect_array](../standard-library/indirect-array-class.md)|Внутренний, вспомогательный шаблон класса, который поддерживает объекты, являющиеся подмножествами объектов valarray, предоставляя операции между массивами подмножества, определенными путем указания подмножества индексов родительского valarray.|
|[Класс mask_array](../standard-library/mask-array-class.md)|Внутренний, вспомогательный шаблон класса, который поддерживает объекты, являющиеся подмножествами родительских объектов valarray, заданные с помощью логического выражения, предоставляя операции между массивами подмножества.|
|[Класс Slice](../standard-library/slice-class.md)|Служебный класс, используемый для определения одномерных векторных подмножеств valarray.|
|[Класс slice_array](../standard-library/slice-array-class.md)|Внутренний, вспомогательный шаблон класса, поддерживающий объекты-срезы путем предоставления операций между массивами подмножества, определяемыми срезом valarray.|
|[Класс valarray](../standard-library/valarray-class.md)|Шаблон класса описывает объект, управляющий последовательностью элементов типа `Type` , которые хранятся в виде массива и предназначены для выполнения высокоскоростных математических операций, оптимизированных для вычислительной производительности.|

### <a name="specializations"></a>Специализации

|Имя|Описание|
|-|-|
|[\<bool>класс valarray](../standard-library/valarray-bool-class.md)|Специализированная версия шаблона класса valarray \<**Type**> к элементам типа **`bool`** .|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
