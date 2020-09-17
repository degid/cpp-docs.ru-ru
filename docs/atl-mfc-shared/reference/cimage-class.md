---
title: Класс CImage
ms.date: 08/19/2019
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: 6e7197648fd91b2280d406c19c1019ca23f6a470
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684304"
---
# <a name="cimage-class"></a>Класс CImage

`CImage` обеспечивает улучшенную поддержку точечных рисунков, включая возможность загрузки и сохранения изображений в форматах JPEG, GIF, BMP и PNG.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CImage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CImage::CImage](#cimage)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Отображает растровые изображения, имеющие прозрачные или полупрозрачные пиксели.|
|[CImage::Attach](#attach)|Присоединяет HBITMAP к `CImage` объекту. Может использоваться с точечными рисунками разделов, не являющимися DIB, или с точечными рисунками в формате DIB.|
|[CImage::BitBlt](#bitblt)|Копирует точечный рисунок из контекста исходного устройства в этот текущий контекст устройства.|
|[CImage::Create](#create)|Создает растровое изображение раздела DIB и прикрепляет его к ранее созданному `CImage` объекту.|
|[CImage::CreateEx](#createex)|Создает растровое изображение раздела DIB (с дополнительными параметрами) и прикрепляет его к ранее созданному `CImage` объекту.|
|[CImage::Destroy](#destroy)|Отсоединяет точечный рисунок от `CImage` объекта и уничтожает точечный рисунок.|
|[CImage::Detach](#detach)|Отсоединяет точечный рисунок от `CImage` объекта.|
|[CImage::Draw](#draw)|Копирует растровое изображение из исходного прямоугольника в прямоугольник назначения. `Draw` растягивает или сжимает растровое изображение в соответствии с размерами прямоугольника назначения, при необходимости и обрабатывает альфа-смешение и прозрачные цвета.|
|[CImage::GetBits](#getbits)|Получает указатель на фактические значения пикселей точечного рисунка.|
|[CImage::GetBPP](#getbpp)|Извлекает биты на пиксель.|
|[CImage::GetColorTable](#getcolortable)|Получает значения цвета красного, зеленого и синего цветов (RGB) из диапазона записей в таблице цветов.|
|[CImage::GetDC](#getdc)|Возвращает контекст устройства, в который выбрано текущее растровое изображение.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Находит доступные форматы изображений и их описания.|
|[CImage::GetHeight](#getheight)|Получает высоту текущего изображения в пикселях.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Находит доступные форматы изображений и их описания.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Возвращает максимальное число записей в таблице цветов.|
|[CImage::GetPitch](#getpitch)|Получает шаг текущего изображения в байтах.|
|[CImage::GetPixel](#getpixel)|Извлекает цвет пикселя, заданный *x* и *y*.|
|[CImage::GetPixelAddress](#getpixeladdress)|Извлекает адрес заданного пикселя.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Получает расположение прозрачного цвета в таблице цветов.|
|[CImage::GetWidth](#getwidth)|Получает ширину текущего изображения в пикселях.|
|[CImage::IsDIBSection](#isdibsection)|Определяет, является ли присоединенный точечный рисунок разделом DIB.|
|[CImage::IsIndexed](#isindexed)|Указывает, что цвета растрового изображения сопоставлены с индексированной палитрой.|
|[CImage::IsNull](#isnull)|Указывает, загружен ли в данный момент исходный точечный рисунок.|
|[CImage::IsTransparencySupported](#istransparencysupported)|Указывает, поддерживает ли приложение прозрачные точечные рисунки.|
|[CImage::Load](#load)|Загружает изображение из указанного файла.|
|[CImage::LoadFromResource](#loadfromresource)|Загружает изображение из указанного ресурса.|
|[CImage::MaskBlt](#maskblt)|Объединяет цветовые данные исходного и целевого точечных рисунков с помощью заданной операции маски и растрового изображения.|
|[CImage::PlgBlt](#plgblt)|Выполняет перенос битового блока из прямоугольника в исходном контексте устройства в параллелограмм в контексте целевого устройства.|
|[CImage::ReleaseDC](#releasedc)|Освобождает контекст устройства, полученный с помощью [CImage:: GetDC](#getdc).|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Высвобождает ресурсы, используемые GDI+. Должен вызываться для освобождения ресурсов, созданных глобальным `CImage` объектом.|
|[CImage::Save](#save)|Сохраняет изображение в указанном типе. `Save` невозможно задать параметры изображения.|
|[CImage::SetColorTable](#setcolortable)|Задает цветовые значения красного, зеленого и синего RGB в диапазоне записей в таблице цветов раздела DIB.|
|[CImage::SetPixel](#setpixel)|Задает пиксель с указанными координатами в заданном цвете.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Задает пиксель с заданными координатами в качестве цвета по указанному индексу палитры.|
|[CImage::SetPixelRGB](#setpixelrgb)|Устанавливает пиксел с заданными координатами в указанное значение красного, зеленого, синего (RGB).|
|[CImage::SetTransparentColor](#settransparentcolor)|Задает индекс цвета, который будет считаться прозрачным. Только один цвет в палитре может быть прозрачным.|
|[CImage::StretchBlt](#stretchblt)|Копирует растровое изображение из исходного прямоугольника в прямоугольник назначения, растягивание или сжатие растрового изображения в соответствии с размерами прямоугольника назначения, если это необходимо.|
|[CImage::TransparentBlt](#transparentblt)|Копирует растровое изображение с прозрачным цветом из контекста исходного устройства в этот текущий контекст устройства.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CImage::operator HBITMAP](#operator_hbitmap)|Возвращает маркер Windows, присоединенный к `CImage` объекту.|

## <a name="remarks"></a>Примечания

`CImage` принимает точечные рисунки, которые являются либо независимыми от устройства (DIB) разделами, либо нет. Однако можно использовать [CREATE](#create) или [CImage::Load](#load) только с разделами DIB. К объекту можно прикрепить битовую карту, отличную от DIB `CImage` , но нельзя использовать следующие [Attach](#attach) `CImage` методы, поддерживающие только растровые изображения раздела DIB:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Чтобы определить, является ли присоединенный точечный рисунок разделом DIB, вызовите [IsDibSection](#isdibsection).

> [!NOTE]
> В Visual Studio .NET 2003 этот класс хранит количество `CImage` созданных объектов. Всякий раз, когда счетчик переходит к 0, функция `GdiplusShutdown` автоматически вызывается для освобождения ресурсов, используемых GDI+. Это гарантирует, что все `CImage` объекты, созданные непосредственно или опосредованно библиотеками DLL, всегда уничтожаются должным образом и `GdiplusShutdown` не вызываются из `DllMain` .

> [!NOTE]
> Использование глобальных `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объект в библиотеке DLL, вызовите метод [CImage::ReleaseGDIPlus](#releasegdiplus) , чтобы явно освободить ресурсы, используемые GDI+.

`CImage` нельзя выбрать в новый [CDC](../../mfc/reference/cdc-class.md). `CImage` создает собственный контекст HDC для образа. Так как HBITMAP можно выбрать только в один параметр HDC, HBITMAP, связанный с параметром, `CImage` нельзя выбрать в другом HDC. Если требуется CDC, извлеките значение HDC из `CImage` и присвойте ему значение [CDC::FromHandle](../../mfc/reference/cdc-class.md#fromhandle).

## <a name="examples"></a>Примеры

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

При использовании `CImage` в проекте MFC Обратите внимание на то, какие функции-члены в проекте предполагают указатель на объект [CBitmap](../../mfc/reference/cbitmap-class.md) . Если вы хотите использовать `CImage` с такой функцией, как [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), используйте [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), передайте ей `CImage` hBitmap и используйте возвращенное значение `CBitmap*` .

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

С помощью `CImage` у вас есть доступ к реальным битам раздела DIB. Вы можете использовать `CImage` объект в любом месте, где ранее использовался раздел Win32 hBitmap или DIB.

Можно использовать `CImage` из MFC или ATL.

> [!NOTE]
> При создании проекта с помощью необходимо `CImage` определить `CString` перед включением *atlimage.h*. Если в проекте используется ATL без MFC, включите *atlstr.h*, прежде чем включать *atlimage.h*. Если в проекте используется MFC (или проект ATL с поддержкой MFC), включите *афксстр.h* перед включением *atlimage.h*.
>
> Аналогично, перед включением *atlimpl.cpp*необходимо включить *atlimage.h* . Чтобы легко сделать это, включите *atlimage.h* в *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях).

## <a name="requirements"></a>Требования

**Заголовок:** atlimage.h

## <a name="cimagealphablend"></a><a name="alphablend"></a> CImage::AlphaBlend

Отображает растровые изображения, имеющие прозрачные или полупрозрачные пиксели.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Обрабатывайте контекст целевого устройства.

*xDest*<br/>
Координата x в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y (в логических единицах) верхнего левого угла прямоугольника назначения.

*bSrcAlpha*<br/>
Значение альфа-прозрачности, используемое во всем исходном растровом изображении. По умолчанию 0xff (255) предполагает, что изображение является непрозрачным и вы хотите использовать только альфа-значения для каждого пикселя.

*bBlendOp*<br/>
Альфа-смешение для исходного и конечного точечных рисунков, глобальное значение Alpha, применяемое ко всему исходному точечному рисунку, и сведения о форматировании исходного растрового изображения. Исходная и Целевая функции Blend в настоящее время ограничены AC_SRC_OVER.

*pointDest*<br/>
Ссылка на структуру [точек](/windows/win32/api/windef/ns-windef-point) , определяющую левый верхний угол прямоугольника назначения в логических единицах.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения.

*nDestHeight*<br/>
Высота прямоугольника назначения в логических единицах.

*xSrc*<br/>
Логическая Координата по оси x верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Логическая Координата по оси y верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина (в логических единицах) исходного прямоугольника.

*nSrcHeight*<br/>
Высота исходного прямоугольника в логических единицах.

*rectDest*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую назначение.

*rectSrc*<br/>
Ссылка на `RECT` структуру, определяющую источник.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Точечные рисунки альфа-смешения поддерживают смешение цветов для отдельных пикселов.

Если для *bBlendOp* задано значение по умолчанию AC_SRC_OVER, то исходное растровое изображение помещается поверх целевого растрового изображения на основе альфа-значений исходных пикселей.

## <a name="cimageattach"></a><a name="attach"></a> CImage::Attach

Присоединяет *hBitmap* к `CImage` объекту.

```cpp
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Маркер HBITMAP.

*eOrientation*<br/>
Задает ориентацию точечного рисунка. Может применяться один из перечисленных ниже типов.

- DIBOR_DEFAULT Ориентация точечного рисунка определяется операционной системой.

- DIBOR_BOTTOMUP строки точечного рисунка находятся в обратном порядке. Это приводит к тому, что [CImage::GetBits](#getbits) возвращает указатель около конца буфера Bitmap и [CImage::](#getpitch) noreturn для возврата отрицательного числа.

- DIBOR_TOPDOWN линии точечного рисунка находятся сверху вниз. В результате [CImage::GetBits](#getbits) возвращает указатель на первый байт буфера Bitmap и [CImage::GetPitch](#getpitch) noreturn для возврата положительного числа.

### <a name="remarks"></a>Примечания

Точечный рисунок может быть либо точечным рисунком раздела, не соdib, либо точечным рисунком раздела DIB. Список методов, которые можно использовать только с точечными рисунками в разделе DIB, см. в разделе [IsDibSection](#isdibsection) .

## <a name="cimagebitblt"></a><a name="bitblt"></a> CImage::BitBlt

Копирует точечный рисунок из контекста исходного устройства в этот текущий контекст устройства.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Целевой параметр HDC.

*xDest*<br/>
Логическая Координата по оси x верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Логическая Координата по оси y верхнего левого угла прямоугольника назначения.

*dwROP*<br/>
Выполняемая растровая операция. Коды операций с растровым набором определяют способ объединения битов источника, назначения и шаблона (как определено текущей выбранной кистью) для формирования назначения. Список других кодов точечных операций и их описание см. в разделе [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) в Windows SDK.

*pointDest*<br/>
Структура [точек](/windows/win32/api/windef/ns-windef-point) , указывающая верхний левый угол прямоугольника назначения.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения.

*nDestHeight*<br/>
Высота прямоугольника назначения в логических единицах.

*xSrc*<br/>
Логическая Координата по оси x верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Логическая Координата по оси y верхнего левого угла исходного прямоугольника.

*rectDest*<br/>
Структура [Rect](/windows/win32/api/windef/ns-windef-rect) , указывающая конечный прямоугольник.

*pointSrc*<br/>
`POINT` cтруктура, указывающая верхний левый угол исходного прямоугольника.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) в Windows SDK.

## <a name="cimagecimage"></a><a name="cimage"></a> CImage::CImage

Формирует объект `CImage`.

```
CImage() throw();
```

### <a name="remarks"></a>Примечания

После создания объекта вызовите [Create](#create), [Load](#load), [LoadFromResource](#loadfromresource)или [Attach](#attach), чтобы присоединить точечный рисунок к объекту.

**Примечание** . В Visual Studio этот класс хранит количество `CImage` созданных объектов. Всякий раз, когда счетчик переходит к 0, функция `GdiplusShutdown` автоматически вызывается для освобождения ресурсов, используемых GDI+. Это гарантирует, что все `CImage` объекты, созданные непосредственно или опосредованно библиотеками DLL, всегда уничтожаются должным образом и `GdiplusShutdown` не вызываются из DllMain.

Использование глобальных `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объект в библиотеке DLL, вызовите метод [CImage::ReleaseGDIPlus](#releasegdiplus), чтобы явно освободить ресурсы, используемые GDI+.

## <a name="cimagecreate"></a><a name="create"></a> CImage::Create

Создает `CImage` точечный рисунок и присоединяет его к ранее созданному `CImage` объекту.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина `CImage` точечного рисунка в пикселях.

*nHeight*<br/>
Высота `CImage` точечного рисунка в пикселях. Если *nHeight* является положительным, то точечный рисунок имеет значение DIB, а его источник — в левом нижнем углу. Если *nHeight* является отрицательным, точечный рисунок является верхним (DIB) и его источником является верхний левый угол.

*nBPP*<br/>
Число битов на пиксель точечного рисунка. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромных точечных рисунков или масок.

*dwFlags*<br/>
Указывает, имеет ли растровый объект альфа-канал. Может быть сочетанием нуля или более следующих значений:

- *createAlphaChannel* Может использоваться, только если *nBPP* имеет значение 32, а *eCompression* — BI_RGB. Если этот параметр задан, созданный образ имеет альфа-значение (прозрачное) для каждого пикселя, которое хранится в 4-байтовом изображении каждого пикселя (не используется в неalpha 32 бит). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

> [!NOTE]
> В вызовах [CImage::Draw](#draw)изображения с альфа-каналом автоматически смешиваются с назначением.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cimagecreateex"></a><a name="createex"></a> CImage::CreateEx

Создает `CImage` точечный рисунок и присоединяет его к ранее созданному `CImage` объекту.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина `CImage` точечного рисунка в пикселях.

*nHeight*<br/>
Высота `CImage` точечного рисунка в пикселях. Если *nHeight* является положительным, то точечный рисунок имеет значение DIB, а его источник — в левом нижнем углу. Если *nHeight* является отрицательным, точечный рисунок является верхним (DIB) и его источником является верхний левый угол.

*nBPP*<br/>
Число битов на пиксель точечного рисунка. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромных точечных рисунков или масок.

*eCompression*<br/>
Указывает тип сжатия для сжатого нижнего точечного рисунка (файлы DIB, расположенные сверху вниз, не могут быть сжаты). Может иметь одно из следующих значений:

- BI_RGB Формат не сжат. Указание этого значения при вызове `CImage::CreateEx` эквивалентно вызову `CImage::Create` .

- BI_BITFIELDS формат не сжат, а таблица цветов состоит из трех цветовых масок DWORD, которые задают красный, зеленый и синий компоненты соответственно для каждого пикселя. Это допустимо при использовании точечных рисунков размером 16 и 32 бит/с.

*pdwBitfields*<br/>
Используется только в том случае, если *eCompression* имеет значение BI_BITFIELDS, в противном случае оно должно быть равно null. Указатель на массив из трех битовых масок DWORD, указывающий, какие биты каждого пикселя используются для красного, зеленого и синего компонентов цвета соответственно. Сведения об ограничениях для битовых полей см. в разделе [BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) в Windows SDK.

*dwFlags*<br/>
Указывает, имеет ли растровый объект альфа-канал. Может быть сочетанием нуля или более следующих значений:

- *createAlphaChannel* Может использоваться, только если *nBPP* имеет значение 32, а *eCompression* — BI_RGB. Если этот параметр задан, созданный образ имеет альфа-значение (прозрачное) для каждого пикселя, которое хранится в 4-байтовом изображении каждого пикселя (не используется в неalpha 32 бит). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

   > [!NOTE]
   > В вызовах [CImage::Draw](#draw)изображения с альфа-каналом автоматически смешиваются с назначением.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнено успешно. В противном случае — FALSE.

### <a name="example"></a>Пример

В следующем примере создается точечный рисунок 100x100 пикселей с использованием 16 бит для кодирования каждого пикселя. В заданном 16-разрядном пикселе биты 0-3 кодируются красным компонентом, биты 4-7 кодируются зеленым цветом, а биты 8-11 — синим. Остальные 4 бита не используются.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a> CImage::Destroy

Отсоединяет точечный рисунок от `CImage` объекта и уничтожает точечный рисунок.

```cpp
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a> CImage::Detach

Отсоединяет точечный рисунок от `CImage` объекта.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Маркер отсоединенного точечного рисунка или значение NULL, если растровое изображение не присоединено.

## <a name="cimagedraw"></a><a name="draw"></a> CImage::Draw

Копирует точечный рисунок из контекста исходного устройства в текущий контекст устройства.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Маркер контекста целевого устройства.

*xDest*<br/>
Координата x в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y (в логических единицах) верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения.

*nDestHeight*<br/>
Высота прямоугольника назначения в логических единицах.

*xSrc*<br/>
Координата x в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата по оси y (в логических единицах) верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина (в логических единицах) исходного прямоугольника.

*nSrcHeight*<br/>
Высота исходного прямоугольника в логических единицах.

*rectDest*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую назначение.

*rectSrc*<br/>
Ссылка на `RECT` структуру, определяющую источник.

*pointDest*<br/>
Ссылка на структуру [POINT](/windows/win32/api/windef/ns-windef-point) , определяющую левый верхний угол прямоугольника назначения в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Draw` выполняет ту же операцию, что и [StretchBlt](#stretchblt), если только изображение не содержит прозрачный цвет или альфа-канал. В этом случае `Draw` выполняет ту же операцию, что и [TransparentBlt](#transparentblt) или [AlphaBlend](#alphablend) , как требуется.

Для версий `Draw` , не указывающих исходный прямоугольник, по умолчанию используется все исходное изображение. Для версии `Draw` , которая не задает размер конечного прямоугольника, размер исходного изображения является значением по умолчанию, а растяжение или сжатие не происходит.

## <a name="cimagegetbits"></a><a name="getbits"></a> CImage::GetBits

Получает указатель на фактические битовые значения заданного пикселя в точечном рисунке.

```cpp
void* GetBits() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер точечного рисунка. Если точечный рисунок имеет значение DIB, указатель находится рядом с концом буфера. Если точечный рисунок является верхним (DIB), указатель указывает на первый байт буфера.

### <a name="remarks"></a>Примечания

Используя этот указатель вместе со значением, возвращаемым методом « [GetPitch](#getpitch)», можно размещать и изменять отдельные пикселы в изображении.

> [!NOTE]
> Этот метод поддерживает только точечные рисунки раздела DIB; Следовательно, вы обращаетесь к пикселам `CImage` объекта так же, как и к пикселям раздела DIB. Возвращаемый указатель указывает на пиксель в положении (0, 0).

## <a name="cimagegetbpp"></a><a name="getbpp"></a> CImage::GetBPP

Извлекает значение бит на пиксель.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число битов на пиксель.

### <a name="remarks"></a>Примечания

Это значение определяет количество битов, определяющих каждый пиксель, и максимальное число цветов в точечном рисунке.

Биты на пиксель обычно имеют значение 1, 4, 8, 16, 24 или 32. `biBitCount`Дополнительные сведения об этом значении см. в описании члена [BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) в Windows SDK.

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a> CImage::GetColorTable

Получает значения цвета красного, зеленого и синего цветов (RGB) из диапазона записей в палитре раздела DIB.

```cpp
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Индекс таблицы цветов первой записи для извлечения.

*nColors*<br/>
Число записей в таблице цветов для извлечения.

*prgbColors*<br/>
Указатель на массив структур [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) для получения записей таблицы цветов.

## <a name="cimagegetdc"></a><a name="getdc"></a> CImage::GetDC

Извлекает контекст устройства, в котором в данный момент выбран образ.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для контекста устройства.

### <a name="remarks"></a>Примечания

Для каждого вызова необходимо `GetDC` последующий вызов к [ReleaseDC](#releasedc).

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a> CImage::GetExporterFilterString

Находит форматы изображений, доступные для сохранения изображений.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Параметры

*strExporters*<br/>
Ссылка на объект `CSimpleString`. Дополнительные сведения см. в разделе **Примечания** .

*aguidFileTypes*<br/>
Массив идентификаторов GUID, каждый элемент которого соответствует одному из типов файлов в строке. В примере, приведенном ниже *pszAllFilesDescription* , *aguidFileTypes*[0] GUID_NULL, а остальные значения массива — форматы файлов изображений, поддерживаемые текущей операционной системой.

> [!NOTE]
> Полный список констант см. в подразделе **константы формата файла изображения** в Windows SDK.

*pszAllFilesDescription*<br/>
Если этот параметр не равен NULL, строка фильтра будет содержать один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущее значение *pszAllFilesDescription* для его описания и принимает файлы любого расширения, поддерживаемые любым другим средством экспорта в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовых флагов, указывающих, какие типы файлов следует исключить из списка. Допустимые флаги:

- `excludeGIF` = 0x01 исключает GIF-файлы.

- `excludeBMP` = 0x02 исключает файлы BMP (точечные рисунки Windows).

- `excludeEMF` = 0x04 исключает файлы EMF (расширенный метафайл).

- `excludeWMF` = 0x08 исключает файлы метафайла WMF (Windows Metafile).

- `excludeJPEG` = 0x10 исключает файлы JPEG.

- `excludePNG` = 0x20 исключает PNG-файлы.

- `excludeTIFF` = 0x40 исключает TIFF-файлы.

- `excludeIcon` = 0x80 исключает файлы ICO (значок Windows).

- `excludeOther` = 0x80000000 исключает все другие типы файлов, не указанные в списке выше.

- `excludeDefaultLoad` = 0 для загрузки; все типы файлов включены по умолчанию

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Для сохранения эти файлы исключаются по умолчанию, так как обычно они имеют особые требования.

*chSeparator*<br/>
Разделитель, используемый между форматами изображения. Дополнительные сведения см. в разделе **Примечания** .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вы можете передать полученную строку формата в объект MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) , чтобы предоставить расширения файлов доступных форматов изображений в диалоговом окне файл сохранить как.

Параметр *strExporter* имеет формат:

файл description0&#124;\* . ext0&#124;filedescription1&#124;\* . EXT1&#124;... Описание файла *n*&#124;\* . ext *n*&#124;&#124;

где "&#124;" — это символ-разделитель, заданный параметром `chSeparator` . Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Используйте разделитель по умолчанию "&#124;", если передать эту строку в `CFileDialog` объект MFC. Используйте разделитель null "\ 0", если передать эту строку в диалоговое окно "Сохранение файла".

## <a name="cimagegetheight"></a><a name="getheight"></a> CImage::GetHeight

Получает высоту изображения в пикселях.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота изображения в пикселях.

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a> CImage::GetImporterFilterString

Находит форматы изображений, доступные для загрузки изображений.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Параметры

*strImporters*<br/>
Ссылка на объект `CSimpleString`. Дополнительные сведения см. в разделе **Примечания** .

*aguidFileTypes*<br/>
Массив идентификаторов GUID, каждый элемент которого соответствует одному из типов файлов в строке. В примере, приведенном ниже *pszAllFilesDescription* , *aguidFileTypes*[0] GUID_NULL с остальными значениями массива — форматы файлов изображений, поддерживаемые текущей операционной системой.

> [!NOTE]
> Полный список констант см. в подразделе **константы формата файла изображения** в Windows SDK.

*pszAllFilesDescription*<br/>
Если этот параметр не равен NULL, строка фильтра будет содержать один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущее значение *pszAllFilesDescription* для его описания и принимает файлы любого расширения, поддерживаемые любым другим средством экспорта в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовых флагов, указывающих, какие типы файлов следует исключить из списка. Допустимые флаги:

- `excludeGIF` = 0x01 исключает GIF-файлы.

- `excludeBMP` = 0x02 исключает файлы BMP (точечные рисунки Windows).

- `excludeEMF` = 0x04 исключает файлы EMF (расширенный метафайл).

- `excludeWMF` = 0x08 исключает файлы метафайла WMF (Windows Metafile).

- `excludeJPEG` = 0x10 исключает файлы JPEG.

- `excludePNG` = 0x20 исключает PNG-файлы.

- `excludeTIFF` = 0x40 исключает TIFF-файлы.

- `excludeIcon` = 0x80 исключает файлы ICO (значок Windows).

- `excludeOther` = 0x80000000 исключает все другие типы файлов, не указанные в списке выше.

- `excludeDefaultLoad` = 0 для загрузки; все типы файлов включены по умолчанию

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Для сохранения эти файлы исключаются по умолчанию, так как обычно они имеют особые требования.

*chSeparator*<br/>
Разделитель, используемый между форматами изображения. Дополнительные сведения см. в разделе **Примечания** .

### <a name="remarks"></a>Примечания

Вы можете передать полученную строку формата в объект MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) , чтобы предоставить расширения файлов доступных форматов изображений в диалоговом окне **открытия файла** .

Параметр *strImporter* имеет формат:

файл description0&#124;\* . ext0&#124;filedescription1&#124;\* . EXT1&#124;... Описание файла *n*&#124;\* . ext *n*&#124;&#124;

где "&#124;" — это символ-разделитель, заданный параметром *chSeparator*. Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Используйте разделитель по умолчанию "&#124;", если передать эту строку в `CFileDialog` объект MFC. Используйте разделитель null "\ 0", если вы передали эту строку в диалоговое окно **открытия общего файла** .

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a> CImage::GetMaxColorTableEntries

Возвращает максимальное число записей в таблице цветов.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число записей в таблице цветов.

### <a name="remarks"></a>Примечания

Этот метод поддерживает только растровые изображения раздела DIB.

## <a name="cimagegetpitch"></a><a name="getpitch"></a> CImage::GetPitch

Получает шаг изображения.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Шаг изображения. Если возвращаемое значение отрицательное, то битовая карта имеет формат DIB, а его источник — в левом нижнем углу. Если возвращаемое значение положительное, то точечный рисунок является верхним (DIB) и его источником является верхний левый угол.

### <a name="remarks"></a>Примечания

Шаг — это расстояние в байтах между двумя адресами памяти, представляющими начало одной строки точечного рисунка, и начало следующей строки. Так как шаг измеряется в байтах, шаг изображения помогает определить формат пикселей. Шаг может также включать дополнительную память, зарезервированную для точечного рисунка.

Используйте `GetPitch` WITH [GetBits](#getbits) , чтобы найти отдельные пиксели изображения.

> [!NOTE]
> Этот метод поддерживает только растровые изображения раздела DIB.

## <a name="cimagegetpixel"></a><a name="getpixel"></a> CImage::GetPixel

Получает цвет пикселя в расположении, заданном как *x* и *y*.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Координата x пикселя.

*y*<br/>
Координата y пикселя.

### <a name="return-value"></a>Возвращаемое значение

Значение красного, зеленого, синего (RGB) пикселя. Если пиксель находится за пределами текущей вырезанной области, возвращаемое значение будет CLR_INVALID.

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a> CImage::GetPixelAddress

Извлекает точный адрес пикселя.

```cpp
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Координата x пикселя.

*y*<br/>
Координата y пикселя.

### <a name="remarks"></a>Примечания

Адрес определяется в соответствии с координатами пиксела, шагом точечного рисунка и битами на пиксель.

Для форматов, имеющих менее 8 бит на пиксель, этот метод возвращает адрес байта, содержащего пиксель. Например, если формат изображения содержит 4 бита на пиксель, то `GetPixelAddress` возвращает адрес первого пикселя в байте, и необходимо вычислить значение в 2 пикселах на байт.

> [!NOTE]
> Этот метод поддерживает только растровые изображения раздела DIB.

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a> CImage::GetTransparentColor

Получает индексированное расположение прозрачного цвета в палитре цветов.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Индекс прозрачного цвета.

## <a name="cimagegetwidth"></a><a name="getwidth"></a> CImage::GetWidth

Получает ширину изображения в пикселях.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина точечного рисунка в пикселях.

## <a name="cimageisdibsection"></a><a name="isdibsection"></a> CImage::IsDIBSection

Определяет, является ли присоединенный точечный рисунок разделом DIB.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если присоединенный точечный рисунок является разделом DIB. В противном случае — FALSE.

### <a name="remarks"></a>Примечания

Если точечный рисунок не является разделом DIB, то нельзя использовать следующие `CImage` методы, поддерживающие только точечные рисунки раздела DIB:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a> CImage::IsIndexed

Определяет, сопоставлены ли пикселы растрового изображения с цветовой палитрой.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE при индексировании; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE только в том случае, если точечный рисунок имеет глубину 8 бит (256 цветов) или меньше.

> [!NOTE]
> Этот метод поддерживает только растровые изображения раздела DIB.

## <a name="cimageisnull"></a><a name="isnull"></a> CImage::IsNull

Определяет, загружен ли точечный рисунок в данный момент.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если точечный рисунок в данный момент не загружен. в противном случае — FALSE.

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a> CImage::IsTransparencySupported

Указывает, поддерживает ли приложение прозрачные точечные рисунки.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текущая платформа поддерживает прозрачность. В противном случае 0.

### <a name="remarks"></a>Примечания

Если возвращаемое значение не равно нулю и поддерживается прозрачность, вызов [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt)или [Draw](#draw) будет работать с прозрачными цветами.

## <a name="cimageload"></a><a name="load"></a> CImage::Load

Загружает изображение.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pszFileName*<br/>
Указатель на строку, содержащую имя загружаемого файла изображения.

*pStream*<br/>
Указатель на поток, содержащий имя загружаемого файла изображения.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Загружает образ, заданный параметром *pszFileName* или *pStream*.

Допустимые типы изображений: BMP, GIF, JPEG, PNG и TIFF.

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a> CImage::LoadFromResource

Загружает изображение из ресурса ТОЧЕЧного рисунка.

```cpp
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработчик экземпляра модуля, содержащего загружаемый образ.

*pszResourceName*<br/>
Указатель на строку, содержащую имя ресурса, который необходимо загрузить.

*nIDResource*<br/>
Идентификатор загружаемого ресурса.

### <a name="remarks"></a>Примечания

Ресурс должен иметь тип BITMAP.

## <a name="cimagemaskblt"></a><a name="maskblt"></a> CImage::MaskBlt

Объединяет цветовые данные исходного и целевого точечных рисунков с помощью заданной операции маски и растрового изображения.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Обработчик для модуля, исполняемый объект которого содержит ресурс.

*xDest*<br/>
Координата x в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y (в логических единицах) верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения и исходного растрового изображения.

*nDestHeight*<br/>
Высота (в логических единицах) прямоугольника назначения и исходного растрового изображения.

*xSrc*<br/>
Логическая Координата по оси x верхнего левого угла исходного растрового изображения.

*ySrc*<br/>
Логическая Координата по оси y верхнего левого угла исходного растрового изображения.

*hbmMask*<br/>
Обрабатывайте растровую маску монохромной маски в сочетании с цветовым рисунком в контексте исходного устройства.

*xMask*<br/>
Горизонтальное смещение точечного рисунка маски, заданное параметром *hbmMask* .

*yMask*<br/>
Вертикальное смещение точечного рисунка маски, заданное параметром *hbmMask* .

*dwROP*<br/>
Задает как передний, так и фоновый ternary растровые коды операций, используемые методом для управления сочетанием исходных и целевых данных. Код фоновой операции растрового изображения хранится в байтовом высоком порядке в слове этого значения. код растровой операции переднего плана хранится в байте нижнего порядка в слове с высоким порядком в этом значении. Младшее слово этого значения игнорируется и должно быть равно нулю. Обсуждение переднего плана и фона в контексте этого метода см `MaskBlt` . в разделе Windows SDK. Список общих кодов растровых операций см `BitBlt` . в разделе Windows SDK.

*rectDest*<br/>
Ссылка на `RECT` структуру, определяющую назначение.

*pointSrc*<br/>
`POINT`Структура, указывающая верхний левый угол исходного прямоугольника.

*pointMask*<br/>
`POINT`Структура, указывающая верхний левый угол битовой карты маски.

*pointDest*<br/>
Ссылка на `POINT` структуру, определяющую левый верхний угол прямоугольника назначения в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха; в противном случае — 0

### <a name="remarks"></a>Примечания

Этот метод применим только к Windows NT версии 4,0 и более поздним.

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a> CImage::operator HBITMAP

Этот оператор используется для получения подключенного маркера GDI Windows `CImage` объекта. Этот оператор является оператором приведения, который поддерживает прямое использование объекта HBITMAP.

## <a name="cimageplgblt"></a><a name="plgblt"></a> CImage::PlgBlt

Выполняет перенос битового блока из прямоугольника в исходном контексте устройства в параллелограмм в контексте целевого устройства.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Маркер контекста целевого устройства.

*pPoints*<br/>
Указатель на массив из трех точек в логическом пространстве, который определяет три угла целевого параллелограмма. Левый верхний угол исходного прямоугольника сопоставляется с первой точкой в этом массиве, правом верхнем углу второй точки в этом массиве, а нижний левый угол — с третьей точкой. Правый нижний угол исходного прямоугольника сопоставляется с неявной четвертой точкой в параллелограмм.

*hbmMask*<br/>
Маркер необязательного нехромного точечного рисунка, который используется для маскирования цветов исходного прямоугольника.

*xSrc*<br/>
Координата x в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата по оси y (в логических единицах) верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина (в логических единицах) исходного прямоугольника.

*nSrcHeight*<br/>
Высота исходного прямоугольника в логических единицах.

*xMask*<br/>
Координата по оси x верхнего левого угла монохромного изображения.

*yMask*<br/>
Координата по оси y верхнего левого угла монохромного изображения.

*rectSrc*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , указывающую координаты исходного прямоугольника.

*pointMask*<br/>
Структура [точек](/windows/win32/api/windef/ns-windef-point) , указывающая верхний левый угол битовой карты маски.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха; в противном случае — 0

### <a name="remarks"></a>Примечания

Если *hbmMask* определяет допустимое монохромное растровое изображение, `PlgBit` использует это растровое изображение для маскирования битов цветовых данных из исходного прямоугольника.

Этот метод применим только к Windows NT версии 4,0 и более поздним. Более подробные сведения см. в разделе [PlgBlt](/windows/win32/api/wingdi/nf-wingdi-plgblt) в Windows SDK.

## <a name="cimagereleasedc"></a><a name="releasedc"></a> CImage::ReleaseDC

Освобождает контекст устройства.

```cpp
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Примечания

Так как в контекст устройства можно выбрать только одно растровое изображение, необходимо вызвать метод `ReleaseDC` для каждого вызова [GetDC](#getdc).

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a> CImage::ReleaseGDIPlus

Высвобождает ресурсы, используемые GDI+.

```cpp
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Примечания

Этот метод должен вызываться для освобождения ресурсов, выделенных глобальным `CImage` объектом. См. раздел [CImage::CImage](#cimage).

## <a name="cimagesave"></a><a name="save"></a> CImage::Save

Сохраняет изображение в указанный поток или файл на диске.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на объект IStream COM, содержащий данные образа файла.

*pszFileName*<br/>
Указатель на имя файла для изображения.

*guidFileType*<br/>
Тип файла для сохранения образа. Может применяться один из перечисленных ниже типов.

- `ImageFormatBMP` Несжатое растровое изображение.

- `ImageFormatPNG` Сжатый PNG-образ.

- `ImageFormatJPEG` Сжатое изображение JPEG.

- `ImageFormatGIF` Сжатое изображение в формате GIF.

> [!NOTE]
> Полный список констант см. в подразделе **константы формата файла изображения** в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы сохранить изображение, используя указанные имя и тип. Если параметр *guidFileType* не включен, то для определения формата образа будет использоваться расширение файла имени файла. Если расширение не указано, образ будет сохранен в формате BMP.

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a> CImage::SetColorTable

Задает значения цвета красного, зеленого и синего (RGB) для диапазона записей в палитре раздела DIB.

```cpp
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Индекс таблицы цветов первой заданной записи.

*nColors*<br/>
Число заданных записей в таблице цветов.

*prgbColors*<br/>
Указатель на массив структур [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) для задания записей в таблице цветов.

### <a name="remarks"></a>Примечания

Этот метод поддерживает только растровые изображения раздела DIB.

## <a name="cimagesetpixel"></a><a name="setpixel"></a> CImage::SetPixel

Задает цвет пикселя в заданном месте точечного рисунка.

```cpp
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение устанавливаемого пикселя.

*y*<br/>
Вертикальное расположение устанавливаемого пикселя.

*color*<br/>
Цвет, в который задается пиксель.

### <a name="remarks"></a>Примечания

Этот метод завершается ошибкой, если координаты пикселя выходят за пределы выбранной области отсечения.

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a> CImage::SetPixelIndexed

Задает цвет пикселя для цвета, расположенного по адресу *iIndex* в палитре цветов.

```cpp
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение устанавливаемого пикселя.

*y*<br/>
Вертикальное расположение устанавливаемого пикселя.

*iIndex*<br/>
Индекс цвета в палитре цветов.

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a> CImage::SetPixelRGB

Задает пиксел в расположениях, заданных *x* и *y* , с цветами, обозначенными *r*, *g*и *b*, красным, зеленым, синим (RGB) образом.

```cpp
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение устанавливаемого пикселя.

*y*<br/>
Вертикальное расположение устанавливаемого пикселя.

*r*<br/>
Интенсивность красного цвета.

*g*<br/>
Интенсивность зеленого цвета.

*b*<br/>
Интенсивность синего цвета.

### <a name="remarks"></a>Примечания

Параметры красного, зеленого и синего параметров представлены числом от 0 до 255. Если для всех трех параметров установить нулевое значение, то итоговый цвет будет черным. Если для всех трех параметров задать значение 255, то итоговый цвет будет белым.

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a> CImage::SetTransparentColor

Задает цвет в указанном индексированном расположении как прозрачный.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Параметры

*iTransparentColor*<br/>
Индекс в цветовой палитре, для которого задается прозрачный цвет. Если задано значение-1, цвет не имеет значения Transparent.

### <a name="return-value"></a>Возвращаемое значение

Индекс цвета, ранее заданный в качестве прозрачного.

## <a name="cimagestretchblt"></a><a name="stretchblt"></a> CImage::StretchBlt

Копирует точечный рисунок из контекста исходного устройства в этот текущий контекст устройства.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Маркер контекста целевого устройства.

*xDest*<br/>
Координата x в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y (в логических единицах) верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения.

*nDestHeight*<br/>
Высота прямоугольника назначения в логических единицах.

*dwROP*<br/>
Выполняемая растровая операция. Коды операций с растровым набором определяют способ объединения битов источника, назначения и шаблона (как определено текущей выбранной кистью) для формирования назначения. Список других кодов точечных операций и их описание см. в разделе [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) в Windows SDK.

*rectDest*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую назначение.

*xSrc*<br/>
Координата x в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата по оси y (в логических единицах) верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина (в логических единицах) исходного прямоугольника.

*nSrcHeight*<br/>
Высота исходного прямоугольника в логических единицах.

*rectSrc*<br/>
Ссылка на `RECT` структуру, определяющую источник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха; в противном случае — 0

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [StretchBlt](/windows/win32/api/wingdi/nf-wingdi-stretchblt) в Windows SDK.

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a> CImage::TransparentBlt

Копирует точечный рисунок из контекста исходного устройства в этот текущий контекст устройства.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Маркер контекста целевого устройства.

*xDest*<br/>
Координата x в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y (в логических единицах) верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина (в логических единицах) прямоугольника назначения.

*nDestHeight*<br/>
Высота прямоугольника назначения в логических единицах.

*crTransparent*<br/>
Цвет исходного растрового изображения, который должен считаться прозрачным. По умолчанию CLR_INVALID, указывающее, что цвет, заданный в данный момент как прозрачный цвет изображения, должен использоваться.

*rectDest*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую назначение.

*xSrc*<br/>
Координата x в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата по оси y (в логических единицах) верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина (в логических единицах) исходного прямоугольника.

*nSrcHeight*<br/>
Высота исходного прямоугольника в логических единицах.

*rectSrc*<br/>
Ссылка на `RECT` структуру, определяющую источник.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнено успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

`TransparentBlt` поддерживается для исходных битовых карт размером 4 бита на пиксель и 8 бит на пиксель. Используйте [CImage::AlphaBlend](#alphablend) , чтобы указать точечные рисунки размером 32 бит на пиксель с прозрачностью.

### <a name="example"></a>Пример

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>См. также

[Пример Ммкссварм](../../overview/visual-cpp-samples.md)<br/>
[Пример Симплеимаже](../../overview/visual-cpp-samples.md)<br/>
[Аппаратно-независимые точечные рисунки](/windows/win32/gdi/device-independent-bitmaps)<br/>
[креатедибсектион](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Аппаратно-независимые точечные рисунки](/windows/win32/gdi/device-independent-bitmaps)<br/>
[креатедибсектион](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
