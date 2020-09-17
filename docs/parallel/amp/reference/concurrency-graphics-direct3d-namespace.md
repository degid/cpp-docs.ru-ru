---
title: Пространство имен Concurrency::graphics::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d
- amp_short_vectors/Concurrency::graphics::direct3d
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
ms.openlocfilehash: 4911787fd17877769eb723cf1e61e29fe626a783
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139437"
---
# <a name="concurrencygraphicsdirect3d-namespace"></a>Пространство имен Concurrency::graphics::direct3d

Предоставляет методы [get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture) и [make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture) .

## <a name="syntax"></a>Синтаксис

```cpp
namespace direct3d;
```

## <a name="members"></a>Члены

### <a name="functions"></a>Функции

|Имя<br /><br /> Description|
|--------------------------|
|[get_sampler](concurrency-graphics-direct3d-namespace-functions.md#get_sampler)<br /><br /> Получение интерфейса состояния выборки Direct3D для данного представления ускорителя, представляющего указанный объект образца.|
|[get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)<br /><br /> Возвращает интерфейс текстуры Direct3D, лежащий в основе указанного объекта [текстуры](texture-class.md) .|
|[make_sampler](concurrency-graphics-direct3d-namespace-functions.md#make_sampler)<br /><br /> Создание образца на основе указателя интерфейса состояния для образца Direct3D.|
|[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)<br /><br /> Создает объект [текстуры](texture-class.md) , используя указанные параметры.|
|[msad4](concurrency-graphics-direct3d-namespace-functions.md#msad4)<br /><br /> Сравнивает 4-байтное ссылочное значение и 8-байтовое исходное значение и накапливает вектор с 4 суммами.|

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
