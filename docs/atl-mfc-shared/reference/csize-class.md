---
title: Класс CSize
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: dc876781cca568a332072938bec2cda0afb2ac8b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746970"
---
# <a name="csize-class"></a>Класс CSize

Аналог структуры [SIZE](/windows/win32/api/windef/ns-windef-size) в ОС Windows, реализующий относительные координаты или положение.

## <a name="syntax"></a>Синтаксис

```
class CSize : public tagSIZE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSize::CSize](#csize)|Формирует объект `CSize`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSize::оператор -](#operator_-)|Вычитает два размера.|
|[CSize::оператор !](#operator_neq)|Проверяет неравенство `CSize` между и размером.|
|[CSize::оператор](#operator_add)|Добавляет два размера.|
|[CSize::оператор](#operator_add_eq)|Добавляет размер `CSize`к .|
|[CSize::оператор -](#operator_-_eq)|Вычитает размер из `CSize`.|
|[CSize::оператор](#operator_eq_eq)|Проверки на `CSize` равенство между и размер.|

## <a name="remarks"></a>Примечания

Этот класс происходит от `SIZE` структуры. Это означает, что `CSize` вы можете пройти `SIZE` в параметр, который `SIZE` требует и что `CSize`данные членов структуры доступны холостых данных членов .

И `cx` `cy` члены `SIZE` (и `CSize`) являются открытыми. Кроме того, `CSize` реализует функции членов `SIZE` для управления структурой.

> [!NOTE]
> Для получения дополнительной информации `CSize`об общих классах утилиты (например), см. [Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagSIZE`

`CSize`

## <a name="requirements"></a>Требования

**Заголовок:** atltypes.h

## <a name="csizecsize"></a><a name="csize"></a>CSize::CSize

Формирует объект `CSize`.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Параметры

*initCX*<br/>
Устанавливает `cx` участника для `CSize`.

*initCY*<br/>
Устанавливает `cy` участника для `CSize`.

*initSize*<br/>
[Структура](/windows/win32/api/windef/ns-windef-size) или `CSize` объект, используемый для инициализации. `CSize`

*initPt*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) Структура point `CPoint` или объект, `CSize`используемый для инициализации.

*dwSize*<br/>
DWORD используется для `CSize`инициализации . Слово низкого порядка является `cx` членом, а слово `cy` высокого порядка — членом.

### <a name="remarks"></a>Примечания

Если аргументы не `cx` приводятся, и `cy` инициализированы до нуля.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a>CSize::оператор

Проверка на равенство между двумя размерами.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевой, если размеры равны, otherwize 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a>CSize::оператор !

Проверяет неравенство между двумя размерами.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевой, если размеры не равны, в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a>CSize::оператор

Добавляет размер к `CSize`этому .

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a>CSize::оператор -

Вычитает размер из `CSize`этого .

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a>CSize::оператор

Эти операторы `CSize` добавляют это значение к значению параметра.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Примечания

Смотрите следующие описания отдельных операторов:

- **оператор No** *(размер)* **)**

  Эта операция `CSize` добавляет два значения.

- **оператор No** *(точка)* **)**

  Эта операция компенсирует (перемещает) значение [POINT](/windows/win32/api/windef/ns-windef-point) (или `CSize` [CPoint)](../../atl-mfc-shared/reference/cpoint-class.md)этим значением. И `cx` `cy` члены `CSize` этого значения добавляются к `x` и `POINT` `y` данные членов значения. Это аналогично версии [CPoint: Оператор,](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) который принимает параметр [СИЗЕ.](/windows/win32/api/windef/ns-windef-size)

- **оператор** *(lpRect* **)**

   Эта операция компенсирует (перемещает) значение [RECT](/windows/win32/api/windef/ns-windef-rect) (или [CRect)](../../atl-mfc-shared/reference/crect-class.md)этим `CSize` значением. И `cx` `cy` члены `CSize` этого значения добавляются `top` `right`к `bottom` `left`, , `RECT` и данные членов значения. Это аналогично версии [CRect: Оператор,](../../atl-mfc-shared/reference/crect-class.md#operator_add) который принимает параметр [СИЗЕ.](/windows/win32/api/windef/ns-windef-size)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a>CSize::оператор -

Первые три из этих операторов вычитают это `CSize` значение в стоимость параметра.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Примечания

Четвертый оператор, неиссякаемый `CSize` минус, меняет знак значения. Смотрите следующие описания отдельных операторов:

- **оператор -(размер)** *size* **)**

  Эта операция вычитает `CSize` два значения.

- **оператор -(точка)** *point* **)**

  Эта операция компенсирует (движется) значение [POINT](/windows/win32/api/windef/ns-windef-point) или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) `CSize` добавкой обратного этого значения. `cy` И `cx` этого `CSize` значения вычитаются из `x` `y` и данных `POINT` членов значения. Он аналогит с версией [CPoint::оператор -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) который принимает параметр [СИЗЕ.](/windows/win32/api/windef/ns-windef-size)

- **оператор -(** *lpRect* **)**

  Эта операция компенсирует (движется) значение [RECT](/windows/win32/api/windef/ns-windef-rect) или [CRect](../../atl-mfc-shared/reference/crect-class.md) `CSize` добавкой обратного этого значения. И `cx` `cy` члены `CSize` этого значения вычитаются `left` `top`из `right`, `bottom` , и `RECT` данные членов значения. Он аналогит с версией [CRect::оператор -](../../atl-mfc-shared/reference/crect-class.md#operator_-) который принимает параметр [СИЗЕ.](/windows/win32/api/windef/ns-windef-size)

- **оператор -()**

  Эта операция возвращает добавку `CSize` обратное этого значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)
