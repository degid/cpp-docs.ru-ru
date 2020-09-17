---
title: CMFCToolBarComboBoxButton класс
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: 995d7d0db55889130e1cad9585b8fc87285ffd27
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754010"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton класс

Кнопка панели инструментов, которая содержит управление комбо-коробкой [(класс CComboBox).](../../mfc/reference/ccombobox-class.md)

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Создает документ `CMFCToolBarComboBoxButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarComboButton:AddItem](#additem)|Добавляет элемент в конец списка комбо-боксов.|
|[CMFCToolBarComboButton::AddSortedItem](#addsorteditem)|Добавляет элемент в список комбо-боксов. Порядок элементов в списке `Compare`указан.|
|[CMFCToolBarComboBoxButton::Сравните](#compare)|Сравнивает два элемента. Вызывается для `AddSortedItems` сортировки элементов, которые добавляет к списку комбо-бокс.|
|[CMFCToolBarComboButton::CreateEdit](#createedit)|Создает новый элемент управления для комбо-бокса кнопки.|
|[CMFCToolBarComboButton::DeleteItem](#deleteitem)|Удаляет элемент из списка комбо-боксов.|
|[CMFCToolBarComboButton::FindItem](#finditem)|Возвращает индекс элемента, содержащего указанную строку.|
|[CMFCToolBarComboButton::GetByCmd](#getbycmd)|Возвращает указатель на кнопку комбо-бокса с указанным идентификатором команды.|
|[CMFCToolBarComboButtonButton::GetComboBox](#getcombobox)|Возвращает указатель на управление комбо-коробкой, встроенной в кнопку комбо-бокса.|
|[CMFCToolBarComboButton::GetCount](#getcount)|Возвращает количество элементов в списке комбо-боксов.|
|[CMFCToolBarComboButtonButton::GetCountAll](#getcountall)|Находит кнопку комбо-бокса с указанным идентификатором команды. Возвращает количество элементов в списке комбо-боксов этой кнопки.|
|[CMFCToolBarComboButton::GetCurSel](#getcursel)|Возвращает индекс выбранного элемента в списке комбо-боксов.|
|[CMFCToolBarComboButtonButton::GetCurSelall](#getcurselall)|Находит кнопку комбо-бокса с указанным идентификатором команды и возвращает индекс выбранного элемента в списке комбо-боксов этой кнопки.|
|[CMFCToolBarComboButton::GetEditCtrl](#geteditctrl)|Возвращает указатель на управление ревертом, встроенное в кнопку комбо-бокса.|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Возвращает строку, связанную с указанным индексом, в списке комбо-боксов.|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Находит кнопку комбо-бокса с указанным идентификатором команды и возвращает строку, связанную с индексом в списке комбо-боксов этой кнопки.|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Возвращает 32-битное значение, связанное с указанным индексом в списке комбо-боксов.|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Находит кнопку комбо-бокса с указанным идентификатором команды и возвращает 32-битное значение, связанное с индексом в списке комбо-боксов этой кнопки.|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Находит кнопку комбо-бокса с указанным идентификатором команды. Получает 32-битное значение, связанное с индексом в списке комбо-боксов этой кнопки, и возвращает 32-битное значение в качестве указателя.|
|[CMFCToolBarComboButton::GetText](#gettext)|Возвращает текст из управления редактированием комбо-коробки.|
|[CMFCToolBarComboButton::GetTextAll](#gettextall)|Находит кнопку комбо-бокса с указанным идентификатором команды и возвращает текст из управления редактированием этой кнопки.|
|[CMFCToolBarComboButton::IsCenterVert](#iscentervert)|Определяет, центрированы ли кнопки комбо-коробки в приложении или выровнены в верхней части панели инструментов.|
|[CMFCToolBarComboButton::IsFlatMode](#isflatmode)|Определяет, имеют ли кнопки комбо-коробки в приложении плоский вид.|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Удаляет все элементы из коробки списка и отодевать управление комбо-коробкой.|
|[CMFCToolBarComboButton::SelectItem](#selectitem)|Выбирает элемент в комбо-коробке в соответствии с его индексом, 32-битное значение, или строки, и уведомляет управление комбо-бокс о выборе.|
|[CMFCToolBarComboButton::SelectItemAll](#selectitemall)|Находит кнопку комбо-бокса с указанным идентификатором команды. Вызовы, `SelectItem` чтобы выбрать элемент в комбо-коробке этой кнопки в соответствии с его строки, индекс, или 32-битное значение.|
|[CMFCToolBarComboButtonButton::SetCenterVert](#setcentervert)|Определяет, по центру ли кнопки комбо-коробки в приложении по центру вертикальны или выровнены с верхней частью панели инструментов.|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Устанавливает высоту выпадающих вниз поле списка.|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Определяет, имеют ли кнопки комбо-коробки в приложении плоский вид.|

## <a name="remarks"></a>Примечания

Чтобы добавить кнопку комбо-коробки в панель инструментов, выполните следующие действия:

1. Зарезервируйте идентификатор ресурсов для кнопки в родительском ресурсе панели инструментов.

2. Постройте `CMFCToolBarComboBoxButton` объект.

3. В обработчике сообщений, который обрабатывает AFX_WM_RESETTOOLBAR сообщение, замените кнопку манекена новой кнопкой комбо-бокса с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Для получения дополнительной информации, [см. Walkthrough: Ввод контроля на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md). Например, кнопку панели инструментов комбо-коробки см.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarComboBoxButton` . Пример показывает, как включить редактирование и комбо-боксы, установить вертикальное положение комбо кнопки коробки в приложении, установить высоту списка поле, когда он упал вниз, установить плоский стиль внешний вид комбо кнопки коробки в приложении, и установить текст в коробке редактирования кнопки комбо окно. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarcomboboxbutton.h

