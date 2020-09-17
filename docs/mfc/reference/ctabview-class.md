---
title: Класс CTabView
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: ad30cbbf5de195708d2d357a76c38b661d095c2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365920"
---
# <a name="ctabview-class"></a>Класс CTabView

Класс `CTabView` упрощает использование класса управления вкладками [(CMFCTabCtrl)](../../mfc/reference/ctabview-class.md)в приложениях, которые используют архитектуру документов/просмотров MFC.

## <a name="syntax"></a>Синтаксис

```
class CTabbedView : public CView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTabView::AddView](#addview)|Добавляет новое представление в управление вкладок.|
|[CTabView::FindTab](#findtab)|Возвращает индекс заданного представления в элемент управления вкладки.|
|[CTabView::GetActiveView](#getactiveview)|Возвращает указатель в действующее представление,|
|[CTabView::GetTabControl](#gettabcontrol)|Возвращает ссылку на элемент управления вкладки, связанный с представлением.|
|[CTabView::RemoveView](#removeview)|Удаляет представление из управления вкладками.|
|[CTabView::SetActiveView](#setactiveview)|Делает представление активным.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CTabView::IsScrollBar](#isscrollbar)|Вызывается фректовом при создании представления вкладки, чтобы определить, имеет ли представление вкладки общую горизонтальную панель прокрутки.|
|[CTabView::OnActivateView](#onactivateview)|Вызывается фреймворком при том, что представление вкладки становится активным или неактивным.|

## <a name="remarks"></a>Примечания

Этот класс упрощает поставить представление вкладок в приложение документа/просмотра. `CTabView`является `CView`классом, полученным, `CMFCTabCtrl` который содержит встроенный объект. `CTabView`обрабатывает все сообщения, необходимые для поддержки `CMFCTabCtrl` объекта. Просто выведивайте класс `CTabView` и `CView`подключите его к `AddView` приложению, а затем добавьте классы, полученные с помощью метода. Управление вкладками будет отображать эти представления в виде вкладок.

Например, у вас может быть документ, который может быть представлен по-разному: как электронная таблица, диаграмма, отслаиваемая форма и так далее. Можно создавать отдельные представления, рисующие данные по мере необходимости, вставлять их в объект, `CTabView`полученный из вашего, и вводить их без дополнительного кодирования.

[TabbedView Образец: MFC Tabbed](../../overview/visual-cpp-samples.md) View `CTabView`Application иллюстрирует использование .

## <a name="example"></a>Пример

Ниже приводится `CTabView` пример использования в образце TabbedView.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Требования

**Заголовок:** afxTabView.h

## <a name="ctabviewaddview"></a><a name="addview"></a>CTabView::AddView

Добавляет представление в элемент управления вкладками.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Параметры

*pViewClass*<br/>
(в) Указатель на класс времени выполнения вставленного представления.

*strViewLabel*<br/>
(в) Определяет текст вкладки.

*iIndex*<br/>
(в) Определяет положение на нулевой основе, на котором можно вставить представление. Если положение -1, новая вкладка вставляется в конце.

*pContext*<br/>
(в) Указатель на `CCreateContext` вид.

### <a name="return-value"></a>Возвращаемое значение

Индекс представления, если этот метод удается. В противном случае –1.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить представление в элемент управления вкладками, встроенное в кадр.

## <a name="ctabviewfindtab"></a><a name="findtab"></a>CTabView::FindTab

Возвращает индекс заданного представления в элемент управления вкладки.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Параметры

*hWndView*<br/>
(в) Ручка представления.

### <a name="return-value"></a>Возвращаемое значение

Индекс представления, если он найден; в противном случае, -1.

### <a name="remarks"></a>Примечания

Вызов ими функции для получения индекса представления с указанной ручкой.

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a>CTabView::GetActiveView

Возвращает указатель в активную в настоящее время представление.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на активное представление, или NULL, если нет активного представления.

### <a name="remarks"></a>Примечания

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a>CTabView::GetTabControl

Возвращает ссылку на элемент управления вкладки, связанный с представлением.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент управления вкладками, связанный с представлением.

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a>CTabView::IsScrollBar

Вызывается фректовом при создании представления вкладки, чтобы определить, имеет ли представление вкладки общую горизонтальную панель прокрутки.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если представление вкладок должно быть создано вместе с общей панелью прокрутки. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При создании объекта *CTabView* система называет этот метод.

Переизобить метод *IsScrollBar* в классе *CTabView*и вернуть true, если вы хотите создать представление с общим горизонтальным прокруткой.

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a>CTabView::OnActivateView

Вызывается фреймворком при том, что представление вкладки становится активным или неактивным.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Параметры

*Вид*<br/>
(в) Указатель на вид.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределить этот метод `CTabView`в классе, полученном для обработки этого уведомления.

## <a name="ctabviewremoveview"></a><a name="removeview"></a>CTabView::RemoveView

Удаляет представление из управления вкладками.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
(в) Индекс представления для удаления.

### <a name="return-value"></a>Возвращаемое значение

Индекс удаленного представления, если этот метод удается. В противном случае -1.

### <a name="remarks"></a>Примечания

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a>CTabView::SetActiveView

Делает представление активным.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
(в) Индекс с нулевым уровнем представления вкладки.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если указанное представление было сделано активным, FALSE, если индекс представления является недействительным.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см. CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
