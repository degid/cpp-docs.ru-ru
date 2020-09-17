---
title: Класс CRgn
ms.date: 11/04/2016
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
ms.openlocfilehash: e84526eec8f4fd4b1935fa39bc7f4ed3c4d5dd71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754489"
---
# <a name="crgn-class"></a>Класс CRgn

Инкапсулирует область интерфейса графических устройств Windows (GDI).

## <a name="syntax"></a>Синтаксис

```
class CRgn : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|Формирует объект `CRgn`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRgn::CombineRgn](#combinergn)|Устанавливает `CRgn` объект таким образом, чтобы он был `CRgn` эквивалентен объединению двух указанных объектов.|
|[CRgn::CopyRgn](#copyrgn)|Устанавливает `CRgn` объект таким образом, чтобы он `CRgn` был копией указанного объекта.|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Инициализирует `CRgn` объект с эллиптическим регионом.|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Инициализирует `CRgn` объект с эллиптическим регионом, определенным структурой [RECT.](/windows/win32/api/windef/ns-windef-rect)|
|[CRgn::CreateFromData](#createfromdata)|Создает регион из данного региона и данные о трансформации.|
|[CRgn::CreateFromPath](#createfrompath)|Создает область из выбранного в контексте данного устройства области.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Инициирует `CRgn` объект с полигональной областью. Система закрывает полигон автоматически, при необходимости, рисуя линию от последней вершины до первой.|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Инициализирует `CRgn` объект с областью, состоящей из ряда закрытых полигонов. Полигоны могут быть разрозненными, или они могут перекрываться.|
|[CRgn::CreateRecRgn](#createrectrgn)|Инициализирует `CRgn` объект с прямоугольной областью.|
|[CRgn::СоздатьRectRgnIndirect](#createrectrgnindirect)|Инициализирует `CRgn` объект с прямоугольной областью, определяемой tructure [RECT.](/windows/win32/api/windef/ns-windef-rect)|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Инициализирует `CRgn` объект с прямоугольной областью с закруглеными углами.|
|[CRgn::EqualRgn](#equalrgn)|Проверяет `CRgn` два объекта, чтобы определить, являются ли они эквивалентными.|
|[CRgn::FromHandle](#fromhandle)|Возвращает указатель объекту `CRgn` при отваге ручки в область Windows.|
|[CRgn::GetRegionData](#getregiondata)|Заполняет указанный буфер данными, описывающими данный данного региона.|
|[CRgn::GetRgnBox](#getrgnbox)|Извлекает координаты ограничивающего прямоугольника `CRgn` объекта.|
|[CRgn::OffsetRgn](#offsetrgn)|Перемещает `CRgn` объект по указанным смещениям.|
|[CRgn::PtInРегион](#ptinregion)|Определяет, находится ли указанная точка в регионе.|
|[CRgn::RectInRegion](#rectinregion)|Определяет, находится ли какая-либо часть указанного прямоугольника в пределах региона.|
|[CRgn::SetRecRgn](#setrectrgn)|Устанавливает `CRgn` объект в указанную прямоугольную область.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CRgn:оператор HRGN](#operator_hrgn)|Возвращает ручку Windows, `CRgn` содержащуюся в объекте.|

## <a name="remarks"></a>Примечания

Область представляет собой эллиптическую или полигональную область в окне. Для использования областей используются функции участника класса `CRgn` с функциями `CDC`отсечения, определенными как члены класса.

Функции `CRgn` участника создания, изменения и получения информации об объекте региона, для которого они называются.

Для получения дополнительной `CRgn`информации об использовании, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="crgncombinergn"></a><a name="combinergn"></a>CRgn::CombineRgn

Создает новый регион GDI, объединяя два существующих региона.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Параметры

*pRgn1*<br/>
Идентифицирует существующий регион.

*pRgn2*<br/>
Идентифицирует существующий регион.

*nКомбинатомод*<br/>
Определяет операцию, которая будет выполняться при объединении двух областей источника. Это может быть любое из следующих значений:

- RGN_AND использует перекрывающиеся области обоих областей (пересечение).

- RGN_COPY Создает копию региона 1 (идентифицированный *pRgn1).*

- RGN_DIFF Создает область, состоящую из районов области 1 (идентифицированных *pRgn1),* которые не являются частью региона 2 (определяется *pRgn2).*

- RGN_OR объединяет оба региона в полном объеме (союз).

- RGN_XOR объединяет оба региона, но удаляет перекрывающиеся области.

### <a name="return-value"></a>Возвращаемое значение

Определяет тип полученного региона. Может иметь одно из следующих значений.

- COMPLEXREGION Новый регион имеет перекрывающиеся границы.

- ERROR Новый регион не создан.

- НОВЫй регион NULLREGION пуст.

- SIMPLEREGION Новый регион не имеет перекрывающихся границ.

### <a name="remarks"></a>Примечания

Регионы объединяются в указании *nCombineMode*.

Два указанных региона объединены, и полученная `CRgn` ручка области хранится в объекте. Таким образом, любой `CRgn` регион, хранящийся в объекте, заменяется комбинированным регионом.

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Используйте [CopyRgn,](#copyrgn) чтобы просто скопировать один регион в другой регион.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

## <a name="crgncopyrgn"></a><a name="copyrgn"></a>CRgn::CopyRgn

Копирует область, определяемую *pRgnSrc,* в `CRgn` объект.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Параметры

*pRgnSrc*<br/>
Идентифицирует существующий регион.

### <a name="return-value"></a>Возвращаемое значение

Определяет тип полученного региона. Может иметь одно из следующих значений.

- COMPLEXREGION Новый регион имеет перекрывающиеся границы.

- ERROR Новый регион не создан.

- НОВЫй регион NULLREGION пуст.

- SIMPLEREGION Новый регион не имеет перекрывающихся границ.

### <a name="remarks"></a>Примечания

Новый регион заменяет область, `CRgn` ранее хранившуюся в объекте. Эта функция является особым случаем функции члена [CombineRgn.](#combinergn)

### <a name="example"></a>Пример

  Смотрите пример [для CRgn::CreateEllipticRgn](#createellipticrgn).

## <a name="crgncreateellipticrgn"></a><a name="createellipticrgn"></a>CRgn::CreateEllipticRgn

Создает эллиптический регион.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Определяет логическую х-координату армирования верхнего левого угла граниющего прямоугольника эллипса.

*y1*<br/>
Определяет логическую y-координацию верхнего левого угла ограничивающего прямоугольника эллипса.

*x2*<br/>
Определяет логическую х-координатум нижнего правого угла ограничивающего прямоугольника эллипса.

*y2*<br/>
Определяет логическую y-координацию нижнего правого угла ограничивающего прямоугольника эллипса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Область определяется прямоугольником, указанным *x1,* *y1,* *x2*и *y2.* Область хранится в `CRgn` объекте.

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Когда он закончил использовать область, `CreateEllipticRgn` созданную с функцией, приложение должно выбрать `DeleteObject` область из контекста устройства и использовать функцию для его удаления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

## <a name="crgncreateellipticrgnindirect"></a><a name="createellipticrgnindirect"></a>CRgn::CreateEllipticRgnInDirect

Создает эллиптический регион.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру `CRect` или объект, содержащий логические координаты верхнего левого и нижнего правого углова, ограничивающего прямоугольник эллипса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Область определяется структурой или объектом, на который указывает `CRgn` *lpRect,* и хранится в объекте.

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Когда он закончил использовать область, `CreateEllipticRgnIndirect` созданную с функцией, приложение должно выбрать `DeleteObject` область из контекста устройства и использовать функцию для его удаления.

### <a name="example"></a>Пример

  Смотрите пример [cRgn::CreateRecRgnIndirect](#createrectrgnindirect).

## <a name="crgncreatefromdata"></a><a name="createfromdata"></a>CRgn::CreateFromData

Создает регион из данного региона и данные о трансформации.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Параметры

*lpXForm*<br/>
Указывает на структуру [ата XFORM,](/windows/win32/api/wingdi/ns-wingdi-xform)определяющую преобразование, которое будет выполняться в регионе. Если этот указатель NULL, используется преобразование идентификации.

*Ncount*<br/>
Определяет количество байтов, на которые указывает *pRgnData.*

*pRgnData*<br/>
Указывает на структуру данных [RGNDATA,](/windows/win32/api/wingdi/ns-wingdi-rgndata) содержащую данные о регионах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение может получать данные для региона, вызывая функцию. `CRgn::GetRegionData`

## <a name="crgncreatefrompath"></a><a name="createfrompath"></a>CRgn::CreateFromPath

Создает область из выбранного в контексте данного устройства области.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Определяет контекст устройства, содержащий закрытый путь.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Контекст устройства, идентифицированный параметром *pDC,* должен содержать закрытый путь. После `CreateFromPath` преобразования пути в область Windows удаляет закрытый путь из контекста устройства.

## <a name="crgncreatepolygonrgn"></a><a name="createpolygonrgn"></a>CRgn::CreatePolygonRgn

Создает полигональную область.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Параметры

*lpPoints*<br/>
Указывает на массив `POINT` структур или `CPoint` массив объектов. Каждая структура определяет X-координат и y-координаты одной вершины полигона. Структура `POINT` имеет следующую форму:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*Ncount*<br/>
Определяет количество `POINT` структур или `CPoint` объектов в массиве, на который указывают *lpPoints.*

*nMode*<br/>
Определяет режим заполнения для региона. Этот параметр может быть либо ALTERNATE, либо WINDING.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Система закрывает полигон автоматически, при необходимости, рисуя линию от последней вершины до первой. Полученная область хранится `CRgn` в объекте.

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Когда режим заполнения полигона ALTERNATE, система заполняет область между нечетными и четными по счетами полигона на каждой линии сканирования. То есть система заполняет область между первой и второй стороной, между третьей и четвертой стороной и так далее.

Когда режим заполнения полигона windING, система использует направление, в котором фигура была нарисована, чтобы определить, следует ли заполнить область. Каждый сегмент линии в полигоне нарисован по часовой стрелке или против часовой стрелки. Всякий раз, когда воображаемые линии, взятые из закрытой области на внешнюю сторону фигуры проходит через по часовой стрелке линии сегмента, кол увеличивается. Когда линия проходит через сегмент линии против часовой стрелки, количество decremented. Область заполняется, если количество ненулевое, когда линия достигает внешней стороны фигуры.

Когда приложение закончило использовать область, `CreatePolygonRgn` созданную с функцией, оно должно выбрать `DeleteObject` область из контекста устройства и использовать функцию для его удаления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

## <a name="crgncreatepolypolygonrgn"></a><a name="createpolypolygonrgn"></a>CRgn::CreatePolyPolygonRgn

Создает область, состоящую из ряда закрытых полигонов.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Параметры

*lpPoints*<br/>
Указывает на массив `POINT` структур или `CPoint` массив объектов, определяющих вершины полигонов. Каждый полигон должен быть явно закрыт, поскольку система не закрывается автоматически. Полигоны определяются последовательно. Структура `POINT` имеет следующую форму:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Указывает на множество целых чихов. Первый целый ряд определяет количество головоретов в первом полигоне в массиве *lpPoints,* второй целый ряд определяет количество вертиков во втором полигоне и так далее.

*Ncount*<br/>
Определяет общее количество целых числа в массиве *lpPolyCounts.*

*nПолиФиллмомод*<br/>
Определяет режим заполнения полигона. Это значение может быть либо ALTERNATE, либо WINDING.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Полученная область хранится `CRgn` в объекте.

Полигоны могут быть разрозненными, или они могут перекрываться.

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Когда режим заполнения полигона ALTERNATE, система заполняет область между нечетными и четными по счетами полигона на каждой линии сканирования. То есть система заполняет область между первой и второй стороной, между третьей и четвертой стороной и так далее.

Когда режим заполнения полигона windING, система использует направление, в котором фигура была нарисована, чтобы определить, следует ли заполнить область. Каждый сегмент линии в полигоне нарисован по часовой стрелке или против часовой стрелки. Всякий раз, когда воображаемые линии, взятые из закрытой области на внешнюю сторону фигуры проходит через по часовой стрелке линии сегмента, кол увеличивается. Когда линия проходит через сегмент линии против часовой стрелки, количество decremented. Область заполняется, если количество ненулевое, когда линия достигает внешней стороны фигуры.

Когда приложение закончило использовать область, `CreatePolyPolygonRgn` созданную с функцией, он должен выбрать область из контекста устройства и использовать функцию члена [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) для его удаления.

## <a name="crgncreaterectrgn"></a><a name="createrectrgn"></a>CRgn::CreateRecRgn

Создает прямоугольную область, которая `CRgn` хранится в объекте.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Определяет логическую х-координацию верхнего левого угла области.

*y1*<br/>
Определяет логическую y-координацию верхнего левого угла области.

*x2*<br/>
Определяет логическую х-координацию в правом нижнем углу региона.

*y2*<br/>
Определяет логическую y-координацию в правом нижнем углу региона.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

После завершения использования созданного `CreateRectRgn`региона приложение должно использовать функцию члена [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) для удаления региона.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Для дополнительного примера [см. CRgn::CombineRgn](#combinergn).

## <a name="crgncreaterectrgnindirect"></a><a name="createrectrgnindirect"></a>CRgn::СоздатьRectRgnIndirect

Создает прямоугольную область, которая `CRgn` хранится в объекте.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру или `CRect` объект, содержащий логические координаты верхнего левого и нижнего правого углов области. Структура `RECT` имеет следующую форму:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

После завершения использования созданного `CreateRectRgnIndirect`региона приложение должно использовать функцию члена [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) для удаления региона.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

## <a name="crgncreateroundrectrgn"></a><a name="createroundrectrgn"></a>CRgn::CreateRoundRectRgn

Создает прямоугольную область с закруглеными `CRgn` углами, которая хранится в объекте.

```
BOOL CreateRoundRectRgn(
    int x1,
    int y1,
    int x2,
    int y2,
    int x3,
    int y3);
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Определяет логическую х-координацию верхнего левого угла области.

