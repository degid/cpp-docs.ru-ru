---
title: Класс CListBox
description: Описание класса CListBox MFC и его функций-членов.
ms.date: 01/22/2020
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
ms.openlocfilehash: 30f28db746856303e10709417ad7545376fd4812
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231810"
---
# <a name="clistbox-class"></a>Класс CListBox

Предоставляет функции списка Windows.

## <a name="syntax"></a>Синтаксис

```
class CListBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CListBox:: CListBox](#clistbox)|Формирует объект `CListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CListBox::AddString](#addstring)|Добавляет строку в список.|
|[CListBox:: Чартоитем](#chartoitem)|Переопределите, чтобы обеспечить настраиваемую обработку WM_CHAR для списков, рисуемых владельцем, которые не имеют строк.|
|[CListBox:: Компареитем](#compareitem)|Вызывается платформой для определения позиции нового элемента в списке отсортированных владельцев.|
|[CListBox:: Create](#create)|Создает окно списка Windows и прикрепляет его к `CListBox` объекту.|
|[CListBox::D Елетеитем](#deleteitem)|Вызывается платформой, когда пользователь удаляет элемент из списка, рисуемого владельцем.|
|[CListBox::D Елетестринг](#deletestring)|Удаляет строку из списка.|
|[CListBox::D IR](#dir)|Добавляет имена файлов, дисков или и то, и другое из текущего каталога в поле со списком.|
|[CListBox::D Равитем](#drawitem)|Вызывается структурой при изменении визуального аспекта поля списка, рисуемого владельцем.|
|[CListBox:: FindString](#findstring)|Выполняет поиск строки в поле со списком.|
|[CListBox:: Финдстринжексакт](#findstringexact)|Находит первую строку списка, совпадающую с указанной строкой.|
|[CListBox:: Жетанчориндекс](#getanchorindex)|Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.|
|[CListBox:: Жеткаретиндекс](#getcaretindex)|Определяет индекс элемента, имеющего прямоугольник фокуса в списке с множественным выбором.|
|[CListBox:: NOCOUNT](#getcount)|Возвращает количество строк в поле со списком.|
|[CListBox:: рекурсивно](#getcursel)|Возвращает отсчитываемый от нуля индекс текущей выбранной строки в списке.|
|[CListBox:: Жесоризонталекстент](#gethorizontalextent)|Возвращает ширину в пикселях, в которой окно списка можно прокручивать по горизонтали.|
|[CListBox:: Жетитемдата](#getitemdata)|Возвращает значение, связанное с элементом списка.|
|[CListBox:: Жетитемдатаптр](#getitemdataptr)|Возвращает указатель на элемент списка.|
|[CListBox:: GetItemHeight](#getitemheight)|Определяет высоту элементов в поле со списком.|
|[CListBox:: Жетитемрект](#getitemrect)|Возвращает ограничивающий прямоугольник элемента списка в том виде, в котором он отображается.|
|[CListBox:: Жетлистбоксинфо](#getlistboxinfo)|Возвращает количество элементов на столбец.|
|[CListBox:: onlocal](#getlocale)|Извлекает идентификатор локали для списка.|
|[CListBox:: Жетсел](#getsel)|Возвращает состояние выбора элемента списка.|
|[CListBox:: Жетселкаунт](#getselcount)|Возвращает число строк, выбранных в данный момент в списке с множественным выбором.|
|[CListBox:: Жетселитемс](#getselitems)|Возвращает индексы строк, выбранных в списке в данный момент.|
|[CListBox:: GetText](#gettext)|Копирует элемент списка в буфер.|
|[CListBox:: Жеттекстлен](#gettextlen)|Возвращает длину в байтах элемента списка.|
|[CListBox:: Жеттопиндекс](#gettopindex)|Возвращает индекс первой видимой строки в поле со списком.|
|[CListBox:: Инитстораже](#initstorage)|Предварительно выделяет блоки памяти для элементов списка и строк.|
|[CListBox::InsertString](#insertstring)|Вставляет строку в указанном месте в поле со списком.|
|[CListBox:: Итемфромпоинт](#itemfrompoint)|Возвращает индекс элемента списка, ближайшего к точке.|
|[CListBox:: Меасуреитем](#measureitem)|Вызывается структурой при создании списка, рисуемого владельцем, для определения размеров списка.|
|[CListBox:: Ресетконтент](#resetcontent)|Удаляет все записи из списка.|
|[CListBox:: Селектстринг](#selectstring)|Выполняет поиск и выбирает строку в списке с единственным выбором.|
|[CListBox:: Селитемранже](#selitemrange)|Выбирает или отменяет выбор диапазона строк в списке с множественным выбором.|
|[CListBox:: Сетанчориндекс](#setanchorindex)|Задает привязку в списке с множественным выбором, чтобы начать расширенный выбор.|
|[CListBox:: Сеткаретиндекс](#setcaretindex)|Задает прямоугольник фокуса для элемента по указанному индексу в списке с множественным выбором.|
|[CListBox:: Сетколумнвидс](#setcolumnwidth)|Задает ширину столбца в списке с многостолбцовым списком.|
|[CListBox:: Сеткурсел](#setcursel)|Выбирает строку списка.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину (в пикселях), в которой окно списка можно прокручивать по горизонтали.|
|[CListBox:: Сетитемдата](#setitemdata)|Задает значение, связанное с элементом списка.|
|[CListBox:: Сетитемдатаптр](#setitemdataptr)|Задает указатель на элемент списка.|
|[CListBox:: Сетитемхеигхт](#setitemheight)|Задает высоту элементов в поле со списком.|
|[CListBox:: SetLocale](#setlocale)|Задает идентификатор локали для списка.|
|[CListBox:: Сетсел](#setsel)|Выбирает или отменяет выбор элемента списка в списке с множественным выбором.|
|[CListBox:: Сеттабстопс](#settabstops)|Задает позиции табуляции в поле со списком.|
|[CListBox:: Сеттопиндекс](#settopindex)|Задает отсчитываемый от нуля индекс первой видимой строки в поле со списком.|
|[CListBox:: Вкэйтоитем](#vkeytoitem)|Переопределите, чтобы обеспечить настраиваемую обработку WM_KEYDOWN для списков с набором стилей LBS_WANTKEYBOARDINPUT.|

## <a name="remarks"></a>Примечания

В окне списка отображается список элементов, например имена файлов, которые пользователь может просматривать и выбирать.

В списке с одним выбором пользователь может выбрать только один элемент. В списке с множественным выбором можно выбрать диапазон элементов. Когда пользователь выбирает элемент, он выделяется, и в поле со списком отправляется сообщение уведомления родительскому окну.

Список можно создать либо из шаблона диалогового окна, либо непосредственно в коде. Чтобы создать его напрямую, создайте `CListBox` объект, а затем вызовите функцию [создания](#create) члена, чтобы создать элемент управления списка Windows и присоединить его к `CListBox` объекту. Чтобы использовать список в шаблоне диалогового окна, объявите переменную списка в классе диалогового окна, а затем используйте `DDX_Control` в функции класса диалогового окна, `DoDataExchange` чтобы подключить переменную-член к элементу управления. (это делается автоматически при добавлении управляющей переменной в класс диалогового окна.)

Построение может быть одношаговым процессом в классе, производном от `CListBox` . Напишите конструктор для производного класса и вызовите `Create` его в конструкторе.

Если требуется работать с сообщениями уведомлений Windows, отправленными списком, в родительский список (обычно это класс, производный от класса [CDialog](../../mfc/reference/cdialog-class.md)), добавьте запись схемы сообщения и функцию-член обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

`ON_Notification( id, memberFxn )`

где `id` указывает идентификатор дочернего окна элемента управления "список", отправляющего уведомление, и `memberFxn` является именем родительской функции-члена, написанной для работы с уведомлением.

Прототип родительской функции выглядит следующим образом:

`afx_msg void memberFxn( );`

Ниже приведен список потенциальных записей схемы сообщений и описание вариантов, в которых они будут отправлены родительскому элементу:

- ON_LBN_DBLCLK пользователь дважды щелкает строку в поле со списком. Только поле со списком, имеющее стиль [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) , будет отсылать это сообщение уведомления.

- ON_LBN_ERRSPACE список не может выделить достаточно памяти для удовлетворения запроса.

- ON_LBN_KILLFOCUS поле со списком теряет фокус ввода.

- ON_LBN_SELCANCEL текущий выбор списка отменен. Это сообщение отправляется только в том случае, если у окна списка имеется LBS_NOTIFY стиль.

- ON_LBN_SELCHANGE выбор в списке изменился. Это уведомление не отправляется, если выбор изменяется функцией-членом [CListBox:: сеткурсел](#setcursel) . Это уведомление относится только к списку с LBS_NOTIFY стиле. Сообщение LBN_SELCHANGE уведомления отправляется для списка с множественным выбором каждый раз, когда пользователь нажимает клавишу со стрелкой, даже если выделение не изменяется.

- ON_LBN_SETFOCUS поле списка получает фокус ввода.

- ON_WM_CHARTOITEM список, рисуемый владельцем, который не имеет строк, получает сообщение WM_CHAR.

- ON_WM_VKEYTOITEM поле со списком, LBS_WANTKEYBOARDINPUT стиль получает сообщение WM_KEYDOWN.

При создании `CListBox` объекта в диалоговом окне (через ресурс диалогового окна) `CListBox` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

При создании `CListBox` объекта в окне может потребоваться уничтожить `CListBox` объект. При создании `CListBox` объекта в стеке он уничтожается автоматически. При создании `CListBox` объекта в куче с помощью **`new`** функции необходимо вызвать **`delete`** для объекта, чтобы уничтожить его, когда пользователь закроет родительское окно.

При выделении памяти в `CListBox` объекте Переопределите `CListBox` деструктор, чтобы удалить выделение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>CListBox:: AddString

Добавляет строку в список.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*лпсзитем*<br/>
Указывает на строку, завершающуюся нулем, которую необходимо добавить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс строки в списке. Возвращаемое значение LB_ERR при возникновении ошибки; Возвращаемое значение LB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

Если список не был создан с [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, строка добавляется в конец списка. В противном случае строка вставляется в список, а список сортируется. Если список был создан с LBS_SORT стиле, но не [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиле, платформа сортирует список по одному или нескольким вызовам `CompareItem` функции члена.

Используйте [инсертстринг](#insertstring) , чтобы вставить строку в определенное место в списке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>CListBox:: Чартоитем

Вызывается структурой, когда родительское окно списка получает WM_CHARTOITEM сообщение из списка.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*нкэй*<br/>
Код ANSI вводимого пользователем символа.

*ниндекс*<br/>
Текущая координата курсора в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение-1 или-2 для отсутствия дальнейших действий или неотрицательных чисел для указания индекса элемента списка, для которого необходимо выполнить действие по умолчанию для нажатия клавиши. Реализация по умолчанию возвращает значение-1.

### <a name="remarks"></a>Примечания

WM_CHARTOITEM сообщение отправляется списком при получении сообщения WM_CHAR, но только в том случае, если список удовлетворяет всем указанным условиям:

- Является списком, рисуемым владельцем.

- Не имеет набора стилей [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) .

- Содержит по крайней мере один элемент.

Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию, чтобы обеспечить собственную настраиваемую обработку сообщений клавиатуры.

В переопределении необходимо вернуть значение, чтобы сообщить платформе, какое действие вы выполнили. Возвращаемое значение, равное-1 или-2, означает, что вы обработали все аспекты выбора элемента и не должны предпринимать дальнейшие действия со списком. Перед возвратом-1 или-2 можно задать выделение или переместить курсор или и то, и другое. Чтобы задать выбор, используйте [сеткурсел](#setcursel) или [сетсел](#setsel). Чтобы переместить курсор, используйте [сеткаретиндекс](#setcaretindex).

Возвращаемое значение 0 или выше указывает индекс элемента в списке и указывает, что окно списка должно выполнять действие по умолчанию для данного элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>CListBox:: CListBox

Формирует объект `CListBox`.

```
CListBox();
```

### <a name="remarks"></a>Примечания

`CListBox`Объект создается в два этапа. Сначала вызовите конструктор `ClistBox` , а затем вызовите метод `Create` , который инициализирует список окон и присоединяет его к `CListBox` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>CListBox:: Компареитем

Вызывается платформой для определения относительного положения нового элемента в списке отсортированных владельцев.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*лпкомпареитемструкт*<br/>
Длинный указатель на `COMPAREITEMSTRUCT` структуру.

### <a name="return-value"></a>Возвращаемое значение

Указывает относительное расположение двух элементов, описанных в структуре [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) . Может принимать любое из следующих значений:

|Значение|Значение|
|-----------|-------------|
|-1|Элемент 1 сортируется до элемента 2.|
|0|Элемент 1 и элемент 2 сортируются одинаково.|
|1|Элемент 1 сортируется после элемента 2.|

Описание структуры см. в разделе [CWnd:: онкомпареитем](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT` .

### <a name="remarks"></a>Примечания

По умолчанию эта функция члена не выполняет никаких действий. При создании списка, рисуемого владельцем, с LBS_SORT стиле необходимо переопределить эту функцию-член, чтобы помочь платформе в сортировке новых элементов, добавленных в список.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>CListBox:: Create

Создает окно списка Windows и прикрепляет его к `CListBox` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль списка. Примените к полю любое сочетание [стилей списка](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) .

*rect*<br/>
Задает размер и расположение окна списка. Может быть либо `CRect` объектом, либо `RECT` структурой.

*ппарентвнд*<br/>
Указывает родительское окно списка (обычно `CDialog` объект). Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления "список".

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`CListBox`Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который инициализирует список окон и присоединяет его к `CListBox` объекту.

Когда `Create` выполняется, Windows отправляет в элемент управления "список" [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения.

Эти сообщения по умолчанию обрабатываются функциями члена [оннккреате](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [оннккалксизе](../../mfc/reference/cwnd-class.md#onnccalcsize)и [онжетминмаксинфо](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в `CWnd` базовом классе. Чтобы расширить обработку сообщений по умолчанию, создайте производный класс от `CListBox` , добавьте к новому классу схему сообщений и переопределите предыдущие функции-члены обработчика сообщений. Переопределение `OnCreate` , например, для выполнения необходимой инициализации нового класса.

Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления "список".

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL добавить вертикальную полосу прокрутки

- WS_HSCROLL добавить горизонтальную полосу прокрутки

- WS_GROUP к группам элементов управления

- WS_TABSTOP разрешить переход к этому элементу управления

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::D Елетеитем

Вызывается платформой, когда пользователь удаляет элемент из объекта рисования владельцем `CListBox` или удаляет окно списка.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*лпделетеитемструкт*<br/>
Длинный указатель на структуру [Делетеитемструкт](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) Windows, содержащую сведения об удаленном элементе.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию, чтобы перерисовать список, рисуемый владельцем, по мере необходимости.

Описание структуры см. в разделе [CWnd:: онделетеитем](../../mfc/reference/cwnd-class.md#ondeleteitem) `DELETEITEMSTRUCT` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>CListBox::D Елетестринг

Удаляет элемент в позиции *ниндекс* из списка.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс удаляемой строки.

### <a name="return-value"></a>Возвращаемое значение

Число оставшихся строк в списке. Возвращаемое значение LB_ERR, если *ниндекс* указывает индекс, превышающий число элементов в списке.

### <a name="remarks"></a>Примечания

Все элементы, следующие за *ниндекс* , теперь перемещаются в одну и ту же позиции. Например, если список содержит два элемента, удаление первого элемента приведет к тому, что оставшийся элемент будет находиться в первой позиции. *ниндекс*= 0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>CListBox::D IR

Добавляет список имен файлов, дисков или и то, и другое в поле со списком.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*атрибутов*<br/>
Может быть любым сочетанием **`enum`** значений, описанным в разделе `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus), или любым сочетанием следующих значений:

|Значение|Значение|
|-----------|-------------|
|0x0000|Файл может быть считан или записан в.|
|0x0001|Файл можно считывать, но не записывает в.|
|0x0002|Файл скрыт и не отображается в списке каталога.|
|0x0004|Файл является системным файлом.|
|0x0010|Имя, заданное параметром *лпсзвилдкард* , указывает каталог.|
|0x0020|Файл архивирован.|
|0x4000|Включить все диски, которые соответствуют имени, указанному параметром *лпсзвилдкард*.|
|0x8000|Флаг Exclusive. Если установлен флаг Exclusive, то отображаются только файлы указанного типа. В противном случае файлы указанного типа будут перечислены в дополнение к обычным файлам.|

*лпсзвилдкард*<br/>
Указывает на строку спецификации файла. Строка может содержать подстановочные знаки (например, *. \* ).

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс последнего имени файла, добавленного в список. Возвращаемое значение LB_ERR при возникновении ошибки; Возвращаемое значение LB_ERRSPACE, если недостаточно места для хранения новых строк.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>CListBox::D Равитем

Вызывается структурой при изменении визуального аспекта поля списка, рисуемого владельцем.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Длинный указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , содержащую сведения о типе требуемой прорисовки.

### <a name="remarks"></a>Примечания

`itemAction`Элементы и `itemState` `DRAWITEMSTRUCT` структуры определяют выполняемое действие рисования.

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта, рисуемого владельцем `CListBox` . Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* , перед завершением этой функции-члена.

Описание структуры см. в разделе [CWnd:: ондравитем](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>CListBox:: FindString

Находит первую строку в списке, которая содержит указанный префикс, не изменяя выбор списка.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Параметры

*нстартафтер*<br/>
Содержит Отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *нстартафтер*. Если *нстартафтер* имеет значение-1, поиск выполняется по всему списку с самого начала.

*лпсзитем*<br/>
Указывает на строку, завершающуюся нулем, которая содержит префикс для поиска. Поиск не зависит от регистра, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс соответствующего элемента или LB_ERR, если Поиск завершился неудачно.

### <a name="remarks"></a>Примечания

Используйте функцию-член [селектстринг](#selectstring) , чтобы найти и выбрать строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox:: Финдстринжексакт

Находит первую строку списка, совпадающую со строкой, указанной в *лпсзфинд*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*ниндексстарт*<br/>
Указывает отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *ниндексстарт*. Если *ниндексстарт* имеет значение-1, поиск выполняется по всему списку с самого начала.

*лпсзфинд*<br/>
Указывает на строку, завершающуюся нулем, для поиска. Эта строка может содержать полное имя файла, включая расширение. При поиске регистр не учитывается, поэтому строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс соответствующего элемента или LB_ERR, если Поиск завершился неудачно.

### <a name="remarks"></a>Примечания

Если список был создан с использованием стиля рисования, но без [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, `FindStringExact` функция-член пытается сопоставить значение Даублеворд со значением *лпсзфинд*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox:: Жетанчориндекс

Возвращает отсчитываемый от нуля индекс текущего элемента привязки в списке.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс текущего элемента привязки, если он успешно выполнен; в противном случае LB_ERR.

### <a name="remarks"></a>Примечания

В списке с множественным выбором элемент привязки является первым или последним элементом в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

  См. пример для [CListBox:: сетанчориндекс](#setanchorindex).

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox:: Жеткаретиндекс

Определяет индекс элемента, имеющего прямоугольник фокуса в списке с множественным выбором.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента, имеющего прямоугольник фокуса в списке. Если список является списком с единственным выбором, возвращаемое значение является индексом выбранного элемента, если он имеется.

### <a name="remarks"></a>Примечания

Элемент может быть или не выбран.

### <a name="example"></a>Пример

  См. пример для [CListBox:: сеткаретиндекс](#setcaretindex).

## <a name="clistboxgetcount"></a><a name="getcount"></a>CListBox:: NOCOUNT

Извлекает количество элементов в списке.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в списке или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Возвращаемое значение счетчика больше значения индекса последнего элемента (индекс отсчитывается от нуля).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>CListBox:: рекурсивно

Возвращает отсчитываемый от нуля индекс текущего выбранного элемента (при наличии) в списке с единственным выбором.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс текущего выбранного элемента, если он является списком с единственным выбором. Это LB_ERR, если в данный момент ни один элемент не выбран.

В списке с множественным выбором — индекс элемента, который находится в фокусе.

### <a name="remarks"></a>Примечания

Не вызывайте `GetCurSel` список с множественным выбором. Вместо этого используйте [CListBox:: жетселитемс](#getselitems) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox:: Жесоризонталекстент

Извлекает из списка ширину в пикселях, на которую его можно прокручивать по горизонтали.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина прокручиваемого окна списка в пикселях.

### <a name="remarks"></a>Примечания

Это применимо только в том случае, если в списке есть горизонтальная полоса прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox:: Жетитемдата

Извлекает указанное приложением значение даублеворд, связанное с указанным элементом списка.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента в списке.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с элементом, или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Значение даублеворд было параметром *двитемдата* вызова [сетитемдата](#setitemdata) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox:: Жетитемдатаптр

Извлекает указанное приложением 32-разрядное значение, связанное с указанным элементом списка в виде указателя ( **`void`** <strong>\*</strong> ).

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента в списке.

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель или-1 при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox:: GetItemHeight

Определяет высоту элементов в поле со списком.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список имеет LBS_OWNERDRAWVARIABLE стиль. в противном случае значение должно быть равно 0.

### <a name="return-value"></a>Возвращаемое значение

Высота элементов списка в пикселях. Если список имеет стиль [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) , возвращаемое значение является высотой элемента, указанного параметром *ниндекс*. Если возникает ошибка, возвращается значение LB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox:: Жетитемрект

Извлекает размеры прямоугольника, ограничивающего элемент списка, который в данный момент отображается в окне списка.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*лпрект*<br/>
Задает длинный указатель на [структуру Rect](/windows/win32/api/windef/ns-windef-rect) , которая получает клиентские координаты элемента списка.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox:: Жетлистбоксинфо

Возвращает количество элементов на столбец.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в столбце `CListBox` объекта.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo) сообщения, как описано в Windows SDK.

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>CListBox:: onlocal

Извлекает языковой стандарт, используемый в списке.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение кода локали для строк в списке.

### <a name="remarks"></a>Примечания

Языковой стандарт используется, например, для определения порядка сортировки строк в отсортированном списке.

### <a name="example"></a>Пример

  См. пример для [CListBox:: setlocale](#setlocale).

## <a name="clistboxgetsel"></a><a name="getsel"></a>CListBox:: Жетсел

Извлекает состояние выбора элемента.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Положительное число, если выбран указанный элемент; в противном случае — 0. Возвращаемое значение LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Эта функция-член работает с списками с одним и несколькими элементами выбора.

Чтобы получить индекс элемента списка, выбранного в данный момент, используйте [CListBox::-рекурсивно](#getcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>CListBox:: Жетселкаунт

Возвращает общее число выбранных элементов в списке с множественным выбором.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число выбранных элементов в поле со списком. Если список является списком с одним выбором, возвращаемое значение будет LB_ERR.

### <a name="example"></a>Пример

  См. пример для [CListBox:: жетселитемс](#getselitems).

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>CListBox:: Жетселитемс

Заполняет буфер массивом целых чисел, указывающим номера элементов выбранных элементов в списке с множественным выбором.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Параметры

*нмакситемс*<br/>
Указывает максимальное количество выбранных элементов, номера элементов которых должны быть помещены в буфер.

*ргиндекс*<br/>
Задает указатель на буфер, достаточно большой для числа целых чисел, заданного параметром *нмакситемс*.

### <a name="return-value"></a>Возвращаемое значение

Фактическое число элементов, помещаемых в буфер. Если список является списком с единственным выбором, возвращается значение `LB_ERR` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>CListBox:: GetText

Возвращает строку из списка.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс извлекаемой строки.

*лпсзбуффер*<br/>
Указывает на буфер, который получает строку. Буфер должен содержать достаточно места для строки и завершающего нуль-символа. Размер строки можно определить заранее, вызвав `GetTextLen` функцию члена.

*rStr*<br/>
Ссылка на объект `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина строки (в байтах), исключая завершающего нуль-символа. Если *ниндекс* не указывает допустимый индекс, возвращаемое значение будет LB_ERR.

### <a name="remarks"></a>Примечания

Вторая форма этой функции-члена заполняет `CString` объект строкой текста.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>CListBox:: Жеттекстлен

Возвращает длину строки в элементе списка.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс строки.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в символах, за исключением завершающего нуль символа. Если *ниндекс* не указывает допустимый индекс, возвращаемое значение будет LB_ERR.

### <a name="example"></a>Пример

  См. пример для [CListBox:: GetText](#gettext).

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>CListBox:: Жеттопиндекс

Возвращает отсчитываемый от нуля индекс первого видимого элемента в списке.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого видимого элемента в списке в случае успеха, LB_ERR в противном случае.

### <a name="remarks"></a>Примечания

Изначально элемент 0 находится в верхней части окна списка, но если список прокручивается, то в верхней части может находиться другой элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>CListBox:: Инитстораже

Выделяет память для хранения элементов списка.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*нитемс*<br/>
Указывает число добавляемых элементов.

*nBytes*<br/>
Указывает объем памяти в байтах, выделяемый для строк элемента.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха максимальное число элементов, которое может храниться в списке, до того, как потребуется перераспределение памяти, в противном случае LB_ERRSPACE, что означает недостаточный объем доступной памяти.

### <a name="remarks"></a>Примечания

Вызовите эту функцию перед добавлением большого числа элементов в `CListBox` .

Эта функция позволяет ускорить инициализацию списков, имеющих большое количество элементов (более 100). Он предварительно выделяет указанный объем памяти, чтобы последующие функции [AddString](#addstring), [инсертстринг](#insertstring)и [dir](#dir) занимают кратчайшие сроки. Для параметров можно использовать оценки. При чрезмерной оценке выделяется часть дополнительной памяти. Если недооценивать, то для элементов, превышающих предварительно выделенный объем, будет использоваться нормальное выделение.

Только для Windows 95/98: параметр *нитемс* ограничен 16-разрядными значениями. Это означает, что списки не могут содержать более 32 767 элементов. Хотя количество элементов ограничено, общий размер элементов в списке ограничивается только объемом доступной памяти.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>CListBox:: Инсертстринг

Вставляет строку в список.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс позиции для вставки строки. Если этот параметр имеет значение-1, строка добавляется в конец списка.

*лпсзитем*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Возвращаемое значение LB_ERR при возникновении ошибки; Возвращаемое значение LB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

В отличие от функции-члена [AddString](#addstring) не `InsertString` приводит к сортировке списка с [LBS_SORTным](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>CListBox:: Итемфромпоинт

Определяет элемент списка, ближайший к точке, указанной в *PT*.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Параметры

*лутор*<br/>
Точка, для которой нужно найти ближайший элемент, заданный относительно левого верхнего угла клиентской области окна списка.

*баутсиде*<br/>
Ссылка на переменную BOOL, которая будет иметь значение TRUE, если *PT* находится за пределами клиентской области списка, значение false, если *PT* находится внутри клиентской области списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс ближайшего элемента к точке, указанной в *PT*.

### <a name="remarks"></a>Примечания

Эту функцию можно использовать для определения того, какой элемент списка перемещает курсор мыши.

### <a name="example"></a>Пример

  См. пример для [CListBox:: сетанчориндекс](#setanchorindex).

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>CListBox:: Меасуреитем

Вызывается структурой при создании поля списка с стилем рисования-прорисовки.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*лпмеасуреитемструкт*<br/>
Длинный указатель на структуру [меасуреитемструкт](/windows/win32/api/winuser/ns-winuser-measureitemstruct) .

### <a name="remarks"></a>Примечания

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член и заполните `MEASUREITEMSTRUCT` структуру, чтобы информировать окна измерений списка. Если список создается с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.

Дополнительные сведения об использовании стиля [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) в списке, рисуемом владельцем, созданном с помощью `SubclassDlgItem` функции-члена `CWnd` , см. в обсуждении в [техническом примечании 14](../../mfc/tn014-custom-controls.md).

Описание структуры см. в разделе [CWnd:: онмеасуреитем](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>CListBox:: Ресетконтент

Удаляет все элементы из списка.

```cpp
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>CListBox:: Селектстринг

Выполняет поиск элемента списка, соответствующего указанной строке, и при обнаружении совпадающего элемента выбирает элемент.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*нстартафтер*<br/>
Содержит Отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *нстартафтер*. Если *нстартафтер* имеет значение-1, поиск выполняется по всему списку с самого начала.

*лпсзитем*<br/>
Указывает на строку, завершающуюся нулем, которая содержит префикс для поиска. Поиск не зависит от регистра, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного элемента, если поиск прошел успешно. Если поиск завершился неудачно, возвращается значение LB_ERR и текущее выделение не изменяется.

### <a name="remarks"></a>Примечания

При необходимости список будет прокручиваться, чтобы отобразить выбранный элемент.

Эту функцию-член нельзя использовать со списком, имеющим стиль [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) .

Элемент выбирается только в том случае, если его начальные символы (от начальной точки) соответствуют символам в строке, указанной параметром *лпсзитем*.

Используйте `FindString` функцию-член для поиска строки без выбора элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>CListBox:: Селитемранже

Выбирает несколько последовательных элементов в списке с множественным выбором.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Параметры

*бселект*<br/>
Указывает, как задать выбор. Если *бселект* имеет значение true, строка выделяется и выделяется. Если значение равно FALSE, выделение удаляется и строка больше не выбирается.

*нфирститем*<br/>
Указывает отсчитываемый от нуля индекс первого элемента, который необходимо задать.

*нластитем*<br/>
Указывает отсчитываемый от нуля индекс последнего элемента, который необходимо задать.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только для списков с множественным выбором. Если необходимо выбрать только один элемент в списке с множественным выбором, то есть если *нфирститем* равен *нластитем* , то вместо этого следует вызвать функцию-член [сетсел](#setsel) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox:: Сетанчориндекс

Задает привязку в списке с множественным выбором, чтобы начать расширенный выбор.

```cpp
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента списка, который будет присутствовать в качестве привязки.

### <a name="remarks"></a>Примечания

В списке с множественным выбором элемент привязки является первым или последним элементом в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox:: Сеткаретиндекс

Задает прямоугольник фокуса для элемента по указанному индексу в списке с множественным выбором.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Задает отсчитываемый от нуля индекс элемента, получающего прямоугольник фокуса в списке.

*бскролл*<br/>
Если это значение равно 0, элемент прокручивается, пока он не будет полностью виден. Если это значение не равно 0, элемент прокручивается, пока не будет частично видимым.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Если элемент не отображается, он прокручивается в представление.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox:: Сетколумнвидс

Задает ширину (в пикселях) всех столбцов в списке с многостолбцовым списком (создается с [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем).

```cpp
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Параметры

*кксвидс*<br/>
Задает ширину всех столбцов в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>CListBox:: Сеткурсел

Выбирает строку и прокручивает ее на представление при необходимости.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Nвыделить*<br/>
Указывает отсчитываемый от нуля индекс строки, которая должна быть выбрана. Если *nвыделить* имеет значение-1, в списке не будет ничего выбора.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

При выборе новой строки список удаляет выделение из ранее выбранной строки.

Используйте эту функцию-член только в списках с одним выбором.

Чтобы задать или удалить выделенный фрагмент в списке с множественным выбором, используйте [CListBox:: сетсел](#setsel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox:: Сесоризонталекстент

Задает ширину (в пикселях), на которую окно списка можно прокручивать по горизонтали.

```cpp
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Параметры

*кксекстент*<br/>
Указывает число пикселей, на которое окно списка можно прокручивать по горизонтали.

### <a name="remarks"></a>Примечания

Если размер списка меньше этого значения, горизонтальная полоса прокрутки будет горизонтально прокручивать элементы списка. Если поле со списком имеет размер или больше, чем это значение, горизонтальная полоса прокрутки скрывается.

Чтобы ответить на вызов `SetHorizontalExtent` , список должен быть определен с помощью стиля [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) .

Эта функция-член не полезна для списков с полями по столбцам. Для списков из многостолбцового списка вызовите `SetColumnWidth` функцию члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox:: Сетитемдата

Задает значение, связанное с указанным элементом в поле со списком.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*двитемдата*<br/>
Указывает значение, которое должно быть связано с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox:: Сетитемдатаптр

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком, в качестве указанного указателя ( **`void`** <strong>\*</strong> ).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*pData*<br/>
Указывает указатель, который должен быть связан с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Этот указатель остается действительным для жизненного цикла списка, даже если относительное расположение элемента в списке может измениться по мере добавления или удаления элементов. Таким образом, индекс элемента в поле может измениться, но указатель остается надежным.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox:: Сетитемхеигхт

Задает высоту элементов в поле со списком.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список имеет LBS_OWNERDRAWVARIABLE стиль. в противном случае значение должно быть равно 0.

*циитемхеигхт*<br/>
Задает высоту элемента в пикселях.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если индекс или высота являются недопустимыми.

### <a name="remarks"></a>Примечания

Если список имеет стиль [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) , эта функция задает высоту элемента, заданного параметром *ниндекс*. В противном случае эта функция задает высоту всех элементов в списке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>CListBox:: SetLocale

Задает код локали для этого списка.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*нневлокале*<br/>
Новое значение идентификатора локали (LCID), которое нужно задать для списка.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение идентификатора локали (LCID) для этого списка.

### <a name="remarks"></a>Примечания

Если `SetLocale` не вызывается, то языковой стандарт по умолчанию получается из системы. Этот системный язык по умолчанию можно изменить с помощью регионального (или международного) приложения панели управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>CListBox:: Сетсел

Выбирает строку в списке с множественным выбором.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс строки, которую необходимо задать. Если значение равно-1, выбор добавляется или удаляется из всех строк в зависимости от значения *бселект*.

*бселект*<br/>
Указывает, как задать выбор. Если *бселект* имеет значение true, строка выделяется и выделяется. Если значение равно FALSE, выделение удаляется и строка больше не выбирается. Указанная строка выбирается и выделяется по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только для списков с множественным выбором.

Чтобы выбрать элемент из списка с одним выбором, используйте [CListBox:: сеткурсел](#setcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>CListBox:: Сеттабстопс

Задает позиции табуляции в поле со списком.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Параметры

*кксеачстоп*<br/>
Позиции табуляции задаются во всех единицах диалогового окна *кксеачстоп* . Описание единицы диалогового окна см. в разделе *ргтабстопс* .

*нтабстопс*<br/>
Указывает количество единиц табуляции, которые должны присутствовать в списке.

*ргтабстопс*<br/>
Указывает на первый элемент массива целых чисел, содержащий позиции табуляции в единицах диалогового окна. Единица диалогового окна — это расстояние по горизонтали или вертикали. Одна горизонтальная единица диалогового окна равна одной четвертой единицы текущей базовой ширины диалогового окна, а одна вертикальная единица диалогового окна равна одной восьмой базовой единицы высоты текущего диалогового окна. Базовые единицы диалогового окна вычисляются на основе высоты и ширины текущего системного шрифта. `GetDialogBaseUnits`Функция Windows возвращает текущие базовые единицы диалогового окна в пикселях. Позиции табуляции должны быть отсортированы в порядке возрастания. вкладки "назад" не допускаются.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если все вкладки заданы; в противном случае — 0.

### <a name="remarks"></a>Примечания

Чтобы задать для позиции табуляции размер по умолчанию 2 единиц диалогового окна, следует вызвать версию этой функции члена без параметров. Чтобы задать для позиции табуляции размер, отличный от 2, вызовите версию с аргументом *кксеачстоп* .

Чтобы задать позиции табуляции для массива размеров, используйте версию с аргументами *ргтабстопс* и *нтабстопс* . Для каждого значения в *ргтабстопс*будет задана позиция табуляции до числа, заданного параметром *нтабстопс*.

Чтобы ответить на вызов `SetTabStops` функции-члена, список должен быть создан с использованием стиля [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>CListBox:: Сеттопиндекс

Обеспечивает видимость определенного элемента списка.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Ноль в случае успеха или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Система прокручивает список до тех пор, пока в верхней части списка не появится элемент, указанный в *ниндекс* , либо достигнут максимальный диапазон прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>CListBox:: Вкэйтоитем

Вызывается структурой, когда родительское окно списка получает WM_VKEYTOITEM сообщение из списка.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*нкэй*<br/>
Виртуальный код клавиши нажатия пользователем. Список стандартных виртуальных клавиш см. в разделе Winuser.h

*ниндекс*<br/>
Текущая координата курсора в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение-2 для отсутствия дальнейших действий, значение-1 для действия по умолчанию или неотрицательное число, чтобы указать индекс элемента списка, для которого необходимо выполнить действие по умолчанию для нажатия клавиши.

### <a name="remarks"></a>Примечания

WM_VKEYTOITEM сообщение отправляется списком при получении сообщения WM_KEYDOWN, но только в том случае, если список соответствует обоим следующим условиям:

- Имеет набор стилей [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) .

- Содержит по крайней мере один элемент.

Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию, чтобы обеспечить собственную настраиваемую обработку сообщений клавиатуры.

Необходимо вернуть значение, чтобы сообщить платформе, какое действие выполняло переопределение. Возвращаемое значение, равное-2, указывает, что приложение обработало все аспекты выбора элемента и не требует дальнейших действий, выполняемых списком. Перед возвратом-2 можно задать выделение или переместить курсор или оба значения. Чтобы задать выбор, используйте [сеткурсел](#setcursel) или [сетсел](#setsel). Чтобы переместить курсор, используйте [сеткаретиндекс](#setcaretindex).

Возвращаемое значение, равное-1, указывает, что окно списка должно выполнять действие по умолчанию в ответ на нажатие клавиши. Реализация по умолчанию возвращает значение-1.

Возвращаемое значение 0 или выше указывает индекс элемента в списке и указывает, что окно списка должно выполнять действие по умолчанию для данного элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>См. также раздел

[Образец CTRLTEST библиотеки MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс Кбуттон](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс Кскроллбар](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс Кстатик](../../mfc/reference/cstatic-class.md)
