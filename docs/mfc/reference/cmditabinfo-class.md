---
title: Класс CMDITabInfo
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: 8e4053bf16672d693adc104c9e88bb46a67ba7dd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845917"
---
# <a name="cmditabinfo-class"></a>Класс CMDITabInfo

`CMDITabInfo`Класс используется для передачи параметров в метод [CMDIFrameWndEx:: EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) . Задайте элементы этого класса, чтобы контролировать поведение групп вкладок MDI.

## <a name="syntax"></a>Синтаксис

```
class CMDITabInfo
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDITabInfo:: Serialize](#serialize)|Считывает этот объект из архива или записывает в него.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMDITabInfo:: m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Указывает, отображается ли кнопка **Закрыть** на метке активной вкладки.|
|[CMDITabInfo:: m_bAutoColor](#m_bautocolor)|Указывает, следует ли открасить вкладки MDI.|
|[CMDITabInfo:: m_bDocumentMenu](#m_bdocumentmenu)|Указывает, отображается ли в группе вкладок всплывающее меню, в котором отображается список открытых документов или отображаются кнопки прокрутки.|
|[CMDITabInfo:: m_bEnableTabSwap](#m_benabletabswap)|Указывает, может ли пользователь менять позиции вкладок путем перетаскивания.|
|[CMDITabInfo:: m_bFlatFrame](#m_bflatframe)|Указывает, имеют ли вкладки плоский фрейм.|
|[CMDITabInfo:: m_bTabCloseButton](#m_btabclosebutton)|Указывает, отображается ли на каждой заметке вкладки Кнопка « **Закрыть** ».|
|[CMDITabInfo:: m_bTabCustomTooltips](#m_btabcustomtooltips)|Указывает, включены ли пользовательские подсказки.|
|[CMDITabInfo:: m_bTabIcons](#m_btabicons)|Указывает, следует ли отображать значки на вкладках MDI.|
|[CMDITabInfo:: m_nTabBorderSize](#m_ntabbordersize)|Задает размер границы для каждого окна вкладки.|
|[CMDITabInfo:: m_style](#m_style)|Задает стиль меток вкладки.|
|[CMDITabInfo:: m_tabLocation](#m_tablocation)|Указывает, расположены ли метки вкладок в верхней или нижней части страницы.|

## <a name="remarks"></a>Примечания

Этот класс задает параметры групп вкладок MDI, создаваемых платформой.

## <a name="example"></a>Пример

В следующем примере показано, как задать значения различных переменных членов в `CMDITabInfo` классе.

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксмдиклиентареавнд.h

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a> CMDITabInfo:: m_bActiveTabCloseButton;

Указывает, отображается ли кнопка **Закрыть** на метке активной вкладки.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, в метке активной вкладки будет отображаться кнопка **Закрыть** . Кнопка **Закрыть** будет удалена из правого верхнего угла области вкладки. В противном случае в метке активной вкладки не будет отображаться кнопка **Закрыть** . В правом верхнем углу области вкладки появится кнопка **Закрыть** .

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a> CMDITabInfo:: m_bAutoColor

Указывает, имеет ли каждая вкладка MDI собственный цвет.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>Примечания

Если значение равно TRUE, каждая вкладка будет иметь собственный цвет. Набор цветов управляется библиотекой MFC. В противном случае вкладки отображаются белым цветом. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a> CMDITabInfo:: m_bDocumentMenu

Указывает, отображается ли на каждой вкладке всплывающее меню, в котором отображается список открытых документов с правой стороны области вкладки.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, в каждой из окон вкладок отображается всплывающее меню, в котором отображается список открытых документов с правой стороны области вкладки. В противном случае в окне вкладки отображаются кнопки прокрутки на правой границе области вкладки. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a> CMDITabInfo:: m_bEnableTabSwap

Указывает, может ли пользователь менять позиции вкладок путем перетаскивания.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, пользователь может изменять позиции вкладок путем перетаскивания вкладок. В противном случае пользователь не сможет изменять позиции вкладок. Значение по умолчанию — TRUE.

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a> CMDITabInfo:: m_bFlatFrame

Указывает, имеется ли в каждом окне вкладки плоский фрейм.

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a> CMDITabInfo:: m_bTabCloseButton

Указывает, отображается ли в каждом окне вкладки Кнопка « **Закрыть** ».

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, в каждом окне вкладки отображается кнопка **Закрыть** на правом крае вкладки. в противном случае кнопка **Закрыть** не отображается. Значение по умолчанию — TRUE.

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a> CMDITabInfo:: m_bTabCustomTooltips

Указывает, отображаются ли подсказки на вкладках.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, приложение отправляет в основной фрейм сообщение AFX_WM_ON_GET_TAB_TOOLTIP. Это сообщение можно обработать с помощью макроса ON_REGISTERED_MESSAGE.

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a> CMDITabInfo:: m_bTabIcons

Указывает, следует ли отображать значки на вкладках MDI.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>Примечания

Если значение — TRUE, значки отображаются на каждой вкладке MDI. в противном случае значки не отображаются на вкладках. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a> CMDITabInfo:: m_nTabBorderSize

Задает размер границы каждого окна табуляции (в пикселях).

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>Примечания

[CMFCVisualManager:: жетмдитабсбордерссизе](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) возвращает значение по умолчанию.

## <a name="cmditabinfom_style"></a><a name="m_style"></a> CMDITabInfo:: m_style

Задает стиль меток вкладки.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>Примечания

Укажите один из следующих стилей для меток вкладки:

|Макрос|Описание|
|-|-|
|STYLE_3D|Трехмерный стиль.  |
|STYLE_3D_ONENOTE|Стиль Microsoft OneNote.  |
|STYLE_3D_VS2005|Стиль Microsoft Visual Studio 2005.  |
|STYLE_3D_SCROLLED|Трехмерный стиль с метками вкладок прямоугольника.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|Плоский стиль с общей горизонтальной полосой прокрутки.  |
|STYLE_3D_ROUNDED_SCROLL|Трехмерный стиль с подписями круглых вкладок.  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a> CMDITabInfo:: m_tabLocation

Указывает, расположены ли метки вкладок в верхней или нижней части страницы.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>Примечания

Примените к вкладкам один из следующих флагов расположения:

- LOCATION_BOTTOM: Метки вкладок расположены в нижней части страницы.

- LOCATION_TOP: Метки вкладок расположены в верхней части страницы

## <a name="cmditabinfoserialize"></a><a name="serialize"></a> CMDITabInfo:: Serialize

Считывает или записывает этот объект из архива или в архив.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
окне Объект [класса CArchive](../../mfc/reference/carchive-class.md) для сериализации.

## <a name="see-also"></a>См. также раздел

[Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)<br/>
[Группы с вкладками MDI](../../mfc/mdi-tabbed-groups.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
