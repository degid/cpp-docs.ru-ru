---
title: Интерфейс Иаксвинамбиентдиспатч
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: a53481a57676b5b4a253a3501d3536e5115907a7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833417"
---
# <a name="iaxwinambientdispatch-interface"></a>Интерфейс Иаксвинамбиентдиспатч

Этот интерфейс предоставляет методы для указания характеристик размещенного элемента управления или контейнера.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu`Свойство указывает, разрешено ли размещенному элементу управления отображать собственное контекстное меню.|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI`Свойство указывает, разрешено ли размещенному элементу управления отображать собственный пользовательский интерфейс.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation`Свойство указывает, будет ли контейнер разрешать активацию без окон.|
|[get_BackColor](#get_backcolor)|`BackColor`Свойство задает цвет фона окружения для контейнера.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` — Это внешнее свойство, которое позволяет элементу управления определить, является ли он элементом управления по умолчанию.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags`Свойство указывает операцию, которая должна быть выполнена в ответ на двойной щелчок.|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags`Свойство определяет возможности пользовательского интерфейса объекта узла.|
|[get_Font](#get_font)|`Font`Свойство задает шрифт окружения контейнера.|
|[get_ForeColor](#get_forecolor)|`ForeColor`Свойство задает цвет переднего плана окружения.|
|[get_LocaleID](#get_localeid)|`LocaleID`Свойство определяет идентификатор локали контейнера.|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect`Свойство окружения указывает, будет ли контейнер отражать сообщения размещаемому элементу управления.|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath`Свойство указывает путь к разделу реестра для параметров пользователя.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles`Свойство окружения позволяет элементу управления определить, должен ли он рисовать себя с маркерами захвата.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching`Внешнее свойство позволяет элементу управления определить, будет ли он нарисован штриховой.|
|[get_UserMode](#get_usermode)|`UserMode`Свойство указывает внешний пользовательский режим контейнера.|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu`Свойство указывает, разрешено ли размещенному элементу управления отображать собственное контекстное меню.|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI`Свойство указывает, разрешено ли размещенному элементу управления отображать собственный пользовательский интерфейс.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation`Свойство указывает, будет ли контейнер разрешать активацию без окон.|
|[put_BackColor](#put_backcolor)|`BackColor`Свойство задает цвет фона окружения для контейнера.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` — Это внешнее свойство, которое позволяет элементу управления определить, является ли он элементом управления по умолчанию.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags`Свойство указывает операцию, которая должна быть выполнена в ответ на двойной щелчок.|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags`Свойство определяет возможности пользовательского интерфейса объекта узла.|
|[put_Font](#put_font)|`Font`Свойство задает шрифт окружения контейнера.|
|[put_ForeColor](#put_forecolor)|`ForeColor`Свойство задает цвет переднего плана окружения.|
|[put_LocaleID](#put_localeid)|`LocaleID`Свойство определяет идентификатор локали контейнера.|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect`Свойство окружения указывает, будет ли контейнер отражать сообщения размещаемому элементу управления.|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath`Свойство указывает путь к разделу реестра для параметров пользователя.|
|[put_UserMode](#put_usermode)|`UserMode`Свойство указывает внешний пользовательский режим контейнера.|

## <a name="remarks"></a>Примечания

Этот интерфейс предоставляется объектами управления ActiveX ATL. Вызовите методы этого интерфейса, чтобы задать свойства окружения, доступные размещаемому элементу управления, или указать другие аспекты поведения контейнера. Чтобы дополнить свойства, предоставляемые `IAxWinAmbientDispatch` , используйте [иаксвинамбиентдиспатчекс](../../atl/reference/iaxwinambientdispatchex-interface.md).

<xref:System.Windows.Forms.AxHost> попытается загрузить сведения о типе `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из typelib, содержащей код.

Если вы связываетесь с ATL90.dll, то **AxHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.

Дополнительные сведения см. [в разделе Размещение элементов управления ActiveX с помощью ATL AxHost](../../atl/hosting-activex-controls-using-atl-axhost.md) .

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в нескольких формах, как показано в таблице ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|описана. idl|
|Библиотека типов|ATL.dll|
|C++|описана.h (также входит в ATLBase.h)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a> Иаксвинамбиентдиспатч:: get_AllowContextMenu

`AllowContextMenu`Свойство указывает, разрешено ли размещенному элементу управления отображать собственное контекстное меню.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*пбалловконтекстмену*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a> Иаксвинамбиентдиспатч:: get_AllowShowUI

`AllowShowUI`Свойство указывает, разрешено ли размещенному элементу управления отображать собственный пользовательский интерфейс.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Параметры

*пбалловшовуи*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a> Иаксвинамбиентдиспатч:: get_AllowWindowlessActivation

`AllowWindowlessActivation`Свойство указывает, будет ли контейнер разрешать активацию без окон.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Параметры

*пбалловвиндовлесс*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a> Иаксвинамбиентдиспатч:: get_BackColor

`BackColor`Свойство задает цвет фона окружения для контейнера.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Параметры

*пклрбаккграунд*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение этого свойства по умолчанию (в зависимости от того, является ли родительский элемент главного окна диалоговым окном или нет).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a> Иаксвинамбиентдиспатч:: get_DisplayAsDefault

`DisplayAsDefault` — Это внешнее свойство, которое позволяет элементу управления определить, является ли он элементом управления по умолчанию.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*пбдисплайасдефаулт*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a> Иаксвинамбиентдиспатч:: get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`Свойство указывает операцию, которая должна быть выполнена в ответ на двойной щелчок.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*пдвдочостдаублекликкфлагс*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a> Иаксвинамбиентдиспатч:: get_DocHostFlags

`DocHostFlags`Свойство определяет возможности пользовательского интерфейса объекта узла.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*пдвдочостфлагс*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a> Иаксвинамбиентдиспатч:: get_Font

`Font`Свойство задает шрифт окружения контейнера.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
заполняет Адрес `IFontDisp` указателя интерфейса, используемого для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт в качестве значения по умолчанию для этого свойства.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a> Иаксвинамбиентдиспатч:: get_ForeColor

`ForeColor`Свойство задает цвет переднего плана окружения.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Параметры

*пклрфореграунд*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует цвет текста системного окна в качестве значения по умолчанию для этого свойства.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a> Иаксвинамбиентдиспатч:: get_LocaleID

`LocaleID`Свойство определяет идентификатор локали контейнера.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Параметры

*плЦидлокалеид*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует языковой стандарт по умолчанию пользователя в качестве значения этого свойства по умолчанию.

С помощью этого метода можно обнаружить внешний LocalID, т. е. LocaleID программы, в которой используется элемент управления. Зная LocaleID, вы можете вызвать код для загрузки заголовков для определенного языкового стандарта, текста сообщения об ошибке и т. д. из файла ресурсов или вспомогательной библиотеки DLL.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a> Иаксвинамбиентдиспатч:: get_MessageReflect

`MessageReflect`Свойство окружения указывает, будет ли контейнер отражать сообщения размещаемому элементу управления.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Параметры

*пбмессажерефлект*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a> Иаксвинамбиентдиспатч:: get_OptionKeyPath

`OptionKeyPath`Свойство указывает путь к разделу реестра для параметров пользователя.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*пбстроптионкэйпас*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a> Иаксвинамбиентдиспатч:: get_ShowGrabHandles

`ShowGrabHandles`Свойство окружения позволяет элементу управления определить, должен ли он рисовать себя с маркерами захвата.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Параметры

*пбшовграбхандлес*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL всегда возвращает VARIANT_FALSE в качестве значения этого свойства.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a> Иаксвинамбиентдиспатч:: get_ShowHatching

`ShowHatching`Внешнее свойство позволяет элементу управления определить, будет ли он нарисован штриховой.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Параметры

*пбшовхатчинг*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL всегда возвращает VARIANT_FALSE в качестве значения этого свойства.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a> Иаксвинамбиентдиспатч:: get_UserMode

`UserMode`Свойство указывает внешний пользовательский режим контейнера.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Параметры

*пбусермоде*<br/>
заполняет Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a> Иаксвинамбиентдиспатч::p ut_AllowContextMenu

`AllowContextMenu`Свойство указывает, разрешено ли размещенному элементу управления отображать собственное контекстное меню.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*балловконтекстмену*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a> Иаксвинамбиентдиспатч::p ut_AllowShowUI

`AllowShowUI`Свойство указывает, разрешено ли размещенному элементу управления отображать собственный пользовательский интерфейс.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Параметры

*балловшовуи*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a> Иаксвинамбиентдиспатч::p ut_AllowWindowlessActivation

`AllowWindowlessActivation`Свойство указывает, будет ли контейнер разрешать активацию без окон.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Параметры

*балловвиндовлесс*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a> Иаксвинамбиентдиспатч::p ut_BackColor

`BackColor`Свойство задает цвет фона окружения для контейнера.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Параметры

*clrBackground*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение этого свойства по умолчанию (в зависимости от того, является ли родительский элемент главного окна диалоговым окном или нет).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a> Иаксвинамбиентдиспатч::p ut_DisplayAsDefault

`DisplayAsDefault` — Это внешнее свойство, которое позволяет элементу управления определить, является ли он элементом управления по умолчанию.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*бдисплайасдефаулт*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a> Иаксвинамбиентдиспатч::p ut_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`Свойство указывает операцию, которая должна быть выполнена в ответ на двойной щелчок.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*двдочостдаублекликкфлагс*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a> Иаксвинамбиентдиспатч::p ut_DocHostFlags

`DocHostFlags`Свойство определяет возможности пользовательского интерфейса объекта узла.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*двдочостфлагс*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a> Иаксвинамбиентдиспатч::p ut_Font

`Font`Свойство задает шрифт окружения контейнера.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт в качестве значения по умолчанию для этого свойства.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a> Иаксвинамбиентдиспатч::p ut_ForeColor

`ForeColor`Свойство задает цвет переднего плана окружения.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Параметры

*клрфореграунд*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует цвет текста системного окна в качестве значения по умолчанию для этого свойства.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a> Иаксвинамбиентдиспатч::p ut_LocaleID

`LocaleID`Свойство определяет идентификатор локали контейнера.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Параметры

*лЦидлокалеид*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует языковой стандарт по умолчанию пользователя в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a> Иаксвинамбиентдиспатч::p ut_MessageReflect

`MessageReflect`Свойство окружения указывает, будет ли контейнер отражать сообщения размещаемому элементу управления.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Параметры

*бмессажерефлект*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a> Иаксвинамбиентдиспатч::p ut_OptionKeyPath

`OptionKeyPath`Свойство указывает путь к разделу реестра для параметров пользователя.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*бстроптионкэйпас*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a> Иаксвинамбиентдиспатч::p ut_UserMode

`UserMode`Свойство указывает внешний пользовательский режим контейнера.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Параметры

*бусермоде*<br/>
окне Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="see-also"></a>См. также раздел

[Интерфейс Иаксвинамбиентдиспатчекс](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[Интерфейс Иаксвинхоствиндов](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[Каксвиндов:: Куерихост](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
