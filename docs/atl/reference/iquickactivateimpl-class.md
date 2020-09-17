---
title: Класс «ИКвисАктивИнИмпл»
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 7e1984249caf66e2986341f9c9f7a939d7039125
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329555"
---
# <a name="iquickactivateimpl-class"></a>Класс «ИКвисАктивИнИмпл»

Этот класс объединяет инициализацию управления контейнерами в один вызов.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IQuickActivateImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ИКвисактивированимпл::GetContentExtent](#getcontentextent)|Извлекает текущий размер дисплея для управления.|
|[ИКВИАктивированИмплл:: БыстрыйАктив](#quickactivate)|Выполняет быструю инициализацию загружаемых элементов управления.|
|[ИКвисактивированимпл::SetContentExtent](#setcontentextent)|Информирует о контроле, сколько пространства отображения контейнер аназначено ему.|

## <a name="remarks"></a>Примечания

Интерфейс [I'u'uickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) помогает контейнерам избежать задержек при погрузке элементов управления путем объединения инициализации в один вызов. Метод `QuickActivate` позволяет контейнеру передавать указатель на структуру [ЗАКОНТЕЙНЕРа,](/windows/win32/api/ocidl/ns-ocidl-qacontainer) которая содержит указатели на все интерфейсы, необходимые для управления. По возвращении элемент управления передает указатель на структуру [ЗАКОНТРОЛ,](/windows/win32/api/ocidl/ns-ocidl-qacontrol) которая содержит указатели на свои собственные интерфейсы, которые используются контейнером. Класс `IQuickActivateImpl` обеспечивает реализацию `IQuickActivate` и реализацию `IUnknown` по умолчанию, отправляя информацию на устройство сброса в сборках отладок.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>ИКвисактивированимпл::GetContentExtent

Извлекает текущий размер дисплея для управления.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер предназначен для полного рендеринга элемента управления и указан в единицах HIMETRIC.

[См. ИКВСАктив::GetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) в Windows SDK.

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a>ИКВИАктивированИмплл:: БыстрыйАктив

Выполняет быструю инициализацию загружаемых элементов управления.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Примечания

Структура содержит указатели на интерфейсы, необходимые для управления, и значения некоторых свойств окружающей среды. По возвращении элемент управления передает указатель на структуру [ЗАКОНТРОЛ,](/windows/win32/api/ocidl/ns-ocidl-qacontrol) которая содержит указатели на собственные интерфейсы, которые требует контейнер, и дополнительную информацию о состоянии.

[См.](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate)

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>ИКвисактивированимпл::SetContentExtent

Информирует о контроле, сколько пространства отображения контейнер аназначено ему.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер указан в единицах HIMETRIC.

[См. ИКВСАктив::SetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
