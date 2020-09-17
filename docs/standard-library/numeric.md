---
title: '&lt;numeric&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: ee1e26d3f174d21ab1ad2c847d292ad075cc0f71
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830596"
---
# <a name="ltnumericgt"></a>&lt;numeric&gt;

Определяет шаблонные функции контейнера, которые выполняют алгоритмы числовой обработки.

## <a name="requirements"></a>Требования

**Заголовок**: \<numeric>

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Числовые алгоритмы похожи на алгоритмы стандартной библиотеки C++ в [\<algorithm>](algorithm.md) и могут применяться к различным структурам данных. Это включает классы контейнеров стандартной библиотеки, например, [vector](../standard-library/vector-class.md) и [list](../standard-library/list-class.md), и программно-определенные структуры данных и массивы элементов, которые удовлетворяют требованиям конкретного алгоритма. Алгоритмы достигают такого уровня универсальности путем получения доступа к элементам контейнера и их просмотра опосредованным образом через итераторы. Алгоритмы обрабатывают диапазоны итератора, которые обычно определяются их начальными или конечными позициями. Указанные диапазоны должны быть допустимы в том смысле, что все указатели в диапазонах должны поддерживать удаление ссылок и в рамках последовательностей каждого диапазона последняя позиция должна быть доступна из первой с помощью приращения.

Алгоритмы расширяют действия, поддерживаемые операциями и функциями-членами каждого из контейнеров стандартной библиотеки C++, и позволяют взаимодействовать с различными типами объектов-контейнеров одновременно.

## <a name="members"></a>Элементы

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Вычисляет сумму всех элементов в указанном диапазоне, включая некоторое исходное значение, путем вычисления последовательных частичных сумм или вычисляет результат последовательных частичных результатов, полученных с помощью определенной бинарной операции вместо операции суммы.|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.|
|[exclusive_scan](../standard-library/numeric-functions.md#exclusive_scan)||
|[GCD](../standard-library/numeric-functions.md#gcd)||
|[inclusive_scan](../standard-library/numeric-functions.md#inclusive_scan)||
|[inner_product](../standard-library/numeric-functions.md#inner_product)|Вычисляет сумму учитывающего элементы произведения двух диапазонов и добавляет ее к указанному начальному значению или вычисляет результат обобщенной процедуры, где операции суммы и произведения заменяются другими определенными бинарными операциями.|
|[Йота](../standard-library/numeric-functions.md#iota)|Хранит начальное значение, начиная с первого элемента, и заполняет последовательными приращениями значения (`value++`) в каждом из элементов в интервале `[first, last)`.|
|[Функция](../standard-library/numeric-functions.md#lcm)||
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|Вычисляет ряд сумм во входном диапазоне с первого элемента по *i*-й элемент и сохраняет результат каждой такой суммы в *i*-м элементе диапазона назначения или вычисляет результат обобщенной процедуры, где операция суммы заменена другой заданной бинарной операцией.|
|[свести](../standard-library/numeric-functions.md#reduce)||
|[transform_exclusive_scan](../standard-library/numeric-functions.md#transform_exclusive_scan)||
|[transform_inclusive_scan](../standard-library/numeric-functions.md#transform_inclusive_scan)||
|[transform_reduce](../standard-library/numeric-functions.md#transform_reduce)||

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
