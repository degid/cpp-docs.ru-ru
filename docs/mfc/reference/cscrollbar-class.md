---
title: Класс Кскроллбар
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: 1ab25ad26357abe9091d273637f3ae9f77457342
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230484"
---
# <a name="cscrollbar-class"></a>Класс Кскроллбар

Предоставляет функции элемента управления полосой прокрутки Windows.

## <a name="syntax"></a>Синтаксис

```
class CScrollBar : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кскроллбар:: Кскроллбар](#cscrollbar)|Формирует объект `CScrollBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кскроллбар:: Create](#create)|Создает полосу прокрутки Windows и прикрепляет ее к `CScrollBar` объекту.|
|[Кскроллбар:: Енаблескроллбар](#enablescrollbar)|Включает или выключает одну или обе стрелки полосы прокрутки.|
|[Кскроллбар:: Жетскроллбаринфо](#getscrollbarinfo)|Получает сведения о полосе прокрутки с помощью `SCROLLBARINFO` структуры.|
|[Кскроллбар:: Жетскроллинфо](#getscrollinfo)|Получает сведения о полосе прокрутки.|
|[Кскроллбар:: Жетскролллимит](#getscrolllimit)|Возвращает предельную полосу прокрутки|
|[Кскроллбар:: Жетскроллпос](#getscrollpos)|Извлекает текущее положение ползунка.|
|[Кскроллбар:: Жетскроллранже](#getscrollrange)|Извлекает текущие минимальные и максимальные позиции полосы прокрутки для данной полосы прокрутки.|
|[Кскроллбар:: Сетскроллинфо](#setscrollinfo)|Задает сведения о полосе прокрутки.|
|[Кскроллбар:: Сетскроллпос](#setscrollpos)|Задает текущую точку прокрутки.|
|[Кскроллбар:: Сетскроллранже](#setscrollrange)|Задает для указанной полосы прокрутки положения минимума и максимума.|
|[Кскроллбар:: Шовскроллбар](#showscrollbar)|Показывает или скрывает полосу прокрутки.|

## <a name="remarks"></a>Примечания

Элемент управления "полоса прокрутки" создается в два этапа. Сначала вызовите конструктор `CScrollBar` для создания `CScrollBar` объекта, а затем вызовите функцию [создания](#create) элемента, чтобы создать элемент управления полосы прокрутки Windows и присоединить его к `CScrollBar` объекту.

При создании `CScrollBar` объекта в диалоговом окне (через ресурс диалогового окна) `CScrollBar` автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если `CScrollBar` объект создается в окне, его также может потребоваться уничтожить.

При создании `CScrollBar` объекта в стеке он уничтожается автоматически. При создании `CScrollBar` объекта в куче с помощью **`new`** функции необходимо вызвать **`delete`** для объекта, чтобы удалить его, когда пользователь закрывает полосу прокрутки Windows.

При выделении памяти в `CScrollBar` объекте Переопределите `CScrollBar` деструктор для удаления выделений.

Связанные сведения об использовании см `CScrollBar` . в разделе [элементы управления](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cscrollbarcreate"></a><a name="create"></a>Кскроллбар:: Create

Создает полосу прокрутки Windows и прикрепляет ее к `CScrollBar` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль полосы прокрутки. Примените любое сочетание [стилей полосы прокрутки](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) к полосе прокрутки.

*rect*<br/>
Задает размер и расположение полосы прокрутки. Может быть либо `RECT` структурой, либо `CRect` объектом.

*ппарентвнд*<br/>
Указывает родительское окно полосы прокрутки, обычно `CDialog` объект. Оно не должно иметь значение NULL.

*nID*<br/>
Идентификатор элемента управления полосы прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`CScrollBar`Объект создается в два этапа. Сначала вызовите конструктор, который создает объект, а `CScrollBar` затем вызовите `Create` , создающий и инициализирующий связанную полосу прокрутки окна, и присоединяет ее к `CScrollBar` объекту.

Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к полосе прокрутки:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_GROUP к группам элементов управления

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>Кскроллбар:: Кскроллбар

Формирует объект `CScrollBar`.

```
CScrollBar();
```

### <a name="remarks"></a>Примечания

После создания объекта вызовите `Create` функцию члена, чтобы создать и инициализировать полосу прокрутки Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>Кскроллбар:: Енаблескроллбар

Включает или выключает одну или обе стрелки полосы прокрутки.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Параметры

*нарровфлагс*<br/>
Указывает, включены или отключены стрелки прокрутки и какие стрелки включены или отключены. Этот параметр может принимать одно из следующих значений:

- ESB_ENABLE_BOTH включает обе стрелки полосы прокрутки.

- ESB_DISABLE_LTUP отключает левую стрелку горизонтальной полосы прокрутки или стрелку вверх вертикальной полосы прокрутки.

- ESB_DISABLE_RTDN отключает стрелку вправо на горизонтальной полосе прокрутки или стрелку вниз вертикальной полосы прокрутки.

- ESB_DISABLE_BOTH отключает обе стрелки полосы прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если стрелки включены или отключены, как указано; в противном случае — значение 0, указывающее, что стрелки уже находятся в запрошенном состоянии или произошла ошибка.

### <a name="example"></a>Пример

  См. пример для [кскроллбар:: сетскроллранже](#setscrollrange).

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>Кскроллбар:: Жетскроллбаринфо

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLBARINFO`.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Параметры

*пскроллинфо*<br/>
Указатель на структуру [скроллбаринфо](/windows/win32/api/winuser/ns-winuser-scrollbarinfo) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo) сообщения, как описано в Windows SDK.

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>Кскроллбар:: Жетскроллинфо

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLINFO`.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Параметры

*лпскроллинфо*<br/>
Указатель на структуру [скроллинфо](/windows/win32/api/winuser/ns-winuser-scrollinfo) . Дополнительные сведения об этой структуре см. в Windows SDK.

*нмаск*<br/>
Задает параметры полосы прокрутки для извлечения. Типичное использование, SIF_ALL, задает сочетание SIF_PAGE, SIF_POS, SIF_TRACKPOS и SIF_RANGE. `SCROLLINFO`Дополнительные сведения о значениях нмаск см. в разделе.

### <a name="return-value"></a>Возвращаемое значение

Если сообщение получает какие-либо значения, возвращается значение TRUE. В противном случае — FALSE.

### <a name="remarks"></a>Примечания

`GetScrollInfo`позволяет приложениям использовать 32-разрядные позиции прокрутки.

Структура [скроллинфо](/windows/win32/api/winuser/ns-winuser-scrollinfo) содержит сведения о полосе прокрутки, включая минимальные и максимальные положения прокрутки, размер страницы и положение ползунка (бегунка). `SCROLLINFO`Дополнительные сведения об изменении структуры по умолчанию см. в разделе "структура" в Windows SDK.

Обработчики сообщений Windows MFC, указывающие расположение полосы прокрутки, [CWnd:: Онхскролл и [CWnd:: онвскролл](../../mfc/reference/cwnd-class.md#onvscroll), предоставляют только 16 бит данных о положении. `GetScrollInfo`и `SetScrollInfo` предоставляют 32 бит данных о положении полосы прокрутки. Таким же, приложение может вызвать `GetScrollInfo` во время обработки либо, `CWnd::OnHScroll` `CWnd::OnVScroll` чтобы получить данные о положении полосы прокрутки 32-х бит.

### <a name="example"></a>Пример

  См. пример для [CWnd:: онхскролл](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>Кскроллбар:: Жетскролллимит

Возвращает максимальную точку прокрутки полосы прокрутки.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Возвращаемое значение

Задает максимальную точку полосы прокрутки при успешном выполнении; в противном случае — 0.

### <a name="example"></a>Пример

  См. пример для [CWnd:: онхскролл](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>Кскроллбар:: Жетскроллпос

Извлекает текущее положение ползунка.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Задает текущее расположение поля прокрутки в случае успешного завершения. в противном случае — 0.

### <a name="remarks"></a>Примечания

Текущая величина — это относительное значение, которое зависит от текущего диапазона прокрутки. Например, если диапазон прокрутки находится в диапазоне от 100 до 200, а поле прокрутки находится в середине линейки, текущее расположение равно 150.

### <a name="example"></a>Пример

  См. пример для [CWnd:: онхскролл](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>Кскроллбар:: Жетскроллранже

Копирует текущие минимальное и максимальное позиции полосы прокрутки для заданной полосы прокрутки в расположения, заданные *лпминпос* и *лпмакспос*.

```cpp
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Параметры

*лпминпос*<br/>
Указывает на целочисленную переменную, которая должна принимать минимальную позиции.

*лпмакспос*<br/>
Указывает на целочисленную переменную, которая должна принимать максимальную позиции.

### <a name="remarks"></a>Примечания

Диапазон по умолчанию для элемента управления "полоса прокрутки" пуст (оба значения равны 0).

### <a name="example"></a>Пример

  См. пример для [CWnd:: онхскролл](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>Кскроллбар:: Сетскроллинфо

Задает сведения, которые `SCROLLINFO` хранятся в структуре, о полосе прокрутки.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*лпскроллинфо*<br/>
Указатель на структуру [скроллинфо](/windows/win32/api/winuser/ns-winuser-scrollinfo) .

*bRedraw*<br/>
Указывает, следует ли перерисовать полосу прокрутки для отражения новой информации. Если *бредрав* имеет значение true, полоса прокрутки перерисовывается. Если значение равно FALSE, оно не перерисовывается. По умолчанию полоса прокрутки перерисовывается.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращается значение TRUE. В противном случае — FALSE.

### <a name="remarks"></a>Примечания

Необходимо указать значения, необходимые для `SCROLLINFO` параметров структуры, включая значения флагов.

`SCROLLINFO`Структура содержит сведения о полосе прокрутки, включая минимальные и максимальные положения прокрутки, размер страницы и положение ползунка (бегунка). Дополнительные сведения об изменении структуры по умолчанию см. в разделе [скроллинфо](/windows/win32/api/winuser/ns-winuser-scrollinfo) structure статьи Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>Кскроллбар:: Сетскроллпос

Устанавливает текущую точку полосы прокрутки в значение, заданную параметром *npos* , и, если оно указано, перерисовывает полосу прокрутки, чтобы отразить новую точку.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Задает новое расположение для ползунка. Он должен находиться в пределах диапазона прокрутки.

*bRedraw*<br/>
Указывает, следует ли перерисовать полосу прокрутки для отражения новой позицией. Если *бредрав* имеет значение true, полоса прокрутки перерисовывается. Если значение равно FALSE, оно не перерисовывается. По умолчанию полоса прокрутки перерисовывается.

### <a name="return-value"></a>Возвращаемое значение

Задает предыдущее расположение поля прокрутки в случае успешного завершения. в противном случае — 0.

### <a name="remarks"></a>Примечания

Установите *бредрав* в значение false, когда полоса прокрутки будет перерисована при последующем вызове другой функции, чтобы избежать повторной прорисовки полосы прокрутки в течение короткого интервала.

### <a name="example"></a>Пример

  См. пример для [кскроллбар:: сетскроллранже](#setscrollrange).

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>Кскроллбар:: Сетскроллранже

Задает для указанной полосы прокрутки положения минимума и максимума.

```cpp
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*нминпос*<br/>
Задает минимальную прокрутку.

*нмакспос*<br/>
Задает максимальную точку прокрутки.

*bRedraw*<br/>
Указывает, следует ли перерисовать полосу прокрутки для отражения изменения. Если *бредрав* имеет значение true, полоса прокрутки перерисовывается; Если значение равно FALSE, оно не перерисовывается. По умолчанию он перерисовывается.

### <a name="remarks"></a>Примечания

Задайте для *нминпос* и *нмакспос* значение 0, чтобы скрыть стандартные полосы прокрутки.

Не вызывайте эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.

Если вызов вызывается `SetScrollRange` сразу же после вызова функции- `SetScrollPos` члена, установите *бредрав* в `SetScrollPos` значение 0, чтобы не допустить повторной прорисовки полосы прокрутки дважды.

Разница между значениями, заданными в *нминпос* и *нмакспос* , не должна превышать 32 767. Диапазон по умолчанию для элемента управления "полоса прокрутки" пуст (оба *нминпос* и *нмакспос* равны 0).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>Кскроллбар:: Шовскроллбар

Показывает или скрывает полосу прокрутки.

```cpp
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, отображается ли полоса прокрутки или скрыта. Если этот параметр имеет значение TRUE, отображается полоса прокрутки. в противном случае он скрыт.

### <a name="remarks"></a>Примечания

Приложение не должно вызывать эту функцию для скрытия полосы прокрутки при обработке сообщения уведомления полосы прокрутки.

### <a name="example"></a>Пример

  См. пример для [кскроллбар:: Create](#create).

## <a name="see-also"></a>См. также раздел

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс Кбуттон](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс Кстатик](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
