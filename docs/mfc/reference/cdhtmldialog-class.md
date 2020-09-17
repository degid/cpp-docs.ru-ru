---
title: Класс CDHtmlDialog
ms.date: 03/27/2019
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
ms.openlocfilehash: 9cc01c94357d7aac7fa6fa98127628a60746e1e8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842888"
---
# <a name="cdhtmldialog-class"></a>Класс CDHtmlDialog

Используется для создания диалоговых окон, в которых для реализации пользовательского интерфейса используется HTML, а не ресурсы диалоговых окон.

## <a name="syntax"></a>Синтаксис

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDHtmlDialog:: CDHtmlDialog](#cdhtmldialog)|Конструирует объект CDHtmlDialog.|
|[CDHtmlDialog:: ~ CDHtmlDialog](#_dtorcdhtmldialog)|Уничтожает объект CDHtmlDialog.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDHtmlDialog:: Канакцессекстернал](#canaccessexternal)|Переопределяемый метод, который вызывается как проверка доступа, чтобы определить, могут ли объекты скрипта на загруженной странице получать доступ к внешней диспетчеризации сайта элемента управления. Проверяет, является ли отправка защищенной для сценариев, или текущая зона допускает использование объектов, которые не являются надежными для сценариев.|
|[CDHtmlDialog:: Креатеконтролсите](#createcontrolsite)|Переопределяемый объект, используемый для создания экземпляра сайта элемента управления для размещения элемента управления WebBrowser в диалоговом окне.|
|[CDHtmlDialog::D DX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Обменивает данные между переменной-членом и значением свойства элемента управления ActiveX на HTML-странице.|
|[CDHtmlDialog::D DX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Обменивает данные между переменной-членом и флажком на HTML-странице.|
|[CDHtmlDialog::D DX_DHtml_ElementText](#ddx_dhtml_elementtext)|Обменивает данные между переменной-членом и любым свойством HTML-элемента на странице HTML.|
|[CDHtmlDialog::D DX_DHtml_Radio](#ddx_dhtml_radio)|Обменивает данные между переменной-членом и переключателем на HTML-странице.|
|[CDHtmlDialog::D DX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Возвращает или задает индекс поля списка на странице HTML.|
|[CDHtmlDialog::D DX_DHtml_SelectString](#ddx_dhtml_selectstring)|Возвращает или задает отображаемый текст записи списка (на основе текущего индекса) на HTML-странице.|
|[CDHtmlDialog::D DX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Возвращает или задает значение записи списка (на основе текущего индекса) на HTML-странице.|
|[CDHtmlDialog::D Естроймоделесс](#destroymodeless)|Уничтожает немодальное диалоговое окно.|
|[CDHtmlDialog:: Енаблемоделесс](#enablemodeless)|Включение немодальных диалоговых окон.|
|[CDHtmlDialog:: Филтердатаобжект](#filterdataobject)|Позволяет диалоговому окну фильтровать объекты данных в буфере обмена, созданные размещенным браузером.|
|[CDHtmlDialog:: Жетконтролдиспатч](#getcontroldispatch)|Извлекает `IDispatch` интерфейс элемента управления ActiveX, внедренного в HTML-документ.|
|[CDHtmlDialog:: Жетконтролпроперти](#getcontrolproperty)|Извлекает запрошенное свойство указанного элемента управления ActiveX.|
|[CDHtmlDialog:: Жеткуррентурл](#getcurrenturl)|Извлекает универсальный указатель ресурсов (URL-адрес), связанный с текущим документом.|
|[CDHtmlDialog:: Жетдхтмлдокумент](#getdhtmldocument)|Извлекает интерфейс IHTMLDocument2 для загруженного в данный момент HTML-документа.|
|[CDHtmlDialog:: Жетдроптаржет](#getdroptarget)|Вызывается вложенным элементом управления WebBrowser, когда он используется в качестве цели перетаскивания, чтобы разрешить диалоговому окну предоставлять альтернативный [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget).|
|[CDHtmlDialog:: элемент](#getelement)|Возвращает интерфейс для элемента HTML.|
|[CDHtmlDialog:: Жетелеменстмл](#getelementhtml)|Извлекает `innerHTML` свойство элемента HTML.|
|[CDHtmlDialog:: Жетелементинтерфаце](#getelementinterface)|Извлекает запрошенный указатель интерфейса из элемента HTML.|
|[CDHtmlDialog:: Жетелементпроперти](#getelementproperty)|Извлекает значение свойства элемента HTML.|
|[CDHtmlDialog:: Жетелементтекст](#getelementtext)|Извлекает `innerText` свойство элемента HTML.|
|[CDHtmlDialog:: четный](#getevent)|Возвращает `IHTMLEventObj` указатель на текущий объект события.|
|[CDHtmlDialog:: External](#getexternal)|Возвращает `IDispatch` интерфейс узла.|
|[CDHtmlDialog:: Жесостинфо](#gethostinfo)|Получает возможности пользовательского интерфейса узла.|
|[CDHtmlDialog:: Жетоптионкэйпас](#getoptionkeypath)|Извлекает раздел реестра, в котором хранятся параметры пользователя.|
|[CDHtmlDialog:: Хидеуи](#hideui)|Скрывает пользовательский интерфейс узла.|
|[CDHtmlDialog:: Исекстерналдиспатчсафе](#isexternaldispatchsafe)|Указывает `IDispatch` , является ли интерфейс узла надежным для сценариев.|
|[CDHtmlDialog:: Лоадфромресаурце](#loadfromresource)|Загружает указанный ресурс в элемент управления WebBrowser.|
|[CDHtmlDialog:: Navigate](#navigate)|Переход по указанному URL-адресу.|
|[CDHtmlDialog:: Онбефоренавигате](#onbeforenavigate)|Вызывается платформой до запуска события навигации.|
|[CDHtmlDialog:: Ондокументкомплете](#ondocumentcomplete)|Вызывается платформой для уведомления приложения о том, что документ достиг состояния READYSTATE_COMPLETE.|
|[CDHtmlDialog:: OnDocWindowActivate](#ondocwindowactivate)|Вызывается структурой при активации или отключении окна документа.|
|[CDHtmlDialog:: OnFrameWindowActivate](#onframewindowactivate)|Вызывается структурой при активации или отключении окна фрейма.|
|[CDHtmlDialog:: Онинитдиалог](#oninitdialog)|Вызывается в ответ на сообщение WM_INITDIALOG.|
|[CDHtmlDialog:: Оннавигатекомплете](#onnavigatecomplete)|Вызывается структурой после завершения события навигации.|
|[CDHtmlDialog:: ResizeBorder](#resizeborder)|Предупреждает объект о том, что ему нужно изменить размер области границ.|
|[CDHtmlDialog:: Сетконтролпроперти](#setcontrolproperty)|Задает новое значение для свойства элемента управления ActiveX.|
|[CDHtmlDialog:: Сетелеменстмл](#setelementhtml)|Задает `innerHTML` свойство элемента HTML.|
|[CDHtmlDialog:: Сетелементпроперти](#setelementproperty)|Задает свойство элемента HTML.|
|[CDHtmlDialog:: Сетелементтекст](#setelementtext)|Задает `innerText` свойство элемента HTML.|
|[CDHtmlDialog:: Сетекстерналдиспатч](#setexternaldispatch)|Задает `IDispatch` интерфейс узла.|
|[CDHtmlDialog:: Сесостфлагс](#sethostflags)|Задает флаги пользовательского интерфейса узла.|
|[CDHtmlDialog:: Шовконтекстмену](#showcontextmenu)|Вызывается при отображении контекстного меню.|
|[CDHtmlDialog:: параметра showUI задано](#showui)|Показывает пользовательский интерфейс узла.|
|[CDHtmlDialog:: TranslateAccelerator](#translateaccelerator)|Вызывается для обработки сообщений сочетания клавиш в меню "обработать".|
|[CDHtmlDialog:: Транслатеурл](#translateurl)|Вызывается для изменения URL-адреса для загрузки.|
|[CDHtmlDialog:: Упдатеуи](#updateui)|Вызывается для уведомления узла об изменении состояния команды.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDHtmlDialog:: m_bUseHtmlTitle](#m_busehtmltitle)|Указывает, следует ли использовать заголовок HTML-документа в качестве заголовка диалогового окна.|
|[CDHtmlDialog:: m_nHtmlResID](#m_nhtmlresid)|Идентификатор ресурса отображаемого HTML-ресурса.|
|[CDHtmlDialog:: m_pBrowserApp](#m_pbrowserapp)|Указатель на приложение веб-браузера.|
|[CDHtmlDialog:: m_spHtmlDoc](#m_sphtmldoc)|Указатель на HTML-документ.|
|[CDHtmlDialog:: m_strCurrentUrl](#m_strcurrenturl)|Текущий URL-адрес.|
|[CDHtmlDialog:: m_szHtmlResID](#m_szhtmlresid)|Строковая версия идентификатора ресурса HTML.|

## <a name="remarks"></a>Примечания

`CDHtmlDialog` может загрузить HTML-код, отображаемый из ресурса HTML или с URL-адреса.

`CDHtmlDialog` также может осуществлять обмен данными с HTML-элементами управления и управлять событиями из элементов управления HTML, таких как нажатия кнопок.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксдхтмл.h

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a> DDX_DHtml вспомогательных макросов

Вспомогательные макросы DDX_DHtml позволяют легко получать доступ к часто используемым свойствам элементов управления на HTML-странице.

### <a name="data-exchange-macros"></a>Макросы обмена данными

|Имя|Описание|
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Задает или получает свойство Value из выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Задает или получает текст между открывающим и закрывающим тегами текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Задает или получает HTML-код между открывающим и закрывающим тегами текущего элемента.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Задает или получает URL-адрес назначения или точку привязки.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклип в документе.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного фрейма.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного фрейма.|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a> CDHtmlDialog:: Канакцессекстернал

Переопределяемый метод, который вызывается как проверка доступа, чтобы определить, могут ли объекты скрипта на загруженной странице получать доступ к внешней диспетчеризации сайта элемента управления. Проверяет, является ли отправка защищенной для сценариев, или текущая зона допускает использование объектов, которые не являются надежными для сценариев.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a> CDHtmlDialog:: CDHtmlDialog

Конструирует диалоговое окно динамического HTML на основе ресурсов.

```
CDHtmlDialog();

CDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID,
    CWnd *pParentWnd = NULL);

CDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd *pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзтемплатенаме*<br/>
Строка, завершающаяся нулем, которая является именем ресурса шаблона диалогового окна.

*сзтмлресид*<br/>
Строка, завершающаяся нулем, которая является именем ресурса HTML.

*ппарентвнд*<br/>
Указатель на родительский или объект окна-владельца (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если значение равно NULL, то родительское окно объекта диалогового окна устанавливается в главное окно приложения.

*нидтемплате*<br/>
Содержит ИДЕНТИФИКАЦИОНный номер ресурса шаблона диалогового окна.

*нхтмлресид*<br/>
Содержит ИДЕНТИФИКАЦИОНный номер ресурса HTML.

### <a name="remarks"></a>Примечания

Вторая форма конструктора предоставляет доступ к ресурсу диалогового окна через имя шаблона. Третья форма конструктора предоставляет доступ к ресурсу диалогового окна через идентификатор шаблона ресурса. Обычно идентификатор начинается с префикса **IDD_** .

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a> CDHtmlDialog:: ~ CDHtmlDialog

Уничтожает объект CDHtmlDialog.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Примечания

Функция члена [CWnd::D естройвиндов](../../mfc/reference/cwnd-class.md#destroywindow) должна использоваться для уничтожения немодальных диалоговых окон, созданных с помощью класса [CDialog:: Create](../../mfc/reference/cdialog-class.md#create).

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a> CDHtmlDialog:: Креатеконтролсите

Переопределяемый объект, используемый для создания экземпляра сайта элемента управления для размещения элемента управления WebBrowser в диалоговом окне.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Параметры

*pContainer*<br/>
Указатель на объект [колеконтролконтаинер](../../mfc/reference/colecontrolcontainer-class.md)

*ппсите*<br/>
Указатель на указатель на [колеконтролсите](../../mfc/reference/colecontrolsite-class.md).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эту функцию-член можно переопределить, чтобы она возвращала экземпляр класса собственного элемента управления.

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a> CDHtmlDialog::D DX_DHtml_AxControl

Обменивает данные между переменной-членом и значением свойства элемента управления ActiveX на HTML-странице.

```cpp
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение параметра ID тега объекта в источнике HTML для элемента управления ActiveX.

*dispId*<br/>
Идентификатор диспетчеризации свойства, с которым необходимо обмениваться данными.

*сзпропнаме*<br/>
Имя свойства.

*var*<br/>
Элемент данных типа VARIANT, [COleVariant](../../mfc/reference/colevariant-class.md)или [CComVariant](../../atl/reference/ccomvariant-class.md), который содержит значение, переданное с помощью свойства элемента управления ActiveX.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a> CDHtmlDialog::D DX_DHtml_CheckBox

Обменивает данные между переменной-членом и флажком на HTML-странице.

```cpp
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*value*<br/>
Значение для обмена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a> CDHtmlDialog::D DX_DHtml_ElementText

Обменивает данные между переменной-членом и любым свойством HTML-элемента на странице HTML.

```cpp
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*dispId*<br/>
Идентификатор диспетчеризации элемента HTML, с которым необходимо обмениваться данными.

*value*<br/>
Значение для обмена.

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a> CDHtmlDialog::D DX_DHtml_Radio

Обменивает данные между переменной-членом и переключателем на HTML-странице.

```cpp
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*value*<br/>
Значение для обмена.

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a> CDHtmlDialog::D DX_DHtml_SelectIndex

Возвращает или задает индекс поля списка на странице HTML.

```cpp
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра HTML-элемента управления `id` .

*value*<br/>
Значение для обмена.

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a> CDHtmlDialog::D DX_DHtml_SelectString

Возвращает или задает отображаемый текст записи списка (на основе текущего индекса) на HTML-странице.

```cpp
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*value*<br/>
Значение для обмена.

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a> CDHtmlDialog::D DX_DHtml_SelectValue

Возвращает или задает значение записи списка (на основе текущего индекса) на HTML-странице.

```cpp
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*сзид*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*value*<br/>
Значение для обмена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a> CDHtmlDialog::D Естроймоделесс

Отсоединяет немодальное диалоговое окно от `CDHtmlDialog` объекта и уничтожает объект.

```cpp
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a> CDHtmlDialog:: Енаблемоделесс

Включение немодальных диалоговых окон.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Параметры

*фенабле*<br/>
См. раздел *фенабле* in [Идочостуихандлер:: енаблемоделесс](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Енаблемоделесс](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a> CDHtmlDialog:: Филтердатаобжект

Позволяет диалоговому окну фильтровать объекты данных в буфере обмена, созданные размещенным браузером.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Параметры

*pDO*<br/>
См. раздел *pDO* in [Идочостуихандлер:: филтердатаобжект](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) в Windows SDK.

*ппдорет*<br/>
См. раздел *ппдорет* в `IDocHostUIHandler::FilterDataObject` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Филтердатаобжект](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a> CDHtmlDialog:: Жетконтролдиспатч

Извлекает `IDispatch` интерфейс элемента управления ActiveX, внедренного в HTML-документ, возвращенный [жетдхтмлдокумент](#getdhtmldocument).

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Параметры

*сзид*<br/>
Идентификатор HTML элемента управления ActiveX.

*ппдисп*<br/>
`IDispatch`Интерфейс элемента управления, если он найден на веб-странице.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a> CDHtmlDialog:: Жетконтролпроперти

Извлекает запрошенное свойство указанного элемента управления ActiveX.

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>Параметры

*сзид*<br/>
Идентификатор HTML элемента управления ActiveX.

*сзпропнаме*<br/>
Имя свойства в языковом стандарте текущего пользователя по умолчанию.

*пдиспконтрол*<br/>
`IDispatch`Указатель элемента управления ActiveX.

*dispId*<br/>
Идентификатор диспетчеризации свойства.

### <a name="return-value"></a>Возвращаемое значение

Значение типа Variant, содержащее запрошенное свойство, или пустое значение типа Variant, если не удалось найти элемент управления или свойство.

### <a name="remarks"></a>Примечания

Перегрузки перечисляются с минимальной эффективностью в верхней части до наиболее эффективных в нижней части.

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a> CDHtmlDialog:: Жеткуррентурл

Извлекает универсальный указатель ресурсов (URL-адрес), связанный с текущим документом.

```cpp
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Параметры

*сзурл*<br/>
Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий URL-адрес для извлечения.

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a> CDHtmlDialog:: Жетдхтмлдокумент

Извлекает интерфейс [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) для загруженного в данный момент HTML-документа.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Параметры

* \* \* пфтмлдок* указатель на указатель на HTML-документ.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Возвращает S_OK в случае успеха.

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a> CDHtmlDialog:: Жетдроптаржет

Вызывается вложенным элементом управления WebBrowser, когда он используется в качестве цели перетаскивания, чтобы разрешить диалоговому окну предоставлять альтернативный [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget).

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Параметры

*пдроптаржет*<br/>
См. раздел *пдроптаржет* in [Идочостуихандлер:: жетдроптаржет](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) в Windows SDK.

*ппдроптаржет*<br/>
См. раздел *ппдроптаржет* в `IDocHostUIHandler::GetDropTarget` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Жетдроптаржет](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a> CDHtmlDialog:: элемент

Возвращает интерфейс для элемента HTML, заданного параметром *сзелементид*.

```
HRESULT GetElement(
    LPCTSTR szElementId,
    IDispatch** ppdisp,
    BOOL* pbCollection = NULL);

HRESULT GetElement(
    LPCTSTR szElementId,
    IHTMLElement** pphtmlElement);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*ппдисп*<br/>
`IDispatch`Указатель на запрошенный элемент или коллекцию элементов.

*пбколлектион*<br/>
Логическое значение, указывающее, является ли объект, представленный *ппдисп* , единственным элементом или коллекцией элементов.

*пфтмлелемент*<br/>
`IHTMLElement`Указатель на запрошенный элемент.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Используйте первую перегрузку, если необходимо обрабатывать условия, в которых может быть несколько элементов с указанным ИДЕНТИФИКАТОРом. Последний параметр можно использовать для определения того, является ли возвращаемый указатель интерфейса коллекцией или одним элементом. Если указатель интерфейса находится в коллекции, можно запросить `IHTMLElementCollection` и использовать его `item` свойство для ссылки на элементы по порядковому номеру.

Вторая перегрузка завершится ошибкой, если на странице имеется более одного элемента с одинаковым ИДЕНТИФИКАТОРом.

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a> CDHtmlDialog:: Жетелеменстмл

Извлекает `innerHTML` свойство элемента HTML, определенного параметром *сзелементид*.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

### <a name="return-value"></a>Возвращаемое значение

`innerHTML`Свойство элемента HTML, идентифицируемое *сзелементид* , или значение null, если элемент не найден.

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a> CDHtmlDialog:: Жетелементинтерфаце

Извлекает запрошенный указатель интерфейса из элемента HTML, определенного параметром *сзелементид*.

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*ппвобж*<br/>
Адрес указателя, который будет заполнен запрошенным указателем интерфейса, если элемент найден и запрос выполнен.

*рефиид*<br/>
Идентификатор интерфейса (IID) запрашиваемого интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a> CDHtmlDialog:: Жетелементпроперти

Получает значение свойства, идентифицируемого *DISPID* , из элемента HTML, определенного параметром *сзелементид*.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*dispId*<br/>
Идентификатор диспетчеризации свойства.

### <a name="return-value"></a>Возвращаемое значение

Значение свойства или пустой вариант, если не удалось найти свойство или элемент.

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a> CDHtmlDialog:: Жетелементтекст

Извлекает `innerText` свойство элемента HTML, определенного параметром *сзелементид*.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

### <a name="return-value"></a>Возвращаемое значение

`innerText`Свойство элемента HTML, идентифицируемое *сзелементид* , или значение null, если не удалось найти свойство или элемент.

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a> CDHtmlDialog:: четный

Возвращает `IHTMLEventObj` указатель на текущий объект события.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Параметры

*ппевентобж*<br/>
Адрес указателя, который будет заполнен `IHTMLEventObj` указателем интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция должна вызываться только в обработчике событий DHTML.

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a> CDHtmlDialog:: External

Возвращает `IDispatch` интерфейс узла.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Параметры

*ппдиспатч*<br/>
См. раздел *ппдиспатч* в [Идочостуихандлер:: External](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или E_NOTIMPL при сбое.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: External](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a> CDHtmlDialog:: Жесостинфо

Получает возможности пользовательского интерфейса узла.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Параметры

*пинфо*<br/>
См. раздел *пинфо* in [Идочостуихандлер:: жесостинфо](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Жесостинфо](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a> CDHtmlDialog:: Жетоптионкэйпас

Извлекает раздел реестра, в котором хранятся параметры пользователя.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*пчкэй*<br/>
См. раздел *пчкэй* in [Идочостуихандлер:: жетоптионкэйпас](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) в Windows SDK.

*dw*<br/>
См. раздел *хранилище* данных в `IDocHostUIHandler::GetOptionKeyPath` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Жетоптионкэйпас](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a> CDHtmlDialog:: Хидеуи

Скрывает пользовательский интерфейс узла.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Хидеуи](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a> CDHtmlDialog:: Исекстерналдиспатчсафе

Указывает `IDispatch` , является ли интерфейс узла надежным для сценариев.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение FALSE.

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a> CDHtmlDialog:: Лоадфромресаурце

Загружает указанный ресурс в элемент управления WebBrowser в диалоговом окне DHTML.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Параметры

*лпсзресаурце*<br/>
Указатель на строку, содержащую имя загружаемого ресурса.

*нрес*<br/>
Идентификатор загружаемого ресурса.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a> CDHtmlDialog:: m_bUseHtmlTitle

Указывает, следует ли использовать заголовок HTML-документа в качестве заголовка диалогового окна.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Примечания

Если параметр **m**_ **бусехтмлтитле** имеет значение true, то заголовок диалогового окна задается равным заголовку HTML-документа. в противном случае используется заголовок в ресурсе диалогового окна.

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a> CDHtmlDialog:: m_nHtmlResID

Идентификатор ресурса отображаемого HTML-ресурса.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a> CDHtmlDialog:: m_pBrowserApp

Указатель на приложение веб-браузера.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a> CDHtmlDialog:: m_spHtmlDoc

Указатель на HTML-документ.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a> CDHtmlDialog:: m_strCurrentUrl

Текущий URL-адрес.

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a> CDHtmlDialog:: m_szHtmlResID

Строковая версия идентификатора ресурса HTML.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a> CDHtmlDialog:: Navigate

Переходит к ресурсу, определяемому URL-адресом, заданным параметром *лпсзурл*.

```cpp
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>Параметры

*лпсзурл*<br/>
Указатель на строку, содержащую URL-адрес для целевого элемента.

*dwFlags*<br/>
Флаги переменной, указывающие, следует ли добавить ресурс в список журнала, следует ли выполнять чтение в кэш или запись из кэша, а также следует ли отображать ресурс в новом окне. Переменная может представлять собой сочетание значений, определенных перечислением [бровсернавконстантс](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) .

*лпсзтаржетфраменаме*<br/>
Указатель на строку, содержащую имя кадра, в котором отображается ресурс.

*лпсзеадерс*<br/>
Указатель на значение, указывающее заголовки HTTP для отправки на сервер. Эти заголовки добавляются в заголовки Internet Explorer по умолчанию. Заголовки могут указывать такие сведения, как действие, требуемое сервером, тип данных, передаваемых на сервер, или код состояния. Этот параметр пропускается, если URL-адрес не является URL-адресом HTTP.

*лпвпостдата*<br/>
Указатель на данные, которые необходимо отправить с помощью транзакции HTTP POST. Например, транзакция POST используется для отправки данных, собранных HTML-формой. Если этот параметр не указывает какие-либо данные POST, `Navigate` выдает транзакцию HTTP GET. Этот параметр пропускается, если URL-адрес не является URL-адресом HTTP.

*двпостдатален*<br/>
Данные, отправляемые с помощью транзакции HTTP POST. Например, транзакция POST используется для отправки данных, собранных HTML-формой. Если этот параметр не указывает какие-либо данные POST, `Navigate` выдает транзакцию HTTP GET. Этот параметр пропускается, если URL-адрес не является URL-адресом HTTP.

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a> CDHtmlDialog:: Онбефоренавигате

Вызвано платформой для срабатывания события перед переходом.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
Указатель на объект `IDispatch`.

*сзурл*<br/>
Указатель на строку, содержащую URL-адрес для перехода.

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a> CDHtmlDialog:: Ондокументкомплете

Вызывается платформой для уведомления приложения о том, что документ получил READYSTATE_COMPLETEное состояние.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
Указатель на объект `IDispatch`.

*сзурл*<br/>
Указатель на строку, содержащую URL-адрес, к которому был выполнен переход.

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a> CDHtmlDialog:: OnDocWindowActivate

Вызывается структурой при активации или отключении окна документа.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*фактивате*<br/>
См. раздел *фактивате* in [Идочостуихандлер:: OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a> CDHtmlDialog:: OnFrameWindowActivate

Вызывается структурой при активации или отключении окна фрейма.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*фактивате*<br/>
См. раздел *фактивате* in [Идочостуихандлер:: OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a> CDHtmlDialog:: Онинитдиалог

Вызывается в ответ на сообщение WM_INITDIALOG.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Это сообщение отправляется в диалоговое окно во время `Create` `CreateIndirect` вызовов, или `DoModal` , которые происходят непосредственно перед отображением диалогового окна.

Переопределите эту функцию-член, если необходимо выполнить специальную обработку при инициализации диалогового окна. В переопределенной версии сначала вызовите базовый класс, `OnInitDialog` но не пропустите его возвращаемое значение. Как правило, вы возвращаете значение TRUE из переопределенной функции члена.

Windows вызывает `OnInitDialog` функцию с помощью стандартного глобального диалогового окна, общего для всех Библиотека Microsoft Foundation Class диалоговых окон, а не с помощью схемы сообщений, поэтому для этой функции-члена не требуется запись схемы сообщений.

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a> CDHtmlDialog:: Оннавигатекомплете

Вызвано структурой после перехода по указанному URL-адресу.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
Указатель на объект `IDispatch`.

*сзурл*<br/>
Указатель на строку, содержащую URL-адрес, к которому был выполнен переход.

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a> CDHtmlDialog:: ResizeBorder

Предупреждает объект о том, что ему нужно изменить размер области границ.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Параметры

*пркбордер*<br/>
См. раздел *пркбордер* in [Идочостуихандлер:: ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) в Windows SDK.

*пуивиндов*<br/>
См. раздел *пуивиндов* в `IDocHostUIHandler::ResizeBorder` Windows SDK.

*ффрамевиндов*<br/>
См. раздел *ффрамевиндов* в `IDocHostUIHandler::ResizeBorder` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a> CDHtmlDialog:: Сетконтролпроперти

Задает новое значение для свойства элемента управления ActiveX.

```cpp
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML элемента управления ActiveX.

*dispId*<br/>
Идентификатор диспетчеризации свойства, которое необходимо задать.

*пвар*<br/>
Указатель на вариант, содержащий новое значение свойства.

*пдиспконтрол*<br/>
Указатель на интерфейс элемента управления ActiveX `IDispatch` .

*сзпропнаме*<br/>
Строка, содержащая имя свойства, которое необходимо задать.

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a> CDHtmlDialog:: Сетелеменстмл

Задает `innerHTML` свойство элемента HTML.

```cpp
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*бстртекст*<br/>
Новое значение свойства `innerHTML` .

*пункелем*<br/>
`IUnknown`Указатель элемента HTML.

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a> CDHtmlDialog:: Сетелементпроперти

Задает свойство элемента HTML.

```cpp
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*dispId*<br/>
Идентификатор диспетчеризации свойства, которое необходимо задать.

*пвар*<br/>
Новое значение свойства.

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a> CDHtmlDialog:: Сетелементтекст

Задает `innerText` свойство элемента HTML.

```cpp
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*сзелементид*<br/>
Идентификатор HTML-элемента.

*бстртекст*<br/>
Новое значение свойства `innerText` .

*пункелем*<br/>
`IUnknown`Указатель элемента HTML.

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a> CDHtmlDialog:: Сетекстерналдиспатч

Задает `IDispatch` интерфейс узла.

```cpp
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Параметры

*пдиспекстернал*<br/>
Новый `IDispatch` интерфейс.

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a> CDHtmlDialog:: Сесостфлагс

Задает флаги пользовательского интерфейса узла.

```cpp
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Возможные значения см. в разделе [дочостуифлаг](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) в Windows SDK.

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a> CDHtmlDialog:: Шовконтекстмену

Вызывается при отображении контекстного меню.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Параметры

*двид*<br/>
См. раздел *ДВИД* in [Идочостуихандлер:: шовконтекстмену](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) в Windows SDK.

*PowerPoint*<br/>
См. статью *PPT* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

*пкмдтресервед*<br/>
См. раздел *пкмдтресервед* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

*пдиспресервед*<br/>
См. раздел *пдиспресервед* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Шовконтекстмену](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogshowui"></a><a name="showui"></a> CDHtmlDialog:: параметра showUI задано

Показывает пользовательский интерфейс узла.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>Параметры

*двид*<br/>
См. раздел *ДВИД* in [Идочостуихандлер:: параметра showUI задано](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) в Windows SDK.

*пактивеобжект*<br/>
См. раздел *d пактивеобжект* in `IDocHostUIHandler::ShowUI` в Windows SDK.

*пкоммандтаржет*<br/>
См. раздел *пкоммандтаржет* в `IDocHostUIHandler::ShowUI` Windows SDK.

*пфраме*<br/>
См. раздел *пфраме* в `IDocHostUIHandler::ShowUI` Windows SDK.

*pDoc*<br/>
См. раздел *pDoc* в `IDocHostUIHandler::ShowUI` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: параметра showUI задано](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a> CDHtmlDialog:: TranslateAccelerator

Вызывается для обработки сообщений сочетания клавиш в меню "обработать".

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Параметры

*лпмсг*<br/>
См. раздел *лпмсг* in [Идочостуихандлер:: TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) в Windows SDK.

*пгуидкмдграуп*<br/>
См. раздел *пгуидкмдграуп* в `IDocHostUIHandler::TranslateAccelerator` Windows SDK.

*нкмдид*<br/>
См. раздел *нкмдид* в `IDocHostUIHandler::TranslateAccelerator` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a> CDHtmlDialog:: Транслатеурл

Вызывается для изменения URL-адреса для загрузки.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Параметры

*двтранслате*<br/>
См. раздел *двтранслате* in [Идочостуихандлер:: транслатеурл](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) в Windows SDK.

*пчурлин*<br/>
См. раздел *пчурлин* в `IDocHostUIHandler::TranslateUrl` Windows SDK.

*ппчурлаут*<br/>
См. раздел *ппчурлаут* в `IDocHostUIHandler::TranslateUrl` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Транслатеурл](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a> CDHtmlDialog:: Упдатеуи

Вызывается для уведомления узла об изменении состояния команды.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией [идочостуихандлер:: Упдатеуи](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))CDHtmlDialog, как описано в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Пример Дхтмлексплоре для MFC](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml вспомогательных макросов](#ddx_dhtml_helper_macros)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
