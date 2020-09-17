---
title: функции серого цвета и сглаживания точечного рисунка
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: 57f163fd36c0f25508d94a84495fcaf1956e277d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837207"
---
# <a name="gray-and-dithered-bitmap-functions"></a>функции серого цвета и сглаживания точечного рисунка

**Функции серого растрового изображения**

MFC предоставляет две функции для придания растровому изображению вида отключенного элемента управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

|Имя|Описание|
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Рисует серую версию растрового изображения.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Копирует серую версию растрового изображения.|

**Функции сглаживания растрового изображения**

MFC также предоставляет две функции для замены фона растрового изображения сглаженным шаблоном.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "Сравнение сглаженных и оригинальных версий значков")

|Имя|Описание|
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Рисует растровое изображение со сглаженным фоном.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Копирует растровое изображение со сглаженным фоном.|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a> афксдравграйбитмап

Рисует серую версию растрового изображения.

```cpp
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указывает на целевой контекст устройства.

*x*<br/>
Целевая координата по оси x.

*y*<br/>
Целевая координата по оси y.

*rSrc*<br/>
Исходное растровое изображение.

*крбаккграунд*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Растровое изображение, рисуемое с использованием `AfxDrawGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a> афксжетграйбитмап

Копирует серую версию растрового изображения.

```cpp
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Параметры

*rSrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*крбаккграунд*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Растровое изображение, копируемое с использованием `AfxGetGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a> афксдравдисередбитмап

Рисует растровое изображение, заменяя его фон на схему с расстановкой (шашка).

```cpp
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указывает на целевой контекст устройства.

*x*<br/>
Целевая координата по оси x.

*y*<br/>
Целевая координата по оси y.

*rSrc*<br/>
Исходное растровое изображение.

*cr1*<br/>
Один из двух цветов сглаживания, обычно белый.

*cr2*<br/>
Другой цвет сглаживания, обычно светло-серый (COLOR_MENU).

### <a name="remarks"></a>Примечания

Исходное растровое изображение рисуется на целевом контроллере домена с помощью*cr1ного* шаблона ( *CR2*), заменяющего фон растрового изображения. Фон исходного растрового изображения определяется как белый пиксел и все пиксели, соответствующие цвету пикселя в левом верхнем углу точечного рисунка.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "Сравнение сглаженных и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a> афксжетдисередбитмап

Копирует растровое изображение, заменяя его фон на схему с расстановкой (шашка).

```cpp
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Параметры

*rSrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*cr1*<br/>
Один из двух цветов сглаживания, обычно белый.

*cr2*<br/>
Другой цвет сглаживания, обычно светло-серый (COLOR_MENU).

### <a name="remarks"></a>Примечания

Исходное растровое изображение копируется в целевое растровое изображение с помощью автоцветного шаблона (*cr1* и *CR2*), заменяющего фон исходного растрового изображения. Фон исходного растрового изображения определяется как белый пиксел и все пиксели, соответствующие цвету пикселя в левом верхнем углу точечного рисунка.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "вкдисередбитмап")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
