---
title: Класс Каксвиндов
ms.date: 11/04/2016
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 1301baef874ac4e482a1b2a7f0a2ee6b1b63396f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833833"
---
# <a name="caxwindow-class"></a>Класс Каксвиндов

Этот класс предоставляет методы для управления окном, в котором размещается элемент ActiveX.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[аттачконтрол](#attachcontrol)|Присоединяет существующий элемент управления ActiveX к `CAxWindow` объекту.|
|[каксвиндов](#caxwindow)|Формирует объект `CAxWindow`.|
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует его и размещает его в `CAxWindow` окне.|
|[креатеконтролекс](#createcontrolex)|Создает элемент управления ActiveX и получает указатель интерфейса (или указатели) из элемента управления.|
|[жетвндкласснаме](#getwndclassname)|Статически Извлекает предопределенное имя класса `CAxWindow` объекта.|
|[куериконтрол](#querycontrol)|Извлекает `IUnknown` из размещенного элемента управления ActiveX.|
|[куерихост](#queryhost)|Извлекает `IUnknown` указатель `CAxWindow` объекта.|
|[сетекстерналдиспатч](#setexternaldispatch)|Задает внешний интерфейс диспетчеризации, используемый `CAxWindow` объектом.|
|[сетекстерналуихандлер](#setexternaluihandler)|Задает внешний `IDocHostUIHandler` интерфейс, используемый `CAxWindow` объектом.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#operator_eq)|Присваивает HWND существующему `CAxWindow` объекту.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для манипуляций с окном, в котором размещается элемент управления ActiveX. Размещение обеспечивается " **AtlAxWin80"**, заключенного в `CAxWindow` .

Класс `CAxWindow` реализуется как специализация `CAxWindowT` класса. Эта специализация объявляется следующим образом:

`typedef CAxWindowT<CWindow> CAxWindow;`

Если необходимо изменить базовый класс, можно использовать `CAxWindowT` и указать новый базовый класс в качестве аргумента шаблона.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a> Каксвиндов:: Аттачконтрол

Создает новый объект узла, если он еще не существует, и присоединяет указанный элемент управления к узлу.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
окне Указатель на `IUnknown` элемент управления.

*ппункконтаинер*<br/>
заполняет Указатель на `IUnknown` узел ( `AxWin` объект).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Присоединяемый объект элемента управления должен быть правильно инициализирован перед вызовом `AttachControl` .

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a> Каксвиндов:: Каксвиндов

Конструирует объект, `CAxWindow` используя существующий обработчик объекта окна.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего объекта Window.

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a> Каксвиндов:: CreateControl

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- Идентификатор ProgID, например `"MSCAL.Calendar.7"`

- CLSID, например `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL-адрес, например `"<https://www.microsoft.com>"`

- Ссылка на активный документ, например `"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML-кода, например `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. На платформах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE Embedded Platforms, кроме Windows Mobile с поддержкой CE IE, поддерживают все типы, включая ProgID, CLSID, URL-адрес, ссылку на активный документ и фрагмент кода HTML.

*пстреам*<br/>
окне Указатель на поток, используемый для инициализации свойств элемента управления. Может иметь значение NULL.

*ппункконтаинер*<br/>
заполняет Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*двресид*<br/>
Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если используется вторая версия этого метода, создается HTML-элемент управления и связывается с ресурсом, идентифицируемым *двресид*.

Этот метод дает тот же результат, что и вызов:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

См. раздел [CAxWindow2T:: креатеконтроллик](../../atl/reference/caxwindow2t-class.md#createcontrollic) для создания, инициализации и размещения лицензированного элемента управления ActiveX.

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) `CreateControl` .

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a> Каксвиндов:: Креатеконтролекс

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- Идентификатор ProgID, например `"MSCAL.Calendar.7"`

- CLSID, например `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL-адрес, например `"<https://www.microsoft.com>"`

- Ссылка на активный документ, например `"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML-кода, например `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. На платформах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE Embedded Platforms, кроме Windows Mobile с поддержкой CE IE, поддерживают все типы, включая ProgID, CLSID, URL-адрес, ссылку на активный документ и фрагмент кода HTML.

*пстреам*<br/>
окне Указатель на поток, используемый для инициализации свойств элемента управления. Может иметь значение NULL.

*ппункконтаинер*<br/>
заполняет Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*ппункконтрол*<br/>
заполняет Адрес указателя, который получит `IUnknown` элемент управления. Может иметь значение NULL.

*иидсинк*<br/>
окне Идентификатор интерфейса для исходящего интерфейса в автономном объекте. Можно IID_NULL.

*пунксинк*<br/>
окне Указатель на `IUnknown` интерфейс объекта приемника, который должен быть подключен к точке подключения в содержащемся объекте, указанном параметром *иидсинк*.

*двресид*<br/>
окне Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод аналогичен [каксвиндов:: CreateControl](#createcontrol), но в отличие от этого метода, `CreateControlEx` также позволяет получить указатель интерфейса на только что созданном элементе управления и настроить приемник событий для получения событий, инициированных элементом управления.

См. раздел [CAxWindow2T:: креатеконтроллицекс](../../atl/reference/caxwindow2t-class.md#createcontrollicex) для создания, инициализации и размещения лицензированного элемента управления ActiveX.

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) `CreateControlEx` .

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a> Каксвиндов:: Жетвндкласснаме

Извлекает имя класса окна.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окна, в котором могут размещаться нелицензированные элементы управления ActiveX.

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a> Каксвиндов::operator=

Присваивает HWND существующему `CAxWindow` объекту.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект `CAxWindow`.

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a> Каксвиндов:: Куериконтрол

Извлекает указанный интерфейс размещенного элемента управления.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Указывает идентификатор IID интерфейса элемента управления.

*ппунк*<br/>
заполняет Указатель на интерфейс элемента управления. В версии шаблона этого метода нет необходимости указывать идентификатор ссылки при условии, что передан типизированный интерфейс со связанным UUID.

*Формате*<br/>
окне Интерфейс, для которого выполняется запрос.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a> Каксвиндов:: Куерихост

Возвращает указанный интерфейс узла.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Указывает идентификатор IID интерфейса элемента управления.

*ппунк*<br/>
заполняет Указатель на интерфейс на узле. В версии шаблона этого метода нет необходимости указывать идентификатор ссылки при условии, что передан типизированный интерфейс со связанным UUID.

*Формате*<br/>
окне Интерфейс, для которого выполняется запрос.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Интерфейс узла предоставляет доступ к базовым функциональным возможностям кода, реализованного в `AxWin` .

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> Каксвиндов:: Сетекстерналдиспатч

Задает внешний интерфейс диспетчеризации для `CAxWindow` объекта.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
окне Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> Каксвиндов:: Сетекстерналуихандлер

Задает внешний интерфейс [идочостуихандлердиспатч](../../atl/reference/idochostuihandlerdispatch-interface.md) для `CAxWindow` объекта.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Параметры

*пуихандлер*<br/>
окне Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Внешний `IDocHostUIHandlerDispatch` интерфейс используется элементами управления, которые запрашивают интерфейс узла узла `IDocHostUIHandlerDispatch` . Элемент управления WebBrowser — это один из элементов управления, который делает это.

## <a name="see-also"></a>См. также раздел

[Пример АТЛКОН](../../overview/visual-cpp-samples.md)<br/>
[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Основные сведения о составном элементе управления](../../atl/atl-composite-control-fundamentals.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)
