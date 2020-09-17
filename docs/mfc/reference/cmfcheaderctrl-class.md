---
title: CMFCHeaderCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: 5140d02c5acbbc430c3b4d175da1933c79c702b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752357"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

Класс `CMFCHeaderCtrl` поддерживает сортировку нескольких столбцов в элементе управления заголовком.

## <a name="syntax"></a>Синтаксис

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Формирует объект `CMFCHeaderCtrl`.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Включает или отсвадает *несколько режимов сортировки столбцов* для текущего элемента управления заголовком.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Указывает, не отсортирована ли столбец или отсортирован в порядке восходящего или убывающего.|
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Извлекает нулевой индекс первого отсортированного столбца в элемент управления заголовком.|
|`CMFCHeaderCtrl::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCHeaderCtrl::Восхождение](#isascending)|Указывает, отсортирована ли столбец в элементе управления заголовка в порядке возрастания.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Указывает, является ли родительское окно текущего элемента управления заголовком диалогового окна.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Указывает, находится ли текущий элемент управления заголовком в режиме *сортировки нескольких столбцов.*|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет указанный столбец из списка сортированных столбцов.|
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Устанавливает порядок сортировки указанного столбца в элементуправления заголовка.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Вызывается фректором, чтобы нарисовать столбец управления заголовком.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Вызывается рамки, чтобы нарисовать стрелку сортировки.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Вызывается фректором для заполнения фона столбца управления заголовком.|

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCHeaderCtrl` построить объект класса и как включить несколько способов *сортировки столбцов* для управления текущим заголовком.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Примечания

Класс `CMFCHeaderCtrl` рисует стрелку сортировки на столбце управления заголовком, чтобы указать, что столбец отсортирован. Используйте несколько способов *сортировки столбцов,* если набор столбцов в элементе управления родительского списка [(CMFCListCtrl Class)](../../mfc/reference/cmfclistctrl-class.md)может быть отсортирован одновременно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxheaderctrl.h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a>CMFCHeaderCtrl::CMFCHeaderCtrl

Формирует объект `CMFCHeaderCtrl`.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Примечания

Этот конструктор инициализирует следующие переменные членов к указанным значениям:

|Переменная-член|Значение|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCHeaderCtrl::EnableMultipleSort

Включает или отсвадает *несколько режимов сортировки столбцов* для текущего элемента управления заголовком.

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для включения режима сортировки нескольких столбцов; FALSE отключить несколько режим сортировки столбцов и удалить любые столбцы из списка отсортированных столбцов. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы включить или отключить режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировке, если элемент управления заголовком находится в режиме сортировки нескольких столбцов.

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a>CMFCHeaderCtrl::GetColumnState

Указывает, является ли столбец несортированным или отсортирован в порядке восходящего или убывающего.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Индекс столбца с нулевым уровнем.

### <a name="return-value"></a>Возвращаемое значение

Значение, указывававе состояние сортировки указанного столбца. В следующем списке указаны возможные значения.

|Значение|Описание|
|-----------|-----------------|
|-1|Сортировка в порядке убывания.|
|0|Не отсортировано.|
|1|Сортировка в порядке возрастания.|

### <a name="remarks"></a>Примечания

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a>CMFCHeaderCtrl::GetSortColumn

Извлекает нулевой индекс первого отсортированного столбца в элемент управления заголовком.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс отсортированного столбца или -1, если не найдено отсортированного столбца.

### <a name="remarks"></a>Примечания

Если управление заголовком находится в режиме *сортировки нескольких столбцов* и вы компилировали приложение в режиме отладки, этот метод утверждает и советует использовать метод [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) метод вместо этого. Если элемент управления заголовком находится в нескольких режимах сортировки столбцов и вы компилировали приложение в режиме розничной торговли, этот метод возвращает -1.

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a>CMFCHeaderCtrl::Восхождение

Указывает, отсортирована ли столбец в элементе управления заголовка в порядке возрастания.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если какая-либо колонка в управлении заголовком отсортирована в порядке возрастания; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Значение, которое возвращается этим методом, используется для отображения соответствующей стрелки сортировки на элементе управления заголовком. Используйте метод [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) для настройки порядка сортировки.

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>CMFCHeaderCtrl::IsDialogControl

Указывает, является ли родительское окно текущего элемента управления заголовком диалогового окна.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если родительское окно текущего элемента управления заголовком является диалоговом упаковозам; в противном случае, FALSE.

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCHeaderCtrl::IsMultipleSort

Указывает, находится ли текущий элемент управления заголовком в режиме *сортировки нескольких столбцов.*

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если включен режим сортировки нескольких столбцов; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) для включения или отключать режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировке, если элемент управления заголовком находится в режиме сортировки нескольких столбцов.

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a>CMFCHeaderCtrl::OnDrawItem

Вызывается фректором, чтобы нарисовать столбец управления заголовком.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*iItem*<br/>
(в) Нулевой индекс элемента для рисования.

*rect*<br/>
(в) Ограничивающий прямоугольник элемента для рисования.

*bIsPressed*<br/>
(в) TRUE для рисования элемента в нажатом состоянии; в противном случае, FALSE.

*bIsHighlighted*<br/>
(в) TRUE для рисования элемента в выделенном состоянии; в противном случае, FALSE.

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a>CMFCHeaderCtrl::OnDrawSortArrow

Вызывается рамки, чтобы нарисовать стрелку сортировки.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectArrow*<br/>
(в) Ограничивающий прямоугольник стрелки рода.

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCHeaderCtrl::OnFillBackground

Вызывается фректором для заполнения фона столбца управления заголовком.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

### <a name="remarks"></a>Примечания

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCHeaderCtrl::RemoveSortColumn

Удаляет указанный столбец из списка сортированных столбцов.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Нулевой индекс столбца для удаления.

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCHeaderCtrl::SetSortColumn

Устанавливает порядок сортировки указанного столбца в элементуправления заголовка.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Индекс нулевой основе столбца управления заголовком. Если этот параметр меньше нуля, этот метод удаляет все столбцы из списка столбцов сортировки.

*bВозня*<br/>
(в) Определяет порядок сортировки столбца, который определяет параметр *iColumn.* TRUE установить восходящий порядок; FALSE установить убывающий порядок. Значение по умолчанию — TRUE.

*bAdd*<br/>
(в) TRUE для установки порядка сортировки столбца, который указывает параметр *iColumn.*

Если элемент управления заголовка — это элемент ы в режиме *сортировки нескольких столбцов,* этот метод добавляет указанный столбец в список столбцов сортировки. Используйте [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) для установки режима сортировки нескольких столбцов.

Если не настроен режим сортировки нескольких столбцов и этот метод компилируется в режиме отладки, этот метод утверждает. Если не настроен режим сортировки нескольких столбцов и этот метод компилируется в режиме розничной торговли, этот метод сначала удаляет все столбцы из списка столбцов, а затем добавляет указанный столбец в список.

FALSE сначала удалить все столбцы из списка столбцов сортировки, а затем добавить указанный столбец в список. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

Используйте этот метод для установки порядка сортировки столбца. При необходимости этот метод добавляет столбец в список сортированных столбцов. Управление заголовком использует порядок сортировки, чтобы нарисовать стрелку сортировки, которая указывает вверх или вниз.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)
