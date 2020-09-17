---
title: Класс CScrollView
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: 5d0eb163fae2aa5fc63470e1c499311ab1a402a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754418"
---
# <a name="cscrollview-class"></a>Класс CScrollView

[CView](../../mfc/reference/cview-class.md) с возможностями прокрутки.

## <a name="syntax"></a>Синтаксис

```
class CScrollView : public CView
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|Формирует объект `CScrollView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|Указывает, имеет ли представление прокрутки горизонтальные и вертикальные бары прокрутки.|
|[CScrollView:FillOutsideRect](#filloutsiderect)|Заполняет область вида за пределами области прокрутки.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Получает текущее положение прокрутки в единицах устройства.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Получает текущий режим отображения, общий размер и размерстроки и размеры страниц прокрутки. Размеры находятся в единицах устройства.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Получает текущее положение прокрутки в логических единицах.|
|[CScrollView::GetTotalSize](#gettotalsize)|Получает общий размер представления прокрутки в логических единицах.|
|[CScrollview::ResizeParentTofit](#resizeparenttofit)|Вызывает размер представления, чтобы диктовать размер его кадра.|
|[Скротноввью::Прокрутка топозиции](#scrolltoposition)|Прокрутите представление до заданной точки, указанной в логических единицах.|
|[CScrollview::SetscaleTofitSize](#setscaletofitsize)|Помещает представление прокрутки в режим масштабирования.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Устанавливает режим отображения представления прокрутки, общий размер и горизонтальные и вертикальные суммы прокрутки.|

## <a name="remarks"></a>Примечания

Вы можете обрабатывать стандартные прокрутки `CView` себя в любом классе, полученном от, переопределяя сообщения отображаются [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) членов функций. Но `CScrollView` добавляет следующие `CView` функции к своим возможностям:

- Он управляет размерами окон и viewport и режимами отображения.

- Он автоматически прокручивается в ответ на сообщения прокрутки-бар.

- Он автоматически прокручивается в ответ на сообщения с клавиатуры, мыши без прокрутки или колеса IntelliMouse.

Чтобы прокрутить автоматически в ответ на сообщения с клавиатуры, добавьте сообщение WM_KEYDOWN и проверьте VK_DOWN, VK_PREV и вызов [SetScrollPos.](/windows/win32/api/winuser/nf-winuser-setscrollpos)

Вы можете обрабатывать мыши колесо прокрутки себя, переопределяя сообщения отображаются [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) и [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) членов функций. Как они `CScrollView`для, эти функции члена поддерживают рекомендуемое поведение для [WM_MOUSEWHEEL,](/windows/win32/inputdev/wm-mousewheel)сообщение вращения колеса.

Чтобы воспользоваться преимуществами автоматической прокрутки, `CView`вычеркните класс представления из. `CScrollView` При первом создании представления, если вы хотите вычислить размер прокрутки представления `SetScrollSizes` на основе размера документа, позвоните функции участника из переопределения [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) или [CView::: OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Вы должны написать свой собственный код, чтобы задать запрос размер документа. Например, см. [образец Scribble](../../overview/visual-cpp-samples.md).)

Вызов функции `SetScrollSizes` члена устанавливает режим отображения представления, общие размеры представления прокрутки и суммы для прокрутки горизонтально и вертикально. Все размеры находятся в логических единицах. Логический размер представления обычно рассчитывается на основе данных, хранящихся в документе, но в некоторых случаях может потребоваться указать фиксированный размер. Примеры обоих подходов см. [CScrollView::SetScrollSizes](#setscrollsizes).

Вы указываете суммы для прокрутки горизонтально и вертикально в логических единицах. По умолчанию, если пользователь нажимает на вал `CScrollView` панели прокрутки за пределами окна прокрутки, прокрутки "страница". Если пользователь нажимает стрелку прокрутки `CScrollView` на обоих концах панели прокрутки, прокрутка "линии". По умолчанию страница составляет 1/10 от общего размера представления; строка 1/10 от размера страницы. Переопределить эти значения по умолчанию, `SetScrollSizes` передавая пользовательские размеры в функции члена. Например, можно установить горизонтальный размер на некоторую долю ширины общего размера и вертикальный размер на высоту линии в текущем шрифте.

Вместо прокрутки `CScrollView` можно автоматически масштабировать представление до текущего размера окна. В этом режиме представление не имеет баров прокрутки, и логический вид растягивается или сжимается, чтобы точно соответствовать клиентской области окна. Чтобы использовать эту возможность масштабирования, позвоните [cScrollView::SetScaleToFitSize](#setscaletofitsize). (Позвоните `SetScaleToFitSize` `SetScrollSizes`либо или , но не оба.)

Перед `OnDraw` вызовом функции элемента вашего `CScrollView` производного класса представления `CPaintDC` автоматически настраивает происхождение `OnDraw`объекта типа «устройство-контекст», на который он переходит.

Чтобы настроить происхождение порта представления для `CScrollView` окна прокрутки, переопределяет [CView::OnPrepareDC.](../../mfc/reference/cview-class.md#onpreparedc) Эта настройка является `CPaintDC` автоматической `CScrollView` для `OnDraw`контекста устройства, который переходит к, но вы должны позвонить `CScrollView::OnPrepareDC` себе для любых других контекстов устройства вы используете, `CClientDC`например, Можно переопределить, `CScrollView::OnPrepareDC` чтобы установить ручку, цвет фона и другие атрибуты чертежа, но вызвать базовый класс, чтобы сделать масштабирование.

Прокрутка баров может отображаться в трех местах относительно представления, как показано в следующих случаях:

- Стандартные панели прокрутки в стиле окна могут быть установлены для представления с помощью WS_HSCROLL и WS_VSCROLL[стилей Windows.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

- Элементы управления прокруткой также могут быть добавлены в кадр, содержащий представление, и в этом случае фреймворк перенаправляет WM_HSCROLL и WM_VSCROLL сообщения из окна кадра в активное представление.

- Фрейм также перенаправляет `CSplitterWnd` сообщения прокрутки из элемента управления сплиттером в действующая в настоящее время сплиттерная панель (вид). При размещении в [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) с `CScrollView` общими полосами прокрутки объект будет использовать общие, а не создавать свои собственные.

Для получения дополнительной `CScrollView`информации об использовании, см. [Документ / Просмотр Архитектура](../../mfc/document-view-architecture.md) и [производные классы просмотра доступны в MFC](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>CScrollView::CheckScrollBars

Вызовите эту функцию участника, чтобы определить, имеет ли представление прокрутки горизонтальные и вертикальные бары.

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Параметры

*bHasHorzBar*<br/>
Указывает, что приложение имеет горизонтальную панель прокрутки.

*bHasVertBar*<br/>
Указывает, что приложение имеет вертикальную панель прокрутки.

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a>CScrollView::CScrollView

Формирует объект `CScrollView`.

```
CScrollView();
```

### <a name="remarks"></a>Примечания

Вы должны `SetScrollSizes` позвонить либо, либо `SetScaleToFitSize` до того, как представление прокрутки можно почерковать.

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>CScrollView:FillOutsideRect

Вызов `FillOutsideRect` для заполнения области представления, которая отображается за пределами области прокрутки.

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Контекст устройства, в котором должна быть выполнена начинка.

*pBrush*<br/>
Кисть, с которой область должна быть заполнена.

### <a name="remarks"></a>Примечания

Используйте `FillOutsideRect` функцию обработчика `OnEraseBkgnd` представления прокрутки, чтобы предотвратить чрезмерную перекраску фона.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>CScrollView::GetDeviceScrollPosition

Звоните, `GetDeviceScrollPosition` когда вам нужно текущее горизонтальное и вертикальное положение ящиков прокрутки в барах прокрутки.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальные и вертикальные положения (в единицах `CPoint` устройства) ящиков прокрутки как объекта.

### <a name="remarks"></a>Примечания

Эта пара координат соответствует местоположению в документе, к которому прокручивается верхний левый угол зрения. Это полезно для компенсации позиций мыши-устройства для прокрутки позиций устройства.

`GetDeviceScrollPosition`возвращает значения в единицах устройства. Если вы хотите логические единицы, вместо этого используйте. `GetScrollPosition`

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes`получает текущий режим отображения, общий размер, а также размерстроки и размеры страниц прокрутки.

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Параметры

*nMapMode*<br/>
Возвращает текущий режим отображения для этого представления. Список возможных значений см. в разделе `SetScrollSizes`.

*размерTotal*<br/>
Возвращает текущий общий размер представления прокрутки в единицах устройства.

*размерСтраница*<br/>
Возвращает текущие горизонтальные и вертикальные суммы для прокрутки в каждом направлении в ответ на щелчп мыши в валу прокрутки-бар. Участник `cx` содержит горизонтальную сумму. Участник `cy` содержит вертикальную сумму.

*sizeLine*<br/>
Возвращает текущие горизонтальные и вертикальные суммы для прокрутки в каждом направлении в ответ на щелчпмыши мышью в стрелке прокрутки. Участник `cx` содержит горизонтальную сумму. Участник `cy` содержит вертикальную сумму.

### <a name="remarks"></a>Примечания

Размеры находятся в единицах устройства. Эта функция члена редко вызывается.

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>CScrollView::GetScrollPosition

Звоните, `GetScrollPosition` когда вам нужно текущее горизонтальное и вертикальное положение ящиков прокрутки в барах прокрутки.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальные и вертикальные положения (в логических `CPoint` единицах) ящиков прокрутки как объекта.

### <a name="remarks"></a>Примечания

Эта пара координат соответствует местоположению в документе, к которому прокручивается верхний левый угол зрения.

`GetScrollPosition`возвращает значения в логических единицах. Если вам нужны устройства, используйте `GetDeviceScrollPosition` вместо этого.

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a>CScrollView::GetTotalSize

Вызов `GetTotalSize` для получения текущих горизонтальных и вертикальных размеров представления прокрутки.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Общий размер представления прокрутки в логических единицах. Горизонтальный размер находится `cx` в `CSize` составе значения возврата. Вертикальный размер находится `cy` в члене.

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>CScrollview::ResizeParentTofit

Вызов, `ResizeParentToFit` чтобы размер представления диктовать размер окна кадра.

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bShrinkТолько*<br/>
Вид изобрезания для выполнения. Значение по умолчанию, TRUE, при необходимости сжимает окно кадра. Прокрутка баров по-прежнему будет отображаться для больших представлений или небольших окон кадра. Значение FALSE приводит к тому, что представление всегда точно изменяет размер окна кадра. Это может быть несколько опасно, так как окно кадра может стать слишком большим, чтобы поместиться внутри многократного интерфейса документа (MDI) окно кадра или экрана.

### <a name="remarks"></a>Примечания

Это рекомендуется только для просмотра в окнах детской рамки MDI. Используйте `ResizeParentToFit` `OnInitialUpdate` в функции обработчика вашего производного `CScrollView` класса. На примере этой функции участника можно ознакомиться на [cScrollView::SetScrollSizes](#setscrollsizes).

`ResizeParentToFit`предполагает, что размер окна представления установлен. Если размер окна представления не `ResizeParentToFit` установлен при вызове, вы получите утверждение. Чтобы этого не произошло, сделайте следующий звонок перед вызовом: `ResizeParentToFit`

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>Скротноввью::Прокрутка топозиции

Призыв `ScrollToPosition` к прокрутке к заданной точке в представлении.

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Точка для прокрутки в логических единицах. Участник `x` должен иметь положительное значение (больше или равно 0, до общего размера представления). То же самое `y` относится и к участнику, когда режим отображения MM_TEXT. Участник `y` отрицательно относится к режимам отображения, кроме MM_TEXT.

### <a name="remarks"></a>Примечания

Вид будет прокручиваться так, чтобы эта точка была в верхнем левом углу окна. Эта функция члена не должна вызываться, если представление масштабируется в соответствии с.

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>CScrollview::SetscaleTofitSize

Вызов, `SetScaleToFitSize` когда требуется автоматически масштабировать размер порта представления до текущего размера окна.

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Параметры

*размерTotal*<br/>
Горизонтальные и вертикальные размеры, к которым можно масштабировать представление. Размер представления прокрутки измеряется логическими единицами. Горизонтальный размер содержится `cx` в члене. Вертикальный размер содержится `cy` в члене. Оба `cx` `cy` и должны быть больше или равны 0.

### <a name="remarks"></a>Примечания

С помощью баров прокрутки в любое время может быть видна только часть логического представления. Но с возможностью масштабирования, вид не имеет прокрутки баров и логический вид растягивается или сокращается, чтобы точно соответствовать клиентской области окна. При повторном размере окна представление рисует свои данные в новом масштабе в зависимости от размера окна.

Обычно вызов будет размещаться `SetScaleToFitSize` в функции `OnInitialUpdate` члена представления. Если вы не хотите автоматического масштабирования, позвоните функции `SetScrollSizes` участника.

`SetScaleToFitSize`может быть использован для реализации операции «Увеличить до фита». Используйте `SetScrollSizes` для рефализации прокрутки.

`SetScaleToFitSize`предполагает, что размер окна представления установлен. Если размер окна представления не `SetScaleToFitSize` установлен при вызове, вы получите утверждение. Чтобы этого не произошло, сделайте следующий звонок перед вызовом: `SetScaleToFitSize`

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>CScrollView::SetScrollSizes

Звоните, `SetScrollSizes` когда представление вот-вот будет обновлено.

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Параметры

*nMapMode*<br/>
Режим отображения для этого представления. Ниже перечислены возможные значения.

|Режим картирования|Логическая группа|Позитивная y-ось расширяется...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 пиксель|Вниз|
|MM_HIMETRIC|0,01 мм|Вверх|
|MM_TWIPS|1/1440 в|Вверх|
|MM_HIENGLISH|0.001 в|Вверх|
|MM_LOMETRIC|0,1 мм|Вверх|
|MM_LOENGLISH|0,01 в|Вверх|

Все эти режимы определяются Windows. Два стандартных режима отображения, MM_ISOTROPIC `CScrollView`и MM_ANISOTROPIC, не используются для . Библиотека классов предоставляет `SetScaleToFitSize` функцию члена для масштабирования представления до размера окна. Колонка 3 в таблице выше описывает ориентацию координат.

*размерTotal*<br/>
Общий размер представления прокрутки. Член `cx` содержит горизонтальную степень. Член `cy` содержит вертикальную степень. Размеры находятся в логических единицах. Оба `cx` `cy` и должны быть больше или равны 0.

*размерСтраница*<br/>
Горизонтальные и вертикальные суммы для прокрутки в каждом направлении в ответ на щелчком мыши в валу прокрутки-бар. Участник `cx` содержит горизонтальную сумму. Участник `cy` содержит вертикальную сумму.

*sizeLine*<br/>
Горизонтальные и вертикальные суммы для прокрутки в каждом направлении в ответ на щелчком мыши в стрелке прокрутки. Участник `cx` содержит горизонтальную сумму. Участник `cy` содержит вертикальную сумму.

### <a name="remarks"></a>Примечания

Назовите его в `OnUpdate` переопределение функции элемента для настройки характеристик прокрутки, когда, например, документ отображается, или когда он изменяет размер.

Обычно вы получаете информацию о размере из связанного документа представления, вызывая функцию члена документа, возможно, называемую, `GetMyDocSize`которую вы поставляете с вашим классом производных документов. Следующий код показывает этот подход:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Кроме того, иногда может потребоваться установить фиксированный размер, как в следующем коде:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

Режим отображения необходимо установить в любом из режимов отображения Windows, за исключением MM_ISOTROPIC или MM_ANISOTROPIC. Если требуется использовать режим неограниченного отображения, позвоните функции `SetScaleToFitSize` участника вместо `SetScrollSizes`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)
