---
title: Класс CMFCRibbonUndoButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 15cf93d39057f0e235779d47cf24d920d80a807d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753491"
---
# <a name="cmfcribbonundobutton-class"></a>Класс CMFCRibbonUndoButton

Класс `CMFCRibbonUndoButton` реализует кнопку списка выпадающих, содержащую самые последние команды пользователей. Пользователи могут выбрать одну или несколько последних команд из списка выпадающих, чтобы либо переделать, либо отменить их.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonUnButton::CMFCRibbonUnButton](#cmfcribbonundobutton)|Строит новый `CMFCRibbonUndoButton` объект с помощью указанного идентификатора команды, текстовой метки и изображений из списка изображений родительского объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonUnButton::AddUndoAction](#addundoaction)|Добавляет новое действие в список действий.|
|[CMFCRibbonUnButton::CleanUpUndoList](#cleanupundolist)|Очищает список действий, который является выпадающим списком.|
|[CMFCRibbonUnДоКнопка:GetActionNumber](#getactionnumber)|Определяет количество элементов, выбранных пользователем из списка выпадающих.|
|[CMFCRibbonUnButton::HasMenu](#hasmenu)|Указывает, содержит ли объект меню.|

## <a name="remarks"></a>Примечания

Класс `CMFCRibbonUndoButton` использует стек для представления списка выпадающих.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCRibbonUndoButton` построить объект класса и добавить новое действие в список действий. Этот фрагмент кода является частью [образца гаджетов ленты.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonundobutton.h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a>CMFCRibbonUnButton::AddUndoAction

Добавляет новое действие в список действий.

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Метка действия, которая будет отображаться в списке выпадающих.

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a>CMFCRibbonUnButton::CleanUpUndoList

Очищает список действий, который является выпадающим списком.

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a>CMFCRibbonUnButton::CMFCRibbonUnButton

Строит новый `CMFCRibbonUndoButton` объект с помощью указанного идентификатора команды, текстовой метки и изображений из списка изображений родительского объекта.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Определяет идентификатор команды.

*lpszText*<br/>
(в) Упомянет текстовую метку кнопки.

*nSmallImageIndex*<br/>
(в) Индекс на нулевой основе в списке изображений родительского объекта для небольшого изображения кнопки.

*nLargeImageIndex*<br/>
(в) Индекс на нулевой основе в списке изображений родительского объекта для большого изображения кнопки.

*hIcon*<br/>
(в) Ручка к значку, которую можно использовать в качестве изображения кнопки.

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a>CMFCRibbonUnДоКнопка:GetActionNumber

Определяет количество элементов, выбранных пользователем из списка выпадающих.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, выбранных пользователем.

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonUnButton::HasMenu

Указывает, содержит ли объект меню.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
