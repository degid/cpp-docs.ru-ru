---
title: Класс Кстоккпропимпл
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 9d54e4e5c49e73a12fc5d360c3963c2bcf5b2b38
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835588"
---
# <a name="cstockpropimpl-class"></a>Класс Кстоккпропимпл

Этот класс предоставляет методы для поддержки значений стандартных свойств.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <
    class T,
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, реализующий элемент управления и производный от `CStockPropImpl` .

*InterfaceName*<br/>
Сдвоенный интерфейс, предоставляющий стандартные свойства.

*пиид*<br/>
Указатель на идентификатор IID `InterfaceName` .

*плибид*<br/>
Указатель на идентификатор LIBID библиотеки типов, содержащей определение `InterfaceName` .

*вмажор*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*вминор*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*тихкласс*<br/>
Класс, используемый для управления сведениями о типе для *T*. Значение по умолчанию — `CComTypeInfoHolder` .

## <a name="members"></a>Элементы

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[get_Appearance](#get_appearance)|Вызовите этот метод, чтобы получить стиль заливки, используемый элементом управления, например Flat или 3D.|
|[get_AutoSize](#get_autosize)|Вызовите этот метод, чтобы получить состояние флага, указывающего, может ли элемент управления иметь другой размер.|
|[get_BackColor](#get_backcolor)|Вызовите этот метод, чтобы получить цвет фона элемента управления.|
|[get_BackStyle](#get_backstyle)|Вызовите этот метод, чтобы получить стиль фона элемента управления: прозрачный или непрозрачный.|
|[get_BorderColor](#get_bordercolor)|Вызовите этот метод, чтобы получить цвет границы элемента управления.|
|[get_BorderStyle](#get_borderstyle)|Вызовите этот метод, чтобы получить стиль границы элемента управления.|
|[get_BorderVisible](#get_bordervisible)|Вызовите этот метод, чтобы получить состояние флага, указывающего, является ли граница элемента управления видимой.|
|[get_BorderWidth](#get_borderwidth)|Вызовите этот метод, чтобы получить ширину (в пикселях) границы элемента управления.|
|[get_Caption](#get_caption)|Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.|
|[get_DrawMode](#get_drawmode)|Вызовите этот метод, чтобы получить режим рисования элемента управления, например, с помощью пера XOR или инвертирования цветов.|
|[get_DrawStyle](#get_drawstyle)|Вызовите этот метод, чтобы получить стиль отображения элемента управления, например сплошной, пунктирный или пунктирный.|
|[get_DrawWidth](#get_drawwidth)|Вызовите этот метод, чтобы получить ширину отрисовки (в пикселях), используемую методами рисования элемента управления.|
|[get_Enabled](#get_enabled)|Вызовите этот метод, чтобы получить состояние флага, указывающего, включен ли элемент управления.|
|[get_FillColor](#get_fillcolor)|Вызовите этот метод, чтобы получить цвет заливки элемента управления.|
|[get_FillStyle](#get_fillstyle)|Вызывайте этот метод для получения стиля заливки элемента управления, например сплошной, прозрачной или перекрестной штриховки.|
|[get_Font](#get_font)|Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.|
|[get_ForeColor](#get_forecolor)|Вызовите этот метод, чтобы получить цвет переднего плана элемента управления.|
|[get_HWND](#get_hwnd)|Вызовите этот метод, чтобы получить маркер окна, связанный с элементом управления.|
|[get_MouseIcon](#get_mouseicon)|Вызовите этот метод, чтобы получить свойства рисунка изображения (значка, растрового изображения или метафайла), отображаемого при наведении указателя мыши на элемент управления.|
|[get_MousePointer](#get_mousepointer)|Вызывайте этот метод для получения типа указателя мыши, отображаемого при наведении указателя мыши на элемент управления, например стрелка, крест или Песочные часы.|
|[get_Picture](#get_picture)|Вызовите этот метод, чтобы получить указатель на свойства рисунка рисунка (значка, растрового изображения или метафайла), который будет отображаться.|
|[get_ReadyState](#get_readystate)|Вызовите этот метод, чтобы получить состояние готовности элемента управления, например загрузка или загрузка.|
|[get_TabStop](#get_tabstop)|Вызовите этот метод, чтобы получить флаг, указывающий, является ли элемент управления элементом табуляции.|
|[get_Text](#get_text)|Вызовите этот метод, чтобы получить текст, отображаемый с элементом управления.|
|[IsValid](#get_valid)|Вызовите этот метод, чтобы получить состояние флага, указывающего, является ли элемент управления допустимым.|
|[get_Window](#get_window)|Вызовите этот метод, чтобы получить маркер окна, связанный с элементом управления. Идентично [кстоккпропимпл:: get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Вызовите этот метод, чтобы задать стиль заливки, используемый элементом управления, например Flat или 3D.|
|[put_AutoSize](#put_autosize)|Вызовите этот метод, чтобы задать значение флага, которое указывает, не может ли элемент управления иметь другой размер.|
|[put_BackColor](#put_backcolor)|Вызовите этот метод, чтобы задать цвет фона элемента управления.|
|[put_BackStyle](#put_backstyle)|Вызовите этот метод, чтобы задать стиль фона элемента управления.|
|[put_BorderColor](#put_bordercolor)|Вызовите этот метод, чтобы задать цвет границы элемента управления.|
|[put_BorderStyle](#put_borderstyle)|Вызовите этот метод, чтобы задать стиль границы элемента управления.|
|[put_BorderVisible](#put_bordervisible)|Вызовите этот метод, чтобы установить значение флага, определяющего видимость границы элемента управления.|
|[put_BorderWidth](#put_borderwidth)|Вызовите этот метод, чтобы задать ширину границы элемента управления.|
|[put_Caption](#put_caption)|Вызовите этот метод, чтобы задать текст, отображаемый с помощью элемента управления.|
|[put_DrawMode](#put_drawmode)|Вызовите этот метод, чтобы задать режим рисования элемента управления, например, перо XOR или Инверсия цветов.|
|[put_DrawStyle](#put_drawstyle)|Вызовите этот метод, чтобы задать стиль отображения элемента управления, например сплошной, пунктирный или пунктирный.|
|[put_DrawWidth](#put_drawwidth)|Вызовите этот метод, чтобы задать ширину (в пикселях), используемую методами рисования элемента управления.|
|[put_Enabled](#put_enabled)|Вызовите этот метод, чтобы установить флаг, указывающий, включен ли элемент управления.|
|[put_FillColor](#put_fillcolor)|Вызовите этот метод, чтобы задать цвет заливки элемента управления.|
|[put_FillStyle](#put_fillstyle)|Вызывайте этот метод для задания стиля заливки элемента управления, например сплошной, прозрачной или перекрестной штриховки.|
|[put_Font](#put_font)|Вызовите этот метод, чтобы задать свойства шрифта элемента управления.|
|[put_ForeColor](#put_forecolor)|Вызовите этот метод, чтобы задать цвет переднего плана элемента управления.|
|[put_HWND](#put_hwnd)|Этот метод возвращает E_FAIL.|
|[put_MouseIcon](#put_mouseicon)|Вызовите этот метод, чтобы задать свойства рисунка (значок, точечный рисунок или метафайл), отображаемые при наведении указателя мыши на элемент управления.|
|[put_MousePointer](#put_mousepointer)|Вызовите этот метод, чтобы задать тип указателя мыши, отображаемого при наведении указателя мыши на элемент управления, например стрелка, крест или Песочные часы.|
|[put_Picture](#put_picture)|Вызовите этот метод, чтобы задать отображение свойств рисунка рисунка (значка, точечного рисунка или метафайла).|
|[put_ReadyState](#put_readystate)|Вызовите этот метод, чтобы задать состояние готовности элемента управления, например загрузка или загрузка.|
|[put_TabStop](#put_tabstop)|Вызовите этот метод, чтобы установить значение флага, указывающего, является ли элемент управления элементом табуляции или нет.|
|[put_Text](#put_text)|Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.|
|[путвалид](#put_valid)|Вызовите этот метод, чтобы установить флаг, указывающий, является ли элемент управления допустимым.|
|[put_Window](#put_window)|Этот метод вызывает [кстоккпропимпл::p ut_HWND](#put_hwnd), который возвращает E_FAIL.|
|[putref_Font](#putref_font)|Вызовите этот метод, чтобы задать свойства шрифта элемента управления со счетчиком ссылок.|
|[putref_MouseIcon](#putref_mouseicon)|Вызовите этот метод, чтобы задать свойства рисунка (значок, точечный рисунок или метафайл), отображаемые при наведении указателя мыши на элемент управления со счетчиком ссылок.|
|[putref_Picture](#putref_picture)|Вызовите этот метод, чтобы задать отображение свойств рисунка (значка, точечного рисунка или метафайла) со счетчиком ссылок.|

## <a name="remarks"></a>Примечания

`CStockPropImpl` предоставляет методы **размещения** и **получения** для каждого стандартного свойства. Эти методы предоставляют код, необходимый для задания или получения элемента данных, связанного с каждым свойством, а также для уведомления и синхронизации с контейнером при изменении любого свойства.

Visual Studio обеспечивает поддержку стандартных свойств с помощью мастеров. Дополнительные сведения о добавлении свойств запасов в элемент управления см. в [учебнике по ATL](../../atl/active-template-library-atl-tutorial.md).

Для обеспечения обратной совместимости `CStockPropImpl` также предоставляет `get_Window` методы и, `put_Window` которые просто вызывают `get_HWND` и `put_HWND` соответственно. Реализация по умолчанию `put_HWND` возвращает E_FAIL, так как HWND должен быть свойством только для чтения.

Следующие свойства также имеют реализацию **путреф** :

- Шрифт

- маусеикон

- Рисунок

Те же три стандартных свойства должны иметь соответствующие элементы данных типа `CComPtr` или другого класса, обеспечивающего правильный подсчет ссылок на интерфейс с помощью оператора присваивания.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл.h

## <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a> Кстоккпропимпл:: get_Appearance

Вызовите этот метод, чтобы получить стиль заливки, используемый элементом управления, например Flat или 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Параметры

*пнаппеаранце*<br/>
Переменная, которая получает стиль заливки элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a> Кстоккпропимпл:: get_AutoSize

Вызовите этот метод, чтобы получить состояние флага, указывающего, может ли элемент управления иметь другой размер.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Параметры

*пбаутосизе*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления не может быть другим размером.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a> Кстоккпропимпл:: get_BackColor

Вызовите этот метод, чтобы получить цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Параметры

*пклрбаккколор*<br/>
Переменная, которая получает цвет фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a> Кстоккпропимпл:: get_BackStyle

Вызовите этот метод, чтобы получить стиль фона элемента управления: прозрачный или непрозрачный.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Параметры

*пнбаккстиле*<br/>
Переменная, которая получает стиль фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a> Кстоккпропимпл:: get_BorderColor

Вызовите этот метод, чтобы получить цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Параметры

*пклрбордерколор*<br/>
Переменная, которая получает цвет границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a> Кстоккпропимпл:: get_BorderStyle

Вызовите этот метод, чтобы получить стиль границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Параметры

*пнбордерстиле*<br/>
Переменная, которая получает стиль границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a> Кстоккпропимпл:: get_BorderVisible

Вызовите этот метод, чтобы получить состояние флага, указывающего, является ли граница элемента управления видимой.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Параметры

*пббордервисибле*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что граница элемента управления является видимой.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a> Кстоккпропимпл:: get_BorderWidth

Вызовите этот метод, чтобы получить ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Параметры

*пнбордервидс*<br/>
Переменная, которая получает ширину границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_caption"></a><a name="get_caption"></a> Кстоккпропимпл:: get_Caption

Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Параметры

*пбстркаптион*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a> Кстоккпропимпл:: get_DrawMode

Вызовите этот метод, чтобы получить режим рисования элемента управления, например, с помощью пера XOR или инвертирования цветов.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Параметры

*пндравмоде*<br/>
Переменная, получающая режим рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a> Кстоккпропимпл:: get_DrawStyle

Вызовите этот метод, чтобы получить стиль отображения элемента управления, например сплошной, пунктирный или пунктирный.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*пндравстиле*<br/>
Переменная, которая получает стиль отображения элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a> Кстоккпропимпл:: get_DrawWidth

Вызовите этот метод, чтобы получить ширину отрисовки (в пикселях), используемую методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Параметры

*пндраввидс*<br/>
Переменная, которая получает значение ширины элемента управления в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a> Кстоккпропимпл:: get_Enabled

Вызовите этот метод, чтобы получить состояние флага, указывающего, включен ли элемент управления.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Параметры

*пбенаблед*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления включен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a> Кстоккпропимпл:: get_FillColor

Вызовите этот метод, чтобы получить цвет заливки элемента управления.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Параметры

*пклрфиллколор*<br/>
Переменная, которая получает цвет заливки элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a> Кстоккпропимпл:: get_FillStyle

Вызовите этот метод, чтобы получить стиль заливки элемента управления, например "Сплошная", "Прозрачная" или "кросшатчед".

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Параметры

*пнфиллстиле*<br/>
Переменная, которая получает стиль заливки элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_font"></a><a name="get_font"></a> Кстоккпропимпл:: get_Font

Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Параметры

*ппфонт*<br/>
Переменная, которая получает указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a> Кстоккпропимпл:: get_ForeColor

Вызовите этот метод, чтобы получить цвет переднего плана элемента управления.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Параметры

*пклрфореколор*<br/>
Переменная, которая получает цвет переднего плана элементов управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a> Кстоккпропимпл:: get_HWND

Вызовите этот метод, чтобы получить маркер окна, связанный с элементом управления.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*фвнд*<br/>
Маркер окна, связанный с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a> Кстоккпропимпл:: get_MouseIcon

Вызовите этот метод, чтобы получить свойства рисунка изображения (значка, растрового изображения или метафайла), отображаемого при наведении указателя мыши на элемент управления.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*пппиктуре*<br/>
Переменная, которая получает указатель на свойства изображения изображения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a> Кстоккпропимпл:: get_MousePointer

Вызывайте этот метод для получения типа указателя мыши, отображаемого при наведении указателя мыши на элемент управления, например стрелка, крест или Песочные часы.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Параметры

*пнмаусепоинтер*<br/>
Переменная, которая получает тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_picture"></a><a name="get_picture"></a> Кстоккпропимпл:: get_Picture

Вызовите этот метод, чтобы получить указатель на свойства рисунка рисунка (значка, растрового изображения или метафайла), который будет отображаться.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*пппиктуре*<br/>
Переменная, которая получает указатель на свойства изображения. Дополнительные сведения см. в разделе [ипиктуредисп](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a> Кстоккпропимпл:: get_ReadyState

Вызовите этот метод, чтобы получить состояние готовности элемента управления, например загрузка или загрузка.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Параметры

*пнреадистате*<br/>
Переменная, которая получает состояние готовности элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a> Кстоккпропимпл:: get_TabStop

Вызовите этот метод, чтобы получить состояние флага, указывающего, является ли элемент управления элементом табуляции или нет.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Параметры

*пбтабстоп*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления является элементом табуляции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_text"></a><a name="get_text"></a> Кстоккпропимпл:: get_Text

Вызовите этот метод, чтобы получить текст, отображаемый с элементом управления.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Параметры

*пбстртекст*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a> Кстоккпропимпл:: IsValid

Вызовите этот метод, чтобы получить состояние флага, указывающего, является ли элемент управления допустимым.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Параметры

*пбвалид*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления является допустимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplget_window"></a><a name="get_window"></a> Кстоккпропимпл:: get_Window

Вызовите этот метод, чтобы получить маркер окна, связанный с элементом управления. Идентично [кстоккпропимпл:: get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*фвнд*<br/>
Маркер окна, связанный с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a> Кстоккпропимпл::p ut_Appearance

Вызовите этот метод, чтобы задать стиль заливки, используемый элементом управления, например Flat или 3D.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Параметры

*наппеаранце*<br/>
Новый стиль заливки, используемый элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a> Кстоккпропимпл::p ut_AutoSize

Вызовите этот метод, чтобы задать значение флага, которое указывает, не может ли элемент управления иметь другой размер.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Параметры

*баутосизе*<br/>
Значение TRUE, если элемент управления не может быть другим размером.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a> Кстоккпропимпл::p ut_BackColor

Вызовите этот метод, чтобы задать цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Параметры

*клрбаккколор*<br/>
Новый цвет фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a> Кстоккпропимпл::p ut_BackStyle

Вызовите этот метод, чтобы задать стиль фона элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Параметры

*нбаккстиле*<br/>
Новый стиль фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a> Кстоккпропимпл::p ut_BorderColor

Вызовите этот метод, чтобы задать цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Параметры

*клрбордерколор*<br/>
Новый цвет границы. Тип данных OLE_COLOR внутренне представлен как 32-разрядное целое число.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a> Кстоккпропимпл::p ut_BorderStyle

Вызовите этот метод, чтобы задать стиль границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Параметры

*нбордерстиле*<br/>
Новый стиль границы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a> Кстоккпропимпл::p ut_BorderVisible

Вызовите этот метод, чтобы установить значение флага, определяющего видимость границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Параметры

*ббордервисибле*<br/>
Значение TRUE, если граница должна быть видимой.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a> Кстоккпропимпл::p ut_BorderWidth

Вызовите этот метод, чтобы задать ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Параметры

*нбордервидс*<br/>
Новая ширина границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_caption"></a><a name="put_caption"></a> Кстоккпропимпл::p ut_Caption

Вызовите этот метод, чтобы задать текст, отображаемый с помощью элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Параметры

*бстркаптион*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a> Кстоккпропимпл::p ut_DrawMode

Вызовите этот метод, чтобы задать режим рисования элемента управления, например, перо XOR или Инверсия цветов.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Параметры

*ндравмоде*<br/>
Новый режим рисования для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a> Кстоккпропимпл::p ut_DrawStyle

Вызовите этот метод, чтобы задать стиль отображения элемента управления, например сплошной, пунктирный или пунктирный.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*ндравстиле*<br/>
Новый стиль отображения для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a> Кстоккпропимпл::p ut_DrawWidth

Вызовите этот метод, чтобы задать ширину (в пикселях), используемую методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Параметры

*ндраввидс*<br/>
Новая ширина, используемая методами рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a> Кстоккпропимпл::p ut_Enabled

Вызовите этот метод, чтобы установить значение флага, указывающего, включен ли элемент управления.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*бенаблед*<br/>
Значение TRUE, если элемент управления включен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a> Кстоккпропимпл::p ut_FillColor

Вызовите этот метод, чтобы задать цвет заливки элемента управления.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Параметры

*клрфиллколор*<br/>
Новый цвет заливки для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a> Кстоккпропимпл::p ut_FillStyle

Вызывайте этот метод для задания стиля заливки элемента управления, например сплошной, прозрачной или перекрестной штриховки.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Параметры

*нфиллстиле*<br/>
Новый стиль заливки для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_font"></a><a name="put_font"></a> Кстоккпропимпл::p ut_Font

Вызовите этот метод, чтобы задать свойства шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a> Кстоккпропимпл::p ut_ForeColor

Вызовите этот метод, чтобы задать цвет переднего плана элемента управления.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Параметры

*клрфореколор*<br/>
Новый цвет переднего плана элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a> Кстоккпропимпл::p ut_HWND

Этот метод возвращает E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_FAIL.

### <a name="remarks"></a>Примечания

Маркер окна является значением только для чтения.

## <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a> Кстоккпропимпл::p ut_MouseIcon

Вызовите этот метод, чтобы задать свойства рисунка (значок, точечный рисунок или метафайл), отображаемые при наведении указателя мыши на элемент управления.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*ппиктуре*<br/>
Указатель на свойства изображения изображения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a> Кстоккпропимпл::p ut_MousePointer

Вызовите этот метод, чтобы задать тип указателя мыши, отображаемого при наведении указателя мыши на элемент управления, например стрелка, крест или Песочные часы.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Параметры

*нмаусепоинтер*<br/>
Тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_picture"></a><a name="put_picture"></a> Кстоккпропимпл::p ut_Picture

Вызовите этот метод, чтобы задать отображение свойств рисунка рисунка (значка, точечного рисунка или метафайла).

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*ппиктуре*<br/>
Указатель на свойства изображения. Дополнительные сведения см. в разделе [ипиктуредисп](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a> Кстоккпропимпл::p ut_ReadyState

Вызовите этот метод, чтобы задать состояние готовности элемента управления, например загрузка или загрузка.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Параметры

*нреадистате*<br/>
Состояние готовности элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a> Кстоккпропимпл::p ut_TabStop

Вызовите этот метод, чтобы установить флаг, указывающий, является ли элемент управления элементом табуляции или нет.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Параметры

*бтабстоп*<br/>
Значение TRUE, если элемент управления является остановкой табуляции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_text"></a><a name="put_text"></a> Кстоккпропимпл::p ut_Text

Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*бстртекст*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplputvalid"></a><a name="put_valid"></a> Кстоккпропимпл::p утвалид

Вызовите этот метод, чтобы установить флаг, указывающий, является ли элемент управления допустимым.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Параметры

*бвалид*<br/>
Значение TRUE, если элемент управления является допустимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="cstockpropimplput_window"></a><a name="put_window"></a> Кстоккпропимпл::p ut_Window

Этот метод вызывает [кстоккпропимпл::p ut_HWND](#put_hwnd), который возвращает E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Дескриптор окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_FAIL.

### <a name="remarks"></a>Примечания

Маркер окна является значением только для чтения.

## <a name="cstockpropimplputref_font"></a><a name="putref_font"></a> Кстоккпропимпл::p utref_Font

Вызовите этот метод, чтобы задать свойства шрифта элемента управления со счетчиком ссылок.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

То же, что и [кстоккпропимпл::p ut_Font](#put_font), но со счетчиком ссылок.

## <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a> Кстоккпропимпл::p utref_MouseIcon

Вызовите этот метод, чтобы задать свойства рисунка (значок, точечный рисунок или метафайл), отображаемые при наведении указателя мыши на элемент управления со счетчиком ссылок.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*ппиктуре*<br/>
Указатель на свойства изображения изображения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

То же, что и [кстоккпропимпл::p ut_MouseIcon](#put_mouseicon), но со счетчиком ссылок.

## <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a> Кстоккпропимпл::p utref_Picture

Вызовите этот метод, чтобы задать отображение свойств рисунка (значка, точечного рисунка или метафайла) со счетчиком ссылок.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*ппиктуре*<br/>
Указатель на свойства изображения. Дополнительные сведения см. в разделе [ипиктуредисп](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

То же, что и [кстоккпропимпл::p ut_Picture](#put_picture), но со счетчиком ссылок.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)
