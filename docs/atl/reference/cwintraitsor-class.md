---
title: Класс CWinTraitsOR
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 825f79190c6f68cd1372154e4e02f430f545aa48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330284"
---
# <a name="cwintraitsor-class"></a>Класс CWinTraitsOR

Этот класс предоставляет метод стандартизации стилей, используемых при создании объекта окна.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>Параметры

*t_dwStyle*<br/>
Стили окон по умолчанию.

*t_dwExStyle*<br/>
Стили расширенных окон по умолчанию.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinTraitsOR:GetWndExStyle](#getwndexstyle)|Извлекает расширенные стили `CWinTraitsOR` для объекта.|
|[CWinTraitsOR:GetWndStyle](#getwndstyle)|Извлекает стандартные стили `CWinTraitsOR` для объекта.|

## <a name="remarks"></a>Примечания

Этот класс [черт оконов](../../atl/understanding-window-traits.md) предоставляет простой метод стандартизации стилей, используемых для создания объекта окна ATL. Используйте специализацию этого класса в качестве параметра шаблона для [CWindowImpl](../../atl/reference/cwindowimpl-class.md) или другого из оконных классов ATL, чтобы указать минимальный набор стандартных и расширенных стилей, которые будут использоваться для экземпляров этого класса окон.

Используйте специализацию этого шаблона, если вы хотите убедиться, что определенные стили настроены для всех экземпляров класса окон, позволяя при этом другим стилям устанавливаться на основе в каждом экземпляре в вызове [cWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).

Если вы хотите предоставить стили окна по умолчанию, которые будут `CWindowImpl::Create`использоваться только тогда, когда в вызове не указаны другие стили, используйте [CWinTraits.](../../atl/reference/cwintraits-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>CWinTraitsOR:GetWndStyle

Вызовите эту функцию, чтобы получить комбинацию (с помощью логического оператора ИЛИ) стандартных стилей `CWinTraits` объекта и стили по умолчанию, указанные *t_dwStyle.*

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Стили, используемые для создания окна.

### <a name="return-value"></a>Возвращаемое значение

Сочетание стилей, которые передаются в *dwStyle* `t_dwStyle`и по умолчанию, указанные, с помощью логического оператора OR.

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraitsOR:GetWndExStyle

Вызовите эту функцию, чтобы получить комбинацию (с помощью логического оператора ИЛИ) расширенных стилей `CWinTraits` объекта и стилей по умолчанию, указанных `t_dwStyle`.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Расширенные стили, используемые для создания окна.

### <a name="return-value"></a>Возвращаемое значение

Сочетание расширенных стилей, которые передаются в *dwExStyle* и по умолчанию, `t_dwExStyle`указанные, с помощью логического оператора OR

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Понимание оконных трасс](../../atl/understanding-window-traits.md)
