---
title: Класс Кмфкстандардколорспропертипаже
ms.date: 11/04/2016
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
ms.openlocfilehash: c57715171816e83cd1e04872d88b452b51b39388
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843954"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>Класс Кмфкстандардколорспропертипаже

Представляет страницу свойств, используемую пользователями для выбора стандартных цветов в диалоговом окне цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|`CMFCStandardColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCStandardColorsPropertyPage::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|

### <a name="remarks"></a>Примечания

`CMFCColorDialog`Класс использует этот класс для вывода страницы свойств стандартного цвета. Дополнительные сведения о см `CMFCColorDialog` . в разделе [класс кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[кмфкстандардколорспропертипаже](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксстандардколорспропертипаже.h

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс Кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md)<br/>
[Класс Кмфккустомколорспропертипаже](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
