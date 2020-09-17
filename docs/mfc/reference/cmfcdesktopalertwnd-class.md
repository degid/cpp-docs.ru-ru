---
title: CMFCDesktopAlertWnd Class
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: cf453b6e69f012bedaf0bd91b5eaf11f7caffa12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752459"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

Класс `CMFCDesktopAlertWnd` реализует функциональность бесрежимного диалогового окна, который появляется на экране, чтобы информировать пользователя о событии.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWnd::Создание](#create)|Создает и инициализирует окно оповещения рабочего стола.|
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Возвращает скорость анимации.|
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Возвращает тип анимации.|
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Возвращает время автоматического закрытия.|
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту подписи.|
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Возвращает последнее действительное положение окна оповещения рабочего стола на экране.|
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Возвращает уровень прозрачности.|
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Определяет, отображается ли окно оповещения рабочего стола с небольшим заголовком.|
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Вызывается по системе, когда пользователь нажимает кнопку ссылки, расположенную в меню оповещения на рабочем столе.|
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Платформа вызывает эту функцию участника, когда пользователь выбирает элемент из меню, когда элемент управления детьми отправляет сообщение уведомления, или когда нажатие клавиши ускорителя переведено. (Оверлет: [OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Устанавливает новую скорость анимации.|
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Устанавливает тип анимации.|
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Устанавливает автоматическое закрытие тайм-аута.|
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Переключается между малыми и нормальными подписями.|
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Устанавливает уровень прозрачности.|

## <a name="remarks"></a>Примечания

Окно оповещения на рабочем столе может быть прозрачным, оно может отображаться с эффектами анимации, и оно может исчезнуть (после указанной задержки или когда пользователь отклоняет его, нажав кнопку закрытия).

Окно оповещения на рабочем столе также может содержать диалог по умолчанию, который, в свою очередь, содержит значок, текст сообщения (метка) и ссылку. Кроме того, окно оповещения на рабочем столе может содержать пользовательский диалог из ресурсов приложения.

Вы создаете окно оповещения рабочего стола в два этапа. Во-первых, позвоните в `CMFCDesktopAlertWnd` конструктор, чтобы построить объект. Во-вторых, позвоните [в CMFCDesktopAlertWnd::Создать](#create) функцию `CMFCDesktopAlertWnd` члена для создания окна и прикрепить его к объекту.

Объект `CMFCDesktopAlertWnd` создает специальную детскую диалоговую коробку, которая заполняет область клиента окна оповещения рабочего стола. Диалог владеет всеми элементами управления, которые расположены на нем.

Чтобы отобразить пользовательский диалоговый ящик на всплывающем окне, выполните следующие действия:

1. Создайте производный класс от класса `CMFCDesktopAlertDialog`.

1. Создайте шаблон детского диалогового окна в ресурсах.

1. Позвоните [CMFCDesktopAlertWnd::Создание](#create) с использованием идентификатора ресурсов шаблона диалогового окна и указателя на информацию класса времени выполнения производного класса.

1. Программа пользовательский диалоговые окна для обработки всех уведомлений, поступающих от размещенных элементов управления, или запрограммируйте размещенные элементы управления для обработки этих уведомлений напрямую.

Используйте следующие функции для управления поведением окна оповещения рабочего стола:

- Установите тип анимации, позвонив [по CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Действительные варианты включают разворачиваться, скользить и исчезать.

- Установите скорость кадра анимации, позвонив [cmFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).

- Установите уровень прозрачности, позвонив [в CMFCDesktopAlertWnd::SetTransparency](#settransparency).

- Измените размер подписи на небольшой, позвонив [по CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Небольшая подпись высотой 7 пикселей.

## <a name="example"></a>Пример

Ниже приведен пример, иллюстрирующий, как `CMFCDesktopAlertWnd` использовать различные `CMFCDesktopAlertWnd` методы в классе для настройки объекта. На примере показано, как установить тип анимации, установить прозрачность всплывающее окно, указать, что окно оповещения отображает небольшую подпись, и установить время, которое проявляется до автоматического закрытия окна оповещения. В примере также показано, как создать и инициализировать окно оповещения рабочего стола. Этот фрагмент кода является частью [образца демо-версии оповещения рабочего стола.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDesktopAlertWnd.h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a>CMFCDesktopAlertWnd::Создание

Создает и инициализирует окно оповещения рабочего стола.

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>Параметры

*pWndВладелец*<br/>
(в, вне) Определяет владельца окна оповещения. Затем этот владелец будет получать все уведомления для окна оповещения на рабочем столе. Это значение не может быть NULL.

*uiDlgResID*<br/>
(в) Упогоняет идентификатор ресурса окна оповещения.

*hMenu*<br/>
(в) Упоняет меню, отображаемые при нажатии кнопки меню. Если NULL, кнопка меню не отображается.

*ptPos*<br/>
(в) Определяет исходное положение, в котором отображается окно оповещения, с помощью координат экрана. Если этот параметр (-1, -1), окно оповещения отображается в правом нижнем углу экрана.

*pRTIDlgBar*<br/>
(в) Информация о классе Runtime для пользовательского класса диалоговых коробок, который охватывает клиентскую зону окна оповещения.

*params*<br/>
(в) Определяет параметры, которые используются для создания окна оповещения.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно оповещения было создано успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы создать окно оповещения. Область клиента окна оповещения содержит детское диалоговое окно, в котором размещаются все элементы управления, отображаемые пользователю.

Перегрузка первого метода создает окно оповещения, содержащее детское диалоговое окно, загруженное из ресурсов приложения. Перегрузка первого метода может также указывать информацию о классе времени выполнения для пользовательского класса диалоговых коробок.

Перегрузка второго метода создает окно оповещения, содержащее элементы управления по умолчанию. Вы можете указать, какие элементы управления для отображения, изменив [CMFCDesktopAlertWnDInfo класса](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed

Возвращает скорость анимации.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Скорость анимации окна оповещения, в миллисекундах.

### <a name="remarks"></a>Примечания

Скорость анимации описывает, как быстро открывается и закрывается окно оповещения.

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType

Возвращает тип анимации.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Возвращаемое значение

Один из следующих типов анимации:

- NO_ANIMATION

- Разворачиваться

- Слайд

- Исчезают

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime

Возвращает время автоматического закрытия.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время, в миллисекундах, после чего окно оповещения автоматически закрывается.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы определить, сколько времени должно продолжаться до автоматического закрытия окна оповещения.

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight

Возвращает высоту подписи.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Возвращаемое значение

Высота, в пикселях, подписи.

### <a name="remarks"></a>Примечания

Этот метод может быть переопределен в производном классе. Реализация по умолчанию также: возвращает небольшое значение высоты заголовка (7 пикселей), если всплывающее окно `GetSystemMetrics(SM_CYSMCAPTION)`должно отображать небольшую подпись, или значение, полученное от функции API Windows.

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos

Возвращает последнее положение окна оповещения рабочего стола на экране.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Точка, в координатах экрана.

### <a name="remarks"></a>Примечания

Этот метод возвращает последнее действительное положение окна оповещения на экране.

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency

Возвращает уровень прозрачности.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Уровень прозрачности между 0 и 255, включительно. Чем больше значение, тем более непрозрачным является окно.

### <a name="remarks"></a>Примечания

Используйте этот метод для получения текущего уровня прозрачности окна оповещения.

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption

Определяет, имеет ли окно оповещения настольного компьютера небольшую подпись или подпись обычного размера.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если всплывающее окно отображается с небольшой подписью; FALSE, если всплывающее окно отображается с речкой обычного размера.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы определить, есть ли всплывающее окно имеет небольшую подпись или подпись обычного размера. По умолчанию высота небольшой подписи составляет 7 пикселей. Вы можете получить высоту подписи обычного размера, позвонив в функцию `GetSystemMetrics(SM_CYCAPTION)`API Windows.

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Параметры

(в) *CPoint&*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton

Вызывается по системе, когда пользователь нажимает кнопку ссылки, расположенную в меню оповещения на рабочем столе.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
(в) Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Всегда значение FALSE.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе, если вы хотите получать уведомления, когда пользователь нажимает на ссылку на окне оповещения.

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

(в) *wParam*<br/>

(в) *lПарам*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Параметры

(в) *hwnd*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed

Устанавливает новую скорость анимации.

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Параметры

*nСкорость*<br/>
(в) Определяет новую скорость анимации, в миллисекундах.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы установить скорость анимации для окна оповещения. Скорость анимации по умолчанию составляет 30 миллисекунд.

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType

Устанавливает тип анимации.

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Параметры

*type*<br/>
(в) Определяет тип анимации.

### <a name="remarks"></a>Примечания

Вызовите этот метод для установки типа анимации. Можно указать одно из следующих значений.

- NO_ANIMATION

- Разворачиваться

- Слайд

- Исчезают

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime

Устанавливает автоматическое закрытие тайм-аута.

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Параметры

*nВремя*<br/>
(в) Время, в миллисекундах, которое продляется до того, как окно оповещения автоматически закрывается.

### <a name="remarks"></a>Примечания

Окно оповещения автоматически закрывается после указанного времени, если пользователь не взаимодействует с окном.

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption

Переключается между подписями малого и обычного размера.

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Параметры

*bSmallCaptioncaption*<br/>
(в) TRUE указать, что окно оповещения отображает небольшую подпись; в противном случае FALSE уточнил, что окно оповещения отображает подпись обычного размера.

### <a name="remarks"></a>Примечания

Вызовите этот метод для отображения подписи небольшого или обычного размера. По умолчанию высота небольшой подписи составляет 7 пикселей. Размер обычной подписи можно получить, позвонив в функцию `GetSystemMetrics(SM_CYCAPTION)`API Windows.

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency

Устанавливает уровень прозрачности всплывающее окно.

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Параметры

*nПрозрачность*<br/>
(в) Определяет уровень прозрачности. Это значение должно быть между 0 и 255, включительно. Чем больше значение, тем более непрозрачным является окно.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы установить уровень прозрачности всплывающее окно.

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CmFCDesktopAlertWndInfo класс](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)
