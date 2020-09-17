---
title: Класс CMFCListCtrl
ms.date: 07/30/2019
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 099ec086bd95a1180af4cf5a8f6a9fa7f1d099ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754232"
---
# <a name="cmfclistctrl-class"></a>Класс CMFCListCtrl

Класс `CMFCListCtrl` расширяет функциональность класса [CListCtrl,](../../mfc/reference/clistctrl-class.md) поддерживая расширенную функциональность управления заголовком [класса CMFCHeaderCtrl.](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="syntax"></a>Синтаксис

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCListCtrl:EnableMarkSortedColumn](#enablemarksortedcolumn)|Позволяет пометить отсортированный столбец другим цветом фона.|
|[CMFCListCtrl:EnableMultipleSort](#enablemultiplesort)|Включает несколько сортированных режимов.|
|[CMFCListCtrl:GetHeaderCtrl](#getheaderctrl)|Возвращает ссылку на подчеркнутый элемент управления заголовком.|
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Проверяет, находится ли элемент управления список в режиме нескольких сортировки.|
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Вызывается в рамках, когда он должен сравнить два элемента управления списком.|
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Вызывается по фрейму, когда он должен определить цвет фона отдельной ячейки.|
|[CMFCListCtrl:OnGetCellFont](#ongetcellfont)|Вызывается по фрейму, когда он должен получить шрифт для ячейки обращается.|
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Вызывается по фрейму, когда он должен определить цвет текста отдельной ячейки.|
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет столбец сортировки из списка отсортированных столбцов.|
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Устанавливает текущий отсортированный столбец и порядок сортировки.|
|[CMFCListCtrl::Сортировать](#sort)|Сортирует элемент управления списком.|

## <a name="remarks"></a>Примечания

`CMFCListCtrl`предлагает два усовершенствования для класса [CListCtrl.](../../mfc/reference/clistctrl-class.md) Во-первых, это означает, что сортировка столбцов является доступной опцией, автоматически нарисовав стрелку сортировки на заголовке. Во-вторых, он поддерживает сортировку данных по нескольким столбцам одновременно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCListCtrl` . На примере показано, как создать элемент управления список, вставить столбцы, вставить элементы, установить текст элемента и установить шрифт элемента. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxlistctrl.h

## <a name="cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl:EnableMarkSortedColumn

Отметки отсортированных столбцов с другим цветом фона.

```cpp
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*bMark*<br/>
(в) Параметр Boolean, определяющий, включать ли другой цвет фона.

*bRedraw*<br/>
(в) Параметр Boolean, определяющий, следует ли немедленно перерисовать элемент управления.

### <a name="remarks"></a>Примечания

`EnableMarkSortedColumn`использует метод `CDrawingManager::PixelAlpha` для расчета цвета для отсортированных столбцов. Выбранный цвет основан на обычном цвете фона.

## <a name="cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl:EnableMultipleSort

Позволяет сортировать строки данных в управлении списком несколькими столбцов.

```cpp
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Boolean, который определяет, следует ли включить несколько режим сортировки столбцов.

### <a name="remarks"></a>Примечания

При вранить сортировку на основе нескольких столбцов столбцы имеет иерархию. Строки данных сначала будут отсортированы по основной колонке. Любые эквивалентные значения затем сортируются каждым последующим столбцом на основе приоритета.

## <a name="cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl:GetHeaderCtrl

Возвращает ссылку на элемент управления заголовком.

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый объект [CMFCHeaderCtrl.](../../mfc/reference/cmfcheaderctrl-class.md)

### <a name="remarks"></a>Примечания

Управление заголовком для управления списком — это окно, содержащее заголовки для столбцов. Обычно он расположен прямо над столбцовами.

## <a name="cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort

Проверяет, поддерживает ли элемент управления список сортировку на нескольких столбцах.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент управления списком поддерживает несколько сортировки; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Когда [класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md) поддерживает несколько сортировки, пользователь может сортировать данные в управлении списком несколькими столбцов. Для включения нескольких сортировки позвоните [по телефону CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).

## <a name="cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems

Фрейм вызывает этот метод, когда сравнивает два элемента.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Параметры

*lParam1*<br/>
(в) Первый элемент для сравнения.

*lParam2*<br/>
(в) Второй элемент для сравнения.

*iColumn*<br/>
(в) Индекс столбца, который сортирует этот метод.

### <a name="return-value"></a>Возвращаемое значение

Цель, которая указывает относительное положение двух элементов. Отрицательное значение указывает на то, что первый элемент должен предшествовать второму, положительное значение указывает на то, что первый элемент должен следовать второму, а ноль означает, что эти два элемента эквивалентны.

### <a name="remarks"></a>Примечания

Реализация по умолчанию всегда возвращает 0. Переизобить эту функцию, чтобы обеспечить свой собственный алгоритм сортировки.

## <a name="cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor

Рамочная система вызывает этот метод, когда он должен определить цвет фона отдельной ячейки.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Параметры

*nRow*<br/>
(в) Ряд ячейки, о котором идет речь.

*nКолом*<br/>
(в) Колонка ячейки, о котором идет речь.

### <a name="return-value"></a>Возвращаемое значение

Значение COLOREF, опознавававцветное цвет ячеек.

### <a name="remarks"></a>Примечания

Реализация по `OnGetCellBkColor` умолчанию не использует поставленные параметры ввода и вместо этого просто вызывает. `GetBkColor` Таким образом, по умолчанию, весь элемент управления списка будет иметь тот же цвет фона. Вы можете `OnGetCellBkColor` переопределить в производном классе, чтобы отметить отдельные ячейки с отдельным цветом фона.

## <a name="cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl:OnGetCellFont

Фрейм называет этот метод, когда он получает шрифт для отдельной ячейки.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>Параметры

*nRow*<br/>
(в) Ряд ячейки, о котором идет речь.

*nКолом*<br/>
(в) Колонка ячейки, о котором идет речь.

*dwData*<br/>
(в) Данные, определяемые пользователем. Реализация по умолчанию не использует этот параметр.

### <a name="return-value"></a>Возвращаемое значение

Ручка к шрифту, который используется для текущей ячейки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод возвращает NULL. Все ячейки в элементе управления списком имеют один и тот же шрифт. Переопределить этот метод, чтобы обеспечить различные шрифты для различных ячеек.

## <a name="cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor

Рамочная система вызывает этот метод, когда он должен определить цвет текста отдельной ячейки.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Параметры

*nRow*<br/>
(в) Ряд ячейки, о котором идет речь.

*nКолом*<br/>
(в) Колонка ячейки, о котором идет речь.

### <a name="return-value"></a>Возвращаемое значение

Значение COLOREF, окрашиваемый цвет текста ячейки.

### <a name="remarks"></a>Примечания

По умолчанию этот `GetTextColor` метод вызывает независимо от параметров ввода. Весь элемент управления списка будет иметь тот же цвет текста. Вы можете `OnGetCellTextColor` переопределить в производном классе, чтобы отметить отдельные ячейки с отдельным цветом текста.

## <a name="cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn

Удаляет столбец сортировки из списка отсортированных столбцов.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Колонка для удаления.

### <a name="remarks"></a>Примечания

Этот метод удаляет столбец сортировки из элемента управления заголовком. Он называет [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).

## <a name="cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn

Устанавливает текущий отсортированный столбец и порядок сортировки.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Колонна для сортировки.

*bВозня*<br/>
(в) Булеан, который определяет порядок сортировки.

*bAdd*<br/>
(в) Boolean, который определяет, добавляет ли метод столбец, указанный *iColumn,* в список столбцов сортировки.

### <a name="remarks"></a>Примечания

Этот метод передает входные параметры в управление заголовком с помощью метода [CMFCHeaderCtrl::SetSortColumn.](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)

## <a name="cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::Сортировать

Сортирует элемент управления списком.

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Параметры

*iColumn*<br/>
(в) Колонна для сортировки.

*bВозня*<br/>
(в) Булеан, который определяет порядок сортировки.

*bAdd*<br/>
(в) Boolean, который определяет, добавляет ли этот метод столбец, указанный *iColumn,* в список столбцов сортировки.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
