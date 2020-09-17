---
title: Класс CReBar
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: c1379d1ef8effea0df564da1b43769bb9a11435d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363929"
---
# <a name="crebar-class"></a>Класс CReBar

Панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.

## <a name="syntax"></a>Синтаксис

```
class CReBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кребар:Адбар](#addbar)|Добавляет полосу к армате.|
|[CReBar::Создание](#create)|Создает элемент управления арматом и `CReBar` прикрепляет его к объекту.|
|[Кребар:Гетребарктр](#getrebarctrl)|Позволяет прямой доступ к базовому общему элементу управления.|

## <a name="remarks"></a>Примечания

Объект арматуры может содержать различные детские окна, обычно другие элементы управления, включая коробки для детона, панели инструментов и коробки с списками. Объект арматы может отображать свои детские окна по указанной битовой карте. Приложение может автоматически изменить размер арматы, или пользователь может вручную изменить размер арматы, нажав или перетащив ее захват бар.

![Пример меню RebarMenu](../../mfc/reference/media/vc4sc61.gif "Пример меню RebarMenu")

## <a name="rebar-control"></a>Управление ребартом

Объект арматы ведет себя аналогично объекту панели инструментов. Армата использует механизм «клик-и-драг», чтобы изменить размер полосы. Элемент управления арматом может содержать одну или несколько полос, при этом каждая группа имеет любую комбинацию панели захвата, бит-карты, текстовой метки и детского окна. Однако полосы не могут содержать более одного окна ребенка.

`CReBar`использует класс [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) для обеспечения его реализации. Вы можете получить доступ к управлению арматурой через [GetReBarCtrl,](#getrebarctrl) чтобы воспользоваться преимуществами опций настройки элемента управления. Для получения дополнительной информации `CReBarCtrl`о элементах управления арматурой см. Для получения дополнительной информации об использовании элементов управления арматурой [см.](../../mfc/using-crebarctrl.md)

> [!CAUTION]
> Объекты управления армабаром и арматарной армаза не поддерживают стыковку панели управления MFC. Если `CRebar::EnableDocking` вызов, ваша заявка будет утверждать.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="crebaraddbar"></a><a name="addbar"></a>Кребар:Адбар

Вызовите эту функцию участника, чтобы добавить полосу к армате.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
Указатель на `CWnd` объект, который является окном ребенка, который будет вставлен в армату. Ссылка на объект должна иметь WS_CHILD.

*lpszText*<br/>
Указатель на строку, содержащую текст, чтобы появиться на армате. NULL по умолчанию. Текст, содержащийся в *lpszText,* не является частью окна ребенка; он находится на самой армате.

*pbmp*<br/>
Указатель на `CBitmap` объект, который отображается на фоне арматы. NULL по умолчанию.

*dwStyle*<br/>
DWORD, содержащий стиль для применения к армате. Смотрите `fStyle` описание функции в структуре Win32 [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) для получения полного списка стилей группы.

*clrFore*<br/>
Значение COLORREF, представляющее цвет арматы на переднем плане.

*clrBack*<br/>
Значение COLORREF, представляющее цвет фона армабы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a>CReBar::Создание

Вызов ими функции участника для создания армазы.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на `CWnd` объект, окно Windows которого является родителем панели статуса. Обычно окно рамы.

*dwCtrlStyle*<br/>
Стиль управления арматом. По умолчанию RBS_BANDBORDERS, который отображает узкие линии, чтобы отделить соседние полосы в пределах контроля арматы. В списке стилей [управления ребартом](/windows/win32/Controls/rebar-control-styles) можно ознакомиться в SDK Windows.

*dwStyle*<br/>
Стили арматы окна.

*nID*<br/>
Идентификатор ребенка-окна армабы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [для CReBar::AddBar](#addbar).

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a>Кребар:Гетребарктр

Эта функция члена позволяет прямой доступ к базовому общему элементу управления.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект [CReBarCtrl.](../../mfc/reference/crebarctrl-class.md)

### <a name="remarks"></a>Примечания

Вызовите эту функцию участника, чтобы воспользоваться функциональностью общего элемента управления арматом Windows при настройке армазы. При вызове `GetReBarCtrl`он возвращает объект `CReBarCtrl` ссылки объекту, так что вы можете использовать любой набор функций члена.

Для получения дополнительной `CReBarCtrl` информации об использовании для настройки арматы см. [Using CReBarCtrl](../../mfc/using-crebarctrl.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример MFC MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
