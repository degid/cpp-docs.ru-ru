---
title: Класс CWinTraits
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: fd73f733e4eff21da92937d1e1b0cce21552a48c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330303"
---
# <a name="cwintraits-class"></a>Класс CWinTraits

Этот класс предоставляет метод стандартизации стилей, используемых при создании объекта окна.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>Параметры

*t_dwStyle*<br/>
Стандартное окно по умолчанию стилей.

*t_dwExStyle*<br/>
Стили расширенных окон по умолчанию.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Статик) Извлекает расширенные стили `CWinTraits` для объекта.|
|[CWinTraits::GetwndStyle](#getwndstyle)|(Статик) Извлекает стандартные стили `CWinTraits` для объекта.|

## <a name="remarks"></a>Примечания

Этот класс [черт оконов](../../atl/understanding-window-traits.md) предоставляет простой метод стандартизации стилей, используемых для создания объекта окна ATL. Используйте специализацию этого класса в качестве параметра шаблона для [CWindowImpl](../../atl/reference/cwindowimpl-class.md) или другого из оконных классов ATL, чтобы указать стандарт по умолчанию и расширенные стили, используемые для экземпляров этого класса окон.

Используйте этот шаблон, когда вы хотите предоставить стили окна по умолчанию, которые будут использоваться только тогда, когда в вызове [cWindowImpl не](../../atl/reference/cwindowimpl-class.md#create)указаны другие стили: :Создать .

ATL предоставляет три предопределенные специализации этого шаблона для широко используемых комбинаций оконных стилей:

- `CControlWinTraits`

   Предназначен для стандартного окна управления. Используются следующие стандартные стили: WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Нет расширенных стилей.

- `CFrameWinTraits`

   Предназначен для стандартного окна рамы. Используемые стандартные стили включают: WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Используемые расширенные стили включают: WS_EX_APPWINDOW и WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`

   Предназначен для стандартного детского окна MDI. Используемые стандартные стили включают: WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Используемые расширенные стили включают: WS_EX_MDICHILD.

Если вы хотите убедиться, что определенные стили настроены для всех экземпляров класса окон, позволяя при этом устанавливать другие стили на основе экземпляра, используйте [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) вместо этого.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a>CWinTraits::GetwndStyle

Вызовите эту функцию, чтобы `CWinTraits` получить стандартные стили объекта.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Стандартные стили, используемые для создания окна. Если *dwStyle* раста 0, значения`t_dwStyle`стиля шаблона () возвращаются. Если *dwStyle* незеро, *dwStyle* возвращается.

### <a name="return-value"></a>Возвращаемое значение

Стандартные стили окна объекта.

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraits::GetWndExStyle

Вызовите эту функцию, чтобы `CWinTraits` получить расширенные стили объекта.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Расширенные стили, используемые для создания окна. Если *dwExStyle* раста 0, значения`t_dwExStyle`стиля шаблона () возвращаются. Если *dwExStyle* является ненулевым, *dwExStyle* возвращается.

### <a name="return-value"></a>Возвращаемое значение

Расширенные стили окна объекта.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Понимание оконных трасс](../../atl/understanding-window-traits.md)
