---
title: CMFCToolBarFontSizeComboBox класс
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 6c90bb1ce464a90295e7edb933d87594444c3648
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745323"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox класс

Кнопка панели инструментов, содержащая управление комбо-коробкой, позволяющее пользователю выбрать размер шрифта.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Формирует объект `CMFCToolBarFontSizeComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Возвращает выбранный размер шрифта в twips.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Заполняет список комбо-боксов всеми поддерживаемыми размерами шрифта для указанного шрифта.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Устанавливает размер шрифта в twips.|

## <a name="remarks"></a>Примечания

Вы можете `CMFCToolBarFontSizeComboBox` использовать объект вместе с объектом [класса CMFCToolBarFontComboBox,](../../mfc/reference/cmfctoolbarfontcombobox-class.md) чтобы пользователь мог выбрать шрифт и размер шрифта.

Вы можете добавить кнопку комбо-коробки размера шрифта в панель инструментов так же, как вы добавляете кнопку комбо-коробки шрифта. Для получения дополнительной информации, см [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Когда пользователь выбирает новый шрифт `CMFCToolBarFontComboBox` в объекте, вы можете заполнить комбо-коробку размера шрифта с поддерживаемыми размерами для этого шрифта с помощью метода [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) метод.

## <a name="example"></a>Пример

В следующем примере показано, как использовать `CMFCToolBarFontSizeComboBox` различные методы в классе для настройки `CMFCToolBarFontSizeComboBox` объекта. Пример иллюстрирует, как получить размер шрифта, в twips, из текстового окна, заполнить размер шрифта комбо поле со всеми действительными размерами данного шрифта, и указать размер шрифта в twips. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Формирует объект `CMFCToolBarFontSizeComboBox`.

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize

Извлекает размер шрифта, в twips, из текстового ящика комбо-коробки размера шрифта.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата положительное, то это размер шрифта в twips. Это -1, если текстовый ящик комбо-бокса пуст. Это -2, если происходит ошибка.

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes

Заполняет комбо-коробку размера шрифта со всеми действительными размерами данного шрифта.

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Параметры

*strFontName*<br/>
(в) Упогоняет имя шрифта.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, когда вы хотите синхронизировать между выбором в комбо-коробке шрифта и комбо-коробке размером шрифта, такой как [CMFCToolBarFontComboBox Class.](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize

Округляет указанный размер (в twips) до ближайшего размера в точках, а затем устанавливает выбранный размер в комбо-коробке к этому значению.

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
(в) Установить размер шрифта (в twips) для установки.

### <a name="remarks"></a>Примечания

Вы можете получить предыдущий допустимый размер шрифта позже, позвонив по методу [CMFCToolBarFontSizeComboBox::GetTwipSize.](#gettwipsize)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton класс](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Класс CMFCФонФоФо](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::Заменить кнопку](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