## <a name="cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a>CMFCToolBarComboButton:AddItem

Придаток уникального элемента к ящику списка.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
(в) Текст элемента, чтобы добавить в поле списка.

*dwData*<br/>
(в) Данные, связанные с элементом для добавления в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего элемента в поле списка.

### <a name="remarks"></a>Примечания

Не используйте этот метод при сортировке стиля коробки списка.

Если текст элемента уже находится в поле списка, новые данные сохраняются вместе с существующим элементом. Поиск элемента является чувствительным к делу.

## <a name="cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a>CMFCToolBarComboButton::AddSortedItem

Добавляет элемент в поле списка в порядке, определяемом методом [Сравнения.](#compare)

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
(в) Текст элемента, чтобы добавить в поле списка.

*dwData*<br/>
(в) Данные, связанные с элементом для добавления в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента, который был добавлен в поле списка.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы добавить элементы в поле списка в определенном порядке.

## <a name="cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarComboBoxButton::CanBeStretched

Указывает, может ли изменяться размер кнопки комбо-коробки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE.

## <a name="cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a>CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton

Строит объект [CMFCToolBarComboButtonButton.](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор команды новой кнопки.

*iImage*<br/>
(в) Индекс изображения, связанный с новой кнопкой.

*dwStyle*<br/>
(в) Стиль новой кнопки.

*iWidth*<br/>
(в) Ширина, в пикселях, новой кнопки.

### <a name="remarks"></a>Примечания

Ширина по умолчанию составляет 150 пикселей.

Для списка стилей кнопок панели инструментов смотрите [стили управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)

## <a name="cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData

Удаляет данные, определяемые пользователем.

```
virtual void ClearData();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод ничего не делает. Переопределить этот метод в производном классе, если вы хотите удалить любые данные, определяемые пользователем.

## <a name="cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a>CMFCToolBarComboBoxButton::Сравните

Сравнивает две строки.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>Параметры

*lpszItem1*<br/>
(в) Первая строка для сравнения.

*lpszItem2*<br/>
(в) Вторая строка для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение, указывавое на чувствительную к случаю лексикографическую связь между строками. В следующем списке указаны возможные значения.

|Значение|Описание|
|-----------|-----------------|
|\<0|Первая строка меньше второй.|
|0|Первая строка равна второй.|
|> 0|Первая строка больше второй.|

### <a name="remarks"></a>Примечания

Переопределить этот метод, чтобы изменить способ сортировки элементов в поле списка.

Сравнение является чувствительным к делу.

Этот метод называется только из метода [AddSortedItem.](#addsorteditem)

## <a name="cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarComboButton::CopyFrom

Копирует состояние указанного `CMFCToolBarComboBoxButton` к текущему объекту.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Объект `CMFCToolBarComboBoxButton` исходного кода.

## <a name="cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a>CMFCToolBarComboButtonButton::CreateCombo

Создает новую комбо-коробку для кнопки комбо-бокс.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно кнопки.

*rect*<br/>
(в) Связанный прямоугольник комбо-коробки.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новую комбо-коробку, если метод был успешным; в противном случае, NULL.

## <a name="cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarComboButton::CreateEdit

Создает новую коробку для вставки для кнопки комбо-бокса.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно кнопки.

*rect*<br/>
(в) Связанный прямоугольник новой коробки для реитров.

*dwEditStyle*<br/>
(в) Стиль управления новой коробкой для отсеивок.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новую коробку для отогвечения, если метод был успешным; в противном случае, NULL.

### <a name="remarks"></a>Примечания

Рамочная система вызывает этот метод, когда создает новую коробку для комбо-бокса. Переопределить этот метод, чтобы изменить способ создания [CMFCToolBarComboBoxEdit.](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a>CMFCToolBarComboButton::DeleteItem

Удаляет указанный элемент из окна списка.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Нулевой индекс элемента, который будет удален.

*dwData*<br/>
(в) Данные, связанные с элементом, который будет удален.

*lpszText*<br/>
(в) Текст элемента, который будет удален. Если есть несколько элементов с одним и тем же текстом, первый элемент удаляется.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент был обнаружен и успешно удален; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a>CMFCToolBarComboButton::DuplicateData

Дублирует данные, определяемые пользователем.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод ничего не делает. Переопределить этот метод в производном классе, если вы хотите скопировать любые данные, определяемые пользователем.

## <a name="cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarComboButtonButton:EnableWindow

Позволяет или отстраняет от депонирований и комбо-боксов.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для включения в него и комбо-коробок; FALSE отключить отодевать и комбо-боксы.

### <a name="remarks"></a>Примечания

При отключении элементы управления не могут стать активными и не могут принимать пользовательский ввод.

## <a name="cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton

Копирует строку из строки приложения в указанное меню с помощью идентификатора команды командного окна комбо-бокса.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*менюButton*<br/>
(ваут) Ссылка на кнопку меню.

### <a name="return-value"></a>Возвращаемое значение

Всегда TRUE.

## <a name="cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a>CMFCToolBarComboButton::FindItem

Возвращает индекс первого элемента в поле списка, содержащем указанную строку.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(в) Текст, для которого можно искать в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс товара; или CB_ERR, если элемент не найден.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarComboButton::GetByCmd

Получает указатель на кнопку комбо-бокса с указанным идентификатором команды.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

*bIsFocus*<br/>
(в) TRUE для поиска только сфокусированных кнопок; FALSE для поиска всех кнопок.

### <a name="return-value"></a>Возвращаемое значение

Указатель на кнопку комбо-бокс; или NULL, если кнопка не найдена.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a>CMFCToolBarComboButtonButton::GetComboBox

Возвращает указатель на комбо-бокс в кнопке комбо-бокса.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [класса CComboBox,](../../mfc/reference/ccombobox-class.md) если метод был успешным; в противном случае NULL.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID

Получает идентификатор ресурса меню shortcut для кнопки комбо-бокса.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню ярлыка.

## <a name="cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a>CMFCToolBarComboButton::GetCount

Возвращает количество элементов в поле списка.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в поле списка.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a>CMFCToolBarComboButtonButton::GetCountAll

Получает количество элементов в поле списка кнопки комбо-бокс, которая имеет указанный идентификатор команды.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в поле списка; в противном случае, CB_ERR, если кнопка комбо-бокс не найдена.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a>CMFCToolBarComboButton::GetCurSel

Получает индекс выбранного в настоящее время элемента в поле списка.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного в настоящее время элемента в поле списка; или CB_ERR, если нет элемента выбран.

### <a name="remarks"></a>Примечания

Индекс коробки списка обнуляется с нулевым уровнем.

## <a name="cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a>CMFCToolBarComboButtonButton::GetCurSelall

Возвращает индекс выбранного в настоящее время элемента в поле списка кнопки комбо-бокса с указанным идентификатором команды.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного в настоящее время элемента в поле списка; в противном случае, CB_ERR, если нет пункта выбран или кнопка комбо-бокс не найдена.

### <a name="remarks"></a>Примечания

Индекс коробки списка обнуляется с нулевым уровнем.

## <a name="cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a>CMFCToolBarComboButton::GetEditCtrl

Возвращает указатель в коробку для отсечения в кнопке комбо-бокса.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отославательную к коробке для отосващения, если метод был успешным; в противном случае, NULL.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarComboButton::GetHwnd

Возвращает ручку окна для комбо-коробки.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка окна, или NULL, если комбо-коробка не связана с объектом окна.

## <a name="cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem

Возвращает строку, связанную с элементом в указанном индексе, в поле списка.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Нулевой индекс элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, связанную с элементом; в противном случае, NULL, если параметр индекса является недействительным, или если параметр индекса -1 и нет выбранного элемента в комбо-коробке.

### <a name="remarks"></a>Примечания

Параметр индекса -1 возвращает строку выбранного в настоящее время элемента.

## <a name="cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll

Возвращает строку, связанную с элементом в указанном индексе, в поле списка кнопки комбо-бокса с указанным идентификатором команды.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку элемента, если метод был успешным; в противном случае, NULL, если индекс недействителен, кнопка комбо-бокса не найдена, или если индекс -1 и нет выбранного элемента в комбо-коробке.

### <a name="remarks"></a>Примечания

Значение индекса -1 возвращает строку выбранного в настоящее время элемента.

## <a name="cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData

Возвращает данные, связанные с элементом, в определенном индексе в поле списка.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Данные, связанные с элементом; или 0, если элемент не существует.

### <a name="remarks"></a>Примечания

Параметр индекса -1 возвращает данные, связанные с выбранным в настоящее время элементом.

## <a name="cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll

Возвращает данные, связанные с элементом в определенном индексе, в поле списка кнопки комбо-бокса с определенным идентификатором команды.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Данные, связанные с элементом, если метод был успешным; в противном случае 0, если указанный индекс не действителен, или CB_ERR, если кнопка комбо-бокса не найдена.

### <a name="remarks"></a>Примечания

Параметр индекса -1 возвращает данные, связанные с выбранным в настоящее время элементом.

## <a name="cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll

Возвращает данные, связанные с элементом в определенном индексе, в поле списка кнопки комбо-бокса с определенным идентификатором команды. Эти данные возвращаются в виде указателя.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса.

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Указатель, связанный с элементом, если метод был успешным; в противном случае, -1, если ошибка происходит, или NULL, если кнопка комбо-бокс не найдена.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a>CMFCToolBarComboButton::GetPrompt

Возвращает строку для кнопки комбо-бокса.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка запроса.

### <a name="remarks"></a>Примечания

Этот метод в настоящее время не реализован.

## <a name="cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a>CMFCToolBarComboButton::GetText

Получает текст в коробке редактирования.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текст в коробке редактирования.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a>CMFCToolBarComboButton::GetTextAll

Получает текст в коробке редактирования кнопки комбо-бокс, которая имеет указанный идентификатор команды.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды определенной кнопки комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

Текст в коробке редактирования, если метод был успешным; в противном случае, NULL.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarComboButton::HasFocus

Указывает ли комбо-бокс в настоящее время находится в центре внимания.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если комбо-бокс в настоящее время находится в центре внимания; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод также возвращает TRUE, если любое окно ребенка комбо-бокс в настоящее время находится в центре внимания.

## <a name="cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a>CMFCToolBarComboButton::IsCenterVert

Возвращает вертикальное положение комбо-боксов в приложении.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопки по центру; FALSE, если кнопки выровнены в верхней части.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarComboButton::IsFlatMode

Возвращает плоский стиль внешний вид комбо кнопки коробки в приложении.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если кнопки имеют плоский стиль; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Плоский стиль по умолчанию для кнопок комбо-бокса FALSE.

## <a name="cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarComboBoxButton::Isownerof

Указывает, связана ли указанная ручка с кнопкой комбо-бокса или с одним из ее детей.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка окна.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ручка assocated с кнопкой комбо окно, или один из его детей; в противном случае, FALSE.

## <a name="cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a>CMFCToolBarComboButton::IsRibbonButton

Указывает, находится ли кнопка комбо-бокса на ленточной панели.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда значение FALSE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает FALSE, что означает, что кнопка комбо-бокса никогда не отображается на ленточной панели.

## <a name="cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarComboButton::ОкноВидимо

Возвращает состояние видимости кнопки комбо-бокса.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние видимости кнопки комбо-бокса.

## <a name="cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarComboButtonButton::NotifyCommand

Указывает, обрабатывает ли сообщение кнопку комбо-бокса.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*iNotifyCode*<br/>
(в) Сообщение об уведомлении, связанное с командой.

### <a name="return-value"></a>Возвращаемое значение

Ли кнопка комбо окно обрабатывает сообщение.

## <a name="cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarComboButton::OnAddTo CustomizePage

Вызывается по фреймворку при добавлении кнопки в поле **настраиваемых** диалогов.

```
virtual void OnAddToCustomizePage();
```

## <a name="cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OncalculateSize

Вызывается по фрейму для расчета размера кнопки.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображающее кнопку комбо-бокса.

*размерПо умолчанию*<br/>
(в) Размер по умолчанию кнопки комбо-бокса.

*bHorz*<br/>
(в) Состояние док-станции родительской панели инструментов. TRUE, когда панель инструментов пристыкована горизонтально и FALSE, когда панель инструментов пристыкована вертикально.

### <a name="return-value"></a>Возвращаемое значение

Структура, `SIZE` содержащая размеры кнопки комбо-бокса, в пикселях.

## <a name="cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarComboButton::OnChangeParentWnd

Вызывается рамки, когда кнопка комбо-бокс вставляется в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на новую родительскую панель инструментов.

## <a name="cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarComboButton::OnClick

Вызывается по фреймворку, когда пользователь нажимает кнопку комбо-бокса.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на родительское окно кнопки комбо-бокса.

*bDelay*<br/>
(в) Зарезервировано для использования в производном классе.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод обрабатывает событие; в противном случае, FALSE.

## <a name="cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarComboButton::OnctlColor

Вызывается рамки, когда пользователь изменяет цвет панели родительских инструментов, чтобы установить цвет кнопки комбо-бокса.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображающее кнопку комбо-бокса.

*nCtlColor*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Ручка к кисти, что фреймворк использует для рисования фона кнопки комбо окно.

### <a name="remarks"></a>Примечания

Этот метод также устанавливает цвет текста текста кнопки комбо коробки.

## <a name="cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarComboButton::Ondraw

Вызывается рамки, чтобы нарисовать кнопку комбо-бокс с помощью указанных стилей и опций.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Параметры

*Pdc*<br/>
(в) Контекст устройства, отображаемый кнопкой.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки.

*pImages*<br/>
(в) Коллекция изображений, связанных с кнопкой.

*bHorz*<br/>
(в) Состояние док-станции родительской панели инструментов. TRUE, когда панель инструментов пристыкована горизонтально и FALSE, когда панель инструментов пристыкована вертикально.

*bCustomizeMode*<br/>
(в) Находится ли приложение в режиме настройки.

*bHighlight*<br/>
(в) Следует ли нарисовать кнопку комбо-бокс выделено.

*bDrawBorder*<br/>
(в) Следует ли нарисовать кнопку комбо-бокс с границей.

*bGrayDisabledButtons*<br/>
(в) TRUE для рисования затененных отключенных кнопок; FALSE для использования коллекции изображений с ограниченными возможностями.

## <a name="cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarComboButton::OnDrawOnCustomizeList

Вызывается рамки, чтобы нарисовать кнопку комбо-бокс в панели **команд** **настраиваемый** диалоговые окна.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображающее кнопку комбо-бокса.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки комбо-бокса.

*bВыбор*<br/>
(в) TRUE, если кнопка комбо-бокс выбрана; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ширина, в пикселях, кнопки комбо-бокса.

## <a name="cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarComboButton::OnGlobalFontsChanged

Вызывается рамки, чтобы установить комбо поле кнопки шрифта при изменении шрифта приложения.

```
virtual void OnGlobalFontsChanged();
```

## <a name="cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarComboButton::OnMove

Вызывается фреймворком, чтобы изменить расположение кнопки комбо-бокса при перемещении родительской панели инструментов.

```
virtual void OnMove();
```

## <a name="cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarComboButton::OnShow

Вызывается рамки, когда кнопка комбо-бокс скрыта или отображается.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) Спрячьте или отобразивкнопку кнопки комбо-бокса.

## <a name="cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarComboBoxButton::Onsize

Вызывается фреймворком, чтобы изменить размер кнопки комбо-коробки при изменении размера родительской панели инструментов.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*iSize*<br/>
(в) Новая ширина кнопки комбо-бокса.

## <a name="cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip

Вызывается рамки, когда пользователь изменяет наконечник инструмента для кнопки комбо-бокс.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно для кнопки комбо-бокса.

*iButtonIndex*<br/>
(в) Id кнопки комбо-бокс.

*wndToolTip*<br/>
(в) Наконечник инструмента, чтобы связать с кнопкой комбо-бокс.

*Ул*<br/>
(в) Текст наконечника инструмента.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод обрабатывает событие; в противном случае, FALSE.

## <a name="cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems

Удаляет все элементы из списка и отославает коробки.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Примечания

Удаляет все элементы из коробки списка и отодевать управление комбо-коробкой.

## <a name="cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a>CMFCToolBarComboButton::SelectItem

Выбирает элемент в поле списка.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

*bNotify*<br/>
(в) TRUE, чтобы уведомить кнопку комбо-бокс выбора; в противном случае FALSE.

*dwData*<br/>
(в) Данные, связанные с элементом в поле списка.

*lpszText*<br/>
(в) Текст элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a>CMFCToolBarComboButton::SelectItemAll

Выбирает элемент в поле списка кнопки комбо-бокса с указанным идентификатором команды.

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки комбо-бокса, содержащей поле списка.

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка. Значение -1 удаляет любой текущий выбор в поле списка и очищает окно для отсылки.

*dwData*<br/>
(в) Данные элемента в поле списка.

*lpszText*<br/>
(в) Текст элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize

Читает этот объект из архива или запишет его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
(в, вне) Объект `CArchive` для сериализации.

### <a name="remarks"></a>Примечания

Настройки объекта `CArchive` определяют, читает ли этот метод или записывает в архив.

## <a name="cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarComboBoxButton:SetACCData

Заполняет указанный `CAccessibilityData` объект, используя данные о доступности из кнопки комбо-бокса.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
(в) Родительское окно кнопки комбо-бокса.

*данные*<br/>
(ваут) Объект, `CAccessibilityData` который получает данные о доступности из кнопки комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

## <a name="cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a>CMFCToolBarComboButtonButton::SetCenterVert

Устанавливает вертикальное положение комбо-боксов в приложении.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>Параметры

*bCenterVert*<br/>
(в) TRUE для центра кнопки комбо-бокс в панели инструментов; FALSE выровнять кнопку комбо-бокс ажиотажа к верхней части панели инструментов.

### <a name="remarks"></a>Примечания

По умолчанию кнопки комбо-коробки выровнены к верху.

## <a name="cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID

Устанавливает идентификатор ресурса меню ярлыка для кнопки комбо-бокса.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Параметры

*uiResID*<br/>
(в) Идентификатор ресурса меню ярлыка.

## <a name="cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight

Устанавливает высоту окна списка, когда он упал.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Параметры

*nВысота*<br/>
(в) Высота, в пикселях, из списка поле.

### <a name="remarks"></a>Примечания

Высота по умолчанию составляет 150 пикселей.

## <a name="cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode

Устанавливает плоский стиль внешний вид комбо кнопки коробки в приложении.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Параметры

*bFlat*<br/>
(в) TRUE для плоского стиля внешний вид; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Плоский стиль по умолчанию для кнопок комбо-бокса FALSE.

## <a name="cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle

Устанавливает указанный стиль для кнопки комбо-бокса и перерисовывает элемент управления, если он не отключен.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
(в) Битовая комбинация (OR) стилей панели инструментов.

### <a name="remarks"></a>Примечания

Для списка стилей кнопок панели инструментов смотрите [стили управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)

## <a name="cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a>CMFCToolBarComboBoxButton::SetText

Устанавливает текст в коробке редактирования кнопки комбо-бокс.

```cpp
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(в) Указатель на строку, содержащую текст для редактирования коробки.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::Заменить кнопку](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