*y1*<br/>
Определяет логическую y-координацию верхнего левого угла области.

*x2*<br/>
Определяет логическую х-координацию в правом нижнем углу региона.

*y2*<br/>
Определяет логическую y-координацию в правом нижнем углу региона.

*x3*<br/>
Определяет ширину эллипса, используемого для создания закругленных углов.

*y3*<br/>
Определяет высоту эллипса, используемого для создания закругленных углов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция удалась; в противном случае 0.

### <a name="remarks"></a>Примечания

Размер региона ограничен 32 767 на 32 767 логических единиц или 64K памяти, в зависимости от того, меньше.

Когда приложение закончило использовать область, `CreateRoundRectRgn` созданную с функцией, он должен выбрать область из контекста устройства и использовать функцию члена [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) для его удаления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

## <a name="crgncrgn"></a><a name="crgn"></a>CRgn::CRgn

Формирует объект `CRgn`.

```
CRgn();
```

### <a name="remarks"></a>Примечания

Член `m_hObject` данных не содержит допустимую область GDI Windows до тех пор, `CRgn` пока объект не будет инициализирован с одной или более другой функцией участника.

### <a name="example"></a>Пример

  Смотрите пример [cRgn::CreateRoundRectRgn](#createroundrectrgn).

## <a name="crgnequalrgn"></a><a name="equalrgn"></a>CRgn::EqualRgn

Определяет, эквивалентен ли данный регион области, хранящейся в объекте. `CRgn`

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Параметры

*pRgn*<br/>
Идентифицирует регион.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если эти два региона эквивалентны; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

## <a name="crgnfromhandle"></a><a name="fromhandle"></a>CRgn::FromHandle

Возвращает указатель объекту `CRgn` при отваге ручки в область Windows.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Параметры

*hRgn*<br/>
Определяет ручку в области Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CRgn`. Если функция не была успешной, значение возврата является NULL.

### <a name="remarks"></a>Примечания

Если `CRgn` объект еще не прикреплен к ручке, создается и прикрепляется временный `CRgn` объект. Этот `CRgn` временный объект действителен только до следующего времени, когда приложение не будет проходить время в цикле событий, после чего все временные графические объекты удаляются. Другой способ сказать это заключается в том, что временный объект действителен только при обработке одного окна сообщения.

## <a name="crgngetregiondata"></a><a name="getregiondata"></a>CRgn::GetRegionData

Заполняет указанный буфер данными, описывающими область.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Параметры

*lpRgnData*<br/>
Указывает на структуру данных [RGNDATA,](/windows/win32/api/wingdi/ns-wingdi-rgndata) которая получает информацию. Если этот параметр NULL, значение возврата содержит количество байтов, необходимых для данных региона.

*Ncount*<br/>
Определяет размер буфера *lpRgnData* в байтах.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно работает и *nCount* указывает достаточное количество байтов, значение возврата всегда *nCount*. Если функция выходит из строя, или если *nCount* указывает меньше, чем достаточное количество байтов, значение возврата составляет 0 (ошибка).

### <a name="remarks"></a>Примечания

Эти данные включают размеры прямоугольников, которые составляют область. Эта функция используется в `CRgn::CreateFromData` сочетании с функцией.

## <a name="crgngetrgnbox"></a><a name="getrgnbox"></a>CRgn::GetRgnBox

Извлекает координаты ограничивающего прямоугольника `CRgn` объекта.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру или `CRect` объект для получения координат связующего прямоугольника. Структура `RECT` имеет следующую форму:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Возвращаемое значение

Определяет тип региона. В качестве такой точки может выступать любой из следующих вариантов:

- Регион КОМПЛЕКСОЛУИмеет имеет перекрывающиеся границы.

- Регион НУЛРЕГИОН пуст.

- Объект `CRgn` ERROR не указывает допустимую область.

- Регион Сспростырегион не имеет перекрывающихся границ.

### <a name="example"></a>Пример

  Смотрите пример [для CRgn::CreatePolygonRgn](#createpolygonrgn).

## <a name="crgnoffsetrgn"></a><a name="offsetrgn"></a>CRgn::OffsetRgn

Перемещает область, хранящуюся в объекте, `CRgn` указанными смещениями.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Определяет количество единиц для перемещения влево или вправо.

*Y*<br/>
Определяет количество единиц для перемещения вверх или вниз.

*Точки*<br/>
X-координат *точки* определяет количество единиц для перемещения влево или вправо. Y-координат *точки* определяет количество единиц для перемещения вверх или вниз. Параметр *точечной* `POINT` точки может `CPoint` быть либо структурой, либо объектом.

### <a name="return-value"></a>Возвращаемое значение

Тип нового региона. Это может быть любое из следующих значений:

- Регион КОМПЛЕКСОЛУИмеет имеет перекрывающиеся границы.

- Ручка ERROR Region недействительна.

- Регион НУЛРЕГИОН пуст.

- Регион Сспростырегион не имеет перекрывающихся границ.

### <a name="remarks"></a>Примечания

Функция перемещает область *x* единиц вдоль оси x и *y* единиц вдоль y-оси.

Значения координат региона должны быть меньше или равны 32 767 и больше или равны -32 768. Параметры *x* и *y* должны быть тщательно выбраны для предотвращения недействительных координат области.

### <a name="example"></a>Пример

  Смотрите пример [для CRgn::CreateEllipticRgn](#createellipticrgn).

## <a name="crgnoperator-hrgn"></a><a name="operator_hrgn"></a>CRgn:оператор HRGN

Используйте этот оператор, чтобы получить прилагаемую ручку Windows GDI `CRgn` объекта.

```
operator HRGN() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка для объекта Windows `CRgn` GDI, представленная объектом; в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот оператор является оператором литья, который поддерживает прямое использование объекта HRGN.

Для получения дополнительной информации об использовании графических объектов смотрите статью [Графические объекты](/windows/win32/gdi/graphic-objects) в Windows SDK.

## <a name="crgnptinregion"></a><a name="ptinregion"></a>CRgn::PtInРегион

Проверяет, находится ли *точка,* приведенная x и `CRgn` *y,* в области, хранящейся в объекте.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Параметры

*x*<br/>
Определяет логическую х-координацию точки для тестирования.

*Y*<br/>
Определяет логическую y-координацию точки для тестирования.

*Точки*<br/>
X- и y-координаты *точки* указывают x- и y-координаты точки для проверки значения. Параметр *точечной* `POINT` точки может `CPoint` быть либо структурой, либо объектом.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если точка находится в регионе; в противном случае 0.

## <a name="crgnrectinregion"></a><a name="rectinregion"></a>CRgn::RectInRegion

Определяет, находится ли какая-либо часть прямоугольника, указанная *lpRect,* `CRgn` в пределах области, хранящейся в объекте.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру или `CRect` объект. Структура `RECT` имеет следующую форму:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Возвращаемое значение

Незерно, если какая-либо часть указанного прямоугольника находится в пределах региона; в противном случае 0.

## <a name="crgnsetrectrgn"></a><a name="setrectrgn"></a>CRgn::SetRecRgn

Создает прямоугольную область.

```cpp
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Определяет x-координат верхнего левого угла прямоугольной области.

*y1*<br/>
Определяет y-координат верхнего левого угла прямоугольной области.

*x2*<br/>
Определяет x-координат в правом нижнем углу прямоугольной области.

*y2*<br/>
Определяет y-координат в правом нижнем углу прямоугольной области.

*lpRect*<br/>
Определяет прямоугольную область. Может быть как указатель `RECT` на `CRect` структуру, так и объект.

### <a name="remarks"></a>Примечания

В отличие от [CreateRecTRgn](#createrectrgn), однако, он не выделяет никакой дополнительной памяти из локального приложения Windows кучу. Вместо этого используется пространство, выделенное `CRgn` для области, хранящейся в объекте. Это означает, `CRgn` что объект должен быть уже инициализирован с действительной областью Windows перед вызовом. `SetRectRgn` Очки, приведенные *x1,* *y1,* *x2*и *y2,* указывают минимальный размер выделенного пространства.

Используйте эту функцию вместо функции `CreateRectRgn` члена, чтобы избежать вызовов локальному менеджеру памяти.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
