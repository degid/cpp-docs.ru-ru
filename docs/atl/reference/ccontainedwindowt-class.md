---
title: CContainedWindowT класс
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 7b89346bbc62cdda808b193a199fdf121f052ebb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747746"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT класс

Этот класс реализует окно, содержащееся в другом объекте.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Параметры

*TBase*<br/>
Базовый класс вашего нового класса. Базовый класс `CWindow`по умолчанию .

*TWinTraits*<br/>
Класс признаков, определяющий стили для вашего окна. Значение по умолчанию — `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) является специализацией `CContainedWindowT`. Если вы хотите изменить базовый класс `CContainedWindowT` или черты, используйте напрямую.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CContainedWindowt::CcontainedWindowT](#ccontainedwindowt)|Конструктор. Инициализация членов данных определяет, какая карта сообщений будет обрабатывать сообщения, содержащиеся в окне.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CContainedWindowT::Создание](#create)|Создает окно.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|
|[CContainedWindowt::GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Регистрирует класс окна, содержащегося в окне.|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Подклассы окна.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Изменяет, какая карта сообщений используется для обработки сообщений, содержащихся в окне.|
|[CContainedWindowT:UnsubclassWindow](#unsubclasswindow)|Восстанавливает ранее подклассифицированное окно.|
|[CContainedWindowT::WindowProc](#windowproc)|(Статик) Обрабатывает сообщения, отправленные в содержащееся окно.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Определяет, какая карта сообщений будет обрабатывать сообщения, содержащиеся в окне.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Упогоняет название существующего класса окон, на котором будет базироваться новый класс окон.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает на оригинальную процедуру окна класса окон.|
|[CContainedWindowT::m_pObject](#m_pobject)|Указывает на содержащий объект.|

## <a name="remarks"></a>Примечания

`CContainedWindowT`реализует окно, содержащееся в другом объекте. `CContainedWindowT`Процедура окна 'S использует карту сообщений в содержащем объекте для направления сообщений соответствующим обработчикам. При построении объекта указывается, какая карта сообщений `CContainedWindowT` должна использоваться.

`CContainedWindowT`позволяет создать новое окно, переклассифицируя существующий класс окон. Метод `Create` сначала регистрирует класс окон, основанный на существующем классе, но используемый. `CContainedWindowT::WindowProc` `Create`затем создает окно на основе этого нового класса окна. Каждый `CContainedWindowT` экземпляр может классифицировать другой класс окон.

`CContainedWindowT`также поддерживает подклассок окон. Метод `SubclassWindow` прикрепляет существующее `CContainedWindowT` окно к объекту `CContainedWindowT::WindowProc`и изменяет процедуру окна на. Каждый `CContainedWindowT` экземпляр может подклассифицировать другое окно.

> [!NOTE]
> Для любого `CContainedWindowT` данного `Create` `SubclassWindow`объекта позвоните или . Вы не должны вызывать оба метода на одном объекте.

При использовании **элемента адбинга на основе** опции в AtL Project Wizard мастер автоматически добавляет в класс элемент `CContainedWindowT` данных, реализующий элемент управления. Следующий пример показывает, как объявляется содержащееся окно:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Дополнительные сведения|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Окна](/windows/win32/winmsg/windows) и последующие темы в SDK Windows|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>CContainedWindowt::CcontainedWindowT

Конструктор инициализирует члены данных.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
(в) Название существующего класса окон, на котором будет базироваться содержащееся окно.

*pObject*<br/>
(в) Указатель на содержащий объект, декларируемый на карте сообщений. Класс этого объекта должен быть получен из [CMessageMap.](../../atl/reference/cmessagemap-class.md)

*dwMsgMapID*<br/>
(в) Идентифицирует карту сообщений, которая будет обрабатывать сообщения, содержащиеся в окне. Значение по умолчанию, 0, определяет карту сообщения по умолчанию, объявленную [с BEGIN_MSG_MAP.](message-map-macros-atl.md#begin_msg_map) Использовать альтернативную карту сообщений, объявленную с ALT_MSG_MAP `msgMapID` [(msgMapID),](message-map-macros-atl.md#alt_msg_map)пройдите.

### <a name="remarks"></a>Примечания

Если вы хотите создать новое окно через [Create,](#create)необходимо передать имя существующего класса окон для параметра *lpszClassName.* Например, [см.](../../atl/reference/ccontainedwindowt-class.md)

Есть три конструктора:

- Конструктор с тремя аргументами называется.

- Конструктор с двумя аргументами использует название `TBase::GetWndClassName`класса от .

- Конструктор без аргументов используется, если вы хотите предоставить аргументы позже. При дальнейшем вызове `Create`необходимо предоставить имя класса окна, объект карты сообщений и идентификатор карты сообщений.

Если вы подклассифицируете существующее окно через [SubclassWindow,](#subclasswindow)значение *lpszClassName* не будет использоваться; таким образом, вы можете пройти NULL для этого параметра.

## <a name="ccontainedwindowtcreate"></a><a name="create"></a>CContainedWindowT::Создание

Вызовы [RegisterWndSuperclass](#registerwndsuperclass) для регистрации класса окон, который основан на существующем классе, но использует [CContainedWindowT::WindowProc.](#windowproc)

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
(в) Название существующего класса окон, на котором будет базироваться содержащееся окно.

*pObject*<br/>
(в) Указатель на содержащий объект, декларируемый на карте сообщений. Класс этого объекта должен быть получен из [CMessageMap.](../../atl/reference/cmessagemap-class.md)

*dwMsgMapID*<br/>
(в) Идентифицирует карту сообщений, которая будет обрабатывать сообщения, содержащиеся в окне. Значение по умолчанию, 0, определяет карту сообщения по умолчанию, объявленную [с BEGIN_MSG_MAP.](message-map-macros-atl.md#begin_msg_map) Использовать альтернативную карту сообщений, объявленную с ALT_MSG_MAP `msgMapID` [(msgMapID),](message-map-macros-atl.md#alt_msg_map)пройдите.

*hWndParent*<br/>
(в) Ручка к окну родителя или владельца.

*rect*<br/>
(в) Структура [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющая положение окна. Может `RECT` быть передан указателем или ссылкой.

*szWindowName*<br/>
(в) Определяет название окна. Значение по умолчанию — NULL.

*dwStyle*<br/>
(в) Стиль окна. Значение по умолчанию WS_CHILD &#124; WS_VISIBLE. Список возможных значений можно узнать в [SDK](/windows/win32/api/winuser/nf-winuser-createwindoww) Windows.

*dwExStyle*<br/>
(в) Расширенный стиль окна. Значение по умолчанию составляет 0, что означает отсутствие расширенного стиля. Список возможных значений можно узнать в [SDK Windows.](/windows/win32/api/winuser/nf-winuser-createwindowexw)

*Менорид*<br/>
(в) Для окна ребенка идентификатор окна. Для окна верхнего уровня ручка меню для окна. Значение по умолчанию **0U**.

*lpСоздатьПарам*<br/>
(в) Указатель на данные создания окон. Для полного описания смотрите описание окончательного параметра [для CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка к вновь созданному окну; в противном случае, NULL.

### <a name="remarks"></a>Примечания

Существующее имя класса окон сохраняется в [m_lpszClassName.](#m_lpszclassname) `Create`затем создает окно на основе этого нового класса. Новое окно автоматически прикрепляется `CContainedWindowT` к объекту.

> [!NOTE]
> Не звоните, `Create` если вы уже позвонили [подклассу Window.](#subclasswindow)

> [!NOTE]
> Если 0 используется в качестве значения для параметра *MenuOrID,* оно должно быть указано как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>CContainedWindowT::DefWindowProc

Вызывается [WindowProc](#windowproc) для обработки сообщений, не обрабатываемых на карте сообщений.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*uMsg*<br/>
(в) Сообщение, отправленное в окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщений.

### <a name="remarks"></a>Примечания

По умолчанию вызывает функцию `DefWindowProc` [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 для отправки информации о сообщении в процедуру окна, указанную в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>CContainedWindowt::GetCurrentMessage

Возвращает текущее`m_pCurrentMsg`сообщение ().

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее сообщение, упакованное в структуру. `MSG`

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID

Сохраняет идентификатор карты сообщений, которая в настоящее время используется для содержащегося окна.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Примечания

Эта карта сообщений должна быть объявлена в содержащем объекте.

Карта сообщений по умолчанию, заявленная [с BEGIN_MSG_MAP,](message-map-macros-atl.md#begin_msg_map)всегда идентифицируется нулем. Альтернативная карта сообщений, объявленная с [ALT_MSG_MAP (msgMapID),](message-map-macros-atl.md#alt_msg_map)идентифицируется по `msgMapID`.

`m_dwMsgMapID`сначала инициализирован конструктором и может быть изменен, позвонив [в SwitchMessageMap.](#switchmessagemap) Например, [см.](../../atl/reference/ccontainedwindowt-class.md)

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName

Упогоняет название существующего класса окон.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Примечания

При создании окна [Создать](#create) регистрирует новый класс окон, основанный на этом существующем классе, но использующийся [CContainedWindowT::WindowProc.](#windowproc)

`m_lpszClassName`инициализированконструктором. Например, [см.](../../atl/reference/ccontainedwindowt-class.md)

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc

Если содержащееся окно `m_pfnSuperWindowProc` подклассно, указывает на исходную процедуру окна класса окна.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Примечания

Если содержащееся окно является суперклассным, то есть оно основано `m_pfnSuperWindowProc` на классе окон, который изменяет существующий класс, указывает на процедуру окна существующего класса окна.

Метод [DefWindowProc](#defwindowproc) отправляет информацию о сообщениях `m_pfnSuperWindowProc`в сохраненную процедуру окна.

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a>CContainedWindowT::m_pObject

Указывает на объект, `CContainedWindowT` содержащий объект.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Примечания

Этот контейнер, класс которого должен быть получен из [CMessageMap,](../../atl/reference/cmessagemap-class.md)объявляет карту сообщений, используемую содержащимся в окне.

`m_pObject`инициализированконструктором. Например, [см.](../../atl/reference/ccontainedwindowt-class.md)

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass

Вызывается [Create](#create) для регистрации класса окна содержащегося окна.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха атом, который однозначно идентифицирует зарегистрированный класс окон; в противном случае, ноль.

### <a name="remarks"></a>Примечания

Этот класс окон основан на существующем классе, но использует [CContainedWindowT::WindowProc.](#windowproc) Имя и процедура окна существующего класса окон сохраняются в [m_lpszClassName](#m_lpszclassname) и [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)соответственно.

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>CContainedWindowT::SubclassWindow

Подклассы окна, идентифицированного *hWnd,* `CContainedWindowT` и прикрепляет его к объекту.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к подклассу окна.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно успешно подклассифицировано; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Подклассное окно теперь использует [CContainedWindowT::WindowProc](#windowproc). Оригинальная процедура окна сохраняется в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

> [!NOTE]
> Не звоните, `SubclassWindow` если вы уже позвонили [Создать](#create).

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap

Изменения, какие карты сообщений будут использоваться для обработки сообщений, содержащихся в окне.

```cpp
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Параметры

