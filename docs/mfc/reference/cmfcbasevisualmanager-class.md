---
title: Класс Кмфкбасевисуалманажер
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
ms.openlocfilehash: 79a3c0945fdd0df04e9ee52d7bad97dc0847fa91
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834301"
---
# <a name="cmfcbasevisualmanager-class"></a>Класс Кмфкбасевисуалманажер

Слой между производными визуальными руководителями и API темы Windows.

`CMFCBaseVisualManager` загружает UxTheme.dll, если он доступен, и управляет доступом к методам API темы Windows.

Этот класс предназначен только для внутреннего использования.

## <a name="syntax"></a>Синтаксис

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|[Кмфкбасевисуалманажер:: Кмфкбасевисуалманажер](#cmfcbasevisualmanager)|Создает и инициализирует объект `CMFCBaseVisualManager`.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфкбасевисуалманажер::D Равчеккбокс](#drawcheckbox)|Рисует элемент управления "флажок" с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер::D Равкомбобордер](#drawcomboborder)|Рисует границу поля со списком с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер::D Равкомбодропбуттон](#drawcombodropbutton)|Рисует кнопку раскрывающегося списка с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер::D Равпушбуттон](#drawpushbutton)|Рисует кнопку отправки с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер::D Раврадиобуттон](#drawradiobutton)|Рисует элемент управления "переключатель" с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер::D Равстатусбарпрогресс](#drawstatusbarprogress)|Рисует индикатор выполнения в элементе управления "строка состояния" ( [Класс CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)), используя текущую тему Windows.|
|[Кмфкбасевисуалманажер:: Филлребарпане](#fillrebarpane)|Заполняет фон элемента управления главной панели с помощью текущей темы Windows.|
|[Кмфкбасевисуалманажер:: Жетстандардвиндовссеме](#getstandardwindowstheme)|Возвращает текущую тему Windows.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|-|-|
|[Кмфкбасевисуалманажер:: Клеанупсемес](#cleanupthemes)|Вызовы `CloseThemeData` для всех дескрипторов, полученных в `UpdateSystemColors` .|
|[Кмфкбасевисуалманажер:: Упдатесистемколорс](#updatesystemcolors)|Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: окон, панелей инструментов, кнопок и т. д.|

## <a name="remarks"></a>Примечания

Нет необходимости напрямую создавать экземпляры объектов этого класса.

Поскольку это базовый класс для всех визуальных диспетчеров, можно просто вызвать [CMFCVisualManager::-instance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), получить указатель на текущий диспетчер визуальных элементов и получить доступ к методам `CMFCBaseVisualManager` , использующим этот указатель. Однако если необходимо отобразить элемент управления с использованием текущей темы Windows, лучше использовать `CMFCVisualManagerWindows` интерфейс.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кмфкбасевисуалманажер](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксвисуалманажер.h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a> Кмфкбасевисуалманажер:: Клеанупсемес

Вызовы `CloseThemeData` для всех дескрипторов, полученных в `UpdateSystemColors` .

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>Примечания

Только для внутреннего использования.

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a> Кмфкбасевисуалманажер:: Кмфкбасевисуалманажер

Создает и инициализирует объект `CMFCBaseVisualManager`.

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a> Кмфкбасевисуалманажер::D Равчеккбокс

Рисует элемент управления "флажок" с помощью текущей темы Windows.

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства

*rect*<br/>
окне Ограничивающий прямоугольник флажка.

*бхигхлигхтед*<br/>
окне Указывает, выделен ли флажок.

*Nсведения*<br/>
[in] 0 флажок снят, 1 — проверено нормальное

2 для смешанной нормальной.

*бенаблед*<br/>
окне Указывает, включен ли флажок.

*бпрессед*<br/>
окне Указывает, нажата ли галочка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Значения *nсведения* соответствуют следующим стилям флажков.

|Nсведения|Стиль флажка|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a> Кмфкбасевисуалманажер::D Равкомбобордер

Рисует границу поля со списком с помощью текущей темы Windows.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства.

*rect*<br/>
окне Ограничивающий прямоугольник границы поля со списком.

*бдисаблед*<br/>
окне Указывает, отключена ли граница поля со списком.

*бисдроппед*<br/>
окне Указывает, отбрасывается ли граница поля со списком.

*бишигхлигхтед*<br/>
окне Указывает, выделяется ли граница поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a> Кмфкбасевисуалманажер::D Равкомбодропбуттон

Рисует кнопку раскрывающегося списка с помощью текущей темы Windows.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Параметры

*Хозяин*\
окне Указатель на контекст устройства.

*перетаскиваемые*\
окне Ограничивающий прямоугольник кнопки раскрывающегося списка в поле со списком.

*бдисаблед*\
окне Указывает, отключена ли кнопка раскрывающегося списка в поле со списком.

*бисдроппед*\
окне Указывает, раскрывается ли кнопка раскрывающегося списка в поле со списком.

*бишигхлигхтед*\
окне Указывает, выделяется ли кнопка раскрывающегося списка в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a> Кмфкбасевисуалманажер::D Равпушбуттон

Рисует кнопку отправки с помощью текущей темы Windows.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства.

*rect*<br/>
окне Ограничивающий прямоугольник кнопки "Отправить".

*пбуттон*<br/>
окне Указатель на объект [класса кмфкбуттон](../../mfc/reference/cmfcbutton-class.md) для рисования.

*уистате*<br/>
окне Игнорируют. Состояние берется из *пбуттон*.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a> Кмфкбасевисуалманажер::D Раврадиобуттон

Рисует элемент управления "переключатель" с помощью текущей темы Windows.

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства.

*rect*<br/>
окне Ограничивающий прямоугольник переключателя.

*бхигхлигхтед*<br/>
окне Указывает, выделен ли переключатель.

*бчеккед*<br/>
окне Указывает, установлен ли переключатель.

*бенаблед*<br/>
окне Указывает, включен ли переключатель.

*бпрессед*<br/>
окне Указывает, нажата ли переключатель.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a> Кмфкбасевисуалманажер::D Равстатусбарпрогресс

Рисует индикатор выполнения в элементе управления "строка состояния" ( [Класс CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)), используя текущую тему Windows.

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства.

*пстатусбар*<br/>
окне Указатель на строку состояния. Это значение игнорируется.

*ректпрогресс*<br/>
окне Ограничивающий прямоугольник индикатора выполнения в координатах *основного контроллера домена* .

*nProgressTotal*<br/>
окне Общее значение хода выполнения.

*nProgressCurr*<br/>
окне Текущее значение хода выполнения.

*клрбар*<br/>
окне Начальный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветных градиентов.

*clrProgressBarDest*<br/>
окне Конечный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветных градиентов.

*clrProgressText*<br/>
окне Цвет текста хода выполнения. `CMFCBaseVisualManager` игнорирует это. Цвет текста определяется в `afxGlobalData.clrBtnText` .

*bProgressText*<br/>
окне Указывает, следует ли отображать текст хода выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a> Кмфкбасевисуалманажер:: Филлребарпане

Заполняет фон элемента управления главной панели с помощью текущей темы Windows.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства.

*пбар*<br/>
окне Указатель на панель, фон которой должен быть нарисован.

*ректклиент*<br/>
окне Ограничивающий прямоугольник области для заполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если API темы включен; в противном случае — FALSE.

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a> Кмфкбасевисуалманажер:: Жетстандардвиндовссеме

Возвращает текущую тему Windows.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Возвращаемое значение

Выбранный цвет темы Windows. Может быть одним из следующих перечисляемых значений:

- `WinXpTheme_None` -Тема не включена.

- `WinXpTheme_NonStandard` — выбрана нестандартная тема (это означает, что тема выбрана, но отсутствует в списке ниже).

- `WinXpTheme_Blue` -синяя тема (Luna).

- `WinXpTheme_Olive` — Тема-оливковый.

- `WinXpTheme_Silver` -серебристая тема.

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a> Кмфкбасевисуалманажер:: Упдатесистемколорс

Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: окон, панелей инструментов, кнопок и т. д.

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>Примечания

Только для внутреннего использования.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
