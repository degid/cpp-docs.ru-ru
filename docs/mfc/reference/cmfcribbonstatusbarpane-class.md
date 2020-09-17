---
title: Класс CMFCRibbonStatusBarPane
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: bb4e09eabab17061812ed22b2739d06accd57fee
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753513"
---
# <a name="cmfcribbonstatusbarpane-class"></a>Класс CMFCRibbonStatusBarPane

Класс `CMFCRibbonStatusBarPane` реализует элемент ленты, который можно добавить в бар состояния ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Создает и инициализирует объект `CMFCRibbonStatusBarPane`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Возвращает строку, определяющую самую длинную текстовую строку, которая может отображаться в стеле без усечения.|
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Возвращает текущую настройку выравнивания текста.|
|[CMFCRibbonStatusBarPane::Анимация](#isanimation)|Определяет, выполняется ли анимация.|
|[CMFCRibbonStatusBarPane::Расширенный](#isextended)|Определяет, находится ли панель в расширенной области ленты статус бар.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Переопределяет [CMFCRibbonButton::OndrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Переопределяет [CMFCRibbonButton::OnFillbackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Определяет самую длинную текстовую строку, которая может отображаться в стеле без усечения.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Присваивает панели список изображений, которые могут быть использованы для анимации.|
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Устанавливает выравнивание текста.|
|[CMFCRibbonStatusBarPane::СтартАним](#startanimation)|Запускает анимацию, назначенную на панель.|
|[CMFCRibbonStatusBarPane:StopAnimation](#stopanimation)|Остановка анимации, назначенной на панель. .|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Вызывается по фреймворку, когда анимация, назначенная панели, останавливается.|

## <a name="example"></a>Пример

В следующем примере демонстрируется использование различных методов класса `CMFCRibbonStatusBarPane`. На примере показано, `CMFCRibbonStatusBarPane` как построить объект, установить выравнивание текста панели знака статуса, определить самый длинный текст, который может отображаться в панели панели состояния без усечения, прикрепить к панели статуса панели список изображений, которые могут быть использованы для анимации, и начать анимацию.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonstatusbarpane.h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Постройте объект панели панели в панели статуса.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
(в) Упогоняет идентификатор команды панели.

*lpszText*<br/>
(в) Определяет строку текста для отображения на панели.

*bIsStatic*<br/>
(в) Если true, панель статуса не может быть выделена или выбрана, нажав на него.

*hIcon*<br/>
(в) Обращайтесь к рукоятке значка, который будет отображаться на панели.

*lpszAlmostLargeText*<br/>
(в) Определяет самую длинную текстовую строку, которая может отображаться на панели.

*hBmpAnimationList*<br/>
(в) Определяет ручку в списке изображений, который используется для анимации.

*cxАнимация*<br/>
(в) Определяет ширину в пикселях значка в списке изображений, который используется для анимации.

*clrTrnsp*<br/>
(в) Определяет прозрачный цвет изображений в списке изображений, которые используются для анимации.

*uiAnimationListResID*<br/>
(в) Упогоняет идентификатор ресурса списка изображений, который используется для анимации.

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText

Получает самую длинную текстовую строку, которую может отображать панель статуса.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Самая длинная строка текста, которую может отображать панель статуса.

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign

Получает текущую настройку выравнивания текста метки панели status.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее выравнивание текста, которое может быть одним из следующих:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a>CMFCRibbonStatusBarPane::Анимация

Определяет, выполняется ли анимация.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если анимация продолжается; FALSE в противном случае.

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a>CMFCRibbonStatusBarPane::Расширенный

Определите, находится ли панель в расширенной области ленты статус бар.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель находится на статус бар расширенной области. FALSE в противном случае.

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Параметры

(в) *CDC&#42;*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation

Рамочная система вызывает этот метод, когда анимация, назначенная панели, заканчивается.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Примечания

`StopAnimation`метод вызывает `OnFinishAnimation` метод, который можно использовать для очистки данных по окончании анимации.

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText

Определите самый длинный текст, который может отображаться в панели панели status bar без усечения.

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Параметры

*lpszAlmostLargeText*<br/>
(в) Определяет самую длинную строку, которая может отображаться на панели строки состояния без усечения.

### <a name="remarks"></a>Примечания

Библиотека вычисляет размер текста, который *lpszAlmostLargeText* определяет и изменяет панель соответственно. Текст будет усечен, если он все еще не помещается в стекол.

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList

Прикрепляет к панели статуса панель списка изображений, которые могут быть использованы для анимации.

```cpp
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>Параметры

*hBmpAnimationList*<br/>
(в) Определяет ручку в списке изображений.

*cxАнимация*<br/>
(в) Определяет ширину в пикселях кадра в списке изображений.

*clrTransp*<br/>
(в) Определяет прозрачный цвет списка изображений.

*uiAnimationListResID*<br/>
(в) Упогоняет идентификатор ресурса списка изображений.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если список изображений успешно прилагается к панели панели панели статуса; FALSE в противном случае.

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign

Устанавливает выравнивание текста метки стежка-панели статуса.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Параметры

*nAlign*<br/>
(в) Определяет выравнивание текста.

### <a name="remarks"></a>Примечания

*nAlign* может иметь одно из следующих значений:

- TA_LEFT: левое выравнивание

- TA_CENTER: выравнивание центра

- TA_RIGHT: правое выравнивание

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a>CMFCRibbonStatusBarPane::СтартАним

Запускает анимацию, которую вы назначаете панели.

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Параметры

*nФреймДерайка*<br/>
(в) Определяет частоту кадров анимации в миллисекундах.

*nDuration*<br/>
(в) Определяет, как долго играть анимацию, в миллисекундах. Используйте -1 для бесконечного цикла.

### <a name="remarks"></a>Примечания

Перед вызовом `StartAnimation` `SetAnimationList`необходимо указать ручку в списке изображений.

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a>CMFCRibbonStatusBarPane:StopAnimation

Остановка анимации, назначенной на панель состояния.

```cpp
void StopAnimation();
```

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Класс CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)
