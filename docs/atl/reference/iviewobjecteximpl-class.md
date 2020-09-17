---
title: IViewObjectExImpl класс
ms.date: 11/04/2016
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
ms.openlocfilehash: 59c5657dcd892544f7e790b52325cb9ecba0dd56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326347"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl класс

Этот класс `IUnknown` реализует и предоставляет реализации по умолчанию интерфейсов [IViewObject,](/windows/win32/api/oleidl/nn-oleidl-iviewobject) [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)и [IViewObjectEx.](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IViewObjectExImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IViewObjectExImpl: :Draw](#draw)|Нарисуйте представление элемента управления на контексте устройства.|
|[IViewObjectExImpl::Заморозка](#freeze)|Замораживает нарисованное представление элемента управления, чтобы `Unfreeze`оно не менялося до . Реализация ATL возвращает E_NOTIMPL.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|Извлекает существующее соединение консультативной раковины на элементе управления, если он имеется.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Возвращает логическую палитру, используемую элементом управления для рисования. Реализация ATL возвращает E_NOTIMPL.|
|[IViewObjectExImpl::GetExtent](#getextent)|Извлекает размер дисплея элемента управления в единицах HIMETRIC (0,01 миллиметра на единицу) от члена данных класса управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Предоставляет подсказки размеров из контейнера для использования объекта при его изобреции.|
|[IViewObjectExImpl::GetRect](#getrect)|Возвращает прямоугольник, описывающий запрашиваемый аспект рисования. Реализация ATL возвращает E_NOTIMPL.|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Возвращает информацию о непрозрачности объекта и о том, какие аспекты рисования поддерживаются.|
|[IViewObjectExImpl::КвихитПойнт](#queryhitpoint)|Проверяет, находится ли указанная точка в указанном прямоугольнике и возвращает значение [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) в. `pHitResult`|
|[IViewObjectExImpl::КвириХитРект](#queryhitrect)|Проверяет, перекрывает ли прямоугольник дисплея элемента управления какую-либо точку `pHitResult`в указанном прямоугольнике местоположения и возвращает значение HITRESULT в.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|Устанавливает соединение между элементом управления и раковиной советовать, чтобы раковина была уведомлена об изменениях в представлении элемента управления.|
|[IViewObjectExImpl::Разморозка](#unfreeze)|Размногивает нарисованное представление элемента управления. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейсы [IViewObject,](/windows/win32/api/oleidl/nn-oleidl-iviewobject) [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)и [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) позволяют элементу управления отображаться напрямую, а также создавать и управлять советом, чтобы уведомить контейнер об изменениях в дисплее управления. Интерфейс `IViewObjectEx` обеспечивает поддержку расширенных функций управления, таких как рисунок без мерцания, непрямоугольные и прозрачные элементы управления, а также хит-тестирование (например, как близко мыши нажмите должны быть рассмотрены на элементе управления). Класс `IViewObjectExImpl` обеспечивает реализацию этих интерфейсов и `IUnknown` реализаций по умолчанию, отправляя информацию на устройство свалки в отладочных сборках.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="iviewobjecteximpldraw"></a><a name="draw"></a>IViewObjectExImpl: :Draw

Нарисуйте представление элемента управления на контексте устройства.

```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```

### <a name="remarks"></a>Примечания

Этот метод `CComControl::OnDrawAdvanced` вызывает, который, в `OnDraw` свою очередь, вызывает метод вашего класса управления. Метод `OnDraw` автоматически добавляется в класс управления при создании элемента управления с помощью atL Control Wizard. По умолчанию `OnDraw` Волшебник рисует прямоугольник с меткой "ATL 3.0".

Смотрите [IViewObject: :Draw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) в SDK Windows.

## <a name="iviewobjecteximplfreeze"></a><a name="freeze"></a>IViewObjectExImpl::Заморозка

Замораживает нарисованное представление элемента управления, чтобы `Unfreeze`оно не менялося до . Реализация ATL возвращает E_NOTIMPL.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Примечания

Смотрите [IViewObject::Заморозить](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) в Windows SDK.

## <a name="iviewobjecteximplgetadvise"></a><a name="getadvise"></a>IViewObjectExImpl::GetAdvise

Извлекает существующее соединение консультативной раковины на элементе управления, если он имеется.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Примечания

Консультационная раковина хранится в элементе данных класса управления [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).

Смотрите [IViewObject::GetAdvise](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) в Windows SDK.

## <a name="iviewobjecteximplgetcolorset"></a><a name="getcolorset"></a>IViewObjectExImpl::GetColorSet

Возвращает логическую палитру, используемую элементом управления для рисования. Реализация ATL возвращает E_NOTIMPL.

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>Примечания

Смотрите [IViewObject::GetColorSet](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) в Windows SDK.

## <a name="iviewobjecteximplgetextent"></a><a name="getextent"></a>IViewObjectExImpl::GetExtent

Извлекает размер дисплея элемента управления в единицах HIMETRIC (0,01 миллиметра на единицу) от члена данных класса управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Примечания

Смотрите [IViewObject2::GetExtent](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) в Windows SDK.

## <a name="iviewobjecteximplgetnaturalextent"></a><a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent

Предоставляет подсказки размеров из контейнера для использования объекта при его изобреции.

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>Примечания

Если `dwAspect` DVASPECT_CONTENT и *pExtentInfo->dwExtentMode* является `psizel` DVEXTENT_CONTENT, устанавливает к члену данных класса управления [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). В противном случае возвращает ошибку HRESULT.

Смотрите [IViewObjectEx::GetNaturalExtent](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) в Windows SDK.

## <a name="iviewobjecteximplgetrect"></a><a name="getrect"></a>IViewObjectExImpl::GetRect

Возвращает прямоугольник, описывающий запрашиваемый аспект рисования. Реализация ATL возвращает E_NOTIMPL.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Примечания

Смотрите [IViewObjectEx::GetRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) в Windows SDK.

## <a name="iviewobjecteximplgetviewstatus"></a><a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus

Возвращает информацию о непрозрачности объекта и о том, какие аспекты рисования поддерживаются.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Примечания

По умолчанию НАБОРы `pdwStatus` ATL указывают, что элемент управления поддерживает VIEWSTATUS_OPAQUE (возможные значения находятся в перечислении [VIEWSTATUS).](/windows/win32/api/ocidl/ne-ocidl-viewstatus)

Смотрите [IViewObjectEx::GetViewStatus](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) в SDK Windows.

## <a name="iviewobjecteximplqueryhitpoint"></a><a name="queryhitpoint"></a>IViewObjectExImpl::КвихитПойнт

Проверяет, находится ли указанная точка в указанном прямоугольнике и возвращает значение [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) в. `pHitResult`

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Примечания

Значение может быть как HITRESULT_HIT, так и HITRESULT_OUTSIDE.

Если `dwAspect` DVASPECT_CONTENT [равен,](/windows/win32/api/wtypes/ne-wtypes-dvaspect)метод возвращается S_OK. В противном случае метод возвращается E_FAIL.

Смотрите [IViewObjectEx::QueryHitPoint](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) в SDK Windows.

## <a name="iviewobjecteximplqueryhitrect"></a><a name="queryhitrect"></a>IViewObjectExImpl::КвириХитРект

Проверяет, перекрывает ли прямоугольник дисплея элемента управления какую-либо точку `pHitResult`в указанном прямоугольнике местоположения и возвращает значение [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) в.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Примечания

Значение может быть как HITRESULT_HIT, так и HITRESULT_OUTSIDE.

Если `dwAspect` DVASPECT_CONTENT [равен,](/windows/win32/api/wtypes/ne-wtypes-dvaspect)метод возвращается S_OK. В противном случае метод возвращается E_FAIL.

Смотрите [IViewObjectEx::QueryHitRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) в Windows SDK.

## <a name="iviewobjecteximplsetadvise"></a><a name="setadvise"></a>IViewObjectExImpl::SetAdvise

Устанавливает соединение между элементом управления и раковиной советовать, чтобы раковина была уведомлена об изменениях в представлении элемента управления.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Примечания

Указатель на интерфейс [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) на раковине советуют хранится в элементе данных класса управления [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).

Смотрите [IViewObject::Установка](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) в Windows SDK.

## <a name="iviewobjecteximplunfreeze"></a><a name="unfreeze"></a>IViewObjectExImpl::Разморозка

Размногивает нарисованное представление элемента управления. Реализация ATL возвращает E_NOTIMPL.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Примечания

Смотрите [IViewObject::Разморозить](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) в Windows SDK.

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::: Близкий к работе

Реализация этого метода для закрытия ручки, связанной с этим объектом.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Параметры

*hHandle*<br/>
Ручка будет закрыта.

### <a name="return-value"></a>Возвращаемое значение

Возврат S_OK на успех, или ошибка HRESULT на неудачу.

### <a name="remarks"></a>Примечания

Ручка, переданная этому методу, ранее была связана с этим объектом путем вызова [cWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

Следующий код показывает простую реализацию `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient:::

Реализация этого метода для выполнения кода, когда ручка, связанная с этим объектом, становится сигнальной.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Параметры

*dwParam*<br/>
Пользовательский параметр.

*hObject*<br/>
Ручка, которая стала сигнальной.

### <a name="return-value"></a>Возвращаемое значение

Возврат S_OK на успех, или ошибка HRESULT на неудачу.

### <a name="remarks"></a>Примечания

Ручка и DWORD/pointer, переданные этому методу, ранее были связаны с этим объектом путем вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

Следующий код показывает простую реализацию `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Учебник](../../atl/active-template-library-atl-tutorial.md)<br/>
[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
