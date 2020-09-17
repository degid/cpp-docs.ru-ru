---
title: Класс CAutoHideDockSite
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 14db8d93ea7706b3a4daad2ba751f8410974f6cb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841640"
---
# <a name="cautohidedocksite-class"></a>Класс CAutoHideDockSite

`CAutoHideDockSite`Расширяет [класс CDockSite](../../mfc/reference/cdocksite-class.md) для реализации автоматически скрытых панелей закрепления.

## <a name="syntax"></a>Синтаксис

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

| name | Описание |
|-|-|
|Имя|Описание|
|`CAutoHideDockSite::CAutoHideDockSite`|Формирует объект `CAutoHideDockSite`.|
|`CAutoHideDockSite::~CAutoHideDockSite`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

| name | Описание |
|-|-|
|Имя|Описание|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Указывает, отображается ли элемент в `CAutoHideDockSite` меню панели.|
|[CAutoHideDockSite:: Канакцептпане](#canacceptpane)|Определяет, является ли базовый объект области производным от [класса CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md).|
|[CAutoHideDockSite::D Оккпане](#dockpane)|Закрепляет область для этого `CAuotHideDockSite` объекта.|
|[CAutoHideDockSite:: Жеталигнрект](#getalignrect)|Возвращает размер сайта закрепления в экранных координатах.|
|[CAutoHideDockSite:: Репоситионпанес](#repositionpanes)|Перерисовывает панель `CAutoHideDockSite` с использованием глобальных полей и расстояния между кнопками.|
|[CAutoHideDockSite:: Сетоффсетлефт](#setoffsetleft)|Задает поле в левой части панели закрепления.|
|[CAutoHideDockSite:: Сетоффсетригхт](#setoffsetright)|Задает поле в правой части панели закрепления.|
|[CAutoHideDockSite:: Унсетаутохидемоде](#unsetautohidemode)|Вызывает [CMFCAutoHideBar:: унсетаутохидемоде](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов в `CAutoHideDockSite` .|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|Имя|Описание|
|[CAutoHideDockSite:: m_nExtraSpace](#m_nextraspace)|Определяет размер пространства между панелями инструментов и границей закрепляемой панели. Это пространство измеряется от левого края или верхнего края в зависимости от выравнивания для пространства закрепления.|

## <a name="remarks"></a>Примечания

При вызове [CFrameWndEx:: енаблеаутохидепанес](../../mfc/reference/cframewndex-class.md#enableautohidepanes)платформа автоматически создает `CAutoHideDockSite` объект. В большинстве случаев нет необходимости создавать или использовать этот класс напрямую.

Панель закрепления — это разрыв между левой границей панели закрепления и левой стороной [класса CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как получить `CAutoHideDockSite` объект из `CMFCAutoHideBar` объекта и как задать левое и правое поля закрепляемой панели.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** афксаутохидедокксите.h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a> CAutoHideDockSite:: Канакцептпане

Определяет, является ли базовая панель объектом [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) или производным от `CMFCAutoHideBar` .

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

*пбар*\
окне Базовая область, которую проверяет платформа.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *пбар* является производным от `CMFCAutoHideBar` ; В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если объект базовой области является производным от `CMFCAutoHideBar` , он может содержать `CAutoHideDockSite` .

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a> CAutoHideDockSite::D Оккпане

Закрепляет область для этого объекта [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) .

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*Приводится*\
окне Панель, которая закрепляется платформой.

*доккмесод*\
окне Параметры закрепления для панели.

*лпрект*\
окне Прямоугольник, указывающий границы закрепленной области.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не использует параметр *доккмесод*, который предоставляется для использования в будущем.

Если *лпрект* имеет значение null, платформа помещает эту панель в расположение по умолчанию на сайте DOCKER. Если сайт закрепления горизонтальный, расположение по умолчанию находится слева от сайта закрепления. В противном случае расположение по умолчанию находится в верхней части сайта DOCKER.

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a> CAutoHideDockSite:: Жеталигнрект

Возвращает размер сайта закрепления в экранных координатах.

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

*перетаскиваемые*\
окне Ссылка на прямоугольник. Метод сохраняет размер сайта закрепления в этом прямоугольнике.

### <a name="remarks"></a>Примечания

Прямоугольник корректируется для полей смещения, чтобы они не включались.

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a> CAutoHideDockSite:: m_nExtraSpace

Размер пространства между краями [класса CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и объектами [класса CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) .

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>Примечания

Когда объект `CMFCAutoHideBar` закрепляется на `CAutoHideDockSite` , он не должен занимать весь сайт DOCKER. Эта глобальная переменная управляет дополнительным пространством между левой или верхней границей `CMFCAutoHideBar` и соответствующим `CAutoHideDockSite` краем. Используется ли верхний или левый край в зависимости от текущего выравнивания.

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a> CAutoHideDockSite:: Сетоффсетлефт

Задает поле в левой части панели закрепления.

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>Параметры

*ноффсет*<br/>
окне Новое смещение.

### <a name="remarks"></a>Примечания

Объекты [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) располагаются статически на `CAutoHideDockSite` объекте. Это означает, что пользователь не может вручную изменить расположение `CMFCAutoHideBar` объектов. `SetOffsetLeft`Метод управляет интервалом между левой границей слева `CMFCAutoHideBar` и левой стороны `CAutoHideDockSite` .

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a> CAutoHideDockSite:: Сетоффсетригхт

Задает поле в правой части панели закрепления.

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>Параметры

*ноффсет*<br/>
окне Новое смещение.

### <a name="remarks"></a>Примечания

Объекты [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) располагаются статически на `CAutoHideDockSite` объекте. Это означает, что пользователь не может вручную изменить расположение `CMFCAutoHideBar` объектов. `SetOffsetRight`Метод управляет интервалом между правой и правой стороной справа от `CMFCAutoHideBar` `CAutoHideDockSite` .

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a> CAutoHideDockSite:: Репоситионпанес

Перерисовывает панели в [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Параметры

*ректневклиентареа*\
окне Зарезервированное значение.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не использует *ректневклиентареа*. Он перерисовывает панели с глобальными полями панели инструментов и промежутками между кнопками.

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a> CAutoHideDockSite:: Унсетаутохидемоде

Вызывает [CMFCAutoHideBar:: унсетаутохидемоде](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на сайте DOCKER.

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>Параметры

*паутохидетулбар*\
окне Указатель на область объекта [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) , расположенный в `CAutoHideDockSite` .

### <a name="remarks"></a>Примечания

Этот метод выполняет поиск строки, содержащей *паутохидетулбар*. Он вызывает `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов в этой строке. Если *паутохидетулбар* не найден или имеет значение null, этот метод вызывает `CMFCAutoHideBar.UnSetAutoHideMode` для всех объектов в `CMFCAutoHideBar` `CAutoHideDockSite` .

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockSite](../../mfc/reference/cdocksite-class.md)
