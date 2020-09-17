---
title: Класс CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: d2440eb05a1367b7d4980494e3d7f5de646d5fd0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562653"
---
# <a name="cstatusbarctrl-class"></a>Класс CStatusBarCtrl

Предоставляет функциональные возможности стандартного элемента управления "индикатор статуса" Windows.

## <a name="syntax"></a>Синтаксис

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStatusBarCtrl:: CStatusBarCtrl](#cstatusbarctrl)|Формирует объект `CStatusBarCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatusBarCtrl:: Create](#create)|Создает элемент управления "строка состояния" и прикрепляет его к `CStatusBarCtrl` объекту.|
|[CStatusBarCtrl:: Креатикс](#createex)|Создает элемент управления "строка состояния" с указанными расширенными стилями Windows и прикрепляет его к `CStatusBarCtrl` объекту.|
|[CStatusBarCtrl::D Равитем](#drawitem)|Вызывается при изменении визуального аспекта элемента управления строки состояния, рисуемого владельцем.|
|[CStatusBarCtrl:: награницы](#getborders)|Извлекает текущие значения ширины горизонтальных и вертикальных границ элемента управления "строка состояния".|
|[CStatusBarCtrl:: "Icon"](#geticon)|Получает значок для части (также известной как область) в текущем элементе управления "строка состояния".|
|[CStatusBarCtrl:: начасти](#getparts)|Извлекает количество частей в элементе управления "строка состояния".|
|[CStatusBarCtrl:: коrect](#getrect)|Извлекает ограничивающий прямоугольник части в элементе управления "строка состояния".|
|[CStatusBarCtrl:: GetText](#gettext)|Извлекает текст из заданной части элемента управления "строка состояния".|
|[CStatusBarCtrl:: Жеттекстленгс](#gettextlength)|Получение длины текста из заданной части строки состояния в символах.|
|[CStatusBarCtrl:: Жеттиптекст](#gettiptext)|Извлекает текст подсказки для панели в строке состояния.|
|[CStatusBarCtrl:: Простое_имя](#issimple)|Проверяет элемент управления окном состояния, чтобы определить, находится ли он в простом режиме.|
|[CStatusBarCtrl:: Сетбкколор](#setbkcolor)|Задает цвет фона в строке состояния.|
|[CStatusBarCtrl:: Сетикон](#seticon)|Задает значок для панели в строке состояния.|
|[CStatusBarCtrl:: Сетминхеигхт](#setminheight)|Задает минимальную высоту области рисования элемента управления "строка состояния".|
|[CStatusBarCtrl:: Сетпартс](#setparts)|Задает количество частей в элементе управления "строка состояния" и координату правого края каждой части.|
|[CStatusBarCtrl:: Сетсимпле](#setsimple)|Указывает, отображает ли элемент управления "строка состояния" простой текст или отображает все элементы управления, заданные предыдущим вызовом метода `SetParts` .|
|[CStatusBarCtrl:: SetText](#settext)|Задает текст в указанной части элемента управления "Строка состояния".|
|[CStatusBarCtrl:: Сеттиптекст](#settiptext)|Задает текст подсказки для панели в строке состояния.|

## <a name="remarks"></a>Примечания

Элемент управления "строка состояния" — это горизонтальное окно, обычно отображаемое в нижней части родительского окна, в котором приложение может отображать различные типы сведений о состоянии. Элемент управления "строка состояния" можно разделить на части, чтобы отобразить более одного типа информации.

Этот элемент управления (и, следовательно, `CStatusBarCtrl` класс) доступен только для программ, работающих под управлением windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Дополнительные сведения об использовании см `CStatusBarCtrl` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a> CStatusBarCtrl:: Create

Создает элемент управления "строка состояния" и прикрепляет его к `CStatusBarCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль элемента управления "строка состояния". Примените любое сочетание стилей элементов управления "строка состояния", перечисленных в списке [общие стили элементов управления](/windows/win32/Controls/common-control-styles) в Windows SDK. Этот параметр должен включать стиль WS_CHILD. Он также должен включать стиль WS_VISIBLE.

*rect*<br/>
Задает размер и расположение элемента управления "строка состояния". Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Задает родительское окно элемента управления "строка состояния", обычно `CDialog` . Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления "строка состояния".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Построение создается `CStatusBarCtrl` в два этапа. Сначала вызовите конструктор, а затем вызов метода `Create` , который создает элемент управления "строка состояния" и присоединяет его к `CStatusBarCtrl` объекту.

Расположение окна состояния по умолчанию находится в нижней части родительского окна, но можно указать стиль CCS_TOP, чтобы он отображался в верхней части клиентской области родительского окна. Можно указать стиль SBARS_SIZEGRIP, чтобы включить захват изменения размера в правой части окна состояния. Не рекомендуется объединять стили CCS_TOP и SBARS_SIZEGRIP, так как полученный захват изменения размера не работает, несмотря на то, что система отображает его в окне состояния.

Чтобы создать строку состояния с расширенными стилями окна, вызовите метод [CStatusBarCtrl:: креатикс](#createex) вместо `Create` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a> CStatusBarCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CStatusBarCtrl` объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двексстиле*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Задает стиль элемента управления "строка состояния". Примените любое сочетание стилей элементов управления "строка состояния", перечисленных в списке [общие стили элементов управления](/windows/win32/Controls/common-control-styles) в Windows SDK. Этот параметр должен включать стиль WS_CHILD. Он также должен включать стиль WS_VISIBLE.

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные стили Windows, заданные **WS_EX_** в расширенном стиле Windows.

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a> CStatusBarCtrl:: CStatusBarCtrl

Формирует объект `CStatusBarCtrl`.

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a> CStatusBarCtrl::D Равитем

Вызывается структурой при изменении визуального аспекта элемента управления "строка состояния", рисуемого владельцем.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Длинный указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , содержащую сведения о типе требуемой прорисовки.

### <a name="remarks"></a>Примечания

`itemAction`Элемент `DRAWITEMSTRUCT` структуры определяет выполняемое действие рисования.

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта, рисуемого владельцем `CStatusBarCtrl` .

Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* , перед завершением этой функции-члена.

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a> CStatusBarCtrl:: награницы

Получает текущую ширину элемента управления "строка состояния" по горизонтальной и вертикальной границам, а также расстояние между прямоугольниками.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Параметры

*пбордерс*<br/>
Адрес целочисленного массива с тремя элементами. Первый элемент получает ширину горизонтальной границы, второй получает ширину вертикальной границы, а третья — ширину границы между прямоугольниками.

*нхорз*<br/>
Ссылка на целое число, получающее ширину горизонтальной границы.

*Бразовать*<br/>
Ссылка на целое число, получающее ширину вертикальной границы.

*нспаЦинг*<br/>
Ссылка на целое число, получающее ширину границы между прямоугольниками.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эти границы определяют интервал между внешним ребром элемента управления и прямоугольниками внутри элемента управления, содержащими текст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a> CStatusBarCtrl:: "Icon"

Получает значок для части (также известной как область) в текущем элементе управления "строка состояния".

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Параметры

*ипарт*\
окне Отсчитываемый от нуля индекс части, содержащей извлекаемый значок. Если этот параметр имеет значение-1, строка состояния считается строкой состояния простого режима.

### <a name="return-value"></a>Возвращаемое значение

Маркер значка, если метод выполнен успешно; в противном случае значение NULL.

### <a name="remarks"></a>Примечания

Этот метод отправляет [SB_GETICON](/windows/win32/Controls/sb-geticon) сообщение, описанное в Windows SDK.

Элемент управления "строка состояния" состоит из строки текстовых областей вывода, которые также называются частями. Дополнительные сведения о строке состояния см. в разделе [Реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Установка режима для объекта CStatusBarCtrl](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_statusBar` которая используется для доступа к текущему элементу управления "строка состояния". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Пример

В следующем примере кода значок копируется на две панели текущего элемента управления "строка состояния". В предыдущем разделе примера кода мы создали элемент управления "строка состояния" с тремя панелями, а затем добавили значок на первую панель. Этот пример извлекает значок из первой панели, а затем добавляет его во вторую и третью панели.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a> CStatusBarCtrl:: начасти

Извлекает количество частей в элементе управления "строка состояния".

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Параметры

*нпартс*<br/>
Число частей, для которых необходимо получить координаты. Если этот параметр больше числа частей в элементе управления, сообщение получает координаты только для существующих частей.

*ппартс*<br/>
Адрес целочисленного массива, имеющего то же количество элементов, что и число частей, заданное параметром *нпартс*. Каждый элемент массива получает клиентскую координату правого края соответствующей части. Если элемент имеет значение-1, то расположение правого края для этой части расширяется до правого края строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Число частей в элементе управления в случае успеха или ноль в противном случае.

### <a name="remarks"></a>Примечания

Эта функция члена также получает координату правого края заданного числа частей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a> CStatusBarCtrl:: коrect

Извлекает ограничивающий прямоугольник части в элементе управления "строка состояния".

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*нпане*<br/>
Отсчитываемый от нуля индекс части, для которой необходимо извлечь ограничивающий прямоугольник.

*лпрект*<br/>
Адрес структуры [Rect](/windows/win32/api/windef/ns-windef-rect) , которая получает ограничивающий прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a> CStatusBarCtrl:: GetText

Извлекает текст из заданной части элемента управления "строка состояния".

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Адрес буфера, который получает текст. Этот параметр является строкой, завершающейся нулем.

*нпане*<br/>
Отсчитываемый от нуля индекс части, из которой требуется получить текст.

*птипе*<br/>
Указатель на целое число, получающее сведения о типе. Тип может иметь одно из следующих значений:

- **0** текст отображается с границей, которая отображается ниже плоскости строки состояния.

- SBT_NOBORDERS текст отображается без границ.

- SBT_POPOUT текст отображается с границей, которая отображается выше плоскости строки состояния.

- SBT_OWNERDRAW если текст имеет SBT_OWNERDRAW тип рисования, *птипе* получает это сообщение и возвращает 32-разрядное значение, связанное с текстом, а не тип операции.

### <a name="return-value"></a>Возвращаемое значение

Длина текста или [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащего текущий текст, в символах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a> CStatusBarCtrl:: Жеттекстленгс

Извлекает длину текста в символах из заданной части элемента управления "строка состояния".

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Параметры

*нпане*<br/>
Отсчитываемый от нуля индекс части, из которой требуется получить текст.

*птипе*<br/>
Указатель на целое число, получающее сведения о типе. Тип может иметь одно из следующих значений:

- **0** текст отображается с границей, которая отображается ниже плоскости строки состояния.

- SBT_NOBORDERS текст отображается без границ.

- SBT_OWNERDRAW текст отображается родительским окном.

- SBT_POPOUT текст отображается с границей, которая отображается выше плоскости строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Длина текста в символах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a> CStatusBarCtrl:: Жеттиптекст

Извлекает текст подсказки для панели в строке состояния.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Параметры

*нпане*<br/>
Отсчитываемый от нуля индекс области строки состояния для получения текста подсказки.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий текст, который будет использоваться в подсказке.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [SB_GETTIPTEXT](/windows/win32/Controls/sb-gettiptext), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a> CStatusBarCtrl:: Простое_имя

Проверяет элемент управления окном состояния, чтобы определить, находится ли он в простом режиме.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления "окно состояния" находится в простом режиме; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [SB_ISSIMPLE](/windows/win32/Controls/sb-issimple), как описано в Windows SDK.

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a> CStatusBarCtrl:: Сетбкколор

Задает цвет фона в строке состояния.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*Кредит*<br/>
Значение COLORREF, указывающее новый цвет фона. Укажите CLR_DEFAULT значение, чтобы строка состояния использовала цвет фона по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , представляющее предыдущий цвет фона по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [SB_SETBKCOLOR](/windows/win32/Controls/sb-setbkcolor), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a> CStatusBarCtrl:: Сетикон

Задает значок для панели в строке состояния.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*нпане*<br/>
Отсчитываемый от нуля индекс области, которая получит значок. Если этот параметр имеет значение-1, строка состояния считается простой строкой состояния.

*hIcon*<br/>
Обрабатываемый значок. Если это значение равно NULL, значок удаляется из части.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [SB_SETICON](/windows/win32/Controls/sb-seticon), как описано в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CStatusBarCtrl:: сетбкколор](#setbkcolor).

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a> CStatusBarCtrl:: Сетминхеигхт

Задает минимальную высоту области рисования элемента управления "строка состояния".

```cpp
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Минимальная высота элемента управления (в пикселях).

### <a name="remarks"></a>Примечания

Минимальная высота — это сумма *nмин.* и вдвое больше ширины (в пикселях) вертикальной границы элемента управления "строка состояния".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a> CStatusBarCtrl:: Сетпартс

Задает количество частей в элементе управления "строка состояния" и координату правого края каждой части.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Параметры

*нпартс*<br/>
Число устанавливаемых частей. Число частей не может быть больше 255.

*пвидсс*<br/>
Адрес целочисленного массива с тем же количеством элементов, что и часть, заданная параметром *нпартс*. Каждый элемент массива задает расположение в координатах клиента правого края соответствующей части. Если элемент имеет значение-1, то расположение правого края для этой части расширяется до правого края элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a> CStatusBarCtrl:: Сетсимпле

Указывает, отображает ли элемент управления "строка состояния" простой текст или отображает все элементы управления, заданные предыдущим вызовом метода [сетпартс](#setparts).

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Параметры

*бсимпле*<br/>
окне Флаг отображаемого типа. Если этот параметр имеет значение TRUE, элемент управления отображает простой текст; Если значение равно FALSE, отображается несколько частей.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Примечания

Если приложение изменяет строку состояния с непростого на простой или наоборот, система немедленно перерисовывает элемент управления.

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a> CStatusBarCtrl:: SetText

Задает текст в указанной части элемента управления "Строка состояния".

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Адрес в виде оканчивающейся нулем строки, в которой указан необходимый текст. Если *nуведомления* имеет значение SBT_OWNERDRAW, *лпсзтекст* представляет 32 бит данных.

*нпане*<br/>
Отсчитываемый от нуля индекс настраиваемой части. Если это значение равно 255, строка состояния считается простым элементом управления, состоящим из одной части.

*nType*<br/>
Тип операции отрисовки. Список возможных значений см. в [SB_SETTEXT сообщении](/windows/win32/Controls/sb-settext) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Сообщение сделает недействительным измененную часть элемента управления, что привело бы к отображению нового текста, когда элемент управления затем получает сообщение WM_PAINT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a> CStatusBarCtrl:: Сеттиптекст

Задает текст подсказки для панели в строке состояния.

```cpp
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*нпане*<br/>
Отсчитываемый от нуля индекс области строки состояния для получения текста подсказки.

*псзтиптекст*<br/>
Указатель на строку, содержащую текст подсказки.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [SB_SETTIPTEXT](/windows/win32/Controls/sb-settiptext), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>См. также

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)
