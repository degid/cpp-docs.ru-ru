---
title: Класс CCheckListBox
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: dc0e80e80d61104a4d8cb5f1cfd4e26a64c42249
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752741"
---
# <a name="cchecklistbox-class"></a>Класс CCheckListBox

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Формирует объект `CCheckListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCheckListBox::Создание](#create)|Создает окно контрольного списка Windows и `CCheckListBox` прикрепляет его к объекту.|
|[CCheckListBox::DrawItem](#drawitem)|Вызывается по фреймворку при изменении визуального аспекта окна списка владельца-рисования.|
|[CCheckListBox::Включить](#enable)|Включает или отражает элемент ящика контрольного списка.|
|[CCheckListBox::GetCheck](#getcheck)|Получает состояние флажка предмета.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Получает стиль контрольного флажка.|
|[CCheckListBox::IsEnabled](#isenabled)|Определяет, включен ли элемент.|
|[CCheckListBox::MeasureItem](#measureitem)|Вызывается по фреймворку при создании окна списка со стилем владельца-рисования.|
|[CChecklistbox::OnGetCheckposition](#ongetcheckposition)|Вызывается рамки, чтобы получить положение флажок элемента.|
|[CCheckListBox::SetCheck](#setcheck)|Устанавливает состояние флажка предмета.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Устанавливает стиль флажков управления.|

## <a name="remarks"></a>Примечания

"Окно списка" отображает список элементов, таких как имена файлов. Каждый элемент в списке имеет флажок рядом с ним, что пользователь может проверить или очистить.

`CCheckListBox`только для нарисованных владельцами элементов управления, поскольку список содержит больше, чем строки текста. В самом простом, контрольный список окно содержит текстовые строки и флажки, но вам не нужно иметь текст на всех. Например, у каждого элемента может быть список небольших битовых карт с флажком.

Чтобы создать свой собственный контрольный список, `CCheckListBox`вы должны получить свой собственный класс из . Чтобы получить свой собственный класс, напишите конструктор для `Create`производного класса, а затем позвоните .

Если вы хотите обрабатывать сообщения уведомлений Windows, отправленные полем списка, его родителю (обычно классу, полученному из [CDialog),](../../mfc/reference/cdialog-class.md)добавьте запись на карту сообщений и функцию обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись на карту сообщений принимает следующую форму:

**НА\_**_Уведомление_ **(id** _id_, _memberFxn_ **)**

где `id` указывается идентификатор окна ребенка `memberFxn` элемента управления, отправляющий уведомление, и является именем функции родительского члена, написанной для обработки уведомления.

Прототип функции родителя:

`afx_msg void memberFxn();`

Существует только одна запись на карту сообщений, которая относится конкретно к `CCheckListBox` (но см. также записи на карту сообщений для [CListBox):](../../mfc/reference/clistbox-class.md)

- ON_CLBN_CHKCHANGE Пользователь изменил состояние флажка элемента.

Если ваш контрольный список является полем контрольного списка по умолчанию (список строк с флажками размером с неподементы слева от каждого из них), вы можете использовать [cCheckListBox::DrawItem,](#drawitem) чтобы нарисовать поле контрольного списка. В противном случае необходимо переопределить функции [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) и [CCheckListBox::DrawItem](#drawitem) и [CCheckListBox::MeasureItem.](#measureitem)

Вы можете создать контрольное поле либо из шаблона диалога, либо непосредственно в коде.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cchecklistboxcchecklistbox"></a><a name="cchecklistbox"></a>CCheckListBox::CCheckListBox

Формирует объект `CCheckListBox`.

```
CCheckListBox();
```

### <a name="remarks"></a>Примечания

Вы строите `CCheckListBox` объект в два этапа. Сначала определите класс, `CCheckListBox`полученный `Create`из, затем вызов , который инициализирует окно контрольного списка Windows и прикрепляет его к объекту. `CCheckListBox`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

## <a name="cchecklistboxcreate"></a><a name="create"></a>CCheckListBox::Создание

Создает окно контрольного списка Windows и `CCheckListBox` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль ящика контрольного списка. Стиль должен быть LBS_HASSTRINGS и либо LBS_OWNERDRAWFIXED (все элементы в списке одинаковой высоты) либо LBS_OWNERDRAWVARIABLE (элементы в списке имеют разную высоту). Этот стиль можно сочетать с [другими стилями списка,](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) за исключением LBS_USETABSTOPS.

*rect*<br/>
Определяет размер и положение контрольного списка. Может быть либо [cRect](../../atl-mfc-shared/reference/crect-class.md) объект или [recT](/windows/win32/api/windef/ns-windef-rect) структуры.

*pParentWnd*<br/>
Определяет родительское окно контрольного списка (обычно `CDialog` объект). Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор управления контрольного списка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Вы строите `CCheckListBox` объект в два этапа. Во-первых, определить класс, полученный из, `CcheckListBox` а затем вызвать `Create`, который `CCheckListBox`инициализирует окно контрольного списка Windows и прикрепляет его к . Смотрите [CCheckListBox::CCheckListBox](#cchecklistbox) для образца.

При `Create` выполнении Windows отправляет [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в контрольный список.

Эти сообщения обрабатываются по умолчанию функциями участников [OnNcCreate,](../../mfc/reference/cwnd-class.md#onnccreate) [OnCreate,](../../mfc/reference/cwnd-class.md#oncreate) [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) `CWnd` и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в базовом классе. Чтобы расширить обработку сообщений по умолчанию, добавьте карту сообщений в ваш производный класс и переизуйте предыдущие функции обработчика сообщений. Переопределить, `OnCreate`например, для выполнения необходимой инициализации для нового класса.

Примените следующие [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления контрольным списком:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_VSCROLL Для добавления вертикальной панели прокрутки

- WS_HSCROLL Для добавления горизонтальной панели прокрутки

- WS_GROUP К управлению группой

- WS_TABSTOP Чтобы позволить табумирование к этому управлению

## <a name="cchecklistboxdrawitem"></a><a name="drawitem"></a>CCheckListBox::DrawItem

Вызывается по структуре, когда визуальный аспект владельца нарисованного контрольного ящика изменения.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Примечания

`itemState` Члены `itemAction` `DRAWITEMSTRUCT` структуры определяют действие чертежа, которое должно быть выполнено.

По умолчанию эта функция рисует список флажков по умолчанию, состоящий из списка строк, каждая из которых имеет флажок размером с непоумолчанию слева. Размер списка флажка — это тот, который указан в [Create.](#create)

Переопределить эту функцию участника для реализации чертежа ящиков контрольного списка владельца, которые не являются по умолчанию, таких как ящики контрольного списка со списками, которые не являются строками, с элементами переменной высоты или с флажками, которые не находятся слева. Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста отображения, поставляемые в *lpDrawItemStruct* до прекращения этой функции участника.

Если элементы контрольного поля не имеют той же высоты, стиль контрольного поля (указанный в) `Create`должен быть **LBS_OWNERVARIABLE,** и вы должны переопределить функцию [MeasureItem.](#measureitem)

## <a name="cchecklistboxenable"></a><a name="enable"></a>CCheckListBox::Включить

Вызов исключите эту функцию, чтобы включить или отключить элемент ящика контрольного списка.

```cpp
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Включен индекс элемента контрольного списка.

