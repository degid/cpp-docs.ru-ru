---
title: CMFCImageEditorEditorДиоредакторКласс
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 23c2a919428689fe107b82041bd87b758ede2bc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367465"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorEditorДиоредакторКласс

Класс `CMFCImageEditorDialog` поддерживает диалоговую коробку редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCImageEditorИсточникДиалог::CMFCImageEditorИсточникДиалог](#cmfcimageeditordialog)|Формирует объект `CMFCImageEditorDialog`.|

## <a name="remarks"></a>Примечания

Класс `CMFCImageEditorDialog` предоставляет диалоговый ящик, который включает в себя:

- Область изображения, используемая для изменения отдельных пикселей на изображении.

- Инструменты рисования для изменения пикселей в области изображения.

- Цветовая палитра для определения цвета, используемого инструментами рисования.

- Область предварительного просмотра, отображая эффект от вашего отправления.

На следующей иллюстрации показан амебьера редактора изображений.

![Диалоговое окно CMFCImageEditorDialog](../../mfc/reference/media/imageedit.png "Диалоговое окно CMFCImageEditorDialog")

Один из способов использования `CMFCImageEditorDialog` объекта `CBitmap` — передать ему изображение, поднисвоее его. Не создавайте большое изображение, поскольку область редактирования изображений имеет ограниченный размер, а логический размер пикселя регулируется в соответствии с этой областью. Вызовите `DoModal` метод, чтобы запустить модальный диалоговый ящик.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afximageeditordialog.h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorИсточникДиалог::CMFCImageEditorИсточникДиалог

Формирует объект `CMFCImageEditorDialog`.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Указатель на изображение.

*pРодитель*<br/>
Указатель на родительское окно текущего окна диалогового редактора изображений.

*nBitsPixel*<br/>
Количество битов, используемых для представления цвета одного пикселя, который также называется глубиной цвета.  Если параметр *nBitsPixel* -1, глубина цвета вытекает из изображения, указанного параметром *pBitmap.* Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Чтобы изменить изображение, передайте указатель `CMFCImageEditorDialog` изображения конструктору. Затем позвоните в `DoModal` метод, чтобы открыть модальный диалоговый ящик. Когда `DoModal` метод возвращается, битная карта содержит новое изображение.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCImageEditorDialog` построить объект класса. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
