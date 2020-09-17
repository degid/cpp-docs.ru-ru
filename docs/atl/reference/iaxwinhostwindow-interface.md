---
title: Интерфейс Иаксвинхоствиндов
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: 44681b94e0bd1dfd757ebfa19f83074785dd95f5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833378"
---
# <a name="iaxwinhostwindow-interface"></a>Интерфейс Иаксвинхоствиндов

Этот интерфейс предоставляет методы для манипулирования элементом управления и его ведущим объектом.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[аттачконтрол](#attachcontrol)|Присоединяет существующий элемент управления к объекту узла.|
|[CreateControl](#createcontrol)|Создает элемент управления и прикрепляет его к объекту узла.|
|[креатеконтролекс](#createcontrolex)|Создает элемент управления, присоединяет его к объекту узла и при необходимости настраивает обработчик событий.|
|[куериконтрол](#querycontrol)|Возвращает указатель интерфейса на размещенный элемент управления.|
|[сетекстерналдиспатч](#setexternaldispatch)|Задает внешний `IDispatch` интерфейс.|
|[сетекстерналуихандлер](#setexternaluihandler)|Задает внешний `IDocHostUIHandlerDispatch` интерфейс.|

## <a name="remarks"></a>Примечания

Этот интерфейс предоставляется объектами управления ActiveX ATL. Вызывайте методы этого интерфейса, чтобы создать и/или присоединить элемент управления к объекту узла, получить интерфейс из размещенного элемента управления или задать внешний диспетчерский интерфейс или обработчик пользовательского интерфейса для использования при размещении веб-браузера.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|Описана. idl|
|C++|Описана.h (также входит в ATLBase.h)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a> Иаксвинхоствиндов:: Аттачконтрол

Присоединяет существующий (и ранее инициализированный) элемент управления к объекту узла с помощью окна, идентифицируемого *HWND*.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Параметры

*пункконтрол*<br/>
окне Указатель на `IUnknown` интерфейс элемента управления, который должен быть присоединен к объекту узла.

*hWnd*<br/>
окне Маркер окна, который будет использоваться для размещения.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a> Иаксвинхоствиндов:: CreateControl

Создает элемент управления, инициализирует его и размещает его в окне, определяемом *HWND*.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Параметры

*лптриксдата*<br/>
окне Строка, идентифицирующая создаваемый элемент управления. Может быть идентификатором CLSID (должен содержать фигурные скобки), ProgID, URL-адрес или необработанный HTML (с префиксом **MSHTML:**).

*hWnd*<br/>
окне Маркер окна, который будет использоваться для размещения.

*пстреам*<br/>
окне Указатель интерфейса для потока, содержащего данные инициализации для элемента управления. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Это окно будет подклассировать объектом размещения, который предоставляет этот интерфейс, чтобы сообщения могли быть отражены в элементе управления, а другие функции контейнера будут работать.

Вызов этого метода эквивалентен вызову [иаксвинхоствиндов:: креатеконтролекс](#createcontrolex).

Сведения о создании лицензированного элемента управления ActiveX см. в разделе [иаксвинхоствиндовлик:: креатеконтроллик](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a> Иаксвинхоствиндов:: Креатеконтролекс

Создает элемент управления ActiveX, инициализирует его и размещает его в указанном окне аналогично [иаксвинхоствиндов:: CreateControl](#createcontrol).

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>Параметры

*лптриксдата*<br/>
окне Строка, идентифицирующая создаваемый элемент управления. Может быть идентификатором CLSID (должен содержать фигурные скобки), ProgID, URL-адрес или необработанный HTML (с префиксом **MSHTML:**).

*hWnd*<br/>
окне Маркер окна, который будет использоваться для размещения.

*пстреам*<br/>
окне Указатель интерфейса для потока, содержащего данные инициализации для элемента управления. Может иметь значение NULL.

*ппунк*<br/>
заполняет Адрес указателя, который получит `IUnknown` интерфейс созданного элемента управления. Может иметь значение NULL.

*риидадвисе*<br/>
окне Идентификатор интерфейса для исходящего интерфейса в автономном объекте. Можно IID_NULL.

*пункадвисе*<br/>
окне Указатель на `IUnknown` интерфейс объекта приемника, который должен быть подключен к точке подключения в содержащемся объекте, указанном параметром `iidSink` .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

В отличие от `CreateControl` метода, `CreateControlEx` также позволяет получить указатель интерфейса на только что созданном элементе управления и настроить приемник событий для получения событий, инициированных элементом управления.

Сведения о создании лицензированного элемента управления ActiveX см. в разделе [иаксвинхоствиндовлик:: креатеконтроллицекс](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> Иаксвинхоствиндов:: Куериконтрол

Возвращает указанный указатель интерфейса, предоставленный размещенным элементом управления.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
окне Идентификатор интерфейса для запрашиваемого элемента управления.

*ппвобжект*<br/>
заполняет Адрес указателя, который получит указанный интерфейс созданного элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> Иаксвинхоствиндов:: Сетекстерналдиспатч

Задает внешний диспетчерский интерфейс, доступный для вложенных элементов управления с помощью метода [идочостуихандлердиспатч:: External](../../atl/reference/idochostuihandlerdispatch-interface.md) .

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
окне Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> Иаксвинхоствиндов:: Сетекстерналуихандлер

Вызовите эту функцию, чтобы задать внешний интерфейс [идочостуихандлердиспатч](../../atl/reference/idochostuihandlerdispatch-interface.md) для `CAxWindow` объекта.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
окне Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция используется элементами управления (например, элементом управления веб-браузера), которые запрашивают интерфейс узла узла `IDocHostUIHandlerDispatch` .

## <a name="see-also"></a>См. также раздел

[Интерфейс Иаксвинамбиентдиспатч](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[Каксвиндов:: Куерихост](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
