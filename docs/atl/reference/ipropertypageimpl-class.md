---
title: IPropertyPageImpl класс
ms.date: 11/04/2016
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: 154bfb5beb258ff26649f44f0bd4c23fb8708977
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745861"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl класс

Этот класс `IUnknown` реализует и обеспечивает реализацию интерфейса [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) по умолчанию.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPropertyPageImpl`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::Активировать](#activate)|Создает окно окна окна диалогового окна для страницы свойств.|
|[IPropertyPageImpl::Apply](#apply)|Применяет текущие значения страницы свойств к `SetObjects`базовым объектам, указанным через. Реализация ATL возвращает S_OK.|
|[IPropertyPageImpl::Dэактив](#deactivate)|Разрушает окно, созданное с помощью `Activate`.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Извлекает информацию о странице свойств.|
|[IPropertyPageImpl::Помощь](#help)|Вызывает помощь Windows для страницы свойств.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Указывается, изменилась ли страница свойств с момента ее активации.|
|[IPropertyPageImpl::Движение](#move)|Позиции и изражает поле диалога страницы свойств.|
|[IPropertyPageImpl::SetDirty](#setdirty)|Флаги состояния страницы свойств как измененные или неизмененные.|
|[IPropertyPageImpl::SetObjects](#setobjects)|Предоставляет массив `IUnknown` указателей для объектов, связанных со страницей свойств. Эти объекты получают текущие значения страницы свойств через `Apply`вызов.|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Предоставляет страницу свойств `IPropertyPageSite` указателем, через который страница свойств общается с рамкой свойств.|
|[IPropertyPageImpl::Показать](#show)|Делает поле диалога страницы свойств видимым или невидимым.|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Обрабатывает указанный нажатие клавиши.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Определяет, изменилось ли состояние страницы свойства.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Хранит идентификатор ресурса, связанный с текстовой строкой, описывающей страницу свойств.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Хранит идентификатор контекста для темы справки, связанной со страницей свойств.|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Хранит идентификатор ресурса, связанный с именем файла справки, описывающего страницу свойств.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Хранит идентификатор ресурса, связанный с строкой текста, которая отображается во вкладке для страницы свойств.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Хранит количество объектов, связанных со страницей свойств.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Указывает на `IPropertyPageSite` интерфейс, через который страница свойств общается с рамкой свойств.|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Указывает на массив `IUnknown` указателей на объекты, связанные со страницей свойств.|
|[IPropertyPageImpl::m_size](#m_size)|Хранит высоту и ширину диалогового окна страницы свойств в пикселях.|

## <a name="remarks"></a>Примечания

Интерфейс [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) позволяет объекту управлять определенной страницей свойств в листе свойств. Класс `IPropertyPageImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ipropertypageimplactivate"></a><a name="activate"></a>IPropertyPageImpl::Активировать

Создает окно окна окна диалогового окна для страницы свойств.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Примечания

По умолчанию диалоговая коробка всегда беспрейрана, независимо от значения параметра *bModal.*

Смотрите [IPropertyPage::Активируйте](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) в Windows SDK.

## <a name="ipropertypageimplapply"></a><a name="apply"></a>IPropertyPageImpl::Apply

Применяет текущие значения страницы свойств к `SetObjects`базовым объектам, указанным через.

