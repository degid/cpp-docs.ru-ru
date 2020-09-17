---
title: Класс CSmartDockingInfo
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: ebb5e75b5b298097cfce043bd83ec88ca0ab4030
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751297"
---
# <a name="csmartdockinginfo-class"></a>Класс CSmartDockingInfo

Определяет внешний вид интеллектуальных маркеров закрепления.

## <a name="syntax"></a>Синтаксис

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSmartDockingInfo::CopyTo](#copyto)|Копирует текущие параметры смарт-стыковки информации в предоставленном объекте [CSmartDockingInfo.](../../mfc/reference/csmartdockinginfo-class.md)|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Определяет, следует ли использовать текущий цвет темы, когда фреймворк отображает смарт-маркеры стыковки.|
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Определяет базовый цвет фона умных маркеров стыковки.|
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Определяет цвет, который заменяет `m_clrToneSrc` в смарт-стыковки маркер bitmaps.|
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Определяет цвет смарт-стыковочного маркера bitmaps.|
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Определяет цвет смарт-маркермаркера bitmaps, когда они прозрачны.|
|[CSmartDockingInfo:::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Определяет смещение центральной группы интеллектуальных маркеров стыковки от границ прямоугольника центральной группы.|
|[CSmartDockingInfo:::m_sizeTotal](#m_sizetotal)|Определяет общий размер всех интеллектуальных маркеров стыковки в группе.|
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Определяет иики ресурсов битовых карт, которые фреймворк использует для интеллектуальных маркеров стыковки, которые не выделены.|
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Определяет иики ресурсов битовых карт, которые фреймворк использует для подсвеченных интеллектуальных маркеров стыковки.|

## <a name="remarks"></a>Примечания

Фрейм обрабатывает интеллектуальные маркеры стыковки внутри компании. На следующей иллюстрации показаны стандартные интеллектуальные маркеры стыковки:

![Стандартные маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkers.png "Стандартные маркеры смарт-закрепления")

На этом рисунке изображение слева показывает смарт-маркер стыковки центральной группы, который не имеет стыковки с включенной вкладкой. Изображение в середине показывает правый край смарт-маркер стыковки. Изображение справа показывает центральную группу смарт-маркер стыковки, который имеет стыковку к вкладке включен. Центральная группа смарт-маркер стыковки имеет основную бит-карту и пять смарт-маркер маркер bitmaps.

Вы можете настроить следующие параметры умных маркеров стыковки:

- Цвет. Например, можно заменить синий цвет маркеров на рисунке любым цветом, определенным пользователем.

- Прозрачность цвета.

- Смещение смарт-маркера стыковки в центральной группе от границы ограничительного прямоугольника.

- Основная бит-карта, представляющая центральную группу.

- Bitmaps, представляющий регулярные и выделенные умные маркеры стыковки.

На следующей иллюстрации показан пример настроенных смарт-маркеров стыковки:

![Пользовательские маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkerscustom.png "Пользовательские маркеры смарт-закрепления")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDockingManager.h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a>CSmartDockingInfo::CopyTo

Копирует текущие параметры смарт-стыковки в предоставленный объект [CSmartDockingInfo.](../../mfc/reference/csmartdockinginfo-class.md)

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Параметры

*params*<br/>
(ваут) Объект типа, `CSmartDockingInfo` населенный текущими интеллектуальными параметрами стыковки.

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading

Определяет, следует ли использовать текущий цвет темы, когда фреймворк отображает смарт-маркеры стыковки.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>Примечания

Если true, маркеры нарисованы с использованием текущего цвета темы; в противном случае маркеры нарисованы с светло-голубым цветом.

Значение по умолчанию — FALSE.

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground

Определяет базовый цвет фона умных маркеров стыковки.

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest

Определяет цвет, который заменит `m_clrToneSrc` в смарт-стыковки маркер bitmaps.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>Примечания

Установите это значение, чтобы изменить цвет маркера bitmaps программно. Например, если вы хотите изменить цвет стандартных маркеров, предусмотренных рамкой, установите это значение на желаемый цвет. По умолчанию, [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) установлен на RGB (61, 123, 241) (голубоватый цвет).

Чтобы изменить цвет пользовательских маркеров, `m_clrToneDest` необходимо `m_clrToneSrc`указать оба и .

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc

Определяет цвет смарт-стыковочного маркера bitmaps.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>Примечания

Установите это значение только тогда, когда вы хотите заменить цвет пользовательской битной карты другим цветом. Вы не должны установить это значение, если вы меняете цвет стандартного (при условии рамки) маркера.

Используйте, `(COLORREF)-1` чтобы оставить члена смарт-группы стыковки пустым.

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent

Определяет цвет смарт-маркермаркера bitmaps, когда они прозрачны.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>Примечания

Вы должны установить это значение при отображении пользовательских маркеров и пользовательских бит-карт в стыковой группе.

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a>CSmartDockingInfo:::m_nCentralGroupOffset

Определяет смещение между центральной группой интеллектуальных маркеров стыковки и границами прямоугольника центральной группы.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>Примечания

Укажите это значение, если вы хотите изменить смещение по умолчанию между пользовательскими маркерами и границами центральной группы умных маркеров стыковки. Смещение по умолчанию составляет 5 пикселей.

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a>CSmartDockingInfo:::m_sizeTotal

Определяет общий размер связующего прямоугольника, который закрывает все умные маркеры стыковки в центральной группе.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>Примечания

Установите `m_sizeTotal` размер связующего прямоугольника центрального маркера группы. Вы должны указать это значение, если вы используете пользовательские bitmaps для маркеров.

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID

Определяет идеки ресурсов битовых карт, которые используются для невыделенных пользовательских смарт-маркеров стыковки.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Примечания

Заполните этот массив иными ими ресурса битовых карт, представляющих интеллектуальные маркеры стыковки. AFX_SD_MARKERS_NUM в настоящее время определяется как 5. Вы заполняете массив следующим образом:

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID

Определяет идеки ресурсов битовых карт, которые используются для выделенных пользовательских смарт-маркеров стыковки.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Примечания

Заполните этот массив иными ими ресурсами битовых карт, представляющих выделенные умные маркеры стыковки. AFX_SD_MARKERS_NUM в настоящее время определяется как 5. Вы заполняете массив следующим образом:

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
