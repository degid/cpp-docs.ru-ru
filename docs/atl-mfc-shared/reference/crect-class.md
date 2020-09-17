---
title: Класс CRect
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: b99eca7fe3a9c84f8b79ef3d694e27b6dd74dcd9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747066"
---
# <a name="crect-class"></a>Класс CRect

Похож на структуру Windows [RECT.](/windows/win32/api/windef/ns-windef-rect)

## <a name="syntax"></a>Синтаксис

```
class CRect : public tagRECT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRect::CRect](#crect)|Формирует объект `CRect`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|Возвращает нижнюю правую `CRect`точку .|
|[CRect::CenterPoint](#centerpoint)|Возвращает центральную `CRect`точку .|
|[CRect::CopyRect](#copyrect)|Копирует размеры прямоугольника источника. `CRect`|
|[CRect::DeflateRect](#deflaterect)|Уменьшает ширину и `CRect`высоту .|
|[CRect::EqualRect](#equalrect)|Определяет, `CRect` равен ли данный прямоугольник.|
|[CRect::Высота](#height)|Вычисляет `CRect`высоту .|
|[CRect::InflateRect](#inflaterect)|Увеличивает ширину и `CRect`высоту .|
|[CRect::ИнтерсектРект](#intersectrect)|Наборы, `CRect` равные пересечению двух прямоугольников.|
|[CRect::RectEmpty](#isrectempty)|Определяет, `CRect` пусто ли это. `CRect`пуст, если ширина и/или высота 0.|
|[CRect::IsRectNull](#isrectnull)|Определяет, все `top` `bottom`ли `left`переменные, равные 0. `right`|
|[CRect::MoveToX](#movetox)|Перемещается `CRect` в указанную х-координацию.|
|[CRect::MoveToXY](#movetoxy)|Перемещается `CRect` к указанным x- и y-координатам.|
|[CRect::MoveToY](#movetoy)|Перемещается `CRect` в указанную y-координацию.|
|[CRect::NormalizeRect](#normalizerect)|Стандартизирует высоту и `CRect`ширину .|
|[CRect::OffsetRect](#offsetrect)|Перемещается `CRect` по указанным смещениям.|
|[CRect::PtInRect](#ptinrect)|Определяет, находится ли указанная точка внутри. `CRect`|
|[CRect::SetRect](#setrect)|Устанавливает размеры `CRect`.|
|[CRect::SettEmpty](#setrectempty)|Устанавливается `CRect` на пустой прямоугольник (все координаты равны 0).|
|[CRect::Размер](#size)|Рассчитывает размер `CRect`.|
|[CRect::SubtractRect](#subtractrect)|Вычитает один прямоугольник из другого.|
|[CRect:TopLeft](#topleft)|Возвращает верхнюю левую `CRect`точку .|
|[CRect::UnionRect](#unionrect)|Наборы, `CRect` равные союзу двух прямоугольников.|
|[CRect::Ширина](#width)|Высчитывает `CRect`ширину .|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CRect:оператор -](#operator_-)|Вычитает данные смещения от `CRect` `CRect` или сдувает и возвращает в результате `CRect`.|
|[CRect::оператор LPCRECT](#operator_lpcrect)|Преобразует `CRect` в `LPCRECT`.|
|[CRect:оператор LPRECT](#operator_lprect)|Преобразует `CRect` в `LPRECT`.|
|[CRect::оператор !](#operator_neq)|Определяет, `CRect` не равен ли прямоугольник.|
|[CRect:оператор&amp;](#operator_amp)|Создает пересечение `CRect` и прямоугольник и `CRect`возвращает в результате .|
|[CRect:оператор&amp;=](#operator_amp_eq)|Устанавливает, `CRect` равный `CRect` пересечению и прямоугольнику.|
|[CRect::оператор &#124;](#operator_or)|Создает союз `CRect` и прямоугольник и возвращает `CRect`полученный .|
|[CRect::оператор &#124;](#operator_or_eq)|Устанавливает, `CRect` равный `CRect` союзу и прямоугольнику.|
|[CRect::оператор](#operator_add)|Добавляет данные смещения `CRect` или `CRect` раздувает и возвращает в результате `CRect`.|
|[CRect::оператор](#operator_add_eq)|Добавляет указанные смещения `CRect` или `CRect`раздувает.|
|[CRect::оператор](#operator_eq)|Копирует размеры прямоугольника до `CRect`.|
|[CRect::оператор -](#operator_-_eq)|Вычитает указанные смещения из `CRect` `CRect`или сдувает.|
|[CRect::оператор](#operator_eq_eq)|Определяет, `CRect` равен ли прямоугольник.|

## <a name="remarks"></a>Примечания

`CRect`также включает функции `CRect` членов для `RECT` управления объектами и структурами Windows.

Объект `CRect` может быть передан в качестве `RECT` параметра функции, где структура, `LPCRECT`или `LPRECT` могут быть переданы.

> [!NOTE]
> Этот класс происходит от `tagRECT` структуры. (Название `tagRECT` является менее часто используемым названием `RECT` для структуры.) Это означает, что`left`члены `right`данных (, `bottom` `top`и ) `RECT` `CRect`структуры являются доступными членами данных .

А `CRect` содержит переменные членов, определяющие верхние левые и нижние точки прямоугольника.

При указании `CRect`, вы должны быть осторожны, чтобы построить его так, чтобы он нормализовались - другими словами, таким образом, что значение левой координаты меньше, чем вправо и сверху меньше, чем дно. Например, верхний левый (10,10) и нижний правый (20,20) определяет нормализованный прямоугольник, но верхний левый (20,20) и нижний правый (10,10) определяет ненормализированный прямоугольник. Если прямоугольник не нормализован, многие `CRect` функции членов могут вернуть неправильные результаты. [(См. CRect::NormalizeRect](#normalizerect) для списка этих функций.) Перед вызовом функции, требующей нормализации прямоугольников, можно нормализовать ненормализованные прямоугольники, позвонив в функцию. `NormalizeRect`

Используйте осторожность при `CRect` манипулировании с [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) и [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) членов функций. Если режим отображения контекста дисплея таков, что `MM_LOENGLISH`y-extent отрицательный, как в, то `CDC::DPtoLP` преобразует `CRect` так, что его верхняя часть больше, чем снизу. Такие функции, как `Height` и `Size` затем вернуть отрицательные `CRect`значения для высоты преобразован, и прямоугольник будет ненормализирован.

При использовании `CRect` перегруженных операторов, первая `CRect`работа должна быть; второй может быть либо структурой `CRect` [RECT,](/windows/win32/api/windef/ns-windef-rect) либо объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagRECT`

`CRect`

## <a name="requirements"></a>Требования

**Заголовок:** atltypes.h

## <a name="crectbottomright"></a><a name="bottomright"></a>CRect::BottomRight

Координаты возвращаются в качестве ссылки на `CRect`объект [CPoint,](cpoint-class.md) который содержится в .

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Координаты нижнего правого угла прямоугольника.

### <a name="remarks"></a>Примечания

Эту функцию можно использовать для получения или установки нижнего правого угла прямоугольника. Установите угол, используя эту функцию на левой стороне оператора назначения.

### <a name="example"></a>Пример

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

## <a name="crectcenterpoint"></a><a name="centerpoint"></a>CRect::CenterPoint

Вычисляет центральную `CRect` точку, добавляя левые и правые значения и разделяя на два, и добавляя верхние и нижние значения и разделяя на два.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CPoint` который является центральной точкой. `CRect`

### <a name="example"></a>Пример

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

## <a name="crectcopyrect"></a><a name="copyrect"></a>CRect::CopyRect

Копирует `lpSrcRect` прямоугольник `CRect`в .

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Параметры

*lpSrcRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) который должен быть скопирован.

### <a name="example"></a>Пример

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

## <a name="crectcrect"></a><a name="crect"></a>CRect::CRect

Формирует объект `CRect`.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Параметры

*L*<br/>
Определяет левую позицию `CRect`.

*t*<br/>
Определяет верхнюю часть `CRect`.

*r*<br/>
Определяет правильное `CRect`положение.

*B*<br/>
Определяет дно `CRect`.

*srcRect*<br/>
Относится к структуре [RECT](/windows/win32/api/windef/ns-windef-rect) `CRect`с координатами для .

*lpSrcRect*<br/>
Указывает на `RECT` структуру с `CRect`координатами для .

*Точки*<br/>
Определяет точку происхождения прямоугольника, которая будет построена. Соответствует верхнему левому углу.

*size*<br/>
Определяет смещение из верхнего левого угла в нижний правый угол прямоугольника, который будет построен.

*topLeft*<br/>
Определяет верхнее левое `CRect`положение .

*bottomRight*<br/>
Определяет позицию в правом нижнем `CRect`углу.

### <a name="remarks"></a>Примечания

Если никаких аргументов `left` `top`не `right`приводится, , , и `bottom` члены не инициализированы.

`CRect`()`const RECT&`и `CRect``LPCRECT`( ) конструкторы выполняют [CopyRect](#copyrect). Другие конструкторы инициализируют переменные члена объекта напрямую.

### <a name="example"></a>Пример

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT structure
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

## <a name="crectdeflaterect"></a><a name="deflaterect"></a>CRect::DeflateRect

`DeflateRect`сдувается, `CRect` двигая его стороны к его центру.

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Определяет количество единиц для сдува левого и `CRect`правого бока.

*Y*<br/>
Определяет количество единиц для дефлации верхней и `CRect`нижней части.

*size*<br/>
[СИЗЕ](/windows/win32/api/windef/ns-windef-size) или [CSize,](csize-class.md) который определяет количество единиц `CRect`для дефлации. Значение `cx` определяет количество единиц для сдува левой и правой сторон, а `cy` значение определяет количество единиц для сдува верхней и нижней частей.

*lpRect*<br/>
Указывает на структуру `CRect` [RECT](/windows/win32/api/windef/ns-windef-rect) или определяет количество единиц для дефлирования каждой стороны.

*L*<br/>
Определяет количество единиц для сдува левой `CRect`стороны .

*t*<br/>
Определяет количество единиц для сдува в `CRect`верхней части .

*r*<br/>
Определяет количество единиц для дефлации правой `CRect`стороны.

*B*<br/>
Определяет количество единиц для сдува `CRect`тьмы.

### <a name="remarks"></a>Примечания

Для этого `DeflateRect` добавляет блоки в левую и верхнюю и вычитает единицы справа и снизу. Параметры подписанных `DeflateRect` значений; положительные значения `CRect` сдувается, а отрицательные значения раздувают его.

Первые две перегрузки сдувают обе `CRect` пары противоположных сторон так, что его `cx`общая ширина уменьшается в два раза *х* (или) и его общая высота уменьшается в два раза *y* (или `cy`). Две другие перегрузки сдуваются с каждой стороны `CRect` независимо от других.

### <a name="example"></a>Пример

```cpp
CRect rect(10, 10, 50, 50);
rect.DeflateRect(1, 2);
ASSERT(rect.left == 11 && rect.right == 49);
ASSERT(rect.top == 12 && rect.bottom == 48);

CRect rect2(10, 10, 50, 50);
CRect rectDeflate(1, 2, 3, 4);
rect2.DeflateRect(&rectDeflate);
ASSERT(rect2.left == 11 && rect2.right == 47);
ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

## <a name="crectequalrect"></a><a name="equalrect"></a>CRect::EqualRect

Определяет, `CRect` равен ли данный прямоугольник.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий верхний левый и нижний правый угол координат прямоугольника.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если два прямоугольника имеют одинаковые верхние, левые, нижние и правые значения; в противном случае 0.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

## <a name="crectheight"></a><a name="height"></a>CRect::Высота

Вычисляет `CRect` высоту, вычитая верхнее значение из нижнего значения.

```
int Height() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота `CRect`.

### <a name="remarks"></a>Примечания

Полученное значение может быть отрицательным.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольник, прежде чем вызвать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a>CRect::InflateRect

`InflateRect`раздувается, `CRect` перемещая его стороны от его центра.

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Определяет количество единиц для раздувания левой и правой `CRect`сторон.

*Y*<br/>
Определяет количество единиц для раздувания верхней и `CRect`нижней части.

*size*<br/>
[СИЗЕ](/windows/win32/api/windef/ns-windef-size) или [CSize,](csize-class.md) который определяет количество единиц `CRect`для раздувания. Значение `cx` определяет количество единиц для раздувания левой и правой `cy` сторон, а значение определяет количество единиц для раздувания верхней и нижней частей.

*lpRect*<br/>
Указывает на структуру `CRect` [RECT](/windows/win32/api/windef/ns-windef-rect) или определяет количество единиц для раздувания каждой стороны.

*L*<br/>
Определяет количество единиц для раздувания левой `CRect`стороны.

*t*<br/>
Определяет количество единиц для раздувания верхней `CRect`части .

*r*<br/>
Определяет количество единиц для раздувания правой `CRect`стороны.

*B*<br/>
Определяет количество единиц для раздувания `CRect`дна.

### <a name="remarks"></a>Примечания

Для этого `InflateRect` вычитает единицы с левой и верхней и добавляет единиц вправо и снизу. Параметры подписанных `InflateRect` значений; положительные значения раздувают `CRect` и отрицательные значения сдувают его.

Первые две перегрузки раздувают обе `CRect` пары противоположных сторон так, что его `cx`общая ширина увеличивается в два `cy`раза *х* (или) и его общая высота увеличивается в два раза *y* (или ). Две другие перегрузки раздувают каждую `CRect` сторону независимо от других.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a>CRect::ИнтерсектРект

Делает `CRect` равное пересечению двух существующих прямоугольников.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий прямоугольник источника.

*lpRect2*<br/>
Указывает на `RECT` структуру или `CRect` объект, содержащий прямоугольник источника.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если перекресток не пуст; 0, если перекресток пуст.

### <a name="remarks"></a>Примечания

Пересечение является самым большим прямоугольником, содержащимся в обоих существующих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rectOne(125,  0, 150, 200);
CRect rectTwo(0, 75, 350, 95);
CRect rectInter;

rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

## <a name="crectisrectempty"></a><a name="isrectempty"></a>CRect::RectEmpty

Определяет, `CRect` пусто ли это.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CRect` если пусто; 0, `CRect` если не пусто.

### <a name="remarks"></a>Примечания

Прямоугольник пуст, если ширина и/или высота 0 или отрицательное. Отличается `IsRectNull`от , который определяет, являются ли все координаты прямоугольника равны нулю.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольник, прежде чем вызвать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a>CRect::IsRectNull

Определяет, равны ли верхние, левые, `CRect` нижние и правые значения 0.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CRect`если верхние, левые, нижние и правые значения равны 0; в противном случае 0.

### <a name="remarks"></a>Примечания

Отличается `IsRectEmpty`от , который определяет, является ли прямоугольник пуст.

### <a name="example"></a>Пример

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

## <a name="crectmovetox"></a><a name="movetox"></a>CRect::MoveToX

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную x-координату, указанную *x.*

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Абсолютная х-координатдля верхний левый угол прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a>CRect::MoveToXY

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютные x- и y-координаты, указанные.

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Абсолютная х-координатдля верхний левый угол прямоугольника.

*Y*<br/>
Абсолютная y-координация для верхнего левого угла прямоугольника.

*Точки*<br/>
Структура, `POINT` определяющая абсолютный верхний левый угол прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a>CRect::MoveToY

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную y-координату, указанную *y.*

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Параметры

*Y*<br/>
Абсолютная y-координация для верхнего левого угла прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a>CRect::NormalizeRect

Нормализует `CRect` так, что и высота и ширина являются положительными.

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>Примечания

Прямоугольник нормализуется для позиционирования четвертого квадранта, которое Windows обычно использует для координат. `NormalizeRect`сравнивает верхние и нижние значения и меняет их, если верхняя часть больше нижней. Аналогичным образом, он меняет левые и правые значения, если левая больше, чем право. Эта функция полезна при работе с различными режимами отображения и перевернутыми прямоугольниками.

> [!NOTE]
> Следующие `CRect` функции члена требуют нормализованных прямоугольников для того, чтобы работать должным образом: [Высота](#height), [Ширина](#width), [Размер](#size), [IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [оператор](#operator_eq_eq), [оператор](#operator_neq) [&#124;](#operator_or), [оператор &#124;](#operator_or_eq), [оператор &](#operator_amp), и [оператор &](#operator_amp_eq).

### <a name="example"></a>Пример

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a>CRect::OffsetRect

Перемещается `CRect` по указанным смещениям.

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Определяет сумму для перемещения влево или вправо. Он должен быть отрицательным, чтобы двигаться влево.

*Y*<br/>
Определяет сумму для перемещения вверх или вниз. Она должна быть отрицательной, чтобы двигаться вверх.

*Точки*<br/>
Содержит структуру [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint,](cpoint-class.md) определяющий оба измерения, по которым необходимо двигаться.

*size*<br/>
Содержит структуру [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize,](csize-class.md) определяющий оба измерения, по которым необходимо двигаться.

### <a name="remarks"></a>Примечания

Перемещает `CRect` *x* единицы вдоль оси x и *у* единиц вдоль y-оси. Параметры *x* и *y* являются подписанными `CRect` значениями, поэтому они могут перемещаться влево или вправо и вверх или вниз.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a>CRect::оператор LPCRECT преобразует `CRect` a в [LPCRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Примечания

При использовании этой функции оператору не нужен адрес оператора.**&** Этот оператор будет автоматически использоваться `CRect` при переходе объекта `LPCRECT`к функции, которая ожидает.

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a>CRect:оператор LPRECT

Преобразуетa `CRect` a в [LPRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Примечания

При использовании этой функции оператору не нужен адрес оператора.**&** Этот оператор будет автоматически использоваться `CRect` при переходе объекта `LPRECT`к функции, которая ожидает.

### <a name="example"></a>Пример

Смотрите пример [для CRect::оператор LPCRECT](#operator_lpcrect).

## <a name="crectoperator-"></a><a name="operator_eq"></a>CRect::оператор

Присваивает *srcRect* . `CRect`

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Параметры

*srcRect*<br/>
Относится к прямоугольнику источника. Может быть [RECT](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a>CRect::оператор

Определяет, `rect` равен `CRect` ли он, сравнивая координаты их верхнего левого и нижнего правого углов.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Относится к прямоугольнику источника. Может быть [RECT](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если равны; в противном случае 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

## <a name="crectoperator-"></a><a name="operator_neq"></a>CRect::оператор !

Определяет, не уравнивается `CRect` ли *рект,* сравнивая координаты их верхнего левого и нижнего правого углов.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Относится к прямоугольнику источника. Может быть [RECT](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевой, если не равный; в противном случае 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

## <a name="crectoperator-"></a><a name="operator_add_eq"></a>CRect::оператор

Первые две перегрузки перемещаются `CRect` по указанным смещениям.

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Структура [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint,](cpoint-class.md) который определяет количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize,](csize-class.md) который определяет количество единиц для перемещения прямоугольника.

*lpRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий количество единиц `CRect`для раздувания каждой стороны.

### <a name="remarks"></a>Примечания

Значения *x* и *y* `cx` параметра `cy`добавлены к. `CRect`

Третья перегрузка раздувается `CRect` количеством единиц, указанных в каждом члене параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a>CRect::оператор -

Первые две перегрузки перемещаются `CRect` по указанным смещениям.

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Структура [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint,](cpoint-class.md) который определяет количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize,](csize-class.md) который определяет количество единиц для перемещения прямоугольника.

*lpRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) который содержит количество `CRect`единиц для дефлирования каждой стороны.

### <a name="remarks"></a>Примечания

Значения *x* и *y* (или) `cx` `cy`параметра вычитаются `CRect`из.

Третья перегрузка сдувается `CRect` по количеству единиц, указанных в каждом члене параметра. Обратите внимание, что эта перегрузка функции, как [DeflateRect](#deflaterect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect:оператор&amp;=

Наборы, `CRect` равные `CRect` `rect`пересечению и .

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит [RECT](/windows/win32/api/windef/ns-windef-rect) `CRect`или .

### <a name="remarks"></a>Примечания

Пересечение является самым большим прямоугольником, который содержится в обоих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

Смотрите пример [для CRect::IntersectRect](#intersectrect).

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a>CRect::оператор &#124;

Наборы, `CRect` равные `CRect` `rect`союзу и .

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит `CRect` или [RECT](/windows/win32/api/windef/ns-windef-rect).

### <a name="remarks"></a>Примечания

Союз является самым маленьким прямоугольником, который содержит оба прямых источника.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a>CRect::оператор

Первые две перегрузки `CRect` возвращают объект, `CRect` равный смещению указанными смещениями.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Структура [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint,](cpoint-class.md) который определяет количество единиц для перемещения значения возврата.

*size*<br/>
Структура [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize,](csize-class.md) который определяет количество единиц для перемещения значения возврата.

*lpRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий количество единиц для раздувания каждой стороны значения возврата.

### <a name="return-value"></a>Возвращаемое значение

В `CRect` результате перемещения или `CRect` раздувания по количеству единиц, указанных в параметре.

### <a name="remarks"></a>Примечания

Параметры *x* и *y* (или) `cx` `cy`параметра добавляются в `CRect`положение '.

Третья перегрузка возвращает `CRect` новую, `CRect` равную завышенной по количеству единиц, указанных в каждом члене параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a>CRect:оператор -

Первые две перегрузки `CRect` возвращают объект, `CRect` равный смещению указанными смещениями.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Структура или `CPoint` объект [POINT,](/windows/win32/api/windef/ns-windef-point) опознавающие количество единиц для перемещения значения возврата.

*size*<br/>
Структура или `CSize` объект [СИЗЕ](/windows/win32/api/windef/ns-windef-size) определяет количество единиц для перемещения значения возврата.

*lpRect*<br/>
Указывает на структуру `CRect` или объект [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий количество единиц для сдувания каждой стороны значения возврата.

### <a name="return-value"></a>Возвращаемое значение

В `CRect` результате перемещения или `CRect` дефлирования по количеству единиц, указанных в параметре.

### <a name="remarks"></a>Примечания

Параметры *x* и *y* (или) `cx` `cy`параметра вычитаются `CRect`из положения '.

Третья перегрузка возвращает `CRect` новую, `CRect` равную спущенной по количеству единиц, указанных в каждом члене параметра. Обратите внимание, что эта перегрузка функции, как [DeflateRect](#deflaterect), а не [SubtractRect](#subtractrect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a>CRect:оператор&amp;

`CRect` Возвращает, что является `CRect` пересечение и *rect2*.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [RECT](/windows/win32/api/windef/ns-windef-rect) `CRect`или .

### <a name="return-value"></a>Возвращаемое значение

A, `CRect` который является `CRect` пересечение и *rect2*.

### <a name="remarks"></a>Примечания

Пересечение является самым большим прямоугольником, который содержится в обоих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a>CRect::оператор &#124;

`CRect` Возвращает, что является `CRect` объединением и *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [RECT](/windows/win32/api/windef/ns-windef-rect) `CRect`или .

### <a name="return-value"></a>Возвращаемое значение

A, `CRect` что является `CRect` объединением и *rect2*.

### <a name="remarks"></a>Примечания

Союз является самым маленьким прямоугольником, который содержит оба прямоугольника.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a>CRect::PtInRect

Определяет, находится ли указанная точка внутри. `CRect`

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Содержит структуру [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint.](cpoint-class.md)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если точка `CRect`находится внутри ; в противном случае 0.

### <a name="remarks"></a>Примечания

Точка находится `CRect` внутри, если она лежит на левой или верхней стороне или находится в пределах всех четырех сторон. Точка на правой или нижней стороне находится снаружи. `CRect`

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольник, прежде чем вызвать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

## <a name="crectsetrect"></a><a name="setrect"></a>CRect::SetRect

Устанавливает размеры `CRect` указанных координат.

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Определяет x-координат верхнего левого угла.

*y1*<br/>
Определяет y-координат верхнего левого угла.

*x2*<br/>
Определяет x-координат в правом нижнем углу.

*y2*<br/>
Определяет y-координат в правом нижнем углу.

### <a name="example"></a>Пример

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a>CRect::SettEmpty

Делает `CRect` нулевой прямоугольник, установив все координаты к нулю.

```cpp
void SetRectEmpty() throw();
```

### <a name="example"></a>Пример

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

## <a name="crectsize"></a><a name="size"></a>CRect::СИЗЕ

И `cx` `cy` члены значения возврата содержат высоту `CRect`и ширину .

```
CSize Size() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](csize-class.md) содержащий `CRect`размер.

### <a name="remarks"></a>Примечания

Либо высота, либо ширина могут быть отрицательными.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольник, прежде чем вызвать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a>CRect::SubtractRect

Делает размеры `CRect` равны вычитания `lpRectSrc2` из `lpRectSrc1`.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Параметры

*lpRectSrc1*<br/>
Указывает на структуру `CRect` [RECT](/windows/win32/api/windef/ns-windef-rect) или объект, из которого должен быть вычитан прямоугольник.

*lpRectSrc2*<br/>
Точки на `RECT` структуру или `CRect` объект, который должен быть вычтен из прямоугольника, на который указывает параметр *lpRectSrc1.*

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вычитание является наименьшим прямоугольником, который содержит все точки в *lpRectScr1,* которые не находятся на пересечении *lpRectScr1* и *lpRectScr2*.

Прямоугольник, указанный *lpRectSrc1,* будет неизменным, если прямоугольник, указанный *lpRectSrc2,* не полностью перекрывает прямоугольник, указанный *lpRectSrc1,* по крайней мере в одном из направлений x- или y.

Например, если бы *lpRectSrc1* были (10,10, 100,100) и *lpRectSrc2* (50,50, 150 150), прямоугольник, на который указывает *lpRectSrc1,* был бы неизменным, когда функция вернулась. Если *lpRectSrc1* были (10,10, 100,100) и *lpRectSrc2* были (50,10, 150,150), однако, прямоугольник указал *на lpRectSrc1* будет содержать координаты (10,10, 50100), когда функция возвращается.

`SubtractRect`не то же самое, что [оператор -](#operator_-) ни оператор [- .](#operator_-_eq) Ни один из `SubtractRect`этих операторов никогда не вызывает .

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
RECT   rectOne;
RECT   rectTwo;

rectOne.left = 10;
rectOne.top = 10;
rectOne.bottom = 100;
rectOne.right = 100;

rectTwo.left = 50;
rectTwo.top = 10;
rectTwo.bottom = 150;
rectTwo.right = 150;

CRect   rectDiff;

rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

ASSERT(rectDiff == rectResult);

// works for CRect, too, since there is
// implicit CRect -> LPCRECT conversion

CRect rect1(10, 10, 100, 100);
CRect rect2(50, 10, 150, 150);
CRect rectOut;

rectOut.SubtractRect(rect1, rect2);
ASSERT(rectResult == rectOut);
```

## <a name="crecttopleft"></a><a name="topleft"></a>CRect:TopLeft

Координаты возвращаются в качестве ссылки на `CRect`объект [CPoint,](cpoint-class.md) который содержится в .

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Координаты верхнего левого угла прямоугольника.

### <a name="remarks"></a>Примечания

Эту функцию можно использовать для получения или установки верхнего левого угла прямоугольника. Установите угол, используя эту функцию на левой стороне оператора назначения.

### <a name="example"></a>Пример

Смотрите пример [cRect::CenterPoint](#centerpoint).

## <a name="crectunionrect"></a><a name="unionrect"></a>CRect::UnionRect

Делает размеры `CRect` равными союзу двух прямоугольников источника.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на [RECT](/windows/win32/api/windef/ns-windef-rect) или `CRect` содержащую прямоугольник источника.

*lpRect2*<br/>
Указывает на `RECT` `CRect` или содержащее прямоугольник источника.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если союз не пуст; 0, если союз пуст.

### <a name="remarks"></a>Примечания

Союз является самым маленьким прямоугольником, который содержит оба прямых источника.

Windows игнорирует размеры пустого прямоугольника; то есть прямоугольник, который не имеет высоты или не имеет ширины.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольники, прежде чем вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a>CRect::Ширина

Вычисляет `CRect` ширину, вычитая левое значение из нужного значения.

```
int Width() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина `CRect`.

### <a name="remarks"></a>Примечания

Ширина может быть отрицательной.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может выполнить неудачу. Вы можете вызвать [NormalizeRect,](#normalizerect) чтобы нормализовать прямоугольник, прежде чем вызвать эту функцию.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>См. также раздел

[Класс CPoint](cpoint-class.md)<br/>
[Класс CSize](csize-class.md)<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect)
