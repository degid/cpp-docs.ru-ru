---
title: Класс CVSListBox
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: 4ea48a263a01133419067979ee5fa3e62105c7f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373195"
---
# <a name="cvslistbox-class"></a>Класс CVSListBox

Класс `CVSListBox` поддерживает элемент управления списком, который будет отсечен.

## <a name="syntax"></a>Синтаксис

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CVSlistBox::CVSlistBox](#cvslistbox)|Формирует объект `CVSListBox`.|
|`CVSListBox::~CVSListBox`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CVSlistBox:AddItem](#additem)|Добавляет строку в элемент управления списком. (Переопределяет `CVSListBoxBase::AddItem`.)|
|[CVSListBox::EditItem](#edititem)|Начинает операцию редактирования текста элемента управления списком. (Переопределяет `CVSListBoxBase::EditItem`.)|
|[CVSlistBox::GetCount](#getcount)|Извлекает количество строк в элементуправления списка. (Переопределяет `CVSListBoxBase::GetCount`.)|
|[CVSlistBox::GetItemData](#getitemdata)|Извлекает 32-битное значение 32-битного значения, связанное с элементом управления списком для отсылки. (Переопределяет `CVSListBoxBase::GetItemData`.)|
|[CVSlistBox::GetItemText](#getitemtext)|Извлекает текст элемента управления списком, отсваиваемого для редактирования. (Переопределяет `CVSListBoxBase::GetItemText`.)|
|[CVSlistBox::GetSelitem](#getselitem)|Извлекает нулевой индекс выбранного в настоящее время элемента в элементе, который можно сделать для отсылки. (Переопределяет `CVSListBoxBase::GetSelItem`.)|
|`CVSListBox::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. Для получения дополнительной информации и метода синтаксиса, [см. CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CVSListBoxBase::PreTranslateMessage`.)|
|[CVSlistBox::RemoveItem](#removeitem)|Удаляет элемент из элемента, сдавленного в список. (Переопределяет `CVSListBoxBase::RemoveItem`.)|
|[CVSlistBox::SelectItem](#selectitem)|Выбирает отслаиваемую строку управления списком. (Переопределяет `CVSListBoxBase::SelectItem`.)|
|[CVSlistBox::SetItemData](#setitemdata)|Связывает 32-битное значение для приложения с элементом управления списком, который будет отстечен. (Переопределяет `CVSListBoxBase::SetItemData`.)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Возвращает ручку в текущий элемент управления представления встроенного списка.|

## <a name="remarks"></a>Примечания

Класс `CVSListBox` предоставляет набор кнопок для элементов, которые позволяют пользователю создавать, изменять, удалять или переставлять элементы в элементы управления списком.

Ниже приводится изображение элемента управления списком. Для редактирования выбрана запись второго списка, которая называется "Пункт2".

![Элемент управления CVSListBox](../../mfc/reference/media/cvslistbox.png "Элемент управления CVSListBox")

Если редактор ресурса используется для добавления элемента управления списком, обратите внимание, что панель **Toolbox** редактора не обеспечивает предопределенный элемент управления списком. Вместо этого добавьте статический элемент управления, такой как управление **group Box.** Платформа использует статический элемент управления в качестве заполнителя для определения размера и положения элемента управления списком.

Чтобы использовать элементуправления списка в шаблоне диалогового `CVSListBox` окна, объявите переменную в классе диалоговых коробок. Для поддержки обмена данными между переменной и элементом управления определите `DDX_Control` макрозапись в `DoDataExchange` методе диалогового окна. По умолчанию элементуправления редитабивого списка создается без кнопок для ред., которые будут отодещены. Используйте унаследованный метод CVSListBoxBase::SetStandardButtons для включения кнопок для отодвилость.

Для получения дополнительной информации смотрите `New Controls` каталог «Образцы», пример, файлы Page3.cpp и Page3.h.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxvslistbox.h

## <a name="cvslistboxadditem"></a><a name="additem"></a>CVSlistBox:AddItem

Добавляет строку в элемент управления списком.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Параметры

*strIext*<br/>
(в) Ссылка на строку.

*dwData*<br/>
(в) 32-битное значение, связанное со строкой, связано с приложением. Значение по умолчанию — 0.

*iIndex*<br/>
(в) Индекс позиции с нулевым уровнем, удерживаемый строкой. Если параметр *iIndex* -1, строка добавляется к концу списка. Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе положения строки в управлении список.

### <a name="remarks"></a>Примечания

Используйте метод [CVSListBox::GetItemData](#getitemdata) для получения значения, указанного параметром *dwData.* Это значение может быть рядом с приложением или указателем на другие данные.

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSlistBox::CVSlistBox

Формирует объект `CVSListBox`.

```
CVSListBox();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::EditItem

Начинает операцию редактирования текста элемента управления списком.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Нулевой индекс элемента управления списком.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если операция по отдействию начинается успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Пользователь начинает операцию по отдействию либо путем двойного нажатия на этикетку элемента, либо нажатием клавиши **F2** или **SPACEBAR,** когда элемент имеет фокус.

## <a name="cvslistboxgetcount"></a><a name="getcount"></a>CVSlistBox::GetCount

Извлекает количество строк в элементуправления списка.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в элементе управления "Список".

### <a name="remarks"></a>Примечания

Обратите внимание, что значение этого показателя превышает значение индекса последнего элемента, поскольку индекс на нулевом уровне.

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSlistBox::GetItemData

Извлекает 32-битное значение 32-битного значения, связанное с элементом управления списком для отсылки.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс с нулевым уровнем отсвасываемого элемента управления списком.

### <a name="return-value"></a>Возвращаемое значение

32-битное значение, связанное с указанным элементом.

### <a name="remarks"></a>Примечания

Используйте [CVSListBox::SetItemData](#setitemdata) или [CVSListBox::AddItem](#additem) метод связать 32-битное значение с элементом управления списком. Это значение может быть рядом с приложением или указателем на другие данные.

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSlistBox::GetItemText

Извлекает текст элемента управления списком, отсваиваемого для редактирования.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс с нулевым уровнем отсвасываемого элемента управления списком.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий текст указанного элемента.

### <a name="remarks"></a>Примечания

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSListBox::GetListHwnd

Возвращает ручку в текущий элемент управления представления встроенного списка.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка для элементаруемого элемента управления представлениям списка.

### <a name="remarks"></a>Примечания

Используйте этот метод для извлечения ручки в `CVSListBox` элемент управления представления списка, поддерживающего класс.

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a>CVSlistBox::GetSelitem

Извлекает нулевой индекс выбранного в настоящее время элемента в элементе, который можно сделать для отсылки.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если этот метод удался, индекс нулевой основе выбранного в настоящее время элемента; в противном случае, -1.

### <a name="remarks"></a>Примечания

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a>CVSlistBox::RemoveItem

Удаляет элемент из элемента, сдавленного в список.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс с нулевым уровнем отсвасываемого элемента управления списком.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанный элемент удален; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a>CVSlistBox::SelectItem

Выбирает отслаиваемую строку управления списком.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
(в) Индекс с нулевым уровнем отсвасываемого элемента управления списком.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод выбирает указанный элемент, и если он необходим, прокручивает элемент в представлении.

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSlistBox::SetItemData

Связывает 32-битное значение для приложения с элементом управления списком, который будет отстечен.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс с нулевым уровнем отсвасываемого элемента управления списком.

*dwData*<br/>
(в) 32-битное значение. Это значение может быть рядом с приложением или указателем на другие данные.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