*bВСтои*<br/>
Определяет, включен или отключен элемент.

## <a name="cchecklistboxgetcheck"></a><a name="getcheck"></a>CCheckListBox::GetCheck

Извлекает состояние указанного флажка.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс флажка, который содержится в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Состояние указанного флажка. В следующей таблице перечислены возможные значения.

|Значение|Описание|
|-----------|-----------------|
|BST_CHECKED|Флажок установлен.|
|BST_UNCHECKED|Флажок не проверяется.|
|BST_INDETERMINATE|Состояние флажка неопределенно.|

## <a name="cchecklistboxgetcheckstyle"></a><a name="getcheckstyle"></a>CCheckListBox::GetCheckStyle

Вызовите эту функцию, чтобы получить стиль контрольного списка.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Стиль контрольно-пропускных коробок.

### <a name="remarks"></a>Примечания

Для получения информации о возможных стилях, см [SetCheckStyle](#setcheckstyle).

## <a name="cchecklistboxisenabled"></a><a name="isenabled"></a>CCheckListBox::IsEnabled

Вызовите эту функцию, чтобы определить, включен ли элемент.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент включен; в противном случае 0.

## <a name="cchecklistboxmeasureitem"></a><a name="measureitem"></a>CCheckListBox::MeasureItem

Вызывается по фреймворку при создании контрольного списка со стилем nondefault.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpИзмеренныйПункт*<br/>
Длинный указатель на структуру [MEASUREITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-measureitemstruct)

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию члена `MEASUREITEMSTRUCT` и заполнить структуру, чтобы сообщить Windows о размерах элементов контрольного списка. Если поле контрольного списка создается с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, фреймворк вызывает эту функцию элемента для каждого элемента в поле списка. В противном случае этот участник называется только один раз.

## <a name="cchecklistboxongetcheckposition"></a><a name="ongetcheckposition"></a>CChecklistbox::OnGetCheckposition

Рамочная система вызывает эту функцию, чтобы получить положение и размер флажка в элементе.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Параметры

*rectItem*<br/>
Положение и размер элемента списка.

*rectCheckBox*<br/>
Положение по умолчанию и размер флажка товара.

### <a name="return-value"></a>Возвращаемое значение

Положение и размер флажка предмета.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает только положение по`rectCheckBox`умолчанию и размер флажка (). По умолчанию флажок выровнен в левом верхнем углу предмета и представляет собой стандартный размер флажка. Там могут быть случаи, когда вы хотите флажки справа, или хотите больше или меньше флажок. В этих случаях `OnGetCheckPosition` переопределить, чтобы изменить положение флажка и размер внутри элемента.

## <a name="cchecklistboxsetcheck"></a><a name="setcheck"></a>CCheckListBox::SetCheck

Устанавливает состояние указанного флажка.

```cpp
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс флажка, который содержится в поле списка.

*Nпроверьте*<br/>
Состояние кнопки для указанного флажка. Смотрите раздел Замечания для возможных значений.

### <a name="remarks"></a>Примечания

В следующей таблице перечислены возможные значения параметра *nCheck.*

|Значение|Описание|
|-----------|-----------------|
|BST_CHECKED|Выберите указанный флажок.|
|BST_UNCHECKED|Очистить указанный флажок.|
|BST_INDETERMINATE|Установите указанное состояние флажка для неопределенного.<br /><br /> Это состояние доступно только в том случае, если стиль флажка BS_AUTO3STATE или BS_3STATE. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#button-styles)|

## <a name="cchecklistboxsetcheckstyle"></a><a name="setcheckstyle"></a>CCheckListBox::SetCheckStyle

Вызовите эту функцию, чтобы установить стиль флажков в поле контрольного списка.

```cpp
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
Определяет стиль флажков в контрольном ящике.

### <a name="remarks"></a>Примечания

Действительные стили:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

Для получения информации об этих стилях, см [Кнопка стили](../../mfc/reference/styles-used-by-mfc.md#button-styles).

## <a name="see-also"></a>См. также раздел

[MFC Образец TSTCON](../../overview/visual-cpp-samples.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)
