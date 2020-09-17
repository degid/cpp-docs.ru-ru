---
title: Класс CMFCLinkCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 79edff8be6e2c37baa938fc5b624253932609e17
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754246"
---
# <a name="cmfclinkctrl-class"></a>Класс CMFCLinkCtrl

Класс `CMFCLinkCtrl` отображает кнопку в виде гиперссылки и вызывает цель ссылки при нажатии кнопки.

## <a name="syntax"></a>Синтаксис

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCLinkCtrl:SetURL](#seturl)|Отображает указанный URL в виде текста кнопки.|
|[CMFCLinkCtrl:SetURLPrefix](#seturlprefix)|Устанавливает неявный протокол (например, "http:") URL.|
|[CMFCLinkCtrl:SizetoContent](#sizetocontent)|Изображает кнопку, чтобы содержать текст кнопки или бит-карту.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Вызывается рамки до фокус прямоугольника кнопки обращается.|

## <a name="remarks"></a>Примечания

При нажатии кнопки, полученной `CMFCLinkCtrl` из класса, фреймворк передает URL-адрес кнопки в качестве параметра методу. `ShellExecute` Затем `ShellExecute` метод открывает цель URL.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCLinkCtrl` установить размер объекта и как установить `CMFCLinkCtrl` URL и набор инструментов в объекте. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxlinkctrl.h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect

Вызывается рамки до фокус прямоугольника кнопки обращается.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectClient*<br/>
(в) Прямоугольник, который граничит с управлением ссылкой.

### <a name="remarks"></a>Примечания

Переопределить этот метод, когда вы хотите использовать свой собственный код, чтобы нарисовать прямоугольник фокуса кнопки.

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl:SetURL

Отображает указанный URL в виде текста кнопки.

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
(в) Текст кнопки для отображения.

### <a name="remarks"></a>Примечания

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl:SetURLPrefix

Устанавливает неявный протокол (например, "http:") URL.

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Параметры

*lpszPrefix*<br/>
(в) Префикс протокола URL.

### <a name="remarks"></a>Примечания

Используйте этот метод для установки префикса URL. Префикс не отображается на лице кнопки, но вы можете использовать его, чтобы помочь просматривать цель URL.

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl:SizetoContent

Изображает кнопку, чтобы содержать текст кнопки или бит-карту.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Параметры

*bVCenter*<br/>
(в) TRUE для центрирования текста кнопки и bitmap вертикально между верхней и нижней части управления ссылкой; в противном случае, FALSE. Значение по умолчанию — FALSE.

*bHCenter*<br/>
(в) TRUE для центрирования текста кнопки и bitmap горизонтально между левой и правой сторонами управления ссылкой; в противном случае, FALSE. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) содержащий новый размер управления ссылками.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CLinkCtrl](../../mfc/reference/clinkctrl-class.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