*dwMsgMapID*<br/>
(в) Идентификатор карты сообщений. Чтобы использовать карту сообщения по умолчанию, объявленную [с BEGIN_MSG_MAP,](message-map-macros-atl.md#begin_msg_map)передайте ноль. Использовать альтернативную карту сообщений, объявленную с ALT_MSG_MAP `msgMapID` [(msgMapID),](message-map-macros-atl.md#alt_msg_map)пройдите.

### <a name="remarks"></a>Примечания

Карта сообщений должна быть определена в содержащем объекте.

Первоначально вы указываете идентификатор карты сообщений в конструкторе.

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>CContainedWindowT:UnsubclassWindow

Отсоединяет подклассифицированное окно от `CContainedWindowT` объекта и восстанавливает исходную процедуру окна, сохраненную в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Параметры

*bForce*<br/>
(в) Установите TRUE, чтобы заставить оригинальную процедуру окна `CContainedWindowT` быть восстановлены, даже если процедура окна для этого объекта в настоящее время не активна. Если *bForce* настроен на FALSE и `CContainedWindowT` процедура окна для этого объекта в настоящее время не активна, первоначальная процедура окна не будет восстановлена.

### <a name="return-value"></a>Возвращаемое значение

Ручка к окну ранее подклассифицирована. Если *bForce* настроен на FALSE и `CContainedWindowT` процедура окна для этого объекта в настоящее время не активна, возвращает NULL.

### <a name="remarks"></a>Примечания

Используйте этот метод только в том случае, если вы хотите восстановить исходную процедуру окна до того, как окно будет уничтожено. В противном случае [WindowProc](#windowproc) автоматически сделает это при разрушении окна.

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a>CContainedWindowT::WindowProc

Этот статический метод реализует процедуру окна.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к окну.

*uMsg*<br/>
(в) Сообщение, отправленное в окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщений.

### <a name="remarks"></a>Примечания

`WindowProc`направляет сообщения на карту сообщений, идентифицированную [m_dwMsgMapID.](#m_dwmsgmapid) При необходимости звоните `WindowProc` в [DefWindowProc](#defwindowproc) для дополнительной обработки сообщений.

## <a name="see-also"></a>См. также раздел

[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Класс CMessageMap](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