```
HRESULT Apply();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage:: Применить](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) в Windows SDK.

## <a name="ipropertypageimpldeactivate"></a><a name="deactivate"></a>IPropertyPageImpl::Dэактив

Уничтожает окно окна окна диалогового окна, созданного с [помощью Activate.](#activate)

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage: :Dактивировать](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) в Windows SDK.

## <a name="ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo

Заполняет структуру *pPageInfo* информацией, содержащейся в данных членов.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Примечания

`GetPageInfo`загружает строки ресурсов, связанных с [m_dwDocString,](#m_dwdocstring) [m_dwHelpFile](#m_dwhelpfile)и [m_dwTitle.](#m_dwtitle)

Смотрите [IPropertyPage::GetPageInfo](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) в Windows SDK.

## <a name="ipropertypageimplhelp"></a><a name="help"></a>IPropertyPageImpl::Помощь

Вызывает помощь Windows для страницы свойств.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage::Помощь](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) в Windows SDK.

## <a name="ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl

Конструктор.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Примечания

Инициализирует всех участников данных.

## <a name="ipropertypageimplispagedirty"></a><a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty

Указывается, изменилась ли страница свойств с момента ее активации.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Примечания

`IsPageDirty`возвращает S_OK, если страница изменилась с момента ее активации.

## <a name="ipropertypageimplm_bdirty"></a><a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty

Определяет, изменилось ли состояние страницы свойства.

```
BOOL m_bDirty;
```

## <a name="ipropertypageimplm_nobjects"></a><a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects

Хранит количество объектов, связанных со страницей свойств.

```
ULONG m_nObjects;
```

## <a name="ipropertypageimplm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext

Хранит идентификатор контекста для темы справки, связанной со страницей свойств.

```
DWORD m_dwHelpContext;
```

## <a name="ipropertypageimplm_dwdocstring"></a><a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString

Хранит идентификатор ресурса, связанный с текстовой строкой, описывающей страницу свойств.

```
UINT m_dwDocString;
```

## <a name="ipropertypageimplm_dwhelpfile"></a><a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile

Хранит идентификатор ресурса, связанный с именем файла справки, описывающего страницу свойств.

```
UINT m_dwHelpFile;
```

## <a name="ipropertypageimplm_dwtitle"></a><a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle

Хранит идентификатор ресурса, связанный с строкой текста, которая отображается во вкладке для страницы свойств.

```
UINT m_dwTitle;
```

## <a name="ipropertypageimplm_ppagesite"></a><a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite

Указывает на интерфейс [IPropertyPageSite,](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) через который страница свойств общается с рамкой свойств.

```
IPropertyPageSite* m_pPageSite;
```

## <a name="ipropertypageimplm_ppunk"></a><a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk

Указывает на массив `IUnknown` указателей на объекты, связанные со страницей свойств.

```
IUnknown** m_ppUnk;
```

## <a name="ipropertypageimplm_size"></a><a name="m_size"></a>IPropertyPageImpl::m_size

Хранит высоту и ширину диалогового окна страницы свойств в пикселях.

```
SIZE m_size;
```

## <a name="ipropertypageimplmove"></a><a name="move"></a>IPropertyPageImpl::Движение

Позиции и изражает поле диалога страницы свойств.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage:: Перемещение](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) в Windows SDK.

## <a name="ipropertypageimplsetdirty"></a><a name="setdirty"></a>IPropertyPageImpl::SetDirty

Флаги состояние страницы свойства, как изменены или без изменений, в зависимости от значения *bDirty*.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*bDirty*<br/>
(в) Если true, состояние страницы свойства помечено как измененное. В противном случае он помечается как неизменный.

### <a name="remarks"></a>Примечания

При необходимости сообщает `SetDirty` кадр о том, что страница свойств изменилась.

## <a name="ipropertypageimplsetobjects"></a><a name="setobjects"></a>IPropertyPageImpl::SetObjects

Предоставляет массив `IUnknown` указателей для объектов, связанных со страницей свойств.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage:: SetObjects](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) в Windows SDK.

## <a name="ipropertypageimplsetpagesite"></a><a name="setpagesite"></a>IPropertyPageImpl::SetPageSite

Предоставляет страницу свойств указателем [IPropertyPageSite,](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) через который страница свойств общается с рамкой свойств.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage::SetPageSite](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) в SDK Windows.

## <a name="ipropertypageimplshow"></a><a name="show"></a>IPropertyPageImpl::Показать

Делает поле диалога страницы свойств видимым или невидимым.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage::Показать](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) в Windows SDK.

## <a name="ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator

Процессы нажатия `pMsg`клавиши, указанные в .

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage::TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IPropertyPage2Impl класс](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyБражИмпл класс](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl класс](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
