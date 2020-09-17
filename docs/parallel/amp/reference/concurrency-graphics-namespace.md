---
title: Пространство имен Concurrency::graphics
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: 942b3bbace85fa297bba6cd4b509f67006a4aed3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226741"
---
# <a name="concurrencygraphics-namespace"></a>Пространство имен Concurrency::graphics

Пространство имен Graphics предоставляет типы и функции, предназначенные для программирования графики.

## <a name="syntax"></a>Синтаксис

```cpp
namespace graphics;
```

## <a name="members"></a>Участники

### <a name="namespaces"></a>Пространства имен

|Имя|Описание|
|----------|-----------------|
|[concurrency::Graphics::d пространство имен irect3d](concurrency-graphics-direct3d-namespace.md)|Предоставляет функции для взаимодействия Direct3D.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`uint`|Тип элемента для [класса uint_2](uint-2-class.md), класса [uint_3](uint-3-class.md)и [класса uint_4](uint-4-class.md). Определен как `typedef unsigned int uint;`.|

### <a name="enumerations"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление address_mode](concurrency-graphics-namespace-enums.md#address_mode).|Указывает режимы адресации, поддерживаемые для выборки текстур.|
|[Перечисление filter_mode](concurrency-graphics-namespace-enums.md#filter_mode)|Задает режимы фильтрации, поддерживаемые для выборки текстур.|

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс текстуры](texture-class.md)|Текстура — это статистическое выражение данных для accelerator_view в домене экстента. Это коллекция переменных, по одному для каждого элемента в домене экстента. Каждая переменная содержит значение, соответствующее типу-примитиву C++ (без знака int, int, float, Double) или норме скалярного типа или unorm (определено в concurrency::graphics) или допустимых коротких векторических типов, определенных в concurrency::graphics.|
|[Класс writeonly_texture_view](writeonly-texture-view-class.md)|Writeonly_texture_view обеспечивает WriteOnly доступ к текстуре.|
|[Класс double_2](double-2-class.md)|Представляет короткий вектор из двух **`double`** значений.|
|[Класс double_3](double-3-class.md)|Представляет короткий вектор из 3 **`double`** значений.|
|[Класс double_4](double-4-class.md)|Представляет короткий вектор из 4 **`double`** значений.|
|[Класс float_2](float-2-class.md)|Представляет короткий вектор из двух **`float`** значений.|
|[Класс float_3](float-3-class.md)|Представляет короткий вектор из 3 **`float`** значений.|
|[Класс float_4](float-4-class.md)|Представляет короткий вектор из 4 **`float`** значений.|
|[Класс int_2](int-2-class.md)|Представляет короткий вектор из двух **`int`** значений.|
|[Класс int_3](int-3-class.md)|Представляет короткий вектор из 3 **`int`** значений.|
|[Класс int_4](int-4-class.md)|Представляет короткий вектор из 4 **`int`** значений.|
|[Класс norm_2](norm-2-class.md)|Представляет короткий вектор из двух `norm` значений.|
|[Класс norm_3](norm-3-class.md)|Представляет короткий вектор из 3 `norm` значений.|
|[Класс norm_4](norm-4-class.md)|Представляет короткий вектор из 4 `norm` значений.|
|[Класс uint_2](uint-2-class.md)|Представляет короткий вектор из двух `uint` значений.|
|[Класс uint_3](uint-3-class.md)|Представляет короткий вектор из 3 `uint` значений.|
|[Класс uint_4](uint-4-class.md)|Представляет короткий вектор из 4 `uint` значений.|
|[Класс unorm_2](unorm-2-class.md)|Представляет короткий вектор из двух `unorm` значений.|
|[Класс unorm_3](unorm-3-class.md)|Представляет короткий вектор из 3 `unorm` значений.|
|[Класс unorm_4](unorm-4-class.md)|Представляет короткий вектор из 4 `unorm` значений.|
|[Класс образцов](sampler-class.md)|Представляет конфигурацию образца, используемую для выборки текстур.|
|[Структура short_vector](short-vector-structure.md)|Предоставляет базовую реализацию короткого вектора значений.|
|[Структура short_vector_traits](short-vector-traits-structure.md)|Предоставляет для получения длины и типа короткого вектора.|
|[Класс texture_view](texture-view-class.md)|Предоставляет доступ на чтение и запись для текстуры.|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[copy](concurrency-graphics-namespace-functions.md#copy)|Перегружен. Копирует содержимое текстуры источника в целевой буфер узла.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Перегружен. Асинхронно копирует содержимое текстуры источника в целевой буфер узла.|

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен** : Concurrency

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
