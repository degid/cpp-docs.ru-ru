---
title: CToolTipCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: a4c2644ff7a9b2ae60cc166247d27d7a25305b97
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561847"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

Инкапсулирует функциональность элемента управления "всплывающая подсказка" — небольшого всплывающего окна, в котором отображается одна строка текста, описывающая назначение инструмента в приложении.

## <a name="syntax"></a>Синтаксис

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl:: CToolTipCtrl](#ctooltipctrl)|Формирует объект `CToolTipCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl:: Activate](#activate)|Активирует и деактивирует элемент управления "Подсказка".|
|[CToolTipCtrl:: Аддтул](#addtool)|Регистрирует инструмент с помощью элемента управления "Подсказка".|
|[CToolTipCtrl:: Аджустрект](#adjustrect)|Выполняет преобразование между текстовым экраном элемента управления "Подсказка" и его прямоугольником окна.|
|[CToolTipCtrl:: Create](#create)|Создает элемент управления "всплывающая подсказка" и прикрепляет его к `CToolTipCtrl` объекту.|
|[CToolTipCtrl:: Креатикс](#createex)|Создает элемент управления "всплывающая подсказка" с указанными расширенными стилями Windows и прикрепляет его к `CToolTipCtrl` объекту.|
|[CToolTipCtrl::D Елтул](#deltool)|Удаляет инструмент из элемента управления "Подсказка".|
|[CToolTipCtrl:: Жетбубблесизе](#getbubblesize)|Возвращает размер подсказки.|
|[CToolTipCtrl:: Жеткурренттул](#getcurrenttool)|Извлекает сведения, такие как размер, расположение и текст, из окна подсказки, отображаемого текущим элементом управления ToolTip.|
|[CToolTipCtrl:: Жетделайтиме](#getdelaytime)|Извлекает начальные, всплывающие и повторно отображаемые длительности, которые в настоящий момент задаются для элемента управления "Подсказка".|
|[CToolTipCtrl:: Margin](#getmargin)|Извлекает верхнее, левое, нижнее и правое поля, заданные для окна подсказки.|
|[CToolTipCtrl:: Жетмакстипвидс](#getmaxtipwidth)|Возвращает максимальную ширину окна подсказки.|
|[CToolTipCtrl:: GetText](#gettext)|Извлекает текст, который поддерживается элементом управления "всплывающая подсказка" для инструмента.|
|[CToolTipCtrl:: Жеттипбкколор](#gettipbkcolor)|Извлекает цвет фона в окне подсказки.|
|[CToolTipCtrl:: Жеттиптекстколор](#gettiptextcolor)|Извлекает цвет текста в окне подсказки.|
|[CToolTipCtrl:: наименование](#gettitle)|Извлекает заголовок текущего элемента управления ToolTip.|
|[CToolTipCtrl:: Жеттулкаунт](#gettoolcount)|Извлекает число инструментов, поддерживаемых элементом управления "всплывающая подсказка".|
|[CToolTipCtrl:: Жеттулинфо](#gettoolinfo)|Извлекает сведения о средстве, которые поддерживает элемент управления "всплывающая подсказка".|
|[CToolTipCtrl:: HitTest](#hittest)|Проверяет точку на предмет того, находится ли он в ограничивающем прямоугольнике данного инструмента. В этом случае получает сведения о средстве.|
|[CToolTipCtrl::P Op](#pop)|Удаляет отображаемое окно подсказки из представления.|
|[CToolTipCtrl::P опуп](#popup)|Приводит к отображению текущего элемента управления ToolTip в координатах последнего сообщения мыши.|
|[CToolTipCtrl:: Релайевент](#relayevent)|Передает сообщение мыши элементу управления "всплывающая подсказка" для обработки.|
|[CToolTipCtrl:: Сетделайтиме](#setdelaytime)|Задает начальные, всплывающие и повторно отображаемые длительности элемента управления "Подсказка".|
|[CToolTipCtrl:: Сетмаргин](#setmargin)|Задает верхнее, левое, нижнее и правое поля для окна подсказки.|
|[CToolTipCtrl:: Сетмакстипвидс](#setmaxtipwidth)|Задает максимальную ширину для окна подсказки.|
|[CToolTipCtrl:: Сеттипбкколор](#settipbkcolor)|Задает цвет фона в окне подсказки.|
|[CToolTipCtrl:: Сеттиптекстколор](#settiptextcolor)|Задает цвет текста в окне подсказки.|
|[CToolTipCtrl:: Сеттитле](#settitle)|Добавляет стандартный значок и строку заголовка в подсказку.|
|[CToolTipCtrl:: Сеттулинфо](#settoolinfo)|Задает сведения, которые поддерживаются подсказкой для инструмента.|
|[CToolTipCtrl:: Сеттулрект](#settoolrect)|Задает новый ограничивающий прямоугольник для инструмента.|
|[CToolTipCtrl:: SetWindowTheme](#setwindowtheme)|Задает визуальный стиль окна подсказки для инструмента.|
|[CToolTipCtrl:: Update](#update)|Принудительное перерисовка текущего средства.|
|[CToolTipCtrl:: Упдатетиптекст](#updatetiptext)|Задает текст подсказки для инструмента.|

## <a name="remarks"></a>Примечания

"Инструмент" — это либо окно, например дочернее окно, либо элемент управления, либо определяемая приложением прямоугольная область в клиентской области окна. Всплывающая подсказка скрыта в большинстве случаев, когда пользователь помещает курсор в средство и оставляет его примерно в течение одной половины секунды. Всплывающая подсказка появляется рядом с курсором и исчезает, когда пользователь нажимает кнопку мыши или перемещает курсор за пределы инструмента.

`CToolTipCtrl` предоставляет функциональные возможности для управления начальным временем и длительностью всплывающей подсказки, ширины полей, окружающих текст подсказки, ширину окна всплывающей подсказки, а также цвет фона и текста всплывающей подсказки. Один элемент управления "всплывающая подсказка" может предоставлять сведения для нескольких инструментов.

`CToolTipCtrl`Класс предоставляет функциональные возможности элемента управления Windows Common Tool подсказки. Этот элемент управления (и, следовательно, `CToolTipCtrl` класс) доступен только для программ, работающих под управлением windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Дополнительные сведения о включении подсказок см. [в разделе всплывающие подсказки в Windows, не являющиеся производными от CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

Дополнительные сведения об использовании см `CToolTipCtrl` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CToolTipCtrl](../../mfc/using-ctooltipctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a> CToolTipCtrl:: Activate

Эта функция вызывается для активации или деактивации элемента управления "Подсказка".

```cpp
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Указывает, должен ли элемент управления "всплывающая подсказка" активирован или деактивирован.

### <a name="remarks"></a>Примечания

Если *бактивате* имеет значение true, элемент управления активируется; Если значение равно FALSE, оно деактивируется.

Когда активен элемент управления "Подсказка", сведения о подсказке отображаются, когда курсор находится на средстве, зарегистрированном в элементе управления. Если он неактивен, сведения о подсказке не отображаются, даже если курсор находится на инструменте.

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a> CToolTipCtrl:: Аддтул

Регистрирует инструмент с помощью элемента управления "Подсказка".

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтекст*<br/>
Идентификатор строкового ресурса, содержащего текст для инструмента.

*лпректтул*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , содержащую координаты ограничивающего прямоугольника инструмента. Координаты указываются относительно левого верхнего угла клиентской области окна, идентифицируемого *приводится*.

*нидтул*<br/>
Идентификатор инструмента.

*lpszText*<br/>
Указатель на текст инструмента. Если этот параметр содержит значение LPSTR_TEXTCALLBACK, TTN_NEEDTEXT уведомления переходят к родительскому элементу окна, на которое *приводится* указывает.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Параметры *лпректтул* и *нидтул* должны быть допустимыми, или если *Лпректтул* имеет значение null, *нидтул* должен быть равен 0.

Элемент управления «Подсказка» может быть связан с несколькими инструментами. Эта функция вызывается для регистрации инструмента с элементом управления "Подсказка", чтобы информация, хранящаяся в подсказке, отображалась при наведении курсора на средство.

> [!NOTE]
> Нельзя задать для подсказки статический элемент управления с помощью `AddTool` .

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a> CToolTipCtrl:: Аджустрект

Выполняет преобразование между текстовым прямоугольником, отображаемым в элементе управления ToolTip, и его прямоугольником окна.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Параметры

*лпрк*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , содержащую либо прямоугольник окна подсказки, либо прямоугольник, отображающий текст.

*бларжер*<br/>
Если значение — TRUE, *ЛПРК* используется для указания прямоугольника текста и получает соответствующий прямоугольник окна. Если значение равно FALSE, *ЛПРК* используется для указания прямоугольника окна и получает соответствующий прямоугольник для вывода текста.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если прямоугольник успешно скорректирован; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция-член вычисляет текстовый прямоугольник элемента управления "всплывающая подсказка" на основе прямоугольника окна или прямоугольника окна подсказки, необходимого для вывода указанного текстового прямоугольника.

Эта функция члена реализует поведение сообщения Win32 [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect), как описано в Windows SDK.

## <a name="ctooltipctrlcreate"></a><a name="create"></a> CToolTipCtrl:: Create

Создает элемент управления "всплывающая подсказка" и прикрепляет его к `CToolTipCtrl` объекту.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указывает родительское окно элемента управления "Подсказка", обычно `CDialog` . Оно не должно иметь значение NULL.

*двстиле*<br/>
Задает стиль элемента управления "Подсказка". Дополнительные сведения см. в разделе **"Примечания"** .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если `CToolTipCtrl` объект успешно создан; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Построение создается `CToolTipCtrl` в два этапа. Сначала вызовите конструктор для создания `CToolTipCtrl` объекта, а затем вызовите, `Create` чтобы создать элемент управления подсказки и присоединить его к `CToolTipCtrl` объекту.

Параметр *двстиле* может быть любым сочетанием [стилей окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Кроме того, элемент управления "Подсказка" имеет два стиля, характерных для класса: TTS_ALWAYSTIP и TTS_NOPREFIX.

|Стиль|Значение|
|-----------|-------------|
|TTS_ALWAYSTIP|Указывает, что всплывающая подсказка отображается, когда курсор находится на инструменте, независимо от того, является ли окно-владелец элемента управления подсказки активным или неактивным. Без этого стиля элемент управления "Подсказка" отображается, когда окно владельца инструмента активно, но не в том случае, если оно неактивно.|
|TTS_NOPREFIX|Этот стиль не дорезает систему от удаления символа амперсанда (&) из строки. Если элемент управления "Подсказка" не имеет стиля TTS_NOPREFIX, система автоматически разрезает символы амперсанда, позволяя приложению использовать ту же строку, что и элемент меню, и как текст в элементе управления "Подсказка".|

Элемент управления "всплывающая подсказка" имеет стили окон WS_POPUP и WS_EX_TOOLWINDOW, независимо от того, указываются ли они при создании элемента управления.

Чтобы создать элемент управления "Подсказка" с расширенными стилями Windows, вызовите метод [CToolTipCtrl:: креатикс](#createex) вместо `Create` .

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a> CToolTipCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CToolTipCtrl` объектом.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*двстиле*<br/>
Задает стиль элемента управления "Подсказка". Дополнительные сведения см. в разделе **"Примечания" раздела "** [Создание](#create) ".

*двстиликс*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешное выполнение равно 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо `Create` для применения расширенных стилей Windows, заданных **WS_EX_** в расширенном стиле Windows.

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a> CToolTipCtrl:: CToolTipCtrl

Формирует объект `CToolTipCtrl`.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать `Create` после создания объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a> CToolTipCtrl::D Елтул

Удаляет средство, заданное с помощью *приводится* и *нидтул* , из коллекции средств, поддерживаемых элементом управления "Подсказка".

```cpp
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтул*<br/>
Идентификатор инструмента.

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a> CToolTipCtrl:: Жетбубблесизе

Возвращает размер подсказки.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*лптулинфо*<br/>
Указатель на структуру [тулинфо](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) всплывающей подсказки.

### <a name="return-value"></a>Возвращаемое значение

Размер подсказки.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize), как описано в Windows SDK.

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a> CToolTipCtrl:: Жеткурренттул

Извлекает сведения, такие как размер, расположение и текст, из окна подсказки, отображаемого текущим элементом управления ToolTip.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*лптулинфо*\
заполняет Указатель на структуру [тулинфо](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , которая получает сведения о текущем окне всплывающей подсказки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если данные извлекаются успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода извлекаются сведения о текущем окне всплывающей подсказки.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a> CToolTipCtrl:: Жетделайтиме

Извлекает начальные, всплывающие и повторно отображаемые длительности, заданные для элемента управления "всплывающая подсказка".

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Параметры

*двдуратион*<br/>
Флаг, указывающий, какое значение длительности будет получено. Этот параметр может принимать одно из следующих значений:

- TTDT_AUTOPOP получить период времени, в течение которого окно подсказки остается видимым, если указатель мыши находится в ограничивающем прямоугольнике инструмента.

- TTDT_INITIAL получить период времени, в течение которого указатель должен оставаться на месте в ограничивающем прямоугольнике инструмента перед отображением окна подсказки.

- TTDT_RESHOW получить время, необходимое для последующего отображения окон всплывающих подсказок при переходе указателя с одного инструмента на другое.

### <a name="return-value"></a>Возвращаемое значение

Указанное время задержки в миллисекундах

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime), как описано в Windows SDK.

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a> CToolTipCtrl:: Margin

Извлекает верхнее, левое, нижнее и правое поля, заданные для окна подсказки.

```cpp
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*лпрк*<br/>
Адрес `RECT` структуры, которая получит сведения о полях. Элементы структуры [Rect](/windows/win32/api/windef/ns-windef-rect) не определяют ограничивающий прямоугольник. Для этого сообщения члены структуры интерпретируется следующим образом:

|Участник|Представление|
|------------|--------------------|
|`top`|Расстояние между верхней границей и верхним краем текста подсказки в пикселях.|
|`left`|Расстояние между левой границей и левым концом текста подсказки в пикселях.|
|`bottom`|Расстояние между нижней границей и нижней частью текста подсказки в пикселях.|
|`right`|Расстояние между правой границей и правым концом текста подсказки в пикселях.|

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin), как описано в Windows SDK.

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a> CToolTipCtrl:: Жетмакстипвидс

Возвращает максимальную ширину окна подсказки.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная ширина окна подсказки.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth), как описано в Windows SDK.

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a> CToolTipCtrl:: GetText

Извлекает текст, который поддерживается элементом управления "всплывающая подсказка" для инструмента.

```cpp
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
Ссылка на `CString` объект, который получает текст средства.

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтул*<br/>
Идентификатор инструмента.

### <a name="remarks"></a>Примечания

Параметры *приводится* и *нидтул* указывают средство. Если это средство ранее было зарегистрировано в подсказке с помощью всплывающей подсказки `CToolTipCtrl::AddTool` , то для объекта, на который ссылается параметр *str* , назначается текст инструмента.

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a> CToolTipCtrl:: Жеттипбкколор

Извлекает цвет фона в окне подсказки.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , представляющее цвет фона.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor), как описано в Windows SDK.

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a> CToolTipCtrl:: Жеттиптекстколор

Извлекает цвет текста в окне подсказки.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , представляющее цвет текста.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_GETTIPTEXTCOLOR](/windows/win32/Controls/ttm-gettiptextcolor), как описано в Windows SDK.

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a> CToolTipCtrl:: наименование

Извлекает заголовок текущего элемента управления ToolTip.

```cpp
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Параметры

*пттгт*\
заполняет Указатель на структуру [ттжеттитле](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) , содержащую сведения о элементе управления ToolTip. При возврате из этого метода элемент *псзтитле* структуры [ттжеттитле](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) указывает на текст заголовка.

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) сообщение, описанное в Windows SDK.

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a> CToolTipCtrl:: Жеттулкаунт

Извлекает количество средств, зарегистрированных с помощью элемента управления "Подсказка".

```
int GetToolCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число инструментов, зарегистрированных с помощью элемента управления "Подсказка".

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a> CToolTipCtrl:: Жеттулинфо

Извлекает сведения о средстве, которые поддерживает элемент управления "всплывающая подсказка".

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*тулинфо*<br/>
Ссылка на `TOOLINFO` объект, который получает текст средства.

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтул*<br/>
Идентификатор инструмента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`hwnd`Элементы и `uId` структуры [тулинфо](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , на которые ссылается *ктулинфо* , определяют средство. Если это средство зарегистрировано с помощью всплывающей подсказки, то при предыдущем вызове `AddTool` `TOOLINFO` Структура заполняется сведениями о средстве.

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a> CToolTipCtrl:: HitTest

Проверяет точку, чтобы определить, находится ли она в ограничивающем прямоугольнике данного инструмента, и, если это так, получить сведения о средстве.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее средство.

*пт*<br/>
Указатель на `CPoint` объект, содержащий координаты проверяемой точки.

*лптулинфо*<br/>
Указатель на структуру [тулинфо](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , содержащую сведения об инструменте.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точка, заданная данными проверки попадания, находится внутри ограничивающего прямоугольника инструмента; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если эта функция возвращает ненулевое значение, то структура, на которую указывает *лптулинфо* , заполняется сведениями об инструменте, в котором находится точка.

`TTHITTESTINFO`Структура определяется следующим образом:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Указывает маркер инструмента.

- `pt`

   Задает координаты точки, если точка находится в ограничивающем прямоугольнике инструмента.

- `ti`

   Сведения о средстве. Дополнительные сведения о `TOOLINFO` структуре см. в разделе [CToolTipCtrl:: жеттулинфо](#gettoolinfo).

## <a name="ctooltipctrlpop"></a><a name="pop"></a> CToolTipCtrl::P Op

Удаляет отображаемое окно подсказки из представления.

```cpp
void Pop();
```

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_POP](/windows/win32/Controls/ttm-pop), как описано в Windows SDK.

## <a name="ctooltipctrlpopup"></a><a name="popup"></a> CToolTipCtrl::P опуп

Приводит к отображению текущего элемента управления ToolTip в координатах последнего сообщения мыши.

```cpp
void Popup();
```

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_POPUP](/windows/win32/Controls/ttm-popup) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода отображается окно подсказки.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a> CToolTipCtrl:: Релайевент

Передает сообщение мыши элементу управления "всплывающая подсказка" для обработки.

```cpp
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*лпмсг*<br/>
Указатель на структуру [MSG](/windows/win32/api/winuser/ns-winuser-msg) , содержащую сообщение для ретрансляции.

### <a name="remarks"></a>Примечания

Элемент управления всплывающая подсказка обрабатывает только следующие сообщения, которые отправляются в него `RelayEvent` :

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a> CToolTipCtrl:: Сетделайтиме

Задает время задержки для элемента управления "Подсказка".

```cpp
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Параметры

*нделай*<br/>
Указывает новое время задержки в миллисекундах.

*двдуратион*<br/>
Флаг, указывающий, какое значение длительности будет получено. Описание допустимых значений см. в разделе [CToolTipCtrl:: жетделайтиме](#getdelaytime) .

*iTime*<br/>
Указанное время задержки в миллисекундах.

### <a name="remarks"></a>Примечания

Время задержки — это период времени, в течение которого курсор должен оставаться на инструменте, прежде чем появится окно подсказки. Время задержки по умолчанию составляет 500 миллисекунд.

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a> CToolTipCtrl:: Сетмаргин

Задает верхнее, левое, нижнее и правое поля для окна подсказки.

```cpp
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Параметры

*лпрк*<br/>
Адрес `RECT` структуры, содержащей сведения о полях, которые необходимо задать. Элементы `RECT` структуры не определяют ограничивающий прямоугольник. Описание сведений о марже см. в разделе [CToolTipCtrl:: Margin](#getmargin) .

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin), как описано в Windows SDK.

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a> CToolTipCtrl:: Сетмакстипвидс

Задает максимальную ширину для окна подсказки.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Параметры

*ивидс*<br/>
Максимальная ширина окна подсказки для инструмента.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая максимальная ширина TIP.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth), как описано в Windows SDK.

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a> CToolTipCtrl:: Сеттипбкколор

Задает цвет фона в окне подсказки.

```cpp
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*среду*<br/>
Новый цвет фона.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor), как описано в Windows SDK.

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a> CToolTipCtrl:: Сеттиптекстколор

Задает цвет текста в окне подсказки.

```cpp
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*среду*<br/>
Новый цвет текста.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor), как описано в Windows SDK.

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a> CToolTipCtrl:: Сеттитле

Добавляет стандартный значок и строку заголовка в подсказку.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Параметры

*уикон*<br/>
См. *значок* в [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) в Windows SDK.

*лпстртитле*<br/>
Указатель на строку заголовка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle), как описано в Windows SDK.

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a> CToolTipCtrl:: Сеттулинфо

Задает сведения, которые поддерживаются подсказкой для инструмента.

```cpp
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Параметры

*лптулинфо*<br/>
Указатель на структуру [тулинфо](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , указывающую сведения, которые необходимо задать.

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a> CToolTipCtrl:: Сеттулрект

Задает новый ограничивающий прямоугольник для инструмента.

```cpp
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтул*<br/>
Идентификатор инструмента.

*лпрект*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , указывающую новый ограничивающий прямоугольник.

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a> CToolTipCtrl:: SetWindowTheme

Задает визуальный стиль окна подсказки для инструмента.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*псзсубаппнаме*<br/>
Указатель на строку в Юникоде, содержащую стиль оформления, который необходимо задать.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не используется.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) сообщения, как описано в Windows SDK.

## <a name="ctooltipctrlupdate"></a><a name="update"></a> CToolTipCtrl:: Update

Принудительное перерисовка текущего средства.

```cpp
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a> CToolTipCtrl:: Упдатетиптекст

Обновляет текст подсказки для средств этого элемента управления.

```cpp
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст инструмента.

*Приводится*<br/>
Указатель на окно, содержащее средство.

*нидтул*<br/>
Идентификатор инструмента.

*нидтекст*<br/>
Идентификатор строкового ресурса, содержащего текст для инструмента.

## <a name="see-also"></a>См. также

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBar](../../mfc/reference/ctoolbar-class.md)
