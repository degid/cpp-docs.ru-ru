---
title: Класс CComboBox
description: Справочник по API для класса поля со списком Windows MFC CComboBox
ms.date: 08/27/2020
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: 515a079ca4f6c3896733bbebec424f63455fb979
ms.sourcegitcommit: c8f1605354724a13566bc3b0fac3c5d98265f1d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "89062189"
---
# <a name="ccombobox-class"></a>Класс CComboBox

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CComboBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComboBox:: CComboBox](#ccombobox)|Формирует объект `CComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|Добавляет строку в конец списка в поле со списком или в отсортированном положении для списков с CBS_SORT стилем.|
|[CComboBox:: Clear](#clear)|Удаляет (очищает) текущее выделение (при наличии) в элементе управления "поле ввода".|
|[CComboBox:: Компареитем](#compareitem)|Вызывается платформой для определения относительного положения нового элемента списка в сортируемом поле со списком, рисуемом владельцем.|
|[CComboBox:: Copy](#copy)|Копирует текущее выделение (если оно имеется) в буфер обмена в CF_TEXT формате.|
|[CComboBox:: Create](#create)|Создает поле со списком и прикрепляет его к `CComboBox` объекту.|
|[CComboBox:: Cut](#cut)|Удаляет (вырезает) текущее выделение (при наличии) в элементе управления "поле ввода" и копирует удаленный текст в буфер обмена в CF_TEXT формате.|
|[CComboBox::D Елетеитем](#deleteitem)|Вызывается структурой при удалении элемента списка из поля со списком, рисуемого владельцем.|
|[CComboBox::D Елетестринг](#deletestring)|Удаляет строку из списка в поле со списком.|
|[CComboBox::D IR](#dir)|Добавляет список имен файлов к списку поля со списком.|
|[CComboBox::D Равитем](#drawitem)|Вызывается структурой при изменении визуального аспекта рисуемого владельцем поля со списком.|
|[CComboBox:: FindString](#findstring)|Находит первую строку, содержащую указанный префикс, в списке поля со списком.|
|[CComboBox:: Финдстринжексакт](#findstringexact)|Находит первую строку списка (в поле со списком), соответствующую указанной строке.|
|[CComboBox:: Жеткомбобоксинфо](#getcomboboxinfo)|Извлекает сведения об `CComboBox` объекте.|
|[CComboBox:: NOCOUNT](#getcount)|Извлекает количество элементов в списке поля со списком.|
|[CComboBox:: Жеткуебаннер](#getcuebanner)|Возвращает текст подсказки, отображаемый для элемента управления "поле со списком".|
|[CComboBox:: рекурсивно](#getcursel)|Получает индекс выбранного в данный момент элемента, если он имеется, в списке поля со списком.|
|[CComboBox:: Жетдроппедконтролрект](#getdroppedcontrolrect)|Получает экранные координаты видимого (сброшенного) поля со списком в раскрывающемся списке.|
|[CComboBox:: Жетдроппедстате](#getdroppedstate)|Определяет, является ли список раскрывающегося списка поля со списком видимым (выводится вниз).|
|[CComboBox:: Жетдроппедвидс](#getdroppedwidth)|Возвращает минимально допустимую ширину для раскрывающегося списка в поле со списком.|
|[CComboBox:: Жетедитсел](#geteditsel)|Возвращает начальные и конечные позиции символов текущего выделения в элементе управления "поле ввода" поля со списком.|
|[CComboBox:: Жетекстендедуи](#getextendedui)|Определяет, имеет ли поле со списком пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.|
|[CComboBox:: Жесоризонталекстент](#gethorizontalextent)|Возвращает ширину в пикселях, на которую можно прокручивать часть списка поля со списком по горизонтали.|
|[CComboBox:: Жетитемдата](#getitemdata)|Извлекает указанное приложением 32-разрядное значение, связанное с указанным элементом поля со списком.|
|[CComboBox:: Жетитемдатаптр](#getitemdataptr)|Извлекает указанный в приложении 32-разрядный указатель, связанный с указанным элементом поля со списком.|
|[CComboBox:: GetItemHeight](#getitemheight)|Извлекает высоту элементов списка в поле со списком.|
|[CComboBox:: Жетлбтекст](#getlbtext)|Возвращает строку из списка в поле со списком.|
|[CComboBox:: Жетлбтекстлен](#getlbtextlen)|Возвращает длину строки в поле со списком.|
|[CComboBox:: onlocal](#getlocale)|Извлекает идентификатор локали для поля со списком.|
|[CComboBox:: Жетминвисибле](#getminvisible)|Возвращает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|
|[CComboBox:: Жеттопиндекс](#gettopindex)|Возвращает индекс первого видимого элемента в списке поля со списком.|
|[CComboBox:: Инитстораже](#initstorage)|Предварительно выделяет блоки памяти для элементов и строк в списке поля со списком.|
|[CComboBox::InsertString](#insertstring)|Вставляет строку в список поля со списком.|
|[CComboBox:: Лимиттекст](#limittext)|Ограничивает длину текста, который пользователь может ввести в поле ввода поля со списком.|
|[CComboBox:: Меасуреитем](#measureitem)|Вызывается платформой для определения размеров поля со списком при создании поля со списком, рисуемого владельцем.|
|[CComboBox::P вставить](#paste)|Вставляет данные из буфера обмена в элемент управления "поле ввода" в текущей позиции курсора. Данные вставляются только в том случае, если буфер обмена содержит данные в CF_TEXTном формате.|
|[CComboBox:: Ресетконтент](#resetcontent)|Удаляет все элементы из списка и элементы управления поля со списком.|
|[CComboBox:: Селектстринг](#selectstring)|Выполняет поиск строки в списке поля со списком и, если строка найдена, выбирает строку в списке и копирует ее в элемент управления "поле ввода".|
|[CComboBox:: Сеткуебаннер](#setcuebanner)|Задает текст подсказки, отображаемый для элемента управления "поле со списком".|
|[CComboBox:: Сеткурсел](#setcursel)|Выбирает строку из списка в поле со списком.|
|[CComboBox:: Сетдроппедвидс](#setdroppedwidth)|Задает минимально допустимую ширину для раскрывающегося списка в поле со списком.|
|[CComboBox:: Сетедитсел](#seteditsel)|Выбирает символы в элементе управления "поле ввода" поля со списком.|
|[CComboBox:: Сетекстендедуи](#setextendedui)|Выбирает пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс для поля со списком, имеющего CBS_DROPDOWN или CBS_DROPDOWNLIST стиле.|
|[CComboBox:: Сесоризонталекстент](#sethorizontalextent)|Задает ширину в пикселях, на которую можно прокручивать часть списка поля со списком по горизонтали.|
|[CComboBox:: Сетитемдата](#setitemdata)|Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.|
|[CComboBox:: Сетитемдатаптр](#setitemdataptr)|Задает 32-разрядный указатель, связанный с указанным элементом в поле со списком.|
|[CComboBox:: Сетитемхеигхт](#setitemheight)|Задает высоту элементов списка в поле со списком или высоту части поля со списком (или статического элемента управления).|
|[CComboBox:: SetLocale](#setlocale)|Задает код локали для поля со списком.|
|[CComboBox:: Сетминвисиблеитемс](#setminvisibleitems)|Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|
|[CComboBox:: Сеттопиндекс](#settopindex)|Сообщает части списка в поле со списком, чтобы в верхней части отображался элемент с указанным индексом.|
|[CComboBox:: Шовдропдовн](#showdropdown)|Показывает или скрывает список полей со списком, имеющих стиль CBS_DROPDOWN или CBS_DROPDOWNLIST.|

## <a name="remarks"></a>Примечания

Поле со списком состоит из списка, Объединенного как статический элемент управления или элемент управления Edit. Часть списка элемента управления может отображаться в любое время или раскрывающийся список только в том случае, когда пользователь выбирает стрелку раскрывающейся списком рядом с элементом управления.

Выбранный в данный момент элемент (если имеется) в списке отображается в статическом или в элементе управления "поле ввода". Кроме того, если поле со списком имеет стиль раскрывающегося списка, пользователь может ввести начальный символ одного из элементов списка, а поле со списком —, если оно отображается, будет выделять следующий элемент с этим начальным символом.

В следующей таблице сравниваются три [стиля](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)поля со списком.

|Стиль|Когда отображается список в списке|Статический или элемент управления Edit|
|-----------|-------------------------------|-----------------------------|
|Простота|Всегда|Изменить|
|Drop-down|При перетаскивании|Изменить|
|Раскрывающийся список|При перетаскивании|Статические|

Объект можно создать `CComboBox` либо из шаблона диалогового окна, либо непосредственно в коде. В обоих случаях сначала вызовите конструктор `CComboBox` для создания объекта. `CComboBox` затем вызовите функцию [создания](#create) члена, чтобы создать элемент управления и присоединить его к `CComboBox` объекту.

Если требуется работать с сообщениями уведомлений Windows, отправленными полем со списком, родительскому элементу (обычно это класс, производный от `CDialog` ), добавьте запись схемы сообщения и функцию-член обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

`ON_Notification( id, memberFxn )`

где `id` указывает идентификатор дочернего окна элемента управления "поле со списком", отправляющего уведомление, и `memberFxn` является именем родительской функции-члена, написанной для работы с уведомлением.

Прототип родительской функции выглядит следующим образом:

`afx_msg void memberFxn( );`

Порядок, в котором будут отправляться определенные уведомления, нельзя прогнозировать. В частности, уведомление о CBN_SELCHANGE может возникнуть либо до, либо после CBN_CLOSEUP уведомления.

Возможны следующие записи схемы сообщений:

- ON_CBN_CLOSEUP (Windows 3,1 и более поздние версии). Список поля со списком закрыт. Это сообщение уведомления не отправляется для поля со списком, имеющего стиль [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

- ON_CBN_DBLCLK пользователь дважды щелкает строку в поле со списком. Это сообщение уведомления отправляется только для поля со списком с CBS_SIMPLE стилем. Для поля со списком, имеющего стиль [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) , двойной щелчок не может произойти, поскольку один щелчок скрывает окно списка.

- ON_CBN_DROPDOWN поле со списком раскрывающегося списка раскрывается (сделать видимым). Это сообщение уведомления может появляться только в поле со списком с CBS_DROPDOWN или CBS_DROPDOWNLIST стилем.

- ON_CBN_EDITCHANGE пользователь выполнил действие, которое могло изменить текст в элементе управления поля со списком. В отличие от сообщения CBN_EDITUPDATE, это сообщение отправляется после того, как Windows обновляет экран. Он не отправляется, если поле со списком имеет стиль CBS_DROPDOWNLIST.

- ON_CBN_EDITUPDATE часть поля со списком, управляющая редактированием, будет отображать измененный текст. Это сообщение уведомления отправляется после того, как элемент управления отформатирует текст, но перед отображением текста. Он не отправляется, если поле со списком имеет стиль CBS_DROPDOWNLIST.

- ON_CBN_ERRSPACE Поле со списком не может выделить достаточно памяти для удовлетворения конкретного запроса.

- ON_CBN_SELENDCANCEL (Windows 3,1 и более поздние версии). Указывает, что выбор пользователя должен быть отменен. Пользователь щелкает элемент, а затем щелкает другое окно или элемент управления, чтобы скрыть список полей со списком. Это уведомление отправляется перед сообщением уведомления CBN_CLOSEUP, чтобы указать, что выбор пользователя следует игнорировать. Сообщение с уведомлением CBN_SELENDCANCEL или CBN_SELENDOK отправляется, даже если уведомление об CBN_CLOSEUP не отправляется (как в случае поля со списком в стиле CBS_SIMPLE).

- ON_CBN_SELENDOK пользователь выбирает элемент и затем либо нажимает клавишу ВВОД, либо нажимает клавишу со стрелкой вниз, чтобы скрыть поле со списком. Это уведомление отправляется перед CBN_CLOSEUP сообщением о том, что выбор пользователя должен считаться допустимым. Сообщение с уведомлением CBN_SELENDCANCEL или CBN_SELENDOK отправляется, даже если уведомление об CBN_CLOSEUP не отправляется (как в случае поля со списком в стиле CBS_SIMPLE).

- ON_CBN_KILLFOCUS поле со списком теряет фокус ввода.

- ON_CBN_SELCHANGE выбор в списке поля со списком будет изменен в результате щелчка в списке или изменения выделенного фрагмента с помощью клавиш со стрелками. При обработке этого сообщения текст в элементе управления "поле со списком" может быть получен только с помощью `GetLBText` или другой аналогичной функции. `GetWindowText` нельзя использовать.

- ON_CBN_SETFOCUS поле со списком получает фокус ввода.

При создании `CComboBox` объекта в диалоговом окне (через ресурс диалогового окна) `CComboBox` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

При внедрении `CComboBox` объекта в другой объект окна его не нужно уничтожать. При создании `CComboBox` объекта в стеке он уничтожается автоматически. При создании `CComboBox` объекта в куче с помощью **`new`** функции необходимо вызвать **`delete`** для объекта, чтобы уничтожить его при уничтожении поля со списком Windows.

**Примечание** . Если требуется обработка сообщений WM_KEYDOWN и WM_CHAR, необходимо создать подкласс элементов управления "поле ввода" и "список" поля со списком, производные классы от `CEdit` и `CListBox` и добавить обработчики для этих сообщений в производные классы. Дополнительные сведения см. в разделе [CWnd:: субклассвиндов](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a> CComboBox:: AddString

Добавляет строку в список поля со списком.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*лпсзстринг*<br/>
Указывает на строку, завершающуюся нулем, которую необходимо добавить.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, то это Отсчитываемый от нуля индекс строки в списке. Возвращаемое значение CB_ERR при возникновении ошибки; Возвращаемое значение CB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

Если список не был создан с [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем, строка добавляется в конец списка. В противном случае строка вставляется в список, а список сортируется.

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` элементом управления Windows. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

Чтобы вставить строку в определенное место в списке, используйте функцию-член [инсертстринг](#insertstring) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a> CComboBox:: CComboBox

Формирует объект `CComboBox`.

```
CComboBox();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a> CComboBox:: Clear

Удаляет (очищает) текущий выделенный фрагмент (если таковой имеется) в элементе управления Edit поля со списком.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

Чтобы удалить текущее выделение и поместить удаленное содержимое в буфер обмена, используйте функцию « [Вырезать](#cut) элемент».

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a> CComboBox:: Компареитем

Вызывается платформой для определения относительного положения нового элемента в списке в поле со списком отсортированного владельца.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*лпкомпареитемструкт*<br/>
Длинный указатель на структуру [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) .

### <a name="return-value"></a>Возвращаемое значение

Указывает относительное расположение двух элементов, описанных в `COMPAREITEMSTRUCT` структуре. В качестве такой точки может выступать любой из следующих вариантов:

|Значение|Значение|
|-----------|-------------|
|- 1|Элемент 1 сортируется до элемента 2.|
|0|Элемент 1 и элемент 2 сортируются одинаково.|
|1|Элемент 1 сортируется после элемента 2.|

Описание см. в разделе [CWnd:: онкомпареитем](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT` .

### <a name="remarks"></a>Примечания

По умолчанию эта функция члена не выполняет никаких действий. При создании поля со списком, рисуемого владельцем, с LBS_SORT стиле необходимо переопределить эту функцию-член, чтобы помочь платформе в сортировке новых элементов, добавленных в список.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a> CComboBox:: Copy

Копирует текущее выделение (при наличии) в поле ввода поля со списком в буфер обмена в формате CF_TEXT.

```cpp
void Copy();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a> CComboBox:: Create

Создает поле со списком и прикрепляет его к `CComboBox` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль поля со списком. Примените к полю любое сочетание [стилей комбинированных](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) полей.

*rect*<br/>
Указывает на расположение и размер поля со списком. Может быть [структурой Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объектом.

*ппарентвнд*<br/>
Задает родительское окно поля со списком (обычно `CDialog` ). Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`CComboBox`Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который создает поле со списком Windows и присоединяет его к `CComboBox` объекту.

Когда `Create` выполняется, Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в поле со списком.

Эти сообщения по умолчанию обрабатываются функциями члена [оннккреате](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [оннккалксизе](../../mfc/reference/cwnd-class.md#onnccalcsize)и [онжетминмаксинфо](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в `CWnd` базовом классе. Чтобы расширить обработку сообщений по умолчанию, создайте производный класс от `CComboBox` , добавьте к новому классу схему сообщений и переопределите предыдущие функции-члены обработчика сообщений. Переопределение `OnCreate` , например, для выполнения необходимой инициализации нового класса.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления "поле со списком". :

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL добавить вертикальную прокрутку для списка в поле со списком

- WS_HSCROLL добавить горизонтальную прокрутку для списка в поле со списком

- WS_GROUP к группам элементов управления

- WS_TABSTOP включить поле со списком в порядок табуляции

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a> CComboBox:: Cut

Удаляет (вырезает) текущее выделение (если оно есть) в элементе управления "поле со списком" и копирует удаленный текст в буфер обмена в CF_TEXT формате.

```cpp
void Cut();
```

### <a name="remarks"></a>Примечания

Чтобы удалить текущее выделение без помещения удаленного текста в буфер обмена, вызовите функцию [clear](#clear) Member.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a> CComboBox::D Елетеитем

Вызывается платформой, когда пользователь удаляет элемент из объекта рисования владельцем `CComboBox` или удаляет поле со списком.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*лпделетеитемструкт*<br/>
Длинный указатель на структуру [Делетеитемструкт](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) Windows, содержащую сведения об удаленном элементе. Описание этой структуры см. в разделе [CWnd:: онделетеитем](../../mfc/reference/cwnd-class.md#ondeleteitem) .

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию, чтобы при необходимости перерисовать поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a> CComboBox::D Елетестринг

Удаляет элемент в позиции *ниндекс* из поля со списком.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает индекс удаляемой строки.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, то это число оставшихся в списке строк. Возвращаемое значение CB_ERR, если *ниндекс* указывает индекс, превышающий число элементов в списке.

### <a name="remarks"></a>Примечания

Все элементы, следующие за *ниндекс* , теперь перемещаются в одну и ту же позиции. Например, если поле со списком содержит два элемента, удаление первого элемента приведет к тому, что оставшийся элемент будет находиться в первой позиции. *ниндекс*= 0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a> CComboBox::D IR

Добавляет список имен файлов или дисков в список поля со списком.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*атрибутов*<br/>
Может быть любым сочетанием **`enum`** значений, описанных в [кфиле:: Status](../../mfc/reference/cfile-class.md#getstatus) , или любым сочетанием следующих значений:

- Файл DDL_READWRITE можно считывать из файла или записывать в него.

- Файл DDL_READONLY можно считывать, но не записывает в.

- Файл DDL_HIDDEN скрыт и не отображается в списке каталога.

- DDL_SYSTEM файл является системным файлом.

- DDL_DIRECTORY имя, заданное параметром *лпсзвилдкард* , указывает каталог.

- DDL_ARCHIVE файл архивирован.

- DDL_DRIVES включить все диски, соответствующие имени, заданному параметром *лпсзвилдкард*.

- DDL_EXCLUSIVE монопольный флаг. Если установлен флаг Exclusive, то отображаются только файлы указанного типа. В противном случае файлы указанного типа будут перечислены в дополнение к обычным файлам.

*лпсзвилдкард*<br/>
Указывает на строку спецификации файла. Строка может содержать подстановочные знаки (например, *. \* ).

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, то это Отсчитываемый от нуля индекс последнего имени файла, добавленного в список. Возвращаемое значение CB_ERR при возникновении ошибки; Возвращаемое значение CB_ERRSPACE, если недостаточно места для хранения новых строк.

### <a name="remarks"></a>Примечания

Эта функция не поддерживается `ComboBoxEx` элементом управления Windows. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a> CComboBox::D Равитем

Вызывается структурой при изменении визуального аспекта поля со списком, рисуемого владельцем.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , содержащую сведения о типе требуемой прорисовки.

### <a name="remarks"></a>Примечания

`itemAction`Элемент `DRAWITEMSTRUCT` структуры определяет выполняемое действие рисования. Описание этой структуры см. в разделе [CWnd:: ондравитем](../../mfc/reference/cwnd-class.md#ondrawitem) .

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта, рисуемого владельцем `CComboBox` . Перед завершением этой функции-члена приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a> CComboBox:: FindString

Находит, но не выбирает первую строку, содержащую указанный префикс, в списке поля со списком.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Параметры

*нстартафтер*<br/>
Содержит Отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *нстартафтер*. Если значение равно-1, поиск выполняется по всему списку с самого начала.

*лпсзстринг*<br/>
Указывает на строку, завершающуюся нулем, которая содержит префикс для поиска. Поиск не зависит от регистра, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, то это Отсчитываемый от нуля индекс соответствующего элемента. Это CB_ERR, если Поиск завершился неудачно.

### <a name="remarks"></a>Примечания

Эта функция не поддерживается `ComboBoxEx` элементом управления Windows. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a> CComboBox:: Финдстринжексакт

Вызовите `FindStringExact` функцию-член, чтобы найти первую строку списка (в поле со списком), совпадающую со строкой, указанной в *лпсзфинд*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*ниндексстарт*<br/>
Указывает отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *ниндексстарт*. Если *ниндексстарт* имеет значение-1, поиск выполняется по всему списку с самого начала.

*лпсзфинд*<br/>
Указывает на строку, завершающуюся нулем, для поиска. Эта строка может содержать полное имя файла, включая расширение. При поиске регистр не учитывается, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс соответствующего элемента или CB_ERR, если Поиск завершился неудачно.

### <a name="remarks"></a>Примечания

Если поле со списком было создано с использованием стиля рисования, но без [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля, `FindStringExact` пытается сопоставить значение Даублеворд со значением *лпсзфинд*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a> CComboBox:: Жеткомбобоксинфо

Получает сведения для `CComboBox` объекта.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Параметры

*пкби*<br/>
Указатель на структуру [комбобоксинфо](/windows/win32/api/winuser/ns-winuser-comboboxinfo) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo) сообщения, как описано в Windows SDK.

## <a name="ccomboboxgetcount"></a><a name="getcount"></a> CComboBox:: NOCOUNT

Вызовите эту функцию-член, чтобы получить количество элементов в поле со списком в списке.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов. Возвращаемое значение счетчика больше значения индекса последнего элемента (индекс отсчитывается от нуля). Это CB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a> CComboBox:: Жеткуебаннер

Возвращает текст подсказки, отображаемый для элемента управления "поле со списком".

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Параметры

*лпсзтекст*\
заполняет Указатель на буфер, который получает текст объявления подсказки.

*кчтекст*\
окне Размер буфера, на который указывает параметр *лпсзтекст* .

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке объект [CString](../../atl-mfc-shared/using-cstring.md) , содержащий текст баннера подсказки, если он существует; в противном случае — `CString` объект, имеющий нулевую длину.

-или-

Во второй перегрузке значение TRUE, если этот метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Текст подсказки — это запрос, отображаемый в области ввода элемента управления "поле со списком". Текст подсказки отображается до тех пор, пока пользователь не предоставит входные данные.

Этот метод отправляет [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) сообщение, описанное в Windows SDK.

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a> CComboBox:: рекурсивно

Вызовите эту функцию-член, чтобы определить, какой элемент в поле со списком выбран.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс текущего выбранного элемента в поле со списком или CB_ERR, если элемент не выбран.

### <a name="remarks"></a>Примечания

`GetCurSel` Возвращает индекс в списке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a> CComboBox:: Жетдроппедконтролрект

Вызовите `GetDroppedControlRect` функцию-член, чтобы получить экранные координаты видимого (раскрывающегося списка) поля со списком в раскрывающемся списке.

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Параметры

*лпрект*<br/>
Указывает на [структуру Rect](/windows/win32/api/windef/ns-windef-rect) , которая должна принимать координаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a> CComboBox:: Жетдроппедстате

Вызовите `GetDroppedState` функцию-член, чтобы определить, является ли список раскрывающегося списка поля со списком видимым (выводится вниз).

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если список является видимым; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a> CComboBox:: Жетдроппедвидс

Вызовите эту функцию, чтобы получить минимальную допустимую ширину (в пикселях) списка поля со списком.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха Минимальная допустимая ширина (в пикселях). в противном случае CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция применяется только к полям со списком, имеющим стиль [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

По умолчанию минимальная допустимая ширина раскрывающегося списка равна 0. Минимальная допустимая ширина может быть установлена путем вызова [сетдроппедвидс](#setdroppedwidth). Когда отображается часть поля со списком, ее ширина превышает минимальную допустимую ширину или ширину поля со списком.

### <a name="example"></a>Пример

  См. пример для [сетдроппедвидс](#setdroppedwidth).

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a> CComboBox:: Жетедитсел

Возвращает начальные и конечные позиции символов текущего выделения в элементе управления "поле ввода" поля со списком.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

32-разрядное значение, содержащее начальную точку в слове с низким порядком и позиции первого невыделенного символа после конца выделенного слова в высоком порядке. Если эта функция используется для поля со списком без элемента управления "поле ввода", возвращается CB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a> CComboBox:: Жетекстендедуи

Вызовите `GetExtendedUI` функцию-член, чтобы определить, имеет ли поле со списком пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если поле со списком имеет расширенный пользовательский интерфейс; в противном случае — 0.

### <a name="remarks"></a>Примечания

Расширенный пользовательский интерфейс можно определить следующими способами.

- При щелчке статического элемента управления список отображается только для полей со списком, имеющих стиль [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

- При нажатии клавиши со стрелкой вниз отображается поле со списком (F4 отключено).

Прокрутка в статическом элементе управления отключена, если список элементов не отображается (клавиши со стрелками отключены).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a> CComboBox:: Жесоризонталекстент

Извлекает из поля со списком ширину в пикселях, на которую можно прокручивать часть списка поля со списком по горизонтали.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина прокручиваемой части поля со списком в пикселях.

### <a name="remarks"></a>Примечания

Это применимо только в том случае, если часть списка в поле со списком имеет горизонтальную полосу прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a> CComboBox:: Жетитемдата

Извлекает указанное приложением 32-разрядное значение, связанное с указанным элементом поля со списком.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс элемента в списке поля со списком.

### <a name="return-value"></a>Возвращаемое значение

32-разрядное значение, связанное с элементом, или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

32-разрядное значение можно задать с помощью параметра *двитемдата* вызова функции-члена [сетитемдата](#setitemdata) . Используйте `GetItemDataPtr` функцию-член, если извлекаемое 32-разрядное значение является указателем ( **`void`** <strong>\*</strong> ).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a> CComboBox:: Жетитемдатаптр

Извлекает указанное приложением 32-разрядное значение, связанное с указанным элементом поля со списком, в качестве указателя ( **`void`** <strong>\*</strong> ).

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс элемента в списке поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель или-1 при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a> CComboBox:: GetItemHeight

Вызовите `GetItemHeight` функцию-член, чтобы получить высоту элементов списка в поле со списком.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает компонент поля со списком, высота которого необходимо получить. Если параметр *ниндекс* имеет значение-1, то высота элемента управления Edit-Control (или статического текста) в поле со списком извлекается. Если поле со списком имеет стиль [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) , *ниндекс* Указывает отсчитываемый от нуля индекс элемента списка, высота которого необходимо получить. В противном случае *ниндекс* должен иметь значение 0.

### <a name="return-value"></a>Возвращаемое значение

Высота (в пикселях) указанного элемента в поле со списком. При возникновении ошибки возвращается значение CB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a> CComboBox:: Жетлбтекст

Возвращает строку из списка в поле со списком.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс копируемой строки списка.

*lpszText*<br/>
Указывает на буфер, который должен получить строку. Буфер должен содержать достаточно места для строки и завершающего нуль-символа.

*rStr*<br/>
Ссылка на `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина строки (в байтах), исключая завершающего нуль-символа. Если *ниндекс* не указывает допустимый индекс, возвращаемое значение будет CB_ERR.

### <a name="remarks"></a>Примечания

Вторая форма этой функции-члена заполняет `CString` объект текстом элемента.
Если *ниндекс* является недопустимым, эта функция создает `E_INVALIDARG` исключение (код ошибки: `-2147024809` , `0x80070057` ).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a> CComboBox:: Жетлбтекстлен

Возвращает длину строки в поле со списком.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс строки списка.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в байтах, за исключением завершающего нуль символа. Если *ниндекс* не указывает допустимый индекс, возвращаемое значение будет CB_ERR.

### <a name="example"></a>Пример

  См. пример для [CComboBox:: жетлбтекст](#getlbtext).

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a> CComboBox:: onlocal

Извлекает языковой стандарт, используемый полем со списком.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение кода локали для строк в поле со списком.

### <a name="remarks"></a>Примечания

Языковой стандарт используется, например, для определения порядка сортировки строк в отсортированном поле со списком.

### <a name="example"></a>Пример

  См. пример для [CComboBox:: setlocale](#setlocale).

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a> CComboBox:: Жетминвисибле

Возвращает минимальное число видимых элементов в раскрывающемся списке текущего элемента управления "поле со списком".

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное число видимых элементов в текущем раскрывающемся списке.

### <a name="remarks"></a>Примечания

Этот метод отправляет [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) сообщение, описанное в Windows SDK.

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a> CComboBox:: Жеттопиндекс

Возвращает отсчитываемый от нуля индекс первого видимого элемента в списке поля со списком.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого видимого элемента в списке поля со списком в случае успеха, CB_ERR в противном случае.

### <a name="remarks"></a>Примечания

Изначально элемент 0 находится в верхней части окна списка, но если список прокручивается, то в верхней части может находиться другой элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a> CComboBox:: Инитстораже

Выделяет память для хранения элементов списка в части поля со списком.

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

В случае успеха максимальное число элементов, которое может храниться в списке поля со списком, до того, как потребуется перераспределение памяти, в противном случае CB_ERRSPACE, что означает недостаточный объем доступной памяти.

### <a name="remarks"></a>Примечания

Вызовите эту функцию перед добавлением большого числа элементов в часть списка `CComboBox` .

Только для Windows 95/98: параметр *wParam* ограничен 16-разрядными значениями. Это означает, что списки не могут содержать более 32 767 элементов. Хотя количество элементов ограничено, общий размер элементов в списке ограничивается только объемом доступной памяти.

Эта функция позволяет ускорить инициализацию списков, имеющих большое количество элементов (более 100). Он предварительно выделяет указанный объем памяти, чтобы последующие функции [AddString](#addstring), [инсертстринг](#insertstring)и [dir](#dir) занимают кратчайшие сроки. Для параметров можно использовать оценки. При чрезмерной оценке выделяется часть дополнительной памяти. Если недооценивать, то для элементов, превышающих предварительно выделенный объем, будет использоваться нормальное выделение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a> CComboBox:: Инсертстринг

Вставляет строку в список поля со списком.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит отсчитываемый от нуля индекс позиции в списке, в которую будет вставлена строка. Если этот параметр имеет значение-1, строка добавляется в конец списка.

*лпсзстринг*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. При возникновении ошибки возвращается значение CB_ERR. Если для хранения новой строки недостаточно места, возвращается значение CB_ERRSPACE.

### <a name="remarks"></a>Примечания

В отличие от функции-члена [AddString](#addstring) , функция-член `InsertString` не вызывает сортировку списка со стилем [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` элементом управления Windows. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a> CComboBox:: Лимиттекст

Ограничивает длину текста в байтах, который пользователь может ввести в поле ввода поля со списком.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Параметры

*нмаксчарс*<br/>
Задает длину (в байтах) текста, который может ввести пользователь. Если этот параметр имеет значение 0, длина текста равна 65 535 байт.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха. При вызове для поля со списком с [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля или для поля со списком без элемента управления "поле ввода" возвращаемое значение равно CB_ERR.

### <a name="remarks"></a>Примечания

Если поле со списком не имеет [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)стиля, Установка предельного размера текста, превышающего размер элемента управления поля ввода, не будет действовать.

`LimitText` ограничивает только текст, который может вводить пользователь. Он не влияет на любой текст, уже находящиеся в элементе управления "поле ввода" при отправке сообщения, и на длину текста, скопированного в элемент управления "поле ввода", при выборе строки в списке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a> CComboBox:: Меасуреитем

Вызывается структурой при создании поля со списком с стилем рисования, рисуемым владельцем.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*лпмеасуреитемструкт*<br/>
Длинный указатель на структуру [меасуреитемструкт](/windows/win32/api/winuser/ns-winuser-measureitemstruct) .

### <a name="remarks"></a>Примечания

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию члена и заполните `MEASUREITEMSTRUCT` структуру, чтобы информировать окна измерений списка в поле со списком. Если поле со списком создается с [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем, то платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.

Использование стиля CBS_OWNERDRAWFIXED в поле со списком, рисуемом владельцем, созданным с помощью функции-члена `CWnd`[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem), требует дальнейших рекомендаций по программированию. См. обсуждение в [техническом примечании 14](../../mfc/tn014-custom-controls.md).

Описание структуры см. в разделе [CWnd:: онмеасуреитем](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a> CComboBox::P вставить

Вставляет данные из буфера обмена в поле ввода поля со списком в текущей позиции курсора.

```cpp
void Paste();
```

### <a name="remarks"></a>Примечания

Данные вставляются только в том случае, если буфер обмена содержит данные в CF_TEXTном формате.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a> CComboBox:: Ресетконтент

Удаляет все элементы из списка и элементы управления поля со списком.

```cpp
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a> CComboBox:: Селектстринг

Выполняет поиск строки в списке поля со списком и, если строка найдена, выбирает строку в списке и копирует ее в элемент управления "поле ввода".

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*нстартафтер*<br/>
Содержит Отсчитываемый от нуля индекс элемента до первого элемента для поиска. Когда поиск достигает нижнего края списка, он переходит от верхней части окна списка к элементу, указанному параметром *нстартафтер*. Если значение равно-1, поиск выполняется по всему списку с самого начала.

*лпсзстринг*<br/>
Указывает на строку, завершающуюся нулем, которая содержит префикс для поиска. Поиск не зависит от регистра, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранного элемента, если строка найдена. Если поиск завершился неудачно, возвращается значение CB_ERR и текущее выделение не изменяется.

### <a name="remarks"></a>Примечания

Строка выбирается только в том случае, если ее начальные символы (от начальной точки) соответствуют символам в строке префикса.

Обратите внимание, что `SelectString` `FindString` функции-члены и находят строку, но функция- `SelectString` член также выбирает строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a> CComboBox:: Сеткуебаннер

Задает текст подсказки, отображаемый для элемента управления "поле со списком".

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*лпсзтекст*\
окне Указатель на буфер, заканчивающийся нулем, который содержит текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Текст подсказки — это запрос, отображаемый в области ввода элемента управления "поле со списком". Текст подсказки отображается до тех пор, пока пользователь не предоставит входные данные.

Этот метод отправляет [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_combobox*, которая используется для программного доступа к элементу управления "поле со списком". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

В следующем примере кода задается баннер подсказки для элемента управления "поле со списком".

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a> CComboBox:: Сеткурсел

Выбирает строку из списка в поле со списком.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Nвыделить*<br/>
Указывает отсчитываемый от нуля индекс строки для выбора. Если значение равно-1, все текущие выделенные элементы в списке удаляются, а элемент управления "поле ввода" удаляется.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента, выбранного в случае успешного выполнения сообщения. Возвращаемое значение CB_ERR, если *nвыделить* больше числа элементов в списке или если *nвыделить* имеет значение-1, что снимает выделение.

### <a name="remarks"></a>Примечания

При необходимости список Прокручивает строку в представление (если список является видимым). Текст в поле ввода поля со списком изменяется в соответствии с новым выбором. Все предыдущие выделения в списке удаляются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a> CComboBox:: Сетдроппедвидс

Вызовите эту функцию, чтобы задать минимальную допустимую ширину (в пикселях) списка в поле со списком.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Параметры

*нвидс*<br/>
Минимальная допустимая ширина части списка в поле со списком в пикселях.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха Новая ширина окна списка, в противном случае CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция применяется только к полям со списком, имеющим стиль [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

По умолчанию минимальная допустимая ширина раскрывающегося списка равна 0. Когда отображается часть поля со списком, ее ширина превышает минимальную допустимую ширину или ширину поля со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a> CComboBox:: Сетедитсел

Выбирает символы в элементе управления "поле ввода" поля со списком.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Параметры

*нстартчар*<br/>
Задает начальную точку. Если начальная ячейка имеет значение-1, то все существующие выделения удаляются.

*нендчар*<br/>
Задает конечную точку. Если для конечной позиции задано значение-1, то выбирается весь текст из начальной позиции к последнему символу в элементе управления "поле ввода".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция-член успешно выполнена; в противном случае — 0. Он CB_ERR, если `CComboBox` имеет стиль [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или не имеет списка.

### <a name="remarks"></a>Примечания

Позиции отсчитываются от нуля. Чтобы выбрать первый символ в элементе управления "поле ввода", укажите начальную точку 0. Конечная позиция — для символа сразу после последнего символа для выбора. Например, чтобы выбрать первые четыре символа элемента управления "поле ввода", следует использовать начальную точку 0 и конечную точку 4.

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` элементом управления Windows. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CComboBox:: жетедитсел](#geteditsel).

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a> CComboBox:: Сетекстендедуи

Вызовите `SetExtendedUI` функцию-член, чтобы выбрать пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс для поля со списком, имеющего [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиле.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Параметры

*бекстендед*<br/>
Указывает, должен ли поле со списком использовать расширенный пользовательский интерфейс или пользовательский интерфейс по умолчанию. Значение TRUE выбирает расширенный пользовательский интерфейс. значение FALSE выбирает стандартный пользовательский интерфейс.

### <a name="return-value"></a>Возвращаемое значение

CB_OKAY, если операция выполнена успешно, или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Расширенный пользовательский интерфейс можно определить следующими способами.

- При щелчке статического элемента управления список отображается только для полей со списком, имеющих стиль CBS_DROPDOWNLIST.

- При нажатии клавиши со стрелкой вниз отображается поле со списком (F4 отключено).

Прокрутка в статическом элементе управления отключена, если список элементов не отображается (клавиши со стрелками отключены).

### <a name="example"></a>Пример

  См. пример для [CComboBox:: жетекстендедуи](#getextendedui).

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a> CComboBox:: Сесоризонталекстент

Задает ширину (в пикселях), на которую можно прокручивать часть списка поля со списком по горизонтали.

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Параметры

*некстент*<br/>
Указывает число пикселей, на которое можно прокручивать часть списка поля со списком по горизонтали.

### <a name="remarks"></a>Примечания

Если ширина списка меньше этого значения, горизонтальная полоса прокрутки будет горизонтально прокручивать элементы списка. Если ширина окна списка равна или больше этого значения, горизонтальная полоса прокрутки скрывается или, если поле со списком имеет стиль [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) , отключено.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a> CComboBox:: Сетитемдата

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс элемента, который необходимо задать.

*двитемдата*<br/>
Содержит новое значение, связываемое с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте `SetItemDataPtr` функцию-член, если 32-разрядный элемент является указателем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a> CComboBox:: Сетитемдатаптр

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком, как заданный указатель ( **`void`** <strong>\*</strong> ).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Содержит Отсчитываемый от нуля индекс для элемента.

*pData*<br/>
Содержит указатель, связываемый с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Этот указатель остается действительным для жизненного цикла поля со списком, даже если относительное расположение элемента в поле со списком может измениться по мере добавления или удаления элементов. Таким образом, индекс элемента в поле может измениться, но указатель остается надежным.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a> CComboBox:: Сетитемхеигхт

Вызовите `SetItemHeight` функцию-член, чтобы задать высоту элементов списка в поле со списком или высоту части поля ввода (или статического элемента управления) в поле со списком.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает, задана ли высота элементов списка или высота элемента управления "поле ввода" (или статического текста).

Если поле со списком имеет стиль [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) , *ниндекс* Указывает отсчитываемый от нуля индекс элемента списка, высота которого задается. в противном случае *ниндекс* должен быть равен 0, а высота всех элементов списка будет задана.

Если *ниндекс* имеет значение-1, то высота элемента управления Edit-Control или Static Text в поле со списком задается.

*циитемхеигхт*<br/>
Задает высоту (в пикселях) компонента поля со списком, определенного параметром *ниндекс*.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR, если индекс или высота являются недопустимыми; в противном случае — 0.

### <a name="remarks"></a>Примечания

Высота части поля со списком, относящейся к редактированию (или статическому тексту), задается независимо от высоты элементов списка. Приложение должно гарантировать, что высота части элемента управления Edit-Control (или статического текста) не меньше высоты определенного элемента списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a> CComboBox:: SetLocale

Задает код локали для этого поля со списком.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*нневлокале*<br/>
Новое значение идентификатора локали (LCID), которое необходимо задать для поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение идентификатора локали (LCID) для этого поля со списком.

### <a name="remarks"></a>Примечания

Если `SetLocale` не вызывается, то языковой стандарт по умолчанию получается из системы. Этот системный язык по умолчанию можно изменить с помощью регионального (или международного) приложения панели управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a> CComboBox:: Сетминвисиблеитемс

Задает минимальное число видимых элементов в раскрывающемся списке текущего элемента управления "поле со списком".

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Параметры

*Невидимый*\
окне Указывает минимальное число видимых элементов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_combobox*, которая используется для программного доступа к элементу управления "поле со списком". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

В следующем примере кода в раскрывающийся список элемента управления "поле со списком" вставляется 20 элементов. Затем он указывает, что при нажатии пользователем стрелки раскрывающегося списка будет отображаться не менее 10 элементов.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a> CComboBox:: Сеттопиндекс

Гарантирует, что конкретный элемент будет виден в части списка в поле со списком.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Указывает отсчитываемый от нуля индекс элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Ноль в случае успеха или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Система прокручивает список до тех пор, пока в верхней части списка не появится элемент, указанный в *ниндекс* , либо достигнут максимальный диапазон прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a> CComboBox:: Шовдропдовн

Показывает или скрывает список полей со списком, имеющих стиль [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Параметры

*бшовит*<br/>
Указывает, следует ли отображать или скрывать раскрывающийся список. Значение TRUE показывает список. Значение FALSE скрывает список.

### <a name="remarks"></a>Примечания

По умолчанию в поле со списком этого стиля отображается список.

Эта функция-член не влияет на поле со списком, созданное с помощью стиля [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

### <a name="example"></a>Пример

  См. пример для [CComboBox:: жетдроппедстате](#getdroppedstate).

## <a name="see-also"></a>См. также раздел

[Пример CTRLBARS в MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс Кбуттон](../../mfc/reference/cbutton-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс Кскроллбар](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс Кстатик](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
