---
title: Класс CTabCtrl
ms.date: 11/04/2016
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
ms.openlocfilehash: 42d4b24222b1760bc418e904881edb2bb0e5a1f4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752310"
---
# <a name="ctabctrl-class"></a>Класс CTabCtrl

Предоставляет функциональные возможности стандартного элемента управления "вкладка" Windows.

## <a name="syntax"></a>Синтаксис

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTabCtrl:CTabCtrl](#ctabctrl)|Формирует объект `CTabCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTabCtrl:AdjustRect](#adjustrect)|Вычисляет область отображения элементауправления вкладки с учетом прямоугольника окна или вычисляет прямоугольник окна, который соответствовал бы заданной области дисплея.|
|[CTabCtrl::Создание](#create)|Создает элементуправления вкладки и прикрепляет его к экземпляру `CTabCtrl` объекта.|
|[CTabCtrl::CreateEx](#createex)|Создает управление вкладками с указанными расширенными стилями Windows `CTabCtrl` и прикрепляет его к экземпляру объекта.|
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы из управления вкладками.|
|[CTabCtrl::DeleteItem](#deleteitem)|Удаляет элемент из управления вкладками.|
|[CTabCtrl::DeselectAll](#deselectall)|Сбросэлементо элементы в элементы управления вкладками, очистив все, что было нажато.|
|[CTabCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления вкладкой.|
|[CTabCtrl:GetCurFocus](#getcurfocus)|Извлекает вкладку с текущим фокусом управления вкладкой.|
|[CTabCtrl:GetCurSel](#getcursel)|Определяет выбранную в настоящее время вкладку в элементаре вкладки.|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые в настоящее время используются для управления вкладками.|
|[CTabCtrl:GetImageList](#getimagelist)|Извлекает список изображений, связанный с управлением вкладками.|
|[CTabCtrl:GetItem](#getitem)|Извлекает информацию о вкладке в элемента речку.|
|[CTabCtrl:GetItemCount](#getitemcount)|Извлекает число вкладок в наборе вкладок.|
|[CTabCtrl:GetItemRect](#getitemrect)|Извлекает прямоугольник для вкладки в элементаре управления вкладкой.|
|[CTabCtrl:GetItemState](#getitemstate)|Извлекает состояние указанного элемента управления вкладками.|
|[CTabCtrl:GetRowCount](#getrowcount)|Извлекает текущее количество строк вкладок в элемента речку.|
|[CTabCtrl::GetToolTips](#gettooltips)|Извлекает ручку управления наконечником инструмента, связанного с управлением вкладкой.|
|[CTabCtrl::HighlightItem](#highlightitem)|Устанавливает состояние выделения элемента вкладки.|
|[CTabCtrl::HitTest](#hittest)|Определяет, какая вкладка, если она имеется, находится в определенном положении экрана.|
|[CTabCtrl::InsertItem](#insertitem)|Вставляет новую вкладку в управление вкладки.|
|[CTabCtrl::RemoveImage](#removeimage)|Удаляет изображение из списка изображений управления вкладками.|
|[CTabCtrl::SetCurFocus](#setcurfocus)|Устанавливает фокус на заданную вкладку в элементаре управления вкладкой.|
|[CTabCtrl::SetCurSel](#setcursel)|Выбирает вкладку в элементаре управления вкладками.|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Устанавливает расширенные стили для управления вкладками.|
|[CTabCtrl:SetImageList](#setimagelist)|Присваивает список изображений элементу управления вкладками.|
|[CTabCtrl:SetItem](#setitem)|Устанавливает некоторые или все атрибуты вкладки.|
|[CTabCtrl::SetItemExtra](#setitemextra)|Устанавливает количество байтов на вкладку, зарезервированное для данных, определяемых приложением, в элементаре управления вкладками.|
|[CTabCtrl:SetItemSize](#setitemsize)|Устанавливает ширину и высоту элемента.|
|[CTabCtrl:SetItemState](#setitemstate)|Устанавливает состояние указанного элемента управления вкладками.|
|[CTabCtrl:SetMinTabWidth](#setmintabwidth)|Устанавливает минимальную ширину элементов в элементах управления вкладками.|
|[CTabCtrl:SetPadding](#setpadding)|Устанавливает количество пространства (обивка) вокруг значка каждой вкладки и метки в управлении вкладкой.|
|[CTabCtrl::SetToolTips](#settooltips)|Назначает управление наконечником инструмента для управления вкладкой.|

## <a name="remarks"></a>Примечания

"Управление вкладками" аналогично разделителям в блокноте или этикеткам в файловом кабинете. С помощью элемента управления "Вкладка" приложение может определить несколько страниц для одной области окна или диалогового окна. Каждая страница состоит из набора информации или группы элементов управления, которые приложение отображает, когда пользователь выбирает соответствующую вкладку. Особый тип управления вкладками отображает вкладки, которые выглядят как кнопки. Нажатие на кнопку должно немедленно выполнить команду, а не отображать страницу.

Этот элемент управления `CTabCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Для получения дополнительной `CTabCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CTabCtrl](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl:AdjustRect

Вычисляет область отображения элементауправления вкладки с учетом прямоугольника окна или вычисляет прямоугольник окна, который соответствовал бы заданной области дисплея.

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*bLarger*<br/>
Указывает, какую операцию выполнять. Если этот параметр является истинным, *lpRect* определяет прямоугольник дисплея и получает соответствующий прямоугольник окна. Если этот параметр FALSE, *lpRect* определяет прямоугольник окна и получает соответствующий прямоугольник дисплея.

*lpRect*<br/>
Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая определяет данный прямоугольник и получает вычисленный прямоугольник.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a>CTabCtrl::Создание

Создает элементуправления вкладки и прикрепляет его к экземпляру `CTabCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления вкладками. Примените любую комбинацию [стилей управления вкладками,](/windows/win32/Controls/tab-control-styles)описанную в SDK Windows. Смотрите **Примечания** для списка стилей окон, которые также можно применить к элементу управления.

*rect*<br/>
Определяет размер и положение управления вкладками. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно управления вкладки, `CDialog`обычно . Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор элемента управления вкладками.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если инициализация объекта была успешной; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вы строите `CTabCtrl` объект в два этапа. Сначала позвоните в конструктор, `Create`а затем вызов, который создает управление `CTabCtrl` вкладкой и прикрепляет его к объекту.

В дополнение к стилям управления вкладками можно применить следующие стили окнов к управлению вкладками:

- WS_CHILD создает окно ребенка, представляющее элемент управления вкладками. Не может быть использован с WS_POPUP стилем.

- WS_VISIBLE создает элементуправления вкладок, который изначально виден.

- WS_DISABLED создает окно, которое изначально отключено.

- WS_GROUP определяет первый элемент управления группой элементов управления, в котором пользователь может перемещаться от одного элемента управления к другому со клавишами стрелки. Все элементы управления, определяемые со стилем WS_GROUP после первого элемента управления принадлежат одной и той же группе. Следующий элемент управления со стилем WS_GROUP завершает группу стилей и запускает следующую группу (т.е. одна группа заканчивается там, где начинается следующая).

- WS_TABSTOP определяет один из любого количества элементов управления, с помощью которых пользователь может перемещаться с помощью ключа TAB. Ключ TAB перемещает пользователя к следующему элементу управления, указанному WS_TABSTOP стилем.

Чтобы создать управление вкладками с расширенными стилями окон, позвоните [cTabCtrl::CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::CreateEx

Создает элемент управления (детское окно) и `CTabCtrl` связывает его с объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет стиль управления вкладками. Примените любую комбинацию [стилей управления вкладками,](/windows/win32/Controls/tab-control-styles)описанную в SDK Windows. Смотрите **Примечания** в [Создании](#create) для списка стилей окна, которые вы также можете применить к элементу управления.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно в противном случае 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

`CreateEx`создает элемент управления с расширенными стилями Windows, указанными *dwExStyle.* Установите расширенные стили, характерные для элемента управления с помощью [SetExtendedStyle.](#setextendedstyle) Например, `CreateEx` использовать для установки таких `SetExtendedStyle` стилей, как WS_EX_CONTEXTHELP, но использовать для установки таких стилей, как TCS_EX_FLATSEPARATORS. Для получения дополнительной информации смотрите стили, описанные в [расширенных стилях управления вкладками](/windows/win32/Controls/tab-control-extended-styles) в Windows SDK.

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl:CTabCtrl

Формирует объект `CTabCtrl`.

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::DeleteAllItems

Удаляет все элементы из управления вкладками.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::DeleteItem

Удаляет указанный элемент из элемента управления вкладками.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Нулевая стоимость элемента для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::DeselectAll

Сбросэлементо элементы в элементы управления вкладками, очистив все, что было нажато.

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Параметры

*fExcludeFocus*<br/>
Пометить область деотбора товара. Если этот параметр установлен на FALSE, все кнопки вкладок будут сбросить. Если он установлен на ИСТИНу, то все элементы вкладки, за исключением одного в настоящее время выбраны будут сбросить.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32, [TCM_DESELECTALL,](/windows/win32/Controls/tcm-deselectall)как описано в SDK Windows.

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::DrawItem

Вызывается фреймворком при изменении визуального аспекта управления вкладкой владельца-рисования.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) описывающую элемент, который будет окрашен.

### <a name="remarks"></a>Примечания

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию элемента для `CTabCtrl` реализации чертежа для объекта владельца-рисования.

Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемые в *lpDrawItemStruct,* прежде чем эта функция участника прекратится.

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl:GetCurFocus

Извлекает индекс вкладки с текущим фокусом.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс вкладки с нулевым уровнем с текущим фокусом.

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl:GetCurSel

Извлекает выбранную в настоящее время вкладку в элемент управления вкладками.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс выбранной вкладки в случае успеха или - 1, если не выбрана вкладка.

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle

Извлекает расширенные стили, которые в настоящее время используются для управления вкладками.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Представляет расширенные стили, которые в настоящее время используются для управления вкладками. Это значение представляет собой сочетание [расширенных стилей управления вкладками,](/windows/win32/Controls/tab-control-extended-styles)как описано в SDK Windows.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_GETEXTENDEDSTYLE,](/windows/win32/Controls/tcm-getextendedstyle)как описано в SDK Windows.

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl:GetImageList

Извлекает список изображений, связанный с управлением вкладками.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на список изображений управления вкладкой; в противном случае, NULL.

## <a name="ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl:GetItem

Извлекает информацию о вкладке в элемента речку.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Нулевой индекс вкладки.

*pTabCtrlItem*<br/>
Указатель на структуру [TCITEM,](/windows/win32/api/commctrl/ns-commctrl-tcitemw) используемый для определения информации для извлечения. Также используется для получения информации о вкладке. Эта структура используется `InsertItem`с `GetItem`функциями , и `SetItem` функциями члена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха; FALSE в противном случае.

### <a name="remarks"></a>Примечания

При отправке сообщения `mask` участник указывает, какие атрибуты должны вернуться. Если `mask` участник указывает значение TCIF_TEXT, `pszText` участник должен содержать адрес буфера, который получает `cchTextMax` текст элемента, и участник должен указать размер буфера.

- `mask`

   Значение, определяющее, какие `TCITEM` структуры члены для извлечения или установки. Этот участник может быть нулевым или комбинацией следующих значений:

  - TCIF_TEXT `pszText` Участник действителен.

  - TCIF_IMAGE `iImage` Участник действителен.

  - TCIF_PARAM `lParam` Участник действителен.

  - TCIF_RTLREADING Текст `pszText` отображается с использованием правого ордера на чтение на иврите или арабском языке.

  - TCIF_STATE `dwState` Участник действителен.

- `pszText`

   Указатель на нулевую строку, содержащую текст вкладки, если структура содержит информацию о вкладке. Если структура получает информацию, этот участник указывает адрес буфера, который получает текст вкладки.

- `cchTextMax`

   Размер буфера, на `pszText`который указывает . Этот участник игнорируется, если структура не получает информацию.

- `iImage`Индекс в список изображений управления вкладкой, или - 1, если нет изображения для вкладки.

- `lParam`

   Данные, связанные с вкладкой, определяемые приложением. Если на вкладку имеется более четырех байтов данных, определяемых `TCITEM` приложением, приложение должно определить структуру и использовать ее вместо структуры. Первым членом структуры, определяемой приложением, должна быть структура [TCITEMHEADER.](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw) Структура `TCITEMHEADER` идентична `TCITEM` структуре, `lParam` но без члена. Разница между размером вашей структуры и `TCITEMHEADER` размером структуры должна равняться количеству дополнительных байтов на вкладку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl:GetItemCount

Извлекает число вкладок в наборе вкладок.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в элементе управления вкладками.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl:GetItemRect

Извлекает прямоугольник для указанной вкладки в элементаре управления вкладкой.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Индекс на нулевой основе элемента вкладки.

*lpRect*<br/>
Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая получает связующий прямоугольник вкладки. Эти координаты используют текущий режим отображения порта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl:GetItemState

Извлекает состояние элемента управления вкладками, идентифицированного *nItem.*

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Номер индекса на нулевом уровне элемента, для которого можно получить информацию о состоянии.

*dwMask*<br/>
Маска уточняет, какой из государственных флагов предмета вернуть. Список значений можно узнать в структуре [TCITEM,](/windows/win32/api/commctrl/ns-commctrl-tcitemw) описанном в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение DWORD, получающее государственную информацию. Может использоваться одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладками выбран.|
|TCIS_HIGHLIGHTED|Элемент управления вкладками выделен, а вкладка и текст нарисованы с использованием текущего цвета выделения. При использовании цвета выделения, это будет истинная интерполяция, а не смягченный цвет.|

### <a name="remarks"></a>Примечания

Состояние элемента определяется `dwState` членом `TCITEM` структуры.

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a>CTabCtrl:GetRowCount

Извлекает текущее количество строк в элементуправления вкладок.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество строк вкладок в управлении вкладками.

### <a name="remarks"></a>Примечания

Только элементы управления вкладками, которые имеют TCS_MULTILINE стиль может иметь несколько строк вкладок.

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::GetToolTips

Извлекает ручку управления наконечником инструмента, связанного с управлением вкладкой.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка управления наконечником инструмента в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Управление вкладками создает управление наконечником инструмента, если он имеет TCS_TOOLTIPS стиль. Вы также можете назначить управление наконечником инструмента `SetToolTips` для управления вкладкой с помощью функции члена.

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::HighlightItem

Устанавливает состояние выделения элемента вкладки.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*idItem*<br/>
Нулевой индекс элемента управления вкладками.

*fHighlight*<br/>
Значение, определяющее состояние выделения, подающееся установлению. Если это значение соответствует действительности, вкладка выделена; если FALSE, вкладка установлена в состоянии по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует сообщение Win32 [TCM_HIGHLIGHTITEM,](/windows/win32/Controls/tcm-highlightitem)как описано в SDK Windows.

## <a name="ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::HitTest

Определяет, какая вкладка, если она имеется, находится в указанном положении экрана.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Параметры

*pHitTestInfo*<br/>
Указатель на структуру [TCHITTESTINFO,](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) как описано в Windows SDK, который определяет положение экрана для тестирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает нулевой индекс вкладки или - 1, если вкладка не находится в указанном положении.

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a>CTabCtrl::InsertItem

Вставляет новую вкладку в существующий элемент управления вкладками.

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Индекс новой вкладки на нулевой основе.

*pTabCtrlItem*<br/>
Указатель на структуру [TCITEM,](/windows/win32/api/commctrl/ns-commctrl-tcitemw) которая определяет атрибуты вкладки.

*lpszItem*<br/>
Адрес строки с нулевым завершением, содержащей текст вкладки.

*nИзображение*<br/>
Индекс изображения с нулевым уровнем, вставляемый из списка изображений.

*nМаск*<br/>
Определяет, какие `TCITEM` атрибуты структуры установить. Может быть ноль или комбинация следующих значений:

- TCIF_TEXT `pszText` Участник действителен.

- TCIF_IMAGE `iImage` Участник действителен.

- TCIF_PARAM член *lParam* действителен.

- TCIF_RTLREADING Текст `pszText` отображается с использованием правого ордера на чтение на иврите или арабском языке.

- TCIF_STATE член *dwState* действителен.

*lParam*<br/>
Данные, связанные с вкладкой, определяемые приложением.

*dwState*<br/>
Определяет значения для состояний элемента. Для получения дополнительной информации [см.](/windows/win32/api/commctrl/ns-commctrl-tcitemw)

*dwStateMask*<br/>
Определяет, какие состояния должны быть установлены. Для получения дополнительной информации [см.](/windows/win32/api/commctrl/ns-commctrl-tcitemw)

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс новой вкладки в случае успеха; в противном случае - 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::RemoveImage

Удаляет указанное изображение из списка изображений элемента управления вкладками.

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения для удаления.

### <a name="remarks"></a>Примечания

Управление вкладкой обновляет индекс изображения каждой вкладки, чтобы каждая вкладка оставалась связанной с тем же изображением.

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::SetCurFocus

Устанавливает фокус на заданную вкладку в элементаре управления вкладкой.

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Определяет индекс вкладки, которая получает фокус.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_SETCURFOCUS,](/windows/win32/Controls/tcm-setcurfocus)как описано в SDK Windows.

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::SetCurSel

Выбирает вкладку в элементаре управления вкладками.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Нулевой индекс выбранного элемента.

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс ранее выбранной вкладки в случае успеха, в противном случае - 1.

### <a name="remarks"></a>Примечания

Управление вкладкой не отправляет сообщение TCN_SELCHANGING или TCN_SELCHANGE уведомления при выборе вкладки с помощью этой функции. Эти уведомления отправляются, используя WM_NOTIFY, когда пользователь нажимает или использует клавиатуру для изменения вкладок.

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle

Устанавливает расширенные стили для управления вкладками.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Параметры

*dwNewStyle*<br/>
Значение, определяющее комбинацию расширенных стилей управления вкладками.

*dwExМаск*<br/>
Значение DWORD, которое указывает, какие стили в *dwNewStyle* должны быть затронуты. Только расширенные стили в *dwExMask* будут изменены. Все остальные стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в *dwNewStyle* будут затронуты.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее предыдущие [расширенные стили управления вкладками,](/windows/win32/Controls/tab-control-extended-styles)как описано в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Эта функция члена реализует поведение сообщения Win32 [TCM_SETEXTENDEDSTYLE,](/windows/win32/Controls/tcm-setextendedstyle)как описано в SDK Windows.

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl:SetImageList

Присваивает список изображений элементу управления вкладками.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на список изображений, который будет назначен элементу управления вкладки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в предыдущий список изображений или NULL, если нет предыдущего списка изображений.

## <a name="ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl:SetItem

Устанавливает некоторые или все атрибуты вкладки.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Нулевой индекс элемента.

*pTabCtrlItem*<br/>
Указатель на структуру [TCITEM,](/windows/win32/api/commctrl/ns-commctrl-tcitemw) содержащую новые атрибуты элемента. Участник `mask` определяет, какие атрибуты установить. Если `mask` участник указывает TCIF_TEXT значение, `pszText` участник является адресом строки с нулевым `cchTextMax` завершением, а участник игнорируется.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [GetItem](#getitem).

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::SetItemExtra

Устанавливает количество байтов на вкладку, зарезервированное для данных, определяемых приложением, в элементаре управления вкладками.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Количество дополнительных байтов для установки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_SETITEMEXTRA,](/windows/win32/Controls/tcm-setitemextra)как описано в SDK Windows.

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl:SetItemSize

Задает ширину и высоту элементов набора вкладок.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Новая ширина и высота (в пикселях) элементов набора вкладок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает старую ширину и высоту элементов набора вкладок.

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl:SetItemState

Устанавливает состояние элемента управления вкладками, идентифицированного *nItem.*

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Номер индекса на нулевом уровне элемента, для которого можно установить информацию о состоянии.

*dwMask*<br/>
Маска, уточняющая, какой из государственных флагов элемента установить. Список значений можно узнать в структуре [TCITEM,](/windows/win32/api/commctrl/ns-commctrl-tcitemw) описанном в SDK Windows.

*dwState*<br/>
Ссылка на значение DWORD, содержащее государственную информацию. Может использоваться одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладками выбран.|
|TCIS_HIGHLIGHTED|Элемент управления вкладками выделен, а вкладка и текст нарисованы с использованием текущего цвета выделения. При использовании цвета выделения, это будет истинная интерполяция, а не смягченный цвет.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl:SetMinTabWidth

Устанавливает минимальную ширину элементов в элементах управления вкладками.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Параметры

*Cx*<br/>
Минимальная ширина, которая будет установлена для элемента управления вкладками. Если этот параметр установлен до -1, элемент управления будет использовать ширину вкладки по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая минимальная ширина вкладок.

### <a name="return-value"></a>Возвращаемое значение

Эта функция члена реализует поведение сообщения Win32 [TCM_SETMINTABWIDTH,](/windows/win32/Controls/tcm-setmintabwidth)как описано в SDK Windows.

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl:SetPadding

Устанавливает количество пространства (обивка) вокруг значка каждой вкладки и метки в управлении вкладкой.

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Устанавливает количество пространства (обивка) вокруг значка каждой вкладки и метки в управлении вкладкой.

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::SetToolTips

Назначает управление наконечником инструмента для управления вкладкой.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Параметры

*pWndTip*<br/>
Ручка управления наконечником инструмента.

### <a name="remarks"></a>Примечания

Вы можете получить контроль наконечника инструмента, связанный `GetToolTips`с управлением вкладкой, сделав звонок.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
