---
title: Класс Кмфкдесктопалертвндбуттон
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 6d296966001dcbc2279a298bdd1d9c21195d61fd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840783"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>Класс Кмфкдесктопалертвндбуттон

Позволяет добавлять кнопки в диалоговое окно оповещения рабочего стола.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Конструктор по умолчанию.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфкдесктопалертвндбуттон:: Искаптионбуттон](#iscaptionbutton)|Определяет, отображается ли кнопка в области субтитров диалогового окна предупреждение.|
|[Кмфкдесктопалертвндбуттон:: Исклосебуттон](#isclosebutton)|Определяет, закрывает ли кнопка диалоговое окно "предупреждение".|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Логическое значение, указывающее, отображается ли кнопка в области субтитров диалогового окна предупреждение.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Логическое значение, указывающее, закрывает ли кнопка диалоговое окно "предупреждение".|

### <a name="remarks"></a>Примечания

По умолчанию конструктор задает `m_bIsCaptionButton` `m_bIsCloseButton` для элементов данных и значение false. Родительский `CMFCDesktopAlertDialog` объект задает `m_bIsCaptionButton` значение true, если кнопка располагается в области заголовка диалогового окна предупреждение. `CMFCDesktopAlertDialog`Класс создает `CMFCDesktopAlertWndButton` объект, который выступает в качестве кнопки, закрываемой диалоговое окно предупреждения, и устанавливает `m_bIsCloseButton` значение true.

Добавляйте `CMFCDesktopAlertWndButton` объекты к `CMFCDesktopAlertDialog` объекту, как только добавляется какая-либо кнопка. Дополнительные сведения о см `CMFCDesktopAlertDialog` . в разделе [класс кмфкдесктопалертдиалог](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как использовать `SetImage` метод в `CMFCDesktopAlertWndButton` классе. Этот фрагмент кода является частью [демонстрационного примера оповещения Desktop](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[кмфкдесктопалертвндбуттон](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксдесктопалертвнд.h

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a> Кмфкдесктопалертвндбуттон:: Искаптионбуттон

Определяет, отображается ли кнопка в области субтитров диалогового окна предупреждение.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка отображается в области субтитров диалогового окна предупреждение. в противном случае — значение 0.

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a> Кмфкдесктопалертвндбуттон:: Исклосебуттон

Определяет, закрывает ли кнопка диалоговое окно "предупреждение".

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка закрывает диалоговое окно "предупреждение". в противном случае — значение 0.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс Кмфкдесктопалертдиалог](../../mfc/reference/cmfcdesktopalertdialog-class.md)
