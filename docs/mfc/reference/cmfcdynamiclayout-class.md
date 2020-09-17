---
title: Класс CMFCDynamicLayout
ms.date: 08/29/2019
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 77dd3a84a0c76b92495bb062eeb83ff013933087
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752389"
---
# <a name="cmfcdynamiclayout-class"></a>Класс CMFCDynamicLayout

Определяет порядок перемещения и изменения размеров элементов управления при изменении размеров окна.

## <a name="syntax"></a>Синтаксис

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Формирует объект `CMFCDynamicLayout`.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|
|[CMFCDynamicLayout::Adjust](#adjust)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|
|[CMFCDynamicLayout::Create](#create)|Хранит и проверяет главное окно.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Возвращает указатель на главное окно.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Возвращает минимальный размер окна для макета.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Извлекает прямоугольник для текущей клиентской области окна.|
|[CMFCDynamicLayout::HasItem](#hasitem)|Проверяет, добавлялся ли дочерний элемент управления в динамический макет.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|Проверяет, что в динамический макет не добавлялись дочерние окна.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.|
|статический [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько элемент управления детьми перемещается горизонтально, когда пользователь изменяет размер окна хостинга.|
|статический [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько элемент управления детьми перемещается горизонтально, когда пользователь изменяет размер окна хостинга.|
|статический [CMFCDynamicLayout:MoveNone](#movenone)|Получает значение [MoveSettings, которое](#movesettings_structure) не представляет движения, вертикального или горизонтального, для управления детьми.|
|статический [CMFCDynamicLayout::MoveVertical](#movevertical)|Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько управления детьми перемещается вертикально, когда пользователь изменяет размер окна хостинга.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Задает минимальный размер окна для макета.|
|статический [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется горизонтально, когда пользователь изменяет размер окна хостинга.|
|статический [CMFCDynamicLayout::SizeHorizontalandVerticalVertical](#sizehorizontalandvertical)|Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется горизонтально, когда пользователь изменяет размер окна хостинга.|
|статический [CMFCDynamicLayout::SizeNone](#sizenone)|Получает значение [SizeSettings,](#sizesettings_structure) которое не представляет никаких изменений в размере для управления детьми.|
|статический [CMFCDynamicLayout::SizeVertical](#sizevertical)|Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется вертикально, когда пользователь изменяет размер окна хостинга.|

## <a name="nested-types"></a>Вложенные типы

|Имя|Описание|
|----------|-----------------|
|[Структура CMFCDynamicLayout::MoveSettings](#movesettings_structure)|Инкапсулирует данные перемещения для элементов управления в динамическом макете.|
|[Структура CMFCDynamicLayout::SizeSettings](#sizesettings_structure)|Инкапсулирует данные об изменении размера элементов управления в динамическом макете.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxlayout.h

## <a name="cmfcdynamiclayoutadditem"></a><a name="additem"></a>CMFCDynamicLayout::AddItem

Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Дескриптор добавляемого окна.

*nID*<br/>
Идентификатор добавляемого дочернего элемента управления.

*moveSettings*<br/>
Структура, описывающая перемещение элемента управления при изменении размера окна.

*sizeSettings*<br/>
Структура, описывающая изменение размера элемента управления при изменении размера окна.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент был успешно добавлен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.

## <a name="cmfcdynamiclayoutadjust"></a><a name="adjust"></a>CMFCDynamicLayout::Отрегулируйте

Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).

```cpp
void Adjust();
```

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.

## <a name="cmfcdynamiclayoutcreate"></a><a name="create"></a>CMFCDynamicLayout::Создание

Хранит и проверяет главное окно.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Параметры

*pHostWnd*<br/>
Указатель на главное окно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если создание прошло успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutgethostwnd"></a><a name="gethostwnd"></a>CMFCDynamicLayout::GetHostWnd

Возвращает указатель на главное окно.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на главное окно.

### <a name="remarks"></a>Примечания

По умолчанию положения всех дочерних элементов управления пересчитываются относительно этого окна. 

## <a name="cmfcdynamiclayoutgetminsize"></a><a name="getminsize"></a>CMFCDynamicLayout::GetMinSize

Возвращает минимальный размер окна для макета.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Возвращаемое значение

Минимальный размер окна для макета.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.

## <a name="cmfcdynamiclayoutgetwindowrect"></a><a name="getwindowrect"></a>CMFCDynamicLayout::GetWindowRect

Извлекает прямоугольник для текущей клиентской области окна.

```cpp
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
После возвращения функцией этот параметр содержит ограничивающий прямоугольник области макета. Это выходной параметр. Входное значение перезаписывается.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayouthasitem"></a><a name="hasitem"></a>CMFCDynamicLayout::HasItem

Проверяет, добавлялся ли дочерний элемент управления в динамический макет.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Дескриптор окна для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если макет уже содержит данный элемент; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutisempty"></a><a name="isempty"></a>CMFCDynamicLayout::Пустой

Проверяет, что в динамический макет не добавлялись дочерние окна.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если макет не содержит элементов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutloadresource"></a><a name="loadresource"></a>CMFCDynamicLayout::LoadResource

Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Параметры

*pHostWnd*<br/>
Указатель на главное окно.

*lpResource*<br/>
Указатель на буфер, содержащий ресурс AFX_DIALOG_LAYOUT.

*dwSize*<br/>
Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ресурс загружен и применен для главного окна; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutmovehorizontal"></a><a name="movehorizontal"></a>CMFCDynamicLayout::MoveHorizontal

Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько элемент управления детьми перемещается горизонтально, когда пользователь изменяет размер окна хостинга.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Параметры

*nСтити*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [MoveSettings,](#movesettings_structure) которое инкапсулирует запрашиваемый коэффициент перемещения.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutmovehorizontalandvertical"></a><a name="movehorizontalandvertical"></a>CMFCDynamicLayout::MoveHorizontalAndVertical

Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько элемент управления детьми перемещается горизонтально, когда пользователь изменяет размер окна хостинга.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Параметры

*nXRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.

*nYRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [MoveSettings,](#movesettings_structure) которое инкапсулирует запрашиваемый коэффициент перемещения.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutmovenone"></a><a name="movenone"></a>CMFCDynamicLayout::MoveNone

Получает значение [MoveSettings, которое](#movesettings_structure) не представляет движения, вертикального или горизонтального, для управления детьми.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Возвращаемое значение

Значение [MoveSettings,](#movesettings_structure) которое фиксирует элемент управления на месте, так что он не перемещается при перемещении пользователя по мере того, как пользователь изменяет размер окна узла.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutmovesettings-structure"></a><a name="movesettings_structure"></a>CMFCDynamicLayout::Перемещение Структура

Инкапсулирует данные перемещения для элементов управления в динамическом макете.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Примечания

Этот класс является вложенным в `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::: Горизонт

Проверяет, задано ли в данных перемещения ненулевое перемещение по горизонтали.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по горизонтали.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::

Проверяет, что задано нулевое перемещение данных.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает нулевое перемещение.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::

Проверяет, задано ли в данных перемещения ненулевое перемещение по вертикали.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по вертикали.

## <a name="cmfcdynamiclayoutmovevertical"></a><a name="movevertical"></a>CMFCDynamicLayout::MoveVertical

Получает значение [MoveSettings,](#movesettings_structure) определяющее, сколько управления детьми перемещается вертикально, когда пользователь изменяет размер окна хостинга.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Параметры

*nСтити*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [MoveSettings,](#movesettings_structure) которое инкапсулирует запрашиваемый коэффициент перемещения.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutsetminsize"></a><a name="setminsize"></a>CMFCDynamicLayout::SetMinSize

Задает минимальный размер окна для макета.

```cpp
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Необходимый минимальный размер макета.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.

## <a name="cmfcdynamiclayoutsizehorizontal"></a><a name="sizehorizontal"></a>CMFCDynamicLayout::SizeHorizontal

Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется горизонтально, когда пользователь изменяет размер окна хостинга.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Параметры

*nСтити*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [SizeSettings,](#sizesettings_structure) которое инкапсулирует запрашиваемый коэффициент размера.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutsizehorizontalandvertical"></a><a name="sizehorizontalandvertical"></a>CMFCDynamicLayout::SizeHorizontalandAndVerticalVertical

Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется горизонтально, когда пользователь изменяет размер окна хостинга.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Параметры

*nXRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера главного окна.

*nYRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [SizeSettings,](#sizesettings_structure) которое инкапсулирует запрашиваемый коэффициент размера.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutsizenone"></a><a name="sizenone"></a>CMFCDynamicLayout::SizeNone

Получает значение [SizeSettings,](#sizesettings_structure) которое не представляет никаких изменений в размере для управления детьми.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Возвращаемое значение

Значение [SizeSettings,](#sizesettings_structure) которое фиксирует элемент управления при определенном размере, чтобы он не изменял размер при изменении размера пользователя.

### <a name="remarks"></a>Примечания

## <a name="cmfcdynamiclayoutsizesettings-structure"></a><a name="sizesettings_structure"></a>CMFCDynamicLayout::SizeSettings Структура

Инкапсулирует данные об изменении размера элементов управления в динамическом макете.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Примечания

Этот класс является вложенным в `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::Горизонт

Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по горизонтали.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по горизонтали.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::

Проверяет, задано ли в данных об изменении размера нулевое изменение размера.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает нулевое изменение размера.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::

Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по вертикали.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по вертикали.

## <a name="cmfcdynamiclayoutsizevertical"></a><a name="sizevertical"></a>CMFCDynamicLayout::SizeVertical

Получает значение [SizeSettings,](#sizesettings_structure) определяющее, сколько элемент управления детьми изменяется вертикально, когда пользователь изменяет размер окна хостинга.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Параметры

*nСтити*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Значение [SizeSettings,](#sizesettings_structure) которое инкапсулирует запрашиваемый коэффициент размера.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
