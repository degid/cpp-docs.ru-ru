---
title: Класс Кмфккустомколорспропертипаже
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 07b369e8c47419db31bed3e49e159e3e7925d5ae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844539"
---
# <a name="cmfccustomcolorspropertypage-class"></a>Класс Кмфккустомколорспропертипаже

Представляет страницу свойств, которая может выбирать пользовательские цвета в диалоговом окне цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|`CMFCCustomColorsPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфккустомколорспропертипаже:: Setup](#setup)|Задает компоненты цвета страницы свойств.|

### <a name="remarks"></a>Примечания

`CMFCColorDialog`Класс использует этот класс для вывода страницы свойств пользовательского цвета. Дополнительные сведения о см `CMFCColorDialog` . в разделе [класс кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как создать `CMFCCustomColorsPropertyPage` объект и установить цветовые компоненты страницы свойств.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[кмфккустомколорспропертипаже](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкскустомколорспропертипаже.h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a> Кмфккустомколорспропертипаже:: Setup

Задает компоненты цвета страницы свойств.

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

*Cерверный*\
окне Красный компонент значения RGB.

*Модуле*\
окне Зеленый компонент значения RGB.

*&*\
окне Синий компонент значения RGB.

### <a name="remarks"></a>Примечания

Этот метод обновляет текущие значения цвета RGB и связанные HLS (оттенок, освещение и насыщенность) на странице свойств. Метод [кмфкколордиалог:: сетпажетво](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) вызывает этот метод, когда платформа Инициализирует диалоговое окно цвета или пользователь нажимает левую кнопку мыши. Дополнительные сведения о см `CMFCColorDialog` . в разделе [класс кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md).

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс Кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md)<br/>
[Класс Кмфкстандардколорспропертипаже](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
