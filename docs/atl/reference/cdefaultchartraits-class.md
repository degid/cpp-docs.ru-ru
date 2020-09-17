---
title: Класс CDefaultCharTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 40c4d107d05e6d7b610e7c46be920d91d8fe6086
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327092"
---
# <a name="cdefaultchartraits-class"></a>Класс CDefaultCharTraits

Этот класс предоставляет две статические функции для преобразования символов между верхним и нижним регистром.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultChartraits::CharTolower](#chartolower)|(Статик) Вызовите эту функцию, чтобы преобразовать символ в верхний регистр.|
|[CDefaultChartraits::Chartoupper](#chartoupper)|(Статик) Вызовите эту функцию, чтобы преобразовать символ в нижний регистр.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет функции, которые используются классом [CStringElementTraitsI.](../../atl/reference/cstringelementtraitsi-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a>CDefaultChartraits::CharTolower

Вызовите эту функцию, чтобы преобразовать символ в нижний регистр.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Знак для преобразования в нижний регистр.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CDefaultChartraits::Chartoupper

Вызовите эту функцию, чтобы преобразовать символ в верхний регистр.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Знак для преобразования в верхний регистр.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
