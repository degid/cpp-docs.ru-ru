---
title: Класс IOleObjectImpl
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: 86d82aea2e92eb99903284abe4ac03478369616c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326527"
---
# <a name="ioleobjectimpl-class"></a>Класс IOleObjectImpl

Этот класс `IUnknown` реализует и является основным интерфейсом, через который контейнер общается с элементом управления.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IOleObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IOleObjectImpl::Консультация](#advise)|Устанавливает консультативную связь с управлением.|
|[IOleObjectImpl::Закрыть](#close)|Изменяет состояние управления от выполнения к загрузке.|
|[IOleObjectImpl: :DoVerb](#doverb)|Говорит элементу управления выполнить одно из перечисленных действий.|
|[IOleObjectImpl: :DoVerbDiscardUndo](#doverbdiscardundo)|Говорит элементу управления, чтобы отбросить любое состояние отстойного, что он поддерживает.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Сообщает элементу управления удалить пользовательский интерфейс из представления.|
|[IOleObjectImpl::DoVerbInPlaceactivate](#doverbinplaceactivate)|Запускает управление и устанавливает его окно, но не устанавливает пользовательский интерфейс управления.|
|[IOleObjectImpl: :DoVerbOpen](#doverbopen)|Вызывает открытость элемента управления в отдельном окне.|
|[IOleObjectImpl: :DoVerbPrimary](#doverbprimary)|Выполняет указанное действие, когда пользователь дважды щелкает элемент управления. Элемент управления определяет действие, обычно для активации элемента управления на месте.|
|[IOleObjectImpl: :DoVerbShow](#doverbshow)|Отображает пользователю недавно вставленный элемент управления.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Активирует элемент управления на месте и показывает пользовательский интерфейс элемента управления, например меню и панели инструментов.|
|[IOleObjectImpl::Инномер](#enumadvise)|Перечисляет консультативные соединения управления.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Перечисляет действия для управления.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|Извлекает клиентский сайт управления.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Извлекает данные из Clipboard. Реализация ATL возвращает E_NOTIMPL.|
|[IOleObjectImpl::GetExtent](#getextent)|Извлекает степень области дисплея элемента управления.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Получает статус элемента управления.|
|[IOleObjectImpl:GetMoniker](#getmoniker)|Извлекает прозвище элемента управления. Реализация ATL возвращает E_NOTIMPL.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Извлекает идентификатор класса элемента управления.|
|[IOleObjectImpl::GetUserType](#getusertype)|Извлекает имя пользователя элемента управления.|
|[IOleObjectImpl::InitFromData](#initfromdata)|Инициализирует элемент управления из выбранных данных. Реализация ATL возвращает E_NOTIMPL.|
|[IOleObjectImpl::IsUpTodate](#isuptodate)|Проверяет, актуален ли элемент управления. Реализация ATL возвращает S_OK.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Вызывается [DoVerbDiscardUndo](#doverbdiscardundo) после отменить состояние отбрасывается.|
|[IOleObjectImpl::OnPostVerbhide](#onpostverbhide)|Вызывается [DoVerbHide](#doverbhide) после того, как контроль скрыт.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Вызывается [DoVerbInPlaceActivate](#doverbinplaceactivate) после того, как контроль активирован на месте.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Вызывается [DoVerbOpen](#doverbopen) после того, как элемент управления был открыт для редактирования в отдельном окне.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Вызывается [DoVerbShow](#doverbshow) после того, как элемент управления был сделан видимым.|
|[IoleObjectImpl::OnPostVerbuIActivate](#onpostverbuiactivate)|Вызывается [DoVerbUIActivate](#doverbuiactivate) после активации пользовательского интерфейса элемента управления.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Вызывается [DoVerbDiscardUndo](#doverbdiscardundo) до отменить состояние отбрасывается.|
|[IoleObjectImpl::OnpreVerbHide](#onpreverbhide)|Вызывается [DoVerbHide](#doverbhide) до того, как элемент управления будет скрыт.|
|[IoleObjectImpl::OnpreverbInPlaceActivate](#onpreverbinplaceactivate)|Вызывается [DoVerbInPlaceActivate](#doverbinplaceactivate) до того, как управление активируется на месте.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Вызывается [DoVerbOpen](#doverbopen) до того, как элемент управления был открыт для редактирования в отдельном окне.|
|[IoleObjectImpl::OnpreVerbShow](#onpreverbshow)|Вызывается [DoVerbShow,](#doverbshow) прежде чем элемент управления был сделан видимым.|
|[IoleObjectImpl::OnpreVerbuiActivate](#onpreverbuiactivate)|Вызывается [DoVerbUIActivate](#doverbuiactivate) до того, как пользовательский интерфейс управления был активирован.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|Сообщает элемент управления о своем клиентском сайте в контейнере.|
|[IOleObjectImpl:SetColorScheme](#setcolorscheme)|Рекомендует цветовую схему для применения элемента управления, если таковые имеется. Реализация ATL возвращает E_NOTIMPL.|
|[IOleObjectImpl::SetExtent](#setextent)|Устанавливает степень зоны дисплея элемента управления.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|Сообщает элементуправления имена контейнерного приложения и контейнерного документа.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|Сообщает контролю, что такое его прозвище. Реализация ATL возвращает E_NOTIMPL.|
|[IOleObjectImpl::Unadvise](#unadvise)|Удаляет консультативное соединение с элементом управления.|
|[IOleObjectImpl::Обновление](#update)|Обновляет элемент управления. Реализация ATL возвращает S_OK.|

## <a name="remarks"></a>Примечания

Интерфейс [IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject) является основным интерфейсом, через который контейнер общается с элементом управления. Класс `IOleObjectImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a>IOleObjectImpl::Консультация

Устанавливает консультативную связь с управлением.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::Консультации](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) в Windows SDK.

## <a name="ioleobjectimplclose"></a><a name="close"></a>IOleObjectImpl::Закрыть

Изменяет состояние управления от выполнения к загрузке.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Примечания

Деактивирует элемент управления и разрушает окно управления, если оно существует. Если член данных класса управления [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) является правдой, а параметр *dwSaveOption* либо OLECLOSE_SAVEIFDIRTY, либо OLECLOSE_PROMPTSAVE, свойства управления сохраняются перед закрытием.

Указатели, хранящиеся в данных класса управления [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) и [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) выпущены, а данные членов [CComControlBase::m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), и [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) настроены на FALSE.

Смотрите [IOleObject::Закрыть](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) в Windows SDK.

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a>IOleObjectImpl: :DoVerb

Говорит элементу управления выполнить одно из перечисленных действий.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>Примечания

В зависимости от `iVerb`значения, одна `DoVerb` из функций помощника ATL называется следующим образом:

|*iVerb* Значение|Функция поддержки DoVerb называется|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[Довербидэйд](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIАктив](#doverbuiactivate)|

Смотрите [IOleObject::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a>IOleObjectImpl: :DoVerbDiscardUndo

Говорит элементу управления, чтобы отбросить любое состояние отстойного, что он поддерживает.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a>IOleObjectImpl::DoVerbHide

Деактивирует и удаляет пользовательский интерфейс элемента управления и скрывает элемент управления.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a>IOleObjectImpl::DoVerbInPlaceactivate

Запускает управление и устанавливает его окно, но не устанавливает пользовательский интерфейс управления.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Активирует элемент управления на месте, позвонив [в CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Если данные члена `m_bWindowOnly` класса управления `DoVerbInPlaceActivate` не соответствуют действительности, первые попытки активировать элемент управления в качестве управления без окон (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteWindowless).](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) Если это не удается, функция пытается активировать элемент управления с расширенными функциями (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteEx).](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex) Если это не удается, функция пытается активировать элемент управления без расширенных функций (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSite).](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) Если активация выполняется успешно, функция уведомляет контейнер, элемент управления активирован.

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a>IOleObjectImpl: :DoVerbOpen

Вызывает открытость элемента управления в отдельном окне.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a>IOleObjectImpl: :DoVerbPrimary

Определяет действие, предпринимаемое при двойном нажатии на элемент управления.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

По умолчанию устанавливается для отображения страниц свойств. Вы можете переопределить это в классе управления, чтобы вызвать другое поведение при двойном нажатии кнопки; например, воспроизвести видео или пойти на место активно.

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a>IOleObjectImpl: :DoVerbShow

Говорит контейнеру, чтобы сделать элемент управления видимым.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a>IOleObjectImpl::DoVerbUIActivate

Активирует пользовательский интерфейс элемента управления и уведомляет контейнер о том, что его меню заменяются составными меню.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
(в) Указатель на прямоугольник контейнер ателье хочет, чтобы элемент управления втягивался.

*hwndParent*<br/>
(в) Ручка окна, содержащая элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a>IOleObjectImpl::Инномер

Обеспечивает перечисление зарегистрированных консультативных соединений для этого управления.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::Подспоминаните](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) в Windows SDK.

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a>IOleObjectImpl::EnumVerbs

Поставляет перечисление зарегистрированных действий (глаголов) для `OleRegEnumVerbs`этого контроля, позвонив .

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Примечания

Вы можете добавить глаголы в файл .rgs вашего проекта. Например, см. RGS в образце [CIRC.](../../overview/visual-cpp-samples.md)

Смотрите [IOleObject::EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) в Windows SDK.

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a>IOleObjectImpl::GetClientSite

Помещает указатель в элемент данных класса управления [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) в *ppClientSite* и приращает значение отсчета отсчета отсчета отсчета отуказатель.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::GetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) в Windows SDK.

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a>IOleObjectImpl::GetClipboardData

Извлекает данные из Clipboard.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::GetClipboardData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) в Windows SDK.

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a>IOleObjectImpl::GetExtent

Извлекает размер дисплея бегущего управления в единицах HIMETRIC (0,01 миллиметра на единицу).

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Примечания

Размер хранится в элементе данных класса управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

Смотрите [IOleObject::GetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) в Windows SDK.

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a>IOleObjectImpl::GetMiscStatus

Возвращает указатель на зарегистрированную информацию `OleRegGetMiscStatus`о статусе для элемента управления, позвонив в службу.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Примечания

Информация о состоянии включает в себя поведение, поддерживаемое данными управления и презентации. Вы можете добавить информацию о состоянии в файл .rgs вашего проекта.

Смотрите [IOleObject::GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) в Windows SDK.

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a>IOleObjectImpl:GetMoniker

Извлекает прозвище элемента управления.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::GetMoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) в Windows SDK.

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID

Возвращает идентификатор класса элемента управления.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::GetUserClassID](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) в Windows SDK.

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a>IOleObjectImpl::GetUserType

Возвращает имя пользователя управления, вызывая. `OleRegGetUserType`

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Примечания

Имя типа пользователя используется для отображения в пользовательских интерфейсах элементов, таких как меню и диалоговые коробки. Вы можете изменить имя типа пользователя в файле .rgs вашего проекта.

Смотрите [IOleObject::GetUserType](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) в Windows SDK.

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a>IOleObjectImpl::InitFromData

Инициализирует элемент управления из выбранных данных.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) в Windows SDK.

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a>IOleObjectImpl::IsUpTodate

Проверяет, актуален ли элемент управления.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::IsUpToDate](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) в Windows SDK.

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a>IOleObjectImpl::OnPostVerbDiscardUndo

Вызывается [DoVerbDiscardUndo](#doverbdiscardundo) после отменить состояние отбрасывается.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода, выполненного после отбрасыва того состояния отсна, необходимого для отмены.

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a>IOleObjectImpl::OnPostVerbhide

Вызывается [DoVerbHide](#doverbhide) после того, как контроль скрыт.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода, выполненного после скрытия элемента управления.

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a>IOleObjectImpl::OnPostVerbInPlaceActivate

Вызывается [DoVerbInPlaceActivate](#doverbinplaceactivate) после того, как контроль активирован на месте.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода после активации элемента управления.

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a>IOleObjectImpl::OnPostVerbOpen

Вызывается [DoVerbOpen](#doverbopen) после того, как элемент управления был открыт для редактирования в отдельном окне.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода, выполненного после того, как элемент управления был открыт для редактирования в отдельном окне.

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a>IOleObjectImpl::OnPostVerbShow

Вызывается [DoVerbShow](#doverbshow) после того, как элемент управления был сделан видимым.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода, выполненного после того, как элемент управления будет видимым.

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a>IoleObjectImpl::OnPostVerbuIActivate

Вызывается [DoVerbUIActivate](#doverbuiactivate) после активации пользовательского интерфейса элемента управления.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределить этот метод с помощью нужного кода после активации пользовательского интерфейса элемента управления.

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a>IOleObjectImpl::OnPreVerbDiscardUndo

Вызывается [DoVerbDiscardUndo](#doverbdiscardundo) до отменить состояние отбрасывается.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить отбрасывание состояния отсутсвия, переуторируйте этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a>IoleObjectImpl::OnpreVerbHide

Вызывается [DoVerbHide](#doverbhide) до того, как элемент управления будет скрыт.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы не скрыть элемент управления, переуторируйте этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a>IoleObjectImpl::OnpreverbInPlaceActivate

Вызывается [DoVerbInPlaceActivate](#doverbinplaceactivate) до того, как управление активируется на месте.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить активацию элемента управления на месте, переуместите этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a>IoleObjectImpl::OnPreVerbOpen

Вызывается [DoVerbOpen](#doverbopen) до того, как элемент управления был открыт для редактирования в отдельном окне.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить открытие элемента управления для редактирования в отдельном окне, переуторите этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a>IoleObjectImpl::OnpreVerbShow

Вызывается [DoVerbShow,](#doverbshow) прежде чем элемент управления был сделан видимым.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы не допустить видимого элемента управления, переуторируйте этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a>IoleObjectImpl::OnpreVerbuiActivate

Вызывается [DoVerbUIActivate](#doverbuiactivate) до того, как пользовательский интерфейс управления был активирован.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить активацию пользовательского интерфейса элемента управления, переуторируйте этот метод, чтобы вернуть ошибку HRESULT.

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a>IOleObjectImpl::SetClientSite

Сообщает элемент управления о своем клиентском сайте в контейнере.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Примечания

Затем метод возвращается S_OK.

Смотрите [IOleObject::SetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) в Windows SDK.

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a>IOleObjectImpl:SetColorScheme

Рекомендует цветовую схему для применения элемента управления, если таковые имеется.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) в Windows SDK.

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a>IOleObjectImpl::SetExtent

Устанавливает степень зоны дисплея элемента управления.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Примечания

В `SetExtent` противном случае, `psizel` хранит значение, на что указывает в элементе данных класса управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Это значение находится в единицах HIMETRIC (0,01 миллиметра на единицу).

Если член данных класса управления [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) является правдой, также хранит значение, `SetExtent` на что указывает `psizel` в элементе данных класса управления [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).

Если член данных класса управления [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) true, звонит `SetExtent` `SendOnDataChange` и `SendOnViewChange` уведомляет все консультационные приемники, зарегистрированные у владельца, что размер элемента управления изменился.

Смотрите [IOleObject::SetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) в Windows SDK.

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a>IOleObjectImpl::SetHostNames

Сообщает элементуправления имена контейнерного приложения и контейнерного документа.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::SetHostNames](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) в Windows SDK.

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a>IOleObjectImpl::SetMoniker

Сообщает контролю, что такое его прозвище.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::SetMoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) в Windows SDK.

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a>IOleObjectImpl::Unadvise

Удаляет консультативное соединение, хранящееся в элементе `m_spOleAdviseHolder` данных класса управления.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::Unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) в Windows SDK.

## <a name="ioleobjectimplupdate"></a><a name="update"></a>IOleObjectImpl::Обновление

Обновляет элемент управления.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleObject::Обновление](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
