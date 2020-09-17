---
title: Класс CMFCMenuButton
ms.date: 07/15/2019
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
- AFXMENUBUTTON/CMFCMenuButton::m_bDefaultClick
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
- CMFCMenuButton [MFC], m_bDefaultClick
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: 929fc1c8166f249fe3babc724b2c0bcd9cb99676
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369674"
---
# <a name="cmfcmenubutton-class"></a>Класс CMFCMenuButton

Кнопку, которая отображает контекстное меню и сообщает, какие пункты выбирает в меню пользователь.

## <a name="syntax"></a>Синтаксис

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCМенюБаттл::CMFCMenuButton](#cmfcmenubutton)|Формирует объект `CMFCMenuButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Вызывается инфраструктурой для перевода оконных сообщений перед отправкой. (Переопределяет `CMFCButton::PreTranslateMessage`.)|
|[CMFCMenuButton::Sizetocontent](#sizetocontent)|Изменяет размер кнопки в зависимости от ее текста и размера изображения.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Уточняется, отображать ли всплывающее меню системы по умолчанию или использовать [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Уточняется, будет ли всплывающее меню отображаться под или справа от кнопки.|
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Уточняется, изменяет ли кнопка меню свое состояние после того, как пользователь выпустит кнопку.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ручка к прилагаемому меню Windows.|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Идентификатор, указывающий, какой элемент выбрал пользователь из всплывающем меню.|
|[CMFCMenuButton::m_bDefaultClick](#m_bdefaultclick)| Разрешить обработку текста/изображения по умолчанию (на кнопке текста/изображения).|

## <a name="remarks"></a>Примечания

Класс `CMFCMenuButton` происходит от [класса CMFCButton,](../../mfc/reference/cmfcbutton-class.md) который, в свою очередь, происходит от [класса CButton.](../../mfc/reference/cbutton-class.md) Таким образом, `CMFCMenuButton` вы можете использовать в коде так же, как вы будете использовать. `CButton`

При `CMFCMenuButton`создании, вы должны пройти в ручку связанного всплывающее меню. Далее позвоните `CMFCMenuButton::SizeToContent`функции . `CMFCMenuButton::SizeToContent`проверяет, что размер кнопки достаточен для включения стрелки, укоторойятой на место, где появится всплывающее окно, а именно, под или справа от кнопки.

## <a name="example"></a>Пример

В следующем примере показано, как настроить ручку меню, прикрепленную к кнопке, изменить размер кнопки в соответствии с ее текстом и размером изображения, а также настроить всплывающее меню, отображаемые рамкой. Этот фрагмент кода является частью [образца new Controls.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxmenubutton.h

## <a name="cmfcmenubuttoncmfcmenubutton"></a><a name="cmfcmenubutton"></a>CMFCМенюБаттл::CMFCMenuButton

Строит новый объект [CMFCMenuButton.](../../mfc/reference/cmfcmenubutton-class.md)

```
CMFCMenuButton();
```

## <a name="cmfcmenubuttonm_bosmenu"></a><a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu

Переменная члена Boolean, которая указывает, какое всплывающее меню отображает фреймворк.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Примечания

Если `m_bOSMenu` это правда, то фреймворк вызывает унаследованный `TrackPopupMenu` метод для этого объекта. В противном случае, фреймворк вызывает [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

## <a name="cmfcmenubuttonm_brightarrow"></a><a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow

Переменная члена Boolean, указывают расположение всплывающем меню.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку меню, приложение показывает всплывающее меню. В фреймворке будет отображаться всплывающее меню либо под кнопкой, либо справа от кнопки. Кнопка также имеет небольшую стрелку, которая указывает, где появится всплывающее меню. Если `m_bRightArrow` это правда, фреймворк отображает всплывающее меню справа от кнопки. В противном случае под кнопкой отображается всплывающее меню.

## <a name="cmfcmenubuttonm_bstaypressed"></a><a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed

Переменная члена Boolean, которая указывает, отображается ли кнопка меню нажатой, в то время как пользователь делает выбор из всплывающих меню.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Примечания

Если `m_bStayPressed` участник FALSE, кнопка меню не становится нажатой, когда использует кнопку. В этом случае фреймворк отображает только всплывающее меню.

Если `m_bStayPressed` участник является правдой, кнопка меню становится нажатой, когда пользователь нажимает на кнопку. Он остается нажатым до тех пор, пока пользователь не закроет всплывающее меню, либо сделав выбор, либо отменив.

## <a name="cmfcmenubuttonm_hmenu"></a><a name="m_hmenu"></a>CMFCMenuButton::m_hMenu

Ручка к прилагаемому меню.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Примечания

Рамки отображает меню, указанное этой переменной участника, когда пользователь нажимает кнопку меню.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult

Цель, которая указывает, какой элемент пользователь выбирает из всплывающем меню.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Примечания

Значение этой переменной участника равен нулю, если пользователь отменяет меню без выделения или если происходит ошибка.

## <a name="cmfcmenubuttonm_bdefaultclick"></a><a name="m_bdefaultclick"></a>CMFCMenuButton::m_bDefaultClick

Позволяет обрабатывать текст или изображения по умолчанию на кнопке.

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>Примечания

Установка m_bDefaultClick на ложные причины кнопки, чтобы показать меню, когда вы нажмете в любом месте на кнопку.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult

Цель, которая указывает, какой элемент пользователь выбирает из всплывающем меню.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubuttonpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage

Вызывается инфраструктурой для перевода оконных сообщений перед отправкой.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
(в) Указывает на структуру [MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было переведено и не должно быть отправлено; 0, если сообщение не было переведено и должно быть отправлено.

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCMenuButton::Sizetocontent

Изменяет размер кнопки в зависимости от размера текста и размера изображения.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcТолько*<br/>
(в) Параметр Boolean, указывающий на то, изменяет ли этот метод кнопку.

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) который определяет новый размер для кнопки.

### <a name="remarks"></a>Примечания

Если вы называете эту функцию и `SizeToContent` *bCalcТолько* правда, вычислит только новый размер кнопки.

Новый размер кнопки рассчитывается в соответствии с текстом кнопки, изображением и стрелкой. Фрейм также добавляет в предопределенных полях 10 пикселей для горизонтального края и 5 пикселей для вертикального края.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
