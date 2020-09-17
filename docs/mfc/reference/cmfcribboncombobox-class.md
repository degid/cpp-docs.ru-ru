---
title: Класс CMFCRibbonComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: 5846b1c5590a756f0a0820583af3d0b159968ea2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375229"
---
# <a name="cmfcribboncombobox-class"></a>Класс CMFCRibbonComboBox

Класс `CMFCRibbonComboBox` реализует комбо-бокс управления, которые можно добавить в ленту бар, лента панели, или лента всплывающее меню.

## <a name="syntax"></a>Синтаксис

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Строит объект CMFCRibbonComboBox.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonComboBox:AddItem](#additem)|Придаток уникального элемента к ящику списка.|
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Удаляет указанный элемент из окна списка.|
|[CMFCRibbonComboBox:EnableDropDownlistresize](#enabledropdownlistresize)|Определяет, может ли поле списка изменять размер, когда оно падает вниз.|
|[CMFCRibbonComboBox:FindItem](#finditem)|Возвращает индекс первого элемента в поле списка, которое соответствует указанной строке.|
|[CMFCRibbonComboBox::GetCount](#getcount)|Возвращает количество элементов в поле списка.|
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Получает индекс выбранного в настоящее время элемента в поле списка.|
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Получает высоту окна списка, когда окно списка падает.|
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Возвращает размер комбо-коробки, отображаемого в промежуточном режиме.|
|[CMFCRibbonComboBox::GetItem](#getitem)|Возвращает строку, связанную с элементом в указанном индексе, в поле списка.|
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Возвращает данные, связанные с элементом в указанном индексе, в поле списка.|
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Указывает, содержит ли элемент управления окно для отсылки.|
|[CMFCRibbonComboBox:IsResizedropdownlist](#isresizedropdownlist)|Указывает, можно ли переопроизнести поле списка.|
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Вызывается по системе, когда пользователь выбирает элемент в поле списка.|
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Удаляет все элементы из окна списка и очищает коробку для отсеиваний.|
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Выбирает элемент в поле списка.|
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Устанавливает высоту окна списка, когда он упал.|

## <a name="remarks"></a>Примечания

Коробка ленты состоит из ящика списка в сочетании со статической этикеткой или этикеткой, которую может отредактировать пользователь. Вы должны указать, какой тип вы хотите, когда вы создаете ленту комбо-бокс.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCRibbonComboBox` построить объект класса, добавить элемент в комбо-коробку, выбрать элемент в комбо-коробке и добавить комбо-коробку на панель.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncombobox.h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a>CMFCRibbonComboBox:AddItem

Придаток уникального элемента к ящику списка.

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
(в) Строка элемента для добавления.

*dwData*<br/>
(в) Данные, связанные с добавлением элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе придативного элемента.

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox

Формирует объект `CMFCRibbonComboBox`.

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Идентификатор комбо-коробки.

*bHasEditBox*<br/>
(в) ПРАВДА, если вы хотите, чтобы коробка для сна, впределах управления; FALSE в противном случае.

*nWidth*<br/>
(в) Ширина комбо-коробки в пикселях; или -1 для ширины по умолчанию.

*lpszLabel*<br/>
(в) Дисплей этикетки комбо-бокс.

*nИзображение*<br/>
(в) Небольшой индекс изображения комбо-коробки.

### <a name="remarks"></a>Примечания

Ширина по умолчанию составляет 108 пикселей.

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem

Удаляет указанный элемент из окна списка.

```cpp
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
(в) Строка элемента, который будет удален. Если есть несколько элементов с одной строкой, первый элемент удаляется.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанный элемент был удален; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a>CMFCRibbonComboBox:EnableDropDownlistresize

Определяет, может ли поле списка изменять размер, когда оно падает вниз.

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для включения в размер размера; FALSE для оттоговать из размеров.

### <a name="remarks"></a>Примечания

При включении изменения размера поле списка будет изменяться размер, чтобы соответствовать элементам, которые он отображает.

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a>CMFCRibbonComboBox:FindItem

Возвращает индекс первого элемента в поле списка, которое соответствует указанной строке.

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(в) Строка элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента с нулевым уровнем; или -1, если элемент не найден.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a>CMFCRibbonComboBox::GetCount

Возвращает количество элементов в поле списка.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в поле списка, или 0, если поле списка не содержит элементов.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel

Получает индекс выбранного в настоящее время элемента в поле списка.

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе выбранного в настоящее время элемента в поле списка; или -1, если элемент не выбран.

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight

Получает высоту окна списка, когда окно списка падает.

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>Возвращаемое значение

Высота, в пикселях, из списка поле.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize

Возвращает размер комбо-коробки, отображаемого в промежуточном режиме.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства для комбо-коробки.

### <a name="return-value"></a>Возвращаемое значение

Размер комбо-коробки.

### <a name="remarks"></a>Примечания

Возвращается размер основан на размере комбо-коробки, когда он отображает небольшие изображения.

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a>CMFCRibbonComboBox::GetItem

Возвращает строку, связанную с элементом в указанном индексе, в поле списка.

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, связанную с элементом; в противном случае, NULL, если параметр индекса является недействительным, или если параметр индекса -1 и нет пункта, выбранного в комбо-коробке.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData

Возвращает данные, связанные с элементом в указанном индексе, в поле списка.

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Данные, связанные с элементом; или 0, если элемент не существует, или если параметр индекса -1 и нет выбранного элемента в поле списка.

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox

Указывает, содержит ли элемент управления окно для отсылки.

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент управления содержит коробку для отодвитых; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a>CMFCRibbonComboBox:IsResizedropdownlist

Указывает, можно ли переопроизнести поле списка.

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если список поле может быть уменьшена; в противном случае FALSE. [CMFCRibbonComboBox:EnableDropDownlistresize](#enabledropdownlistresize)

### <a name="remarks"></a>Примечания

Вы можете включить изменить размер окна списка с помощью метода [CMFCRibbonComboBox::EnableDropDropListReSize.](#enabledropdownlistresize)

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem

Вызывается по системе, когда пользователь выбирает элемент в поле списка.

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
(в) Индекс выбранного элемента.

### <a name="remarks"></a>Примечания

Переопределить этот метод, если вы хотите обработать выбор ввода пользователя.

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems

Удаляет все элементы из окна списка и очищает коробку для отсеиваний.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a>CMFCRibbonComboBox::SelectItem

Выбирает элемент в поле списка.

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Индекс элемента с нулевым уровнем в поле списка.

*dwData*<br/>
(в) Данные, связанные с элементом в поле списка.

*lpszText*<br/>
(в) Строка элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight

Устанавливает высоту окна списка, когда он упал.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Параметры

*nВысота*<br/>
(в) Высота, в пикселях, из списка поле.

### <a name="remarks"></a>Примечания

Высота по умолчанию составляет 150 пикселей.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)
