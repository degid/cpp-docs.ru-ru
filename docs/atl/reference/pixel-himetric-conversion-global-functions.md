---
title: Глобальные функции преобразования «пиксель-HIMETRIC»
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: e71dccbccbe43ea7df3b6a7005da138a8e31aeb3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834691"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования пикселей и HIMETRIC

Эти функции обеспечивают поддержку преобразования в Пиксели и HIMETRIC единицы измерения.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Преобразует единицы HIMETRIC (каждая единица — 0,01 мм) в пиксели.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Преобразует Пиксели в HIMETRIC единицы (каждая единица — 0,01 мм).|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a> атлхиметриктопиксел

Преобразует размер объекта в единицах HIMETRIC (каждая единица равна 0,01 мм) в размер в пикселях на экране устройства.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Параметры

*лпсизеинхиметрик*<br/>
окне Указатель на размер объекта в единицах HIMETRIC.

*лпсизеинпикс*<br/>
заполняет Указатель на место, где должен возвращаться размер объекта в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a> атлпикселтохиметрик

Преобразует размер объекта в пикселях на экране устройства в единицы HIMETRIC (каждая единица равна 0,01 мм).

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Параметры

*лпсизеинпикс*<br/>
окне Указатель на размер объекта в пикселях.

*лпсизеинхиметрик*<br/>
заполняет Указатель на место, где должен возвращаться размер объекта в единицах HIMETRIC.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
