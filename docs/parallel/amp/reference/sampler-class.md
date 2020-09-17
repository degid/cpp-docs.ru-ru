---
title: Класс sampler
ms.date: 06/28/2018
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 8f47bf6e9b88dba1e94e9e2ed2b93c8d2d3f9b8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126360"
---
# <a name="sampler-class"></a>Класс sampler

Класс выборки выполняет статистическую обработку сведений о конфигурации, которые будут использоваться для выборки текстур.

## <a name="syntax"></a>Синтаксис

```cpp
class sampler;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор образцов](#ctor)|Перегружен. Конструирует экземпляр образца.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Возвращает `address_mode`, связанный с объектом образца.|
|[get_border_color](#get_border_color)|Возвращает цвет границы, связанный с объектом образца.|
|[get_filter_mode](#get_filter_mode)|Возвращает `filter_mode`, связанный с объектом образца.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Перегружен. Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[address_mode](#address_mode)|Возвращает режим адреса объекта `sampler`.|
|[border_color](#border_color)|Возвращает цвет границы для объекта `sampler`.|
|[filter_mode](#filter_mode)|Возвращает режим фильтрации объекта `sampler`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`sampler`

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics

## <a name="ctor"></a>образец

Конструирует экземпляр [класса образца](sampler-class.md).

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);

sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);

sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Параметры

*_Filter_mode*<br/>
Режим фильтрации, используемый в выборки.

*_Address_mode*<br/>
Режим адресации, используемый в выборки для всех измерений.

*_Border_color*<br/>
Цвет границы, используемый, если используется режим адреса address_border. Значение по умолчанию — `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Other*<br/>
[5] конструктор копий объект `sampler` для копирования в новый экземпляр `sampler`.

[6] конструктор Move объект `sampler`, который необходимо переместить в новый экземпляр `sampler`.

## <a name="address_mode"></a>address_mode

Возвращает режим адреса объекта `sampler`.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

## <a name="border_color"></a>border_color

Возвращает цвет границы для объекта `sampler`.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

## <a name="filter_mode"></a>filter_mode

Возвращает режим фильтрации объекта `sampler`.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

## <a name="get_address_mode"></a>get_address_mode

Возвращает режим фильтрации, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Возвращаемое значение

Режим адресации, настроенный для образца.

## <a name="get_border_color"></a>get_border_color

Возвращает цвет границы, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Float_4, содержащий цвет границы.

## <a name="get_filter_mode"></a>get_filter_mode

Возвращает режим фильтрации, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Режим фильтрации, настроенный для образца.

## <a name="operator_eq"></a>Оператор =

Присваивает значение другого объекта выборки существующему образцу.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
[1] оператор назначения копирования объект `sampler`, который необходимо скопировать в этот `sampler`.

[2] оператор присваивания перемещения объект `sampler`, который необходимо переместить в `sampler`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот экземпляр образца.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
