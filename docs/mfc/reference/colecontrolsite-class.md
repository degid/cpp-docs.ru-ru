---
title: Класс COleControlSite
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 90c41a1be1a66cdceebb3f045a98167e56b7cf4c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753956"
---
# <a name="colecontrolsite-class"></a>Класс COleControlSite

Обеспечивает поддержку пользовательских интерфейсов клиентских элементов управления.

## <a name="syntax"></a>Синтаксис

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeControlSite::COleControlSite](#colecontrolsite)|Формирует объект `COleControlSite`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeControlSite::BindDefaultProperty](#binddefaultproperty)|Связывает свойство по умолчанию размещенного элемента управления с источником данных.|
|[COleControlSite::BindProperty](#bindproperty)|Привязывает свойство размещенного элемента управления к источнику данных.|
|[ColeControlSite::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|
|[COleControlSite::DestroyControl](#destroycontrol)|Уничтожает размещенный элемент управления.|
|[COleControlSite::DoVerb](#doverb)|Выполняет определенный глагол развмещаемого управления.|
|[ColeControlSite::EnableDSC](#enabledsc)|Позволяет найти данные для сайта управления.|
|[ColeControlSite::EnableWindow](#enablewindow)|Включает сайт управления.|
|[ColeControlSite::FreezeEvents](#freezeevents)|Упоняет, принимает ли сайт управления события.|
|[ColeControlSite::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопки по умолчанию для развмещаемого элемента управления.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Извлекает идентификатор элемента управления.|
|[ColeControlSite::GetEventIID](#geteventiid)|Извлекает идентификатор интерфейса события для развлеки.|
|[ColeControlSite::GetExStyle](#getexstyle)|Извлекает расширенные стили сайта управления.|
|[ColeControlSite::GetProperty](#getproperty)|Извлекает определенное свойство размещенного элемента управления.|
|[ColeControlSite::GetStyle](#getstyle)|Извлекает стили сайта управления.|
|[COleControlSite::GetWindowText](#getwindowtext)|Извлекает текст размещенного элемента управления.|
|[COleControlSite::InvokeHelper](#invokehelper)|Вызвать определенный метод размещаемого управления.|
|[ColeControlSite::InvokeHelperV](#invokehelperv)|Вызвать конкретный метод развмещаемого управления с переменным списком аргументов.|
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Определяет, является ли элемент управления кнопкой по умолчанию в окне.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Проверяет видимое состояние сайта управления.|
|[ColeControlSite::ModifyStyle](#modifystyle)|Изменяет текущие расширенные стили сайта управления.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Изменяет текущие стили сайта управления.|
|[COleControlSite::MoveWindow](#movewindow)|Изменяет положение сайта управления.|
|[ColeControlSite::Быстрыйактивация](#quickactivate)|Быстрый активации размещенного элемента управления.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Устанавливает свойство или метод управления без шансов на то, чтобы выбросить исключение.|
|[ColeControlSite::SetDefaultButton](#setdefaultbutton)|Устанавливает кнопку по умолчанию в окне.|
|[ColeControlSite::SetDlgCtrlID](#setdlgctrlid)|Извлекает идентификатор элемента управления.|
|[COleControlSite::SetFocus](#setfocus)|Устанавливает фокус на контрольном сайте.|
|[ColeControlSite::SetProperty](#setproperty)|Устанавливает определенное свойство размещаемого элемента управления.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Устанавливает определенное свойство развмещаемого элемента управления переменным списком аргументов.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Устанавливает положение сайта управления.|
|[ColeControlSite::SetWindowText](#setwindowtext)|Устанавливает текст размещенного элемента управления.|
|[COleControlSite::ShowWindow](#showwindow)|Показывает или скрывает сайт управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[ColeControlSite::GetControlInfo](#getcontrolinfo)|Получает клавиатуру информации и мнемоники для хостинга управления.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeControlSite::m_bIsWindowless](#m_biswindowless)|Определяет, является ли развяженный элемент управления бесхозным.|
|[ColeControlSite:::m_ctlInfo](#m_ctlinfo)|Содержит информацию об обработке клавиатуры для управления.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Файлы cookie точки соединения управления.|
|[ColeControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Различные государства для размещенного контроля.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Печенье `IPropertyNotifySink` элемента управления.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Стили развязаемого управления.|
|[COleControlSite::m_hWnd](#m_hwnd)|Ручка сайта управления.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Идентификатор интерфейса события для развмещаемого управления.|
|[ColeControlSite::m_nID](#m_nid)|Идентификатор разведрена.|
|[ColeControlSite::m_pActiveObject](#m_pactiveobject)|Указатель на `IOleInPlaceActiveObject` объект размещаемого элемента управления.|
|[ColeControlSite::m_pCtrlCont](#m_pctrlcont)|Контейнер размещаемого управления.|
|[ColeControlSite:::m_pInPlaceObject](#m_pinplaceobject)|Указатель на `IOleInPlaceObject` объект размещаемого элемента управления.|
|[ColeControlSite::m_pObject](#m_pobject)|Указатель на `IOleObjectInterface` интерфейс управления.|
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Указатель на `IOleInPlaceObjectWindowless` интерфейс управления.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Указатель на объект окна для размещаемого элемента управления.|
|[COleControlSite::m_rect](#m_rect)|Размеры контрольного участка.|

## <a name="remarks"></a>Примечания

Эта поддержка является основным средством, с помощью которого встроенный элемент управления ActiveX получает информацию о местоположении и масштабах своего сайта отображения, его прозвище, пользовательский интерфейс, его окружающие свойства и другие ресурсы, предоставляемые контейнером. `COleControlSite`полностью реализует [интерфейсы IOleControlSite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite), [IOleInPlaceSite,](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), , `IBoundObjectSite` `INotifyDBEvents`, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) интерфейсы. Кроме того, реализован интерфейс IDispatch (обеспечивающий поддержку свойств окружающей среды и поглотителей событий).

Для создания сайта управления `COleControlSite`ActiveX с `COleControlSite`использованием, получить класс из . В `CWnd`вашем классе производных для контейнера (например, вашего диалогового окна) переопределение функции. `CWnd::CreateControlSite`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Требования

**Заголовок:** afxocc.h

## <a name="colecontrolsitebinddefaultproperty"></a><a name="binddefaultproperty"></a>ColeControlSite::BindDefaultProperty

Связывает простое связанное свойство объекта вызова по умолчанию, отмеченное в библиотеке типа, с базовым курсором, определяемым свойствами DataSource, UserName, Password и S'L управления источником данных.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Определяет DISPID свойства на элементе управления, связанном с данными, которое должно быть связано с управлением источником данных.

*vtProp*<br/>
Упомяните тип собственности, который должен быть связан - например, VT_BSTR, VT_VARIANT и так далее.

*szFieldName*<br/>
Укравит название столбца в курсоре, предоставленном управлением источником данных, к которому будет привязано свойство.

*pDSCWnd*<br/>
Указатель на `CWnd`объект, полученный из полученных данных, который размещает элемент управления исходным источником данных, к которому будет привязано свойство.

### <a name="remarks"></a>Примечания

Объект, `CWnd` на котором вы называете эту функцию, должен быть элементом управления, связанным с данными.

## <a name="colecontrolsitebindproperty"></a><a name="bindproperty"></a>ColeControlSite::BindProperty

Связывает простое связанное свойство вызывающего объекта, отмеченное в библиотеке типа, с базовым курсором, определяемым свойствами DataSource, UserName, Password и S'L управления источником данных.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Параметры

*dwDispId*<br/>
Определяет DISPID свойства на элементе управления, связанном с данными, которое должно быть связано с управлением источником данных.

*pWndDSC*<br/>
Указатель на `CWnd`объект, полученный из полученных данных, который размещает элемент управления исходным источником данных, к которому будет привязано свойство.

### <a name="remarks"></a>Примечания

Объект, `CWnd` на котором вы называете эту функцию, должен быть элементом управления, связанным с данными.

## <a name="colecontrolsitecolecontrolsite"></a><a name="colecontrolsite"></a>ColeControlSite::COleControlSite

Создает новый объект `COleControlSite`.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Параметры

*pCtrlCont*<br/>
Указатель на контейнер управления (который представляет окно, в котором размещается элемент управления AtiveX).

### <a name="remarks"></a>Примечания

Эта функция называется [cOccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) функции. Для получения дополнительной информации о настройке создания контейнеров, [см. COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).

## <a name="colecontrolsitecreatecontrol"></a><a name="createcontrol"></a>ColeControlSite::CreateControl

Создает элемент управления ActiveX, `COleControlSite` размещенный объектом.

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Параметры

*pWndCtrl*<br/>
Указатель на объект окна, представляющий элемент управления.

*clsid*<br/>
Уникальный идентификатор класса управления.

*lpszWindowName*<br/>
Указатель на текст, который отображается в элементе управления. Устанавливает значение свойства подписи winodw или текста (если таковое имеется).

*dwStyle*<br/>
Стили Windows. Доступные стили перечислены в разделе **Замечания.**

*rect*<br/>
Определяет размер и положение элемента управления. Это может быть `CRect` либо `RECT` объект, либо структура.

*nID*<br/>
Упоняет идентификатор окна ребенка элемента управления.

*pPersist*<br/>
Указатель на `CFile` содержащее постоянное состояние для управления. Значение по умолчанию является NULL, что указывает на то, что элемент управления инициализирует себя без восстановления его состояния от постоянного хранилища. Если не NULL, то он должен `CFile`быть указателем на объект, содержащий постоянные данные элемента управления, в виде потока или хранилища. Эти данные могли быть сохранены при предыдущей активации клиента. Может `CFile` содержать другие данные, но должен иметь свой указатель на чтение-запись, установленный `CreateControl`на первый байт стойких данных во время вызова.

*bХранение*<br/>
Указывает, следует ли интерпретировать данные `IStorage` в `IStream` *pPersist* как или данные. Если данные в *pPersist* является хранилищем, *bStorage* должно быть правдой. Если данные в *pPersist* является потоком, *bStorage* должен быть FALSE. Значение по умолчанию — FALSE.

*bstrLicKey*<br/>
Дополнительные данные ключей лицензии. Эти данные необходимы только для создания элементов управления, требующих ключа лицензии времени выполнения. Если элемент управления поддерживает лицензирование, необходимо предоставить ключ лицензии для создания элемента управления для достижения успеха. Значение по умолчанию — NULL.

*Ppt*<br/>
Указатель на `POINT` структуру, содержащую верхний левый угол элемента управления. Размер элемента определяется значением *psize.* Значения *ppt* и *psize* являются необязательным методом определения размера и положения opf элемента управления.

*psize*<br/>
Указатель на `SIZE` структуру, содержащую размер элемента управления. Верхний левый угол определяется значением *ppt.* Значения *ppt* и *psize* являются необязательным методом определения размера и положения opf элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Поддерживается `CreateControl`только подмножество флагов Windows *dwStyle:*

- WS_VISIBLE создает окно, которое изначально видно. Требуется, если вы хотите, чтобы элемент управления был виден немедленно, как обычные окна.

- WS_DISABLED создает окно, которое изначально отключено. Отключенное окно не может получать ввод от пользователя. Может быть установлен, если элемент управления имеет свойство enabled.

- WS_BORDER создает окно с тонкой линией границы. Может быть установлен, если контроль имеет свойство BorderStyle.

- WS_GROUP определяет первый элемент управления группой элементов управления. Пользователь может изменить фокус клавиатуры с одного элемента управления в группе на другой, используя клавиши направления. Все элементы управления, определяемые со стилем WS_GROUP после первого элемента управления принадлежат одной и той же группе. Следующий элемент управления со стилем WS_GROUP завершает группу и запускает следующую группу.

- WS_TABSTOP определяет элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает на ключ TAB. Нажатие клавиши TAB изменяет фокус клавиатуры на следующий элемент управления стилем WS_TABSTOP.

Используйте вторую перегрузку для создания элементов управления размером с непосредствение.

## <a name="colecontrolsitedestroycontrol"></a><a name="destroycontrol"></a>ColeControlSite: :DestroyControl

Уничтожает `COleControlSite` объект.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Примечания

После завершения, объект освобождается от памяти и любые указатели на объект больше не действительны.

## <a name="colecontrolsitedoverb"></a><a name="doverb"></a>ColeControlSite::DoVerb

Выполняет указанный глагол.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Параметры

*nVerb*<br/>
Определяет глагол для выполнения. Она может включать в себя один из следующих:

|Значение|Значение|Символ|
|-----------|-------------|------------|
|0|первичный глагол|OLEIVERB_PRIMARY|
|-1|Вторичный глагол|(нет)|
|1|Отображает объект для редактирования.|OLEIVERB_SHOW|
|-2|Отсваивай элемент в отдельном окне.|OLEIVERB_OPEN|
|–3|Скрывает объект.|OLEIVERB_HIDE|
|–4|Активирует элемент управления на месте.|OLEIVERB_UIACTIVATE|
|-5|Активирует элемент управления на месте, без дополнительных элементов пользовательского интерфейса.|OLEIVERB_INPLACEACTIVATE|
|-7|Отобразите свойства элемента управления.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
Указать на сообщение, которое вызвало активацию элемента.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция напрямую вызывает `IOleObject` через интерфейс управления для выполнения указанного глагола. Если в результате этого вызова функции выбрасывается исключение, возвращается код ошибки HRESULT.

Для получения дополнительной информации [см. IOleObject::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

## <a name="colecontrolsiteenabledsc"></a><a name="enabledsc"></a>ColeControlSite::EnableDSC

Позволяет найти данные для сайта управления.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Примечания

Вызывается в рамках для включения и инициализации поиска данных для сайта управления. Переопределить эту функцию, чтобы обеспечить индивидуальное поведение.

## <a name="colecontrolsiteenablewindow"></a><a name="enablewindow"></a>ColeControlSite::EnableWindow

Позволяет или отсрочивает ввод мыши и клавиатуры на сайт управления.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Определяет, включать или отключать окно: правда, если вход окона должен быть включен, в противном случае FALSE.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если окно ранее было отключено, в противном случае 0.

## <a name="colecontrolsitefreezeevents"></a><a name="freezeevents"></a>ColeControlSite::FreezeEvents

Уточняется, будет ли сайт управления обрабатывать или игнорировать события, выпущенные из-под контроля.

```cpp
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Параметры

*bFreeze*<br/>
Указывает, требуется ли остановить прием событий для местоположения элемента управления. Nonzero, если элемент управления не принимает события; в противном случае ноль.

### <a name="remarks"></a>Примечания

Если *bFreeze* является правдой, сайт управления запрашивает элемент управления, чтобы остановить fring событий. Если *bFreeze* false, сайт управления запрашивает элемент управления для продолжения событий стрельбы.

> [!NOTE]
> Контроль не требуется, чтобы остановить события стрельбы, если требуется на сайте управления. Он может продолжать стрельбу, но все последующие события будут проигнорированы сайтом управления.

## <a name="colecontrolsitegetcontrolinfo"></a><a name="getcontrolinfo"></a>ColeControlSite::GetControlInfo

Получает информацию о мнемоники клавиатуры управления и поведении клавиатуры.

```cpp
void GetControlInfo();
```

### <a name="remarks"></a>Примечания

Информация хранится в [COleControlSite::m_ctlInfo](#m_ctlinfo).

## <a name="colecontrolsitegetdefbtncode"></a><a name="getdefbtncode"></a>ColeControlSite::GetDefBtnCode

Определяет, является ли элемент управления кнопкой нажатия по умолчанию.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Возвращаемое значение

Может использоваться одно из следующих значений:

- DLGC_DEFPUSHBUTTON управление — это кнопка по умолчанию в диалоге.

- DLGC_UNDEFPUSHBUTTON управление не является кнопкой по умолчанию в диалоге.

- **0** Управление не является кнопкой.

## <a name="colecontrolsitegetdlgctrlid"></a><a name="getdlgctrlid"></a>ColeControlSite::GetDlgCtrlID

Извлекает идентификатор элемента управления.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор элемента диалога элемента управления.

## <a name="colecontrolsitegeteventiid"></a><a name="geteventiid"></a>ColeControlSite::GetEventIID

Извлекает указатель на интерфейс события события элемента по умолчанию.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Параметры

*пиид*<br/>
Указатель на идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0. В случае успеха *piid* содержит идентификатор интерфейса для интерфейса события элемента по умолчанию.

## <a name="colecontrolsitegetexstyle"></a><a name="getexstyle"></a>ColeControlSite::GetExStyle

Извлекает расширенные стили окна.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расширенные стили окна управления.

### <a name="remarks"></a>Примечания

Чтобы получить обычные стили, позвоните [COleControlSite::GetStyle](#getstyle).

## <a name="colecontrolsitegetproperty"></a><a name="getproperty"></a>ColeControlSite::GetProperty

Получает контрольное свойство, указанное *dwDispID.*

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства, найденный на интерфейсе по умолчанию `IDispatch` элемента управления, который должен быть извлечен.

*vtProp*<br/>
Упогоняет тип извлечения свойства. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvProp*<br/>
Адрес переменной, которая получит стоимость свойства. Он должен соответствовать типу, указанному *vtProp.*

### <a name="remarks"></a>Примечания

Значение возвращается через *pvProp*.

## <a name="colecontrolsitegetstyle"></a><a name="getstyle"></a>ColeControlSite::GetStyle

Извлекает стили сайта управления.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Стили окна.

### <a name="remarks"></a>Примечания

Список возможных значений можно узнать в [windows Styles.](../../mfc/reference/styles-used-by-mfc.md#window-styles) Чтобы получить расширенные стили сайта управления, позвоните [COleControlSite::GetExStyle](#getexstyle).

## <a name="colecontrolsitegetwindowtext"></a><a name="getwindowtext"></a>ColeControlSite::GetWindowText

Извлекает текущий текст элемента управления.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Ссылка на `CString` объект, содержащий текущий текст элемента управления.

### <a name="remarks"></a>Примечания

Если элемент управления поддерживает свойство акции Caption, это значение возвращается. Если свойство акции caption не поддерживается, значение для свойства Text возвращается.

## <a name="colecontrolsiteinvokehelper"></a><a name="invokehelper"></a>ColeControlSite::InvokeHelper

Вызывает метод или свойство, указанное *dwDispID,* в контексте, указанном *wFlags*.

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства или метода, `IDispatch` найденный на интерфейсе управления, который будет вызываться.

*wFlags*<br/>
Флаги, описывающие контекст вызова IDispatch::Invoke. Для возможных *значений wFlags* см. `IDispatch::Invoke`

*vtRet*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, указанному *vtRet.*

*pbParamInfo*<br/>
Указатель на нулевую строку байтов с указанием типов параметров, следующих *pbParamInfo.* Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Переменный список параметров, типов, указанных в *pbParamInfo*.

### <a name="remarks"></a>Примечания

Параметр *pbParamInfo* определяет типы параметров, передаваемых методу или свойству. Переменный список аргументов представлен в объявлении синтаксиса как ....

Эта функция преобразует параметры в значения VARIANTARG, а `IDispatch::Invoke` затем вызывает метод на элементе управления. Если вызов `IDispatch::Invoke` завершается сбоем, эта функция создает исключение. Если код состояния, `IDispatch::Invoke` `DISP_E_EXCEPTION`возвращенный, является, `COleDispatchException` эта функция бросает `COleException`объект, в противном случае он бросает .

## <a name="colecontrolsiteinvokehelperv"></a><a name="invokehelperv"></a>ColeControlSite::InvokeHelperV

Вызывает метод или свойство, указанное *dwDispID,* в контексте, указанном *wFlags*.

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства или метода, `IDispatch` найденный на интерфейсе управления, который будет вызываться.

*wFlags*<br/>
Флаги, описывающие контекст вызова IDispatch::Invoke.

*vtRet*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, указанному *vtRet.*

*pbParamInfo*<br/>
Указатель на нулевую строку байтов с указанием типов параметров, следующих *pbParamInfo.* Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Указатель на список переменных аргументов.

### <a name="remarks"></a>Примечания

Параметр *pbParamInfo* определяет типы параметров, передаваемых методу или свойству. Дополнительные параметры вызываемого метода или свойства могут быть пройдены с помощью *va_list* параметра.

Как правило, эта `COleControlSite::InvokeHelper`функция вызывается .

## <a name="colecontrolsiteisdefaultbutton"></a><a name="isdefaultbutton"></a>ColeControlsite::IsDefaultButton

Определяет, является ли элемент управления кнопкой по умолчанию.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент управления является кнопкой по умолчанию на окне, в противном случае ноль.

## <a name="colecontrolsiteiswindowenabled"></a><a name="iswindowenabled"></a>ColeControlsite::IsWindowEnabled

Определяет, включен ли участок управления.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент управления включен, в противном случае ноль.

### <a name="remarks"></a>Примечания

Значение извлекается из элементауправления включенного элемента управления.

## <a name="colecontrolsitem_biswindowless"></a><a name="m_biswindowless"></a>ColeControlSite::m_bIsWindowless

Определяет, является ли объект элементом управления без окон.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Примечания

Nonzero, если элемент управления не имеет окна, в противном случае ноль.

## <a name="colecontrolsitem_ctlinfo"></a><a name="m_ctlinfo"></a>ColeControlSite:::m_ctlInfo

Информация о том, как ввод клавиатуры обрабатывается элементом управления.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Примечания

Эта информация хранится в структуре [CONTROLINFO.](/windows/win32/api/ocidl/ns-ocidl-controlinfo)

## <a name="colecontrolsitem_dweventsink"></a><a name="m_dweventsink"></a>ColeControlSite:::m_dwEventSink

Содержит файл cookie точки соединения из раковины события элемента управления.

```
DWORD m_dwEventSink;
```

## <a name="colecontrolsitem_dwmiscstatus"></a><a name="m_dwmiscstatus"></a>ColeControlSite::m_dwMiscStatus

Содержит различную информацию о элементе управления.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/oleidl/ne-oleidl-olemisc)

## <a name="colecontrolsitem_dwpropnotifysink"></a><a name="m_dwpropnotifysink"></a>ColeControlSite::m_dwPropNotifySink

Содержит файл cookie [IPropertyNotifySink.](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)

```
DWORD m_dwPropNotifySink;
```

## <a name="colecontrolsitem_dwstyle"></a><a name="m_dwstyle"></a>ColeControlSite::m_dwStyle

Содержит стили управления Window.

```
DWORD m_dwStyle;
```

## <a name="colecontrolsitem_hwnd"></a><a name="m_hwnd"></a>ColeControlSite::m_hWnd

Содержит HWND элемента управления или NULL, если элемент управления не имеет окон.

```
HWND m_hWnd;
```

## <a name="colecontrolsitem_iidevents"></a><a name="m_iidevents"></a>ColeControlSite::m_iidEvents

Содержит идентификатор интерфейса интерфейса интерфейса погружения события элемента по умолчанию.

```
IID m_iidEvents;
```

## <a name="colecontrolsitem_nid"></a><a name="m_nid"></a>ColeControlSite::m_nID

Содержит идентификатор элемента диалога элемента управления.

```
UINT m_nID;
```

## <a name="colecontrolsitem_pactiveobject"></a><a name="m_pactiveobject"></a>ColeControlSite::m_pActiveObject

Содержит интерфейс управления [IOleInPlaceActiveObject.](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject)

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

## <a name="colecontrolsitem_pctrlcont"></a><a name="m_pctrlcont"></a>ColeControlSite::m_pCtrlCont

Содержит контейнер элемента управления (представляющий форму).

```
COleControlContainer* m_pCtrlCont;
```

## <a name="colecontrolsitem_pinplaceobject"></a><a name="m_pinplaceobject"></a>ColeControlSite:::m_pInPlaceObject

Содержит  интерфейс `IOleInPlaceObject` [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) элемента управления.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

## <a name="colecontrolsitem_pobject"></a><a name="m_pobject"></a>ColeControlSite::m_pObject

Содержит `IOleObjectInterface` интерфейс управления.

```
LPOLEOBJECT m_pObject;
```

## <a name="colecontrolsitem_pwindowlessobject"></a><a name="m_pwindowlessobject"></a>ColeControlSite::m_pWindowlessObject

`IOleInPlaceObjectWindowless`Содержит интерфейс управления [IOleInPlaceObjectWindowless.](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless)

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

## <a name="colecontrolsitem_pwndctrl"></a><a name="m_pwndctrl"></a>ColeControlSite::m_pWndCtrl

Содержит указатель на `CWnd` объект, представляющий сам элемент управления.

```
CWnd* m_pWndCtrl;
```

## <a name="colecontrolsitem_rect"></a><a name="m_rect"></a>ColeControlSite::m_rect

Содержит границы элемента управления, относительно окна контейнера.

```
CRect m_rect;
```

## <a name="colecontrolsitemodifystyle"></a><a name="modifystyle"></a>ColeControlSite::ModifyStyle

Изменяет стили управления.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*dwRemove*<br/>
Стили, которые должны быть удалены из текущих стилей окна.

*dwAdd*<br/>
Стили, которые будут добавлены из текущих стилей окна.

*nФлаги*<br/>
Флаги позиционирования окон. Список возможных значений можно [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) узнать в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если стили изменены, в противном случае ноль.

### <a name="remarks"></a>Примечания

Свойство включено в акции элемента управления будет изменено в соответствии с настройками для WS_DISABLED. Свойство пограничного стиля управления будет изменено в соответствии с запрошенной настройкой для WS_BORDER. Все остальные стили применяются непосредственно к оконной ручке элемента управления, если он присутствует.

Изменяет стили управления окнами. Стили, которые должны быть добавлены или удалены, могут быть объединены с помощью bitwise OR (&#124;) оператора. Ознакомьтесь с функцией [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в SDK Windows, чтобы получить информацию о доступных стилях окон.

Если *nFlags* незеро, `ModifyStyle` вызовите `SetWindowPos`функцию Win32 и перерисуйте окно, объединив *nFlags* со следующими четырьмя флагами:

- SWP_NOSIZE сохраняет текущий размер.

- SWP_NOMOVE сохраняет текущее положение.

- SWP_NOZORDER сохраняет текущий заказ.

- SWP_NOACTIVATE не активирует окно.

Чтобы изменить расширенные стили окна, позвоните [ModifyStyleEx.](#modifystyleex)

## <a name="colecontrolsitemodifystyleex"></a><a name="modifystyleex"></a>ColeControlSite::ModifyStyleEx

Изменяет расширенные стили управления.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*dwRemove*<br/>
Расширенные стили, которые должны быть удалены из текущих стилей окна.

*dwAdd*<br/>
Расширенные стили, которые будут добавлены из текущих стилей окна.

*nФлаги*<br/>
Флаги позиционирования окон. Список возможных значений можно [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) узнать в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если стили изменены, в противном случае ноль.

### <a name="remarks"></a>Примечания

Свойство элемента управления по внешнему виду будет изменено в соответствии с настройками для WS_EX_CLIENTEDGE. Все остальные расширенные стили окон применяются непосредственно к оконной ручке элемента управления, если он присутствует.

Изменяет расширенные стили объекта сайта управления. Стили, которые должны быть добавлены или удалены, могут быть объединены с помощью bitwise OR (&#124;) оператора. Ознакомьтесь с функцией [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в SDK Windows, чтобы получить информацию о доступных стилях окон.

Если *nFlags* незеро, `ModifyStyleEx` вызовите `SetWindowPos`функцию Win32 и перерисуйте окно, объединив *nFlags* со следующими четырьмя флагами:

- SWP_NOSIZE сохраняет текущий размер.

- SWP_NOMOVE сохраняет текущее положение.

- SWP_NOZORDER сохраняет текущий заказ.

- SWP_NOACTIVATE не активирует окно.

Чтобы изменить расширенные стили окна, позвоните [ModifyStyle.](#modifystyle)

## <a name="colecontrolsitemovewindow"></a><a name="movewindow"></a>ColeControlSite::MoveWindow

Изменяет положение элемента управления.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Новое положение левой стороны окна.

*Y*<br/>
Новое положение верхней части окна.

*nWidth*<br/>
Новая ширина окна

*nВысота*<br/>
Новая высота окна.

## <a name="colecontrolsitequickactivate"></a><a name="quickactivate"></a>ColeControlSite::Быстрыйактивация

Быстрый активации сдерживаемого элемента управления.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контрольный участок был активирован, в противном случае ноль.

### <a name="remarks"></a>Примечания

Эта функция должна вызываться только в том случае, если пользователь переопределяет процесс создания элемента управления.

`IPersist*::Load` Методы `IPersist*::InitNew` и методы должны быть вызваны после быстрой активации происходит. Контроль должен установить его соединения с раковинами контейнера во время быстрой активации. Тем не менее, эти `IPersist*::Load` `IPersist*::InitNew` соединения не живут до тех пор, пока или не был вызван.

## <a name="colecontrolsitesafesetproperty"></a><a name="safesetproperty"></a>ColeControlSite::SafeSetProperty

Устанавливает свойство управления, указанное *dwDispID.*

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства или метода, `IDispatch` найденный на интерфейсе управления, который будет установлен.

*vtProp*<br/>
Определяет тип свойства, подавивих на себя. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Единый параметр типа, указанный *vtProp*.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
> В `SetProperty` `SetPropertyV`отличие от и, если ошибка встречается (например, попытка установить несуществующее свойство), не выбрасывается исключение.

## <a name="colecontrolsitesetdefaultbutton"></a><a name="setdefaultbutton"></a>ColeControlSite::SetDefaultButton

Устанавливает элемент управления в качестве кнопки по умолчанию.

```cpp
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*bDefault*<br/>
Nonzero, если элемент управления должен стать кнопкой по умолчанию; в противном случае ноль.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Элемент управления должен иметь набор бита OLEMISC_ACTSLIKEBUTTON статуса.

## <a name="colecontrolsitesetdlgctrlid"></a><a name="setdlgctrlid"></a>ColeControlSite::SetDlgCtrlID

Изменяет значение идентификатора элемента диалога элемента элемента элемента управления.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Новое значение идентификатора.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха предыдущий идентификатор элемента диалога окна; в противном случае 0.

### <a name="remarks"></a>Примечания

## <a name="colecontrolsitesetfocus"></a><a name="setfocus"></a>ColeControlSite::SetFocus

Устанавливает фокус на элемент управления.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Параметры

*lpmsg*<br/>
Указатель на [структуру MSG.](/windows/win32/api/winuser/ns-winuser-msg) Эта структура содержит сообщение Windows, запускающее `SetFocus` запрос на элемент управления, содержащийся в текущем сайте управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно, которое ранее было фокус.

## <a name="colecontrolsitesetproperty"></a><a name="setproperty"></a>ColeControlSite::SetProperty

Устанавливает свойство управления, указанное *dwDispID.*

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства или метода, `IDispatch` найденный на интерфейсе управления, который будет установлен.

*vtProp*<br/>
Определяет тип свойства, подавивих на себя. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Единый параметр типа, указанный *vtProp*.

### <a name="remarks"></a>Примечания

При `SetProperty` возникновении ошибки выбрасывается исключение.

Тип исключения определяется значением возврата попытки установить свойство или метод. Если значение возврата, `DISP_E_EXCEPTION` `COleDispatchExcpetion` a брошено; в `COleException`противном случае .

## <a name="colecontrolsitesetpropertyv"></a><a name="setpropertyv"></a>ColeControlSite::SetPropertyV

Устанавливает свойство управления, указанное *dwDispID.*

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует идентификатор отправки свойства или метода, `IDispatch` найденный на интерфейсе управления, который будет установлен.

*vtProp*<br/>
Определяет тип свойства, подавивих на себя. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Дополнительные параметры вызываемого метода или свойства могут быть пройдены с помощью *arg_list* параметра. При `SetProperty` возникновении ошибки выбрасывается исключение.

Тип исключения определяется значением возврата попытки установить свойство или метод. Если значение возврата, `DISP_E_EXCEPTION` `COleDispatchExcpetion` a брошено; в `COleException`противном случае .

## <a name="colecontrolsitesetwindowpos"></a><a name="setwindowpos"></a>ColeControlSite::SetWindowPos

Устанавливает размер, положение и порядок управления сайтом.

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*pWndInsertAfter*<br/>
Указатель на окно.

*x*<br/>
Новое положение левой стороны окна.

*Y*<br/>
Новое положение верхней части окна.

*Cx*<br/>
Новая ширина окна

*Cy*<br/>
Новая высота окна.

*nФлаги*<br/>
Определяет размер оконного размера и позиционирование флагов. Для возможных значений смотрите раздел Замечания для [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае ноль.

## <a name="colecontrolsitesetwindowtext"></a><a name="setwindowtext"></a>ColeControlSite::SetWindowText

Устанавливает текст для сайта управления.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*lpszString*<br/>
Указатель на нулевую строку, которая будет использоваться в качестве нового заголовка или текста управления.

### <a name="remarks"></a>Примечания

Эта функция сначала пытается установить свойство акции Caption. Если свойство акции caption не поддерживается, вместо него устанавливается свойство Текста.

## <a name="colecontrolsiteshowwindow"></a><a name="showwindow"></a>ColeControlSite::ShowWindow

Устанавливает состояние шоу окна.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Параметры

*nCmdShow*<br/>
Определяет, как должен отображаться сайт управления. Это должно быть одно из следующих значений:

- SW_HIDE скрывает это окно и передает активацию в другое окно.

- SW_MINIMIZE минимизирует окно и активирует окно верхнего уровня в списке системы.

- SW_RESTORE активирует и отображает окно. Если окно сведено к минимуму или максимизировано, Windows восстанавливает его до исходного размера и положения.

- SW_SHOW активирует окно и отображает его в текущем размере и положении.

- SW_SHOWMAXIMIZED активирует окно и отображает его как максимальное окно.

- SW_SHOWMINIMIZED активирует окно и отображает его как значок.

- SW_SHOWMINNOACTIVE отображает окно в виде значка. Окно, которое в настоящее время активно, остается активным.

- SW_SHOWNA отображает окно в текущем состоянии. Окно, которое в настоящее время активно, остается активным.

- SW_SHOWNOACTIVATE отображает окно в своем последнем размере и положении. Окно, которое в настоящее время активно, остается активным.

- SW_SHOWNORMAL активирует и отображает окно. Если окно сведено к минимуму или максимизировано, Windows восстанавливает его до исходного размера и положения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если окно было ранее видно; 0, если окно было ранее скрыто.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)
