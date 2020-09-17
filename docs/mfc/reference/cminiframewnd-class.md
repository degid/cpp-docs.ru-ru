---
title: Класс CMiniFrameWnd
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: e9b91161f4207f4d2215d8777beade93617ddfac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319818"
---
# <a name="cminiframewnd-class"></a>Класс CMiniFrameWnd

Представляет фреймовое окно половинной высоты по сравнению с тем, которое стандартно отображается на плавающих панелях инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Формирует объект `CMiniFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMiniFrameWnd::Создание](#create)|Создает `CMiniFrameWnd` объект после строительства.|
|[CMiniFrameWnd::CreateEx](#createex)|Создает `CMiniFrameWnd` объект (с дополнительными опциями) после строительства.|

## <a name="remarks"></a>Примечания

Эти окна мини-рамки ведут себя как обычные окна кадра, за исключением того, что они не имеют минимизации / максимизировать кнопки или меню, и вы только должны одним нажатием на меню системы, чтобы уволить их.

Чтобы использовать `CMiniFrameWnd` объект, сначала определите объект. Затем позвоните в функцию [члена Create](#create) для отображения окна мини-рамки.

Для получения дополнительной информации о том, как использовать `CMiniFrameWnd` объекты, см. [Docking and Floating Toolbars](../../mfc/docking-and-floating-toolbars.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd

Строит `CMiniFrameWnd` объект, но не создает окно.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Примечания

Чтобы создать окно, позвоните [cMiniFrameWnd::Create](#create).

## <a name="cminiframewndcreate"></a><a name="create"></a>CMiniFrameWnd::Создание

Создает окно мини-рамки Windows и прикрепляет его к объекту. `CMiniFrameWnd`

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Параметры

*lpClassName*<br/>
Указывает на строку символов с нулевым завершением, которая называет класс Windows. Имя класса может быть любым именем, зарегистрированным с глобальной функцией [AfxRegisterWndClass.](application-information-and-management.md#afxregisterwndclass) Если NULL, класс окон будет зарегистрирован для вас рамкой. MFC дает классу по умолчанию следующие стили и атрибуты:

- Устанавливает бит стиля CS_DBLCLKS, который отправляет сообщения с двойным нажатием кнопки на процедуру окна, когда пользователь дважды щелкает мышью.

- Устанавливает биты стиля CS_HREDRAW и CS_VREDRAW, которые направляют содержимое области клиента на перерисовку при изменении размера окна.

- Устанавливает курсор класса в стандартную IDC_ARROW Windows.

- Устанавливает фоновую кисть класса в NULL, поэтому окно не будет стирать фон.

- Устанавливает значок класса в стандартную иконку логотипа Windows с развевающимся флагом.

- Устанавливает окно в размер и положение по умолчанию, как указано Windows.

*lpWindowName*<br/>
Указывает на строку символов с нулевым завершением, содержащую имя окна.

*dwStyle*<br/>
Определяет атрибуты стиля окна. Они могут включать стандартные стили окон и один или несколько из следующих специальных стилей:

- MFS_MOVEFRAME позволяет перемещать окно мини-рамки, нажав на любой край окна, а не только на подпись.

- MFS_4THICKFRAME отправления изменяя размер окна мини-рамки.

- MFS_SYNCACTIVE синхронизирует активацию окна мини-кадра с активацией родительского окна.

- MFS_THICKFRAME позволяет размеру окна мини-рамки размером снес ьменьшее количество содержимого клиентской области.

- MFS_BLOCKSYSMENU отстраняет доступ к меню системы и меню управления и преобразует их в часть заголовка (заголовок бара).

[См. CWnd:: Создать](../../mfc/reference/cwnd-class.md#create) для описания возможных значений стиля окна. Типичная комбинация, используемая для окон мини-рамки, WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU.

*rect*<br/>
Структура, `RECT` определяющая желаемые размеры окна.

*pParentWnd*<br/>
Указывает на родительское окно. Используйте NULL для окон верхнего уровня.

*nID*<br/>
Если окно мини-рамки создается как окно ребенка, это идентификатор управления детьми; в противном случае 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Create`инициализация имени класса окна и имени окна и регистрирует значения по умолчанию для его стиля и родительского значения.

## <a name="cminiframewndcreateex"></a><a name="createex"></a>CMiniFrameWnd::CreateEx

Создает объект `CMiniFrameWnd`.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого. `CMiniFrameWnd` Примените к окну любой из [расширенных стилей окна.](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

*lpClassName*<br/>
Указывает на строку символов с нулевым завершением, которая называет класс Windows (структура [WNDCLASS).](/windows/win32/api/winuser/ns-winuser-wndclassw) Имя класса может быть любым именем, зарегистрированным с глобальной функцией [AfxRegisterWndClass,](application-information-and-management.md#afxregisterwndclass) или любым из предопределенных имен контрольного класса. Она не должна быть NULL.

*lpWindowName*<br/>
Указывает на строку символов с нулевым завершением, содержащую имя окна.

*dwStyle*<br/>
Определяет атрибуты стиля окна. Смотрите [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CWnd::Создание](../../mfc/reference/cwnd-class.md#create) для описания возможных значений.

*rect*<br/>
Размер и положение окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указывает на объект родительского окна.

*nID*<br/>
Идентификатор окна ребенка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Параметры `CreateEx` определяют WNDCLASS, стиль окна и (по желанию) исходное положение и размер окна. `CreateEx`также указывается родитель окна (если таковые имеется) и идентификатор.

При `CreateEx` выполнении Windows отправляет [WM_GETMINMAXINFO,](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) сообщения в окно.

Чтобы расширить обработку сообщений по `CMiniFrameWnd`умолчанию, вывемите класс из, добавьте карту сообщений в новый класс и предоставьте функции членов для вышеуказанных сообщений. Переопределить, `OnCreate`например, для выполнения необходимой инициализации для нового класса.

Переопределить `On`дополнительные обработчики *сообщений сообщений,* чтобы добавить дополнительную функциональность к вашему производному классу.

Если приведен WS_VISIBLE стиль, Windows отправляет в окно все сообщения, необходимые для активации и отобрагиваемого окна. Если стиль окна определяет заголовок бара, в заголовке отображается название окна, на которое указывает параметр *lpszWindowName.*

Параметр *dwStyle* может быть любым сочетанием [оконных стилей.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

Окна старой палитры стиля больше не поддерживаются. Старый стиль, который не имел кнопки "X" Заклятсный, был поддержан при запуске приложения MFC на предыдущих версиях Windows, но больше не поддерживается в Visual C.NET. Только новый стиль WS_EX_TOOLWINDOW теперь поддерживается; для описания этого стиля, см [Расширенный стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>См. также раздел

[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
