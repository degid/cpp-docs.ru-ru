---
title: числовой (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
ms.openlocfilehash: 1939a6dd9b6d8186eb278623f3b0a5a3d851f4d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208485"
---
# <a name="numeric-stlclr"></a>числовой (STL/CLR)

Определяет функции шаблонов контейнеров, которые выполняют алгоритмы, предоставляемые для числовой обработки.

## <a name="syntax"></a>Синтаксис

```
#include <cliext/numeric>
```

## <a name="requirements"></a>Требования

**Заголовок:** \<cliext/numeric >

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Компонент|Description|
|--------------|-----------------|
|[accumulate (STL/CLR)](#accumulate)|Вычисляет сумму всех элементов в указанном диапазоне, включая некоторое начальное значение, путем вычисления последовательных частичных сумм или вычисляет результат последовательных частичных сумм, аналогичным образом полученных от использования указанной бинарной операции, отличной от суммы.|
|[adjacent_difference (STL/CLR)](#adjacent_difference)|Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.|
|[inner_product (STL/CLR)](#inner_product)|Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.|
|[partial_sum (STL/CLR)](#partial_sum)|Вычисляет ряд сумм в диапазоне ввода из первого элемента с помощью `i`-го элемента и сохраняет результат каждой такой суммы в `i`-го элемента диапазона назначения или вычисляет результат обобщенной процедуры, в которой операция Sum заменяется другой заданной бинарной операцией.|

## <a name="members"></a>Члены

## <a name="accumulate-stlclr"></a><a name="accumulate"></a>накопление (STL/CLR)

Вычисляет сумму всех элементов в указанном диапазоне, включая некоторое начальное значение, путем вычисления последовательных частичных сумм или вычисляет результат последовательных частичных сумм, аналогичным образом полученных от использования указанной бинарной операции, отличной от суммы.

### <a name="syntax"></a>Синтаксис

```cpp
template<class _InIt, class _Ty> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);
template<class _InIt, class _Ty, class _Fn2> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);
```

### <a name="remarks"></a>Примечания

Эта функция ведет себя так же, как и C++ числовая функция стандартной библиотеки `accumulate`. Дополнительные сведения см. в разделе [накопление](../standard-library/numeric-functions.md#accumulate).

## <a name="adjacent_difference-stlclr"></a><a name="adjacent_difference"></a>adjacent_difference (STL/CLR)

Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.

### <a name="syntax"></a>Синтаксис

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Примечания

Эта функция ведет себя так же, как и C++ числовая функция стандартной библиотеки `adjacent_difference`. Дополнительные сведения см. в разделе [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).

## <a name="inner_product-stlclr"></a><a name="inner_product"></a>inner_product (STL/CLR)

Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.

### <a name="syntax"></a>Синтаксис

```cpp
template<class _InIt1, class _InIt2, class _Ty> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val);
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,
       class _Fn22> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);
```

### <a name="remarks"></a>Примечания

Эта функция ведет себя так же, как и C++ числовая функция стандартной библиотеки `inner_product`. Дополнительные сведения см. в разделе [inner_product](../standard-library/numeric-functions.md#inner_product).

## <a name="partial_sum-stlclr"></a><a name="partial_sum"></a>partial_sum (STL/CLR)

Вычисляет ряд сумм в диапазоне ввода из первого элемента с помощью `i`-го элемента и сохраняет результат каждой такой суммы в `i`-го элемента диапазона назначения или вычисляет результат обобщенной процедуры, в которой операция Sum заменяется другой заданной бинарной операцией.

### <a name="syntax"></a>Синтаксис

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Примечания

Эта функция ведет себя так же, как и C++ числовая функция стандартной библиотеки `partial_sum`. Дополнительные сведения см. в разделе [partial_sum](../standard-library/numeric-functions.md#partial_sum).
