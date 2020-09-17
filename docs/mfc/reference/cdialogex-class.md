---
title: Класс CDialogEx
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: 717e560035d42957c16168097577d0c8c589e3c7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753347"
---
# <a name="cdialogex-class"></a>Класс CDialogEx

Класс `CDialogEx` задает цвет фона и фоновое изображение для диалогового окна.

## <a name="syntax"></a>Синтаксис

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Формирует объект `CDialogEx`.|
|`CDialogEx::~CDialogEx`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Задает цвет фона диалогового окна.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Задает фоновое изображение диалогового окна.|

## <a name="remarks"></a>Примечания

Чтобы использовать класс `CDialogEx`, сформируйте класс диалогового окна из класса `CDialogEx` вместо класса `CDialog`.

Изображения диалогового окна хранятся в файле ресурсов. Платформа автоматически удаляет все изображения, загруженные из файла ресурсов. Чтобы программно удалить текущее фоновое изображение, позвоните в метод [CDialogEx::SetBackgroundImage](#setbackgroundimage) или реализуйте `OnDestroy` обработчик событий. При вызове [метода CDialogEx::SetBackgroundImage](#setbackgroundimage) `HBITMAP` передайте параметр в качестве ручки изображения. Объект `CDialogEx` будет распоряжаться изображением и может удалить его, если для флажка `m_bAutoDestroyBmp` установлено значение `TRUE`.

Объект `CDialogEx` может быть родительским объектом [класса CMFCPopupMenu.](../../mfc/reference/cmfcpopupmenu-class.md) Объект [класса CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) `CDialogEx::SetActiveMenu` вызывает метод при открытии [объекта класса CMFCPopupMenu.](../../mfc/reference/cmfcpopupmenu-class.md) После этого `CDialogEx` объект обрабатывает любое событие меню до тех пор, пока объект [класса CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) не будет закрыт.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdialogex.h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a>CDialogEx::CDialogEx

Формирует объект `CDialogEx`.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
(в) Идентификатор ресурса шаблона диалогового окна.

*lpszTemplateName*<br/>
(в) Название ресурса шаблона диалогового окна.

*pРодитель*<br/>
(в) Указатель на родительское окно. Значение по умолчанию — NULL.

*pParentWnd*<br/>
(в) Указатель на родительское окно. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a>CDialogEx::SetBackgroundColor

Задает цвет фона диалогового окна.

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение цвета RGB.

*bRepaint*<br/>
(в) TRUE для немедленного обновления экрана; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a>CDialogEx::SetBackgroundImage

Задает фоновое изображение диалогового окна.

```cpp
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
(в) Ручка к фоновому изображению.

*uiBmpResId*<br/>
(в) Идентификатор ресурса фонового изображения.

*расположение*<br/>
(в) Одно из `CDialogEx::BackgroundLocation` значений, определяющих местоположение изображения. Допустимые значения включают BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT и BACKGR_BOTTOMRIGHT. Значение по умолчанию является BACKGR_TILE.

*bAutoDestroy*<br/>
(в) TRUE для автоматического уничтожения фонового изображения; в противном случае, FALSE.

*bRepaint*<br/>
(в) TRUE, чтобы немедленно перерисовать диалоговую коробку; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

Во втором методе перегрузки синтаксиса, TRUE, если метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Изображение, указанное, не растягивается в соответствии с областью клиента диалогового окна.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[Класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)
