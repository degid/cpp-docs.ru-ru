---
title: CMFCRibbonProgressBar Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: b7cbddbd4fca8379562b762fadbb3d2bda44f166
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753530"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar Класс

Реализует элемент управления, который визуально показывает ход выполнения длительных операций.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Создает и инициализирует объект `CMFCRibbonProgressBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|Возвращает текущий прогресс.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Возвращает максимальное значение текущего диапазона.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Возвращает минимальное значение текущего диапазона.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Оверлет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Определяет, работает ли панель прогресса в бесконечном режиме.|
|[CMFCRibbonProgressBar::Ondraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::Ondraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Устанавливает панель прогресса для работы в бесконечном режиме.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|Устанавливает текущий прогресс.|
|[CMFCRibbonProgressBar::SetRange](#setrange)|Устанавливает минимальные и максимальные значения.|

## <a name="remarks"></a>Примечания

A `CMFCRibbonProgressBar` может работать в двух режимах: регулярном и бесконечном. В обычном режиме панель прогресса заполняется слева направо и останавливается, когда достигает максимального значения. В бесконечном режиме панель прогресса неоднократно заполняется от минимального значения до максимального значения. Можно использовать бесконечный режим, чтобы указать, что операция продолжается, но время завершения неизвестно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonProgressBar` . В примере показано, как настроить панель прогресса для работы в бесконечном режиме (когда время завершения операции неизвестно), установить минимальные и максимальные значения для панели прогресса и установить текущее положение панели прогресса. Этот фрагмент кода является частью [образца MS Office 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonProgressBar.h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar

Строит и инициализирует объект [CMFCRibbonProgressBar.](../../mfc/reference/cmfcribbonprogressbar-class.md)

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Определяет идентификатор команды для панели прогресса ленты.

*nWidth*<br/>
(в) Определяет ширину, в пикселях, ленты панели прогресса.

*nВысота*<br/>
(в) Определяет высоту, в пикселях, ленты прогресса бар.

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a>CMFCRibbonProgressBar::GetPos

Возвращает текущее положение бара прогресса.

```
int GetPos () const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее текущее положение панели прогресса.

### <a name="remarks"></a>Примечания

Диапазон, устанавливаемый, должен находиться в пределах диапазона, указанного методом [CMFCRibbonProgressBar::SetRange.](#setrange)

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax

Возвращает текущее максимальное значение панели прогресса.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное значение текущего диапазона.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin

Возвращает текущее минимальное значение диапазона хода.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное значение текущего диапазона.

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode

Определяет, работает ли панель прогресса в бесконечном режиме.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель прогресса находится в бесконечном режиме; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

В бесконечном режиме панель прогресса заполняется повторно от минимального значения до максимального значения. Можно использовать бесконечный режим, чтобы указать, что операция продолжается, но время завершения неизвестно.

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a>CMFCRibbonProgressBar::Ondraw

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode

Устанавливает панель прогресса для работы в бесконечном режиме.

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
(в) TRUE указать, что панель прогресса находится в бесконечном режиме; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Обычно, если панель прогресса находится в бесконечном режиме, она говорит пользователю, что операция продолжается, но время завершения неизвестно. Таким образом, панель прогресса заполняет повторно от минимального значения к максимальному значению.

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a>CMFCRibbonProgressBar::SetPos

Устанавливает текущее положение панели прогресса.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
(в) Определяет положение, в котором установлена панель прогресса.

*bRedraw*<br/>
(в) Определяет, следует ли перерисовывать планку прогресса.

### <a name="remarks"></a>Примечания

Диапазон, устанавливаемый, должен находиться в пределах диапазона, указанного методом [CMFCRibbonProgressBar::SetRange.](#setrange)

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a>CMFCRibbonProgressBar::SetRange

Устанавливает минимальные и максимальные значения для панели прогресса.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
(в) Определяет минимальное значение диапазона.

*nMax*<br/>
(в) Определяет максимальное значение диапазона.

### <a name="remarks"></a>Примечания

Используйте этот метод для определения диапазона панели прогресса, установив минимальные и максимальные значения.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
