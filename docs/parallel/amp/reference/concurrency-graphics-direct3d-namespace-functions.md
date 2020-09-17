---
title: Функции пространства имен Concurrency::graphics::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 66db1d348c6c58a9226322b51662ef7a4ef75b3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841302"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Функции пространства имен Concurrency::graphics::direct3d

:::row:::
   :::column span="":::
      [`get_sampler`](#get_sampler)\
      [`get_texture`](#get_texture)
   :::column-end:::
   :::column span="":::
      [`make_sampler`](#make_sampler)
   :::column-end:::
   :::column span="":::
      [`make_texture`](#make_texture)
   :::column-end:::
   :::column span="":::
      [`msad4`](#msad4)
   :::column-end:::
:::row-end:::

## <a name="get_sampler"></a><a name="get_sampler"></a> get_sampler

Получение интерфейса состояния D3D образца для данного представления ускорителя, представляющего указанный объект образца.

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Представление D3D-ускорителя, на котором должно быть создано состояние образца D3D.

*_Sampler*<br/>
Объект образца, для которого создается базовый интерфейс состояния D3D-образца.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий состоянию D3D, представляющему данный образец.

## <a name="get_texture"></a><a name="get_texture"></a> get_texture

Возвращает интерфейс текстуры Direct3D, лежащий в основе указанного объекта [текстуры](texture-class.md) .

```cpp
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элемента текстуры.

*_Rank*<br/>
Ранг текстуры.

*_Texture*<br/>
Представление текстуры или текстуры, связанное с accelerator_view, для которого возвращается базовый интерфейс текстуры Direct3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий текстуре Direct3D, лежащей в основе текстуры.

## <a name="make_sampler"></a><a name="make_sampler"></a> make_sampler

Создание образца с помощью указателя интерфейса состояния D3D-образца.

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_D3D_sampler*<br/>
Указатель интерфейса IUnknown состояния образца D3D для создания образца.

### <a name="return-value"></a>Возвращаемое значение

Образец представляет указанное состояние образца D3D.

## <a name="make_texture"></a><a name="make_texture"></a> make_texture

Создает объект [текстуры](texture-class.md) , используя указанные параметры.

```cpp
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов текстуры.

*_Rank*<br/>
Ранг текстуры.

*_Av*<br/>
Представление D3D Accelerator, на котором должна быть создана текстура.

*_D3D_texture*<br/>
Указатель интерфейса IUnknown текстуры D3D, из которой создается текстура.

*_View_format*<br/>
Формат DXGI, используемый для представлений, созданных из этой текстуры. Передайте DXGI_FORMAT_UNKNOWN (по умолчанию), чтобы получить формат из базового формата _D3D_texture и value_type этого шаблона. Указанный формат должен быть совместим с базовым форматом _D3D_texture.

### <a name="return-value"></a>Возвращаемое значение

Текстура, использующая предоставленную текстуру D3D.

## <a name="msad4"></a><a name="msad4"></a> msad4

Сравнивает 4-байтное ссылочное значение и 8-байтовое исходное значение и накапливает вектор с 4 суммами. Каждая сумма соответствует маскированной сумме абсолютных различий между значением ссылки и исходным значением.

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Reference*<br/>
Массив ссылок 4 байта в одном значении uint

*_Source*<br/>
Исходный массив из 8 байтов в векторе двух значений uint.

*_Accum*<br/>
Вектор из 4 значений, добавляемых к маскированной сумме абсолютных различий между значением ссылки и исходным значением.

### <a name="return-value"></a>Возвращаемое значение

Возвращает вектор из 4 сумм. Каждая сумма соответствует маскированной сумме абсолютных различий между значением ссылки и исходным значением.

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics::direct3d

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency::graphics::direct3d](concurrency-graphics-direct3d-namespace.md)