---
title: Класс CPoint
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 331b89ff118f727303e887670960ee6078b01fb1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747082"
---
# <a name="cpoint-class"></a>Класс CPoint

Как и в структуре `POINT` Windows.

## <a name="syntax"></a>Синтаксис

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|Создает документ `CPoint`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPoint::Offset](#offset)|Добавляет значения для `x` `y` членов `CPoint`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPoint::оператор -](#operator_-)|Возвращает разницу `CPoint` в размере и размера, или отрицание точки, или разницу в размерах между двумя точками, или смещение отрицательным размером.|
|[CPoint::оператор !](#operator_neq)|Проверка на неравенство между двумя точками.|
|[CPoint::оператор](#operator_add)|Возвращает сумму `CPoint` и размер или точку, `CRect` или смещение размером.|
|[CPoint::оператор](#operator_add_eq)|Смещения `CPoint` путем добавления размера или точки.|
|[CPoint::оператор -](#operator_-_eq)|Смещения `CPoint` путем вычитания размера или точки.|
|[CPoint::оператор](#operator_eq_eq)|Проверка на равенство между двумя пунктами.|

## <a name="remarks"></a>Примечания

Она также включает в `CPoint` себя функции членов для манипулирования и [POINT](/windows/win32/api/windef/ns-windef-point) структур.

Объект `CPoint` может использоваться `POINT` везде, где используется структура. Операторы этого класса, которые взаимодействуют с "размером", принимают либо объекты [CSize,](../../atl-mfc-shared/reference/csize-class.md) либо структуры [СИЗЕ,](/windows/win32/api/windef/ns-windef-size) так как они взаимозаменяемы.

> [!NOTE]
> Этот класс происходит от `tagPOINT` структуры. (Имя `tagPOINT` является менее часто используемым `POINT` названием для структуры.) Это означает, что данные `POINT` `x` членов `y`структуры, и `CPoint`, являются доступными членами данных .

> [!NOTE]
> Для получения дополнительной информации `CPoint`об общих классах утилиты (например), см. [Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Требования

**Заголовок:** atltypes.h

## <a name="cpointcpoint"></a><a name="cpoint"></a>CPoint::CPoint

Формирует объект `CPoint`.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Параметры

*initX*<br/>
Определяет значение члена `x` структуры `CPoint`.

*initY*<br/>
Определяет значение члена `y` структуры `CPoint`.

*initPt*<br/>
[Структура](/windows/win32/api/windef/ns-windef-point) POINT `CPoint` или которая определяет значения, используемые `CPoint`для инициализации.

*initSize*<br/>
[СИЗЕ](/windows/win32/api/windef/ns-windef-size) структура или [CSize,](../../atl-mfc-shared/reference/csize-class.md) который определяет значения, используемые для инициализации. `CPoint`

*dwPoint*<br/>
Устанавливает `x` участника на слово низкого порядка *dwPoint* и `y` члена на слово высокого порядка *dwPoint*.

### <a name="remarks"></a>Примечания

Если аргументы не указаны, для членов `x` и `y` задается значение 0.

### <a name="example"></a>Пример

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

## <a name="cpointoffset"></a><a name="offset"></a>CPoint::Offset

Добавляет значения для `x` `y` членов `CPoint`.

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*xOffset*<br/>
Определяет сумму, чтобы компенсировать `x` член `CPoint`.

*yOffset*<br/>
Определяет сумму, чтобы компенсировать `y` член `CPoint`.

*Точки*<br/>
Укажите сумму [(POINT](/windows/win32/api/windef/ns-windef-point) `CPoint`или ), `CPoint`чтобы компенсировать .

*size*<br/>
Упомягает сумму [(СИЗЕ](/windows/win32/api/windef/ns-windef-size) `CPoint`или [CSize](../../atl-mfc-shared/reference/csize-class.md)), чтобы компенсировать .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a>CPoint::оператор

Проверка на равенство между двумя пунктами.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Содержит структуру `CPoint` или объект [POINT.](/windows/win32/api/windef/ns-windef-point)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если очки равны; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a>CPoint::оператор !

Проверка на неравенство между двумя точками.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Содержит структуру `CPoint` или объект [POINT.](/windows/win32/api/windef/ns-windef-point)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если очки не равны; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a>CPoint::оператор

Первая перегрузка добавляет `CPoint`размер к .

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize.](../../atl-mfc-shared/reference/csize-class.md)

*Точки*<br/>
Содержит структуру [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint.](../../atl-mfc-shared/reference/cpoint-class.md)

### <a name="remarks"></a>Примечания

Вторая перегрузка добавляет `CPoint`точку в .

В обоих случаях добавление `x` делается `cx`путем добавления (или) члена `x` правой `CPoint` руки `y` к `cy`члену и добавления (или) `y` члена `CPoint`правой руки к члену .

Например, `CPoint(5, -7)` добавление к переменной, содержащей `CPoint(30, 40)` изменения переменной к `CPoint(35, 33)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a>CPoint::оператор -

Первая перегрузка вычитает размер `CPoint`из .

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize.](../../atl-mfc-shared/reference/csize-class.md)

*Точки*<br/>
Содержит структуру [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint.](../../atl-mfc-shared/reference/cpoint-class.md)

### <a name="remarks"></a>Примечания

Вторая перегрузка вычитает точку из `CPoint`.

В обоих случаях вычитание осуществляется `x` путем вычитания (или) `cx`члена `x` правой `CPoint` руки от члена `y` и `cy`вычитания (или) члена правой руки от `y` члена `CPoint`.

Например, вычитание `CPoint(5, -7)` из `CPoint(30, 40)` переменной, `CPoint(25, 47)`содержащей изменения переменной.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a>CPoint::оператор

Используйте этот `CPoint` оператор, `CPoint` `CSize` чтобы компенсировать или `CRect` объект, `CPoint`или компенсировать на .

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize.](../../atl-mfc-shared/reference/csize-class.md)

*Точки*<br/>
Содержит структуру [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint.](../../atl-mfc-shared/reference/cpoint-class.md)

*lpRect*<br/>
Содержит указатель на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect.](../../atl-mfc-shared/reference/crect-class.md)

### <a name="return-value"></a>Возвращаемое значение

А, `CPoint` который компенсируется размером, `CPoint` то, что компенсируется точкой, или `CRect` смещением точкой.

### <a name="remarks"></a>Примечания

Например, использование одной из первых двух перегрузок для `CPoint(25, -19)` компенсации точки на точку `CPoint(15, 5)` или размер `CSize(15, 5)` возвращает значение. `CPoint(40, -14)`

Добавление прямоугольника в точку возвращает прямоугольник после `x` `y` того, как он компенсируется значениями, указанными в точке. Например, использование последней перегрузки `CRect(125, 219, 325, 419)` для компенсации `CRect(150, 200, 350, 400)`прямоугольника путем возврата точек. `CPoint(25, -19)`

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a>CPoint::оператор -

Используйте одну из первых двух перегрузок, чтобы вычесть `CPoint` или `CSize` объект из. `CPoint`

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Структура [POINT](/windows/win32/api/windef/ns-windef-point) или объект [CPoint.](../../atl-mfc-shared/reference/cpoint-class.md)

*size*<br/>
Структура [СИЗЕ](/windows/win32/api/windef/ns-windef-size) или объект [CSize.](../../atl-mfc-shared/reference/csize-class.md)

*lpRect*<br/>
Указатель на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect.](../../atl-mfc-shared/reference/crect-class.md)

### <a name="return-value"></a>Возвращаемое значение

А `CSize` это разница между двумя `CPoint` точками, которая компенсируется отрицанием `CRect` размера, которая компенсируется отрицанием точки, `CPoint` или отрицанием точки.

### <a name="remarks"></a>Примечания

Третья перегрузка компенсирует `CRect` отрицание `CPoint`. Наконец, используйте неопрягие оператора, чтобы свести на нет `CPoint`.

Например, используя первую перегрузку, чтобы `CPoint(25, -19)` `CPoint(15, 5)` найти `CSize(10, -24)`разницу между двумя точками и возвратами.

Вычитание `CSize` `CPoint` из делает тот же расчет, как выше, но возвращает `CPoint` объект, а `CSize` не объект. Например, используя вторую перегрузку, чтобы `CPoint(25, -19)` найти `CSize(15, 5)` разницу между точкой и размером возвращается. `CPoint(10, -24)`

Вычитание прямоугольника из точки возвращает прямоугольник, компенсированный `x` `y` негативами и значениями, указанными в точке. Например, использование последней перегрузки `CRect(125, 200, 325, 400)` для компенсации `CRect(100, 219, 300, 419)`прямоугольника по возврату точек. `CPoint(25, -19)`

Используйте неопрятого оператора, чтобы свести на нет точку. Например, использование неоправного `CPoint(25, -19)` оператора `CPoint(-25, 19)`с точечной отдачей.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура POINT](/windows/win32/api/windef/ns-windef-point)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CSize](../../atl-mfc-shared/reference/csize-class.md)
