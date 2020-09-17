---
title: Класс Кмфкколорпопупмену
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: 2964f250b25ad6c77c70e8f10cd92cca0c7d11da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844565"
---
# <a name="cmfccolorpopupmenu-class"></a>Класс Кмфкколорпопупмену

Представляет всплывающее меню, используемое пользователями для выбора цветов в документе или приложении.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|[Кмфкколорпопупмену:: Кмфкколорпопупмену](#cmfccolorpopupmenu)|Формирует объект `CMFCColorPopupMenu`.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфкколорпопупмену:: Креатетеароффбар](#createtearoffbar)|Создает закрепляемую цветную полосу разрыва. (Переопределяет [CMFCPopupMenu:: креатетеароффбар](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|
|[Кмфкколорпопупмену:: Жетменубар](#getmenubar)|Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренный во всплывающее меню. (Переопределяет [CMFCPopupMenu:: жетменубар](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкколорпопупмену:: Сетпроплист](#setproplist)|Задает объект элемента управления сетки свойств внедренного `CMFCColorBar` объекта.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|`m_bEnabledInCustomizeMode`|Логическое значение, определяющее, следует ли отображать цветовую панель.|
|`m_wndColorBar`|`CMFCColorBar`Объект, предоставляющий выбор цвета.|

### <a name="remarks"></a>Примечания

Этот класс наследует функции всплывающего меню `CMFCPopupMenu` класса и управляет `CMFCColorBar` объектом, предоставляющим выбор цвета. Если платформа панели инструментов находится в режиме настройки и `m_bEnabledInCustomizeMode` для элемента задано значение false, объект цветовой шкалы не отображается. Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Дополнительные сведения о см `CMFCColorBar` . в разделе [класс кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[кмфкколорпопупмену](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксколорпопупмену.h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a> Кмфкколорпопупмену:: Кмфкколорпопупмену

Формирует объект `CMFCColorPopupMenu`.

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*красок*<br/>
окне Массив цветов, отображаемый платформой во всплывающем меню.

*color*<br/>
окне Выбранный цвет по умолчанию.

*лпсзаутоколор*<br/>
окне Текстовая метка для кнопки цвета *автоматически* (по умолчанию) или null.

Стандартная метка для автоматической кнопки — **автоматически**.

*лпсзосерколор*<br/>
окне Текстовая метка *другой* кнопки, в которой отображаются дополнительные варианты выбора цвета или значение null.

Стандартная метка для другой кнопки — **Дополнительные цвета...**.

*лпсздокколорс*<br/>
окне Текстовая метка кнопки цвета документа. В палитре цвета документа перечислены все цвета, используемые в документе.

*лстдокколорс*<br/>
окне Список цветов, используемых в настоящий момент в документе.

*nColumns*<br/>
окне Число столбцов в массиве цветов.

*нхорздоккровс*<br/>
окне Число строк, которое имеет цветовая шкала, когда она закреплена по горизонтали.

*нвертдоккколумнс*<br/>
окне Число столбцов, которое имеет цветовую полосу, когда она закреплена по вертикали.

*колораутоматик*<br/>
окне Цвет по умолчанию, применяемый платформой при нажатии кнопки "автоматически".

*уикоммандид*<br/>
окне Идентификатор команды элемента управления "Цветовая шкала".

*бстдколордлг*<br/>
окне Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или диалоговое окно [кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) .

*ппарентбтн*<br/>
окне Указатель на родительскую кнопку.

*nID*<br/>
окне Идентификатор команды.

### <a name="remarks"></a>Примечания

Каждый перегруженный конструктор задает `m_bEnabledInCustomizeMode` для элемента значение false.

### <a name="example"></a>Пример

В следующем примере показано, как создать `CMFCColorPopupMenu` объект.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a> Кмфкколорпопупмену:: Креатетеароффбар

Создает закрепляемую цветную полосу разрыва.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*пвндмаин*\
окне Указатель на родительское окно отрывной полосы.

*уиид*\
окне Идентификатор команды для отрывной строки.

*лпсзнаме*\
окне Текст окна для отрывной строки.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый объект-разделитель элементов управления.

### <a name="remarks"></a>Примечания

Этот метод создает объект [класса кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md) и приводит его к указателю [класса CPane](../../mfc/reference/cpane-class.md) . Это значение можно привести обратно к указателю [класса кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md) с помощью одного из макросов приведения, описанных в разделе [приведение типов объектов классов MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md).

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a> Кмфкколорпопупмену:: Жетменубар

Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренный во всплывающее меню.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на встроенный объект `CMFCPopupMenuBar` .

### <a name="remarks"></a>Примечания

Во всплывающем меню «цвет» имеется внедренный объект [класса CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) . Переопределите этот метод в производном классе, если приложение использует другой внедренный тип.

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a> Кмфкколорпопупмену:: Сетпроплист

Задает объект элемента управления сетки свойств внедренного `CMFCColorBar` объекта.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

*пвндлист*<br/>
окне Указатель на объект элемента управления сетки свойств.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
