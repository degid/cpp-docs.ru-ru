---
title: Класс Кмфкдисаблеменуаниматион
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 97a93e000b3e12d8ec4824100059581216b1b8d9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840769"
---
# <a name="cmfcdisablemenuanimation-class"></a>Класс Кмфкдисаблеменуаниматион

Отключает анимацию всплывающего меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Формирует объект `CMFCDisableMenuAnimation`.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфкдисаблеменуаниматион:: RESTORE](#restore)|Восстанавливает предыдущую анимацию, используемую платформой для отображения всплывающего меню.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|`CMFCDisableMenuAnimation::m_animType`|Сохраняет предыдущий тип анимации всплывающего меню.|

### <a name="remarks"></a>Примечания

Используйте этот вспомогательный класс, чтобы временно отключить анимацию всплывающего меню (например, при обработке команд мыши или клавиатуры).

`CMFCDisableMenuAnimation`Объект отключает анимацию всплывающего меню в течение своего времени существования. Конструктор сохраняет текущий тип анимации всплывающего меню в `m_animType` поле и устанавливает для текущего типа анимации значение `CMFCPopupMenu::NO_ANIMATION` . Деструктор восстанавливает предыдущий тип анимации.

Можно создать `CMFCDisableMenuAnimation` объект в стеке, чтобы отключить анимацию всплывающего меню в рамках одной функции. Если вы хотите отключить анимацию всплывающего меню между функциями, создайте `CMFCDisableMenuAnimation` объект в куче, а затем удалите его, если хотите восстановить анимацию всплывающего меню.

## <a name="example"></a>Пример

В следующем примере показано, как использовать стек для временного отключения анимации меню.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[кмфкдисаблеменуаниматион](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспопупмену.h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a> Кмфкдисаблеменуаниматион:: RESTORE

Восстанавливает предыдущую анимацию, используемую платформой для отображения всплывающего меню.

```cpp
void Restore ();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается `CMFCDisableMenuAnimation` деструктором для восстановления предыдущей анимации, используемой платформой для отображения всплывающего меню.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
