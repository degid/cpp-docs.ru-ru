---
title: Класс CComControl
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: 3518de3596748fa284c1f898b69d1576903e9510
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320770"
---
# <a name="ccomcontrol-class"></a>Класс CComControl

Этот класс предоставляет методы создания и управления управлением управлением ATL.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, реализующий элемент управления.

*WinBase*<br/>
Базовый класс, реализующий функции оконного окна. По умолчанию для [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComControl::ControlqueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComControl::CreateControlWindow](#createcontrolwindow)|Создает окно для управления.|
|[CComControl::FireonChanged](#fireonchanged)|Уведомляет раковину контейнера о том, что элемент управления изменился.|
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Уведомляет раковину контейнера о том, что элемент управления вот-вот изменится и что объект запрашивает раковину, как действовать.|
|[CComControl::MessageBox](#messagebox)|Вызовите этот метод для создания, отображения и эксплуатации ящика сообщений.|

## <a name="remarks"></a>Примечания

`CComControl`представляет собой набор полезных функций помощника управления и основных элементов данных для управления ATL. При создании стандартного элемента управления или управления DHTML с помощью atL `CComControl`Control Wizard мастер автоматически выводит ваш класс из. `CComControl`получает большую часть своих методов от [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).

Для получения дополнительной информации о [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md)создании элемента управления, см. Для получения дополнительной информации о ATL [Creating an ATL Project](../../atl/reference/creating-an-atl-project.md)проект Мастера, см.

Для демонстрации `CComControl` методов и членов [CIRC](../../overview/visual-cpp-samples.md) данных см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ccomcontrolccomcontrol"></a><a name="ccomcontrol"></a>CComControl::CComControl

Конструктор.

```
CComControl();
```

### <a name="remarks"></a>Примечания

Вызывает конструктор [cComControlBase,](ccomcontrolbase-class.md#ccomcontrolbase) передавая `m_hWnd` члену данных унаследованный через [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

## <a name="ccomcontrolcontrolqueryinterface"></a><a name="controlqueryinterface"></a>CComControl::ControlqueryInterface

Извлекает указатель на запрошенный интерфейс.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*Ppv*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid,* или NULL, если интерфейс не найден.

### <a name="remarks"></a>Примечания

Только обрабатывает интерфейсы в таблице карты COM.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

## <a name="ccomcontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CComControl::CreateControlWindow

По умолчанию создается окно для `CWindowImpl::Create`управления, вызывая .

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Обработка к окну родителя или владельца. Допустимая ручка окна должна быть поставлена. Окно управления приковано к области родительского окна.

*rcPos*<br/>
(в) Первоначальный размер и положение создаваемого окна.

### <a name="remarks"></a>Примечания

Переопределить этот метод, если вы хотите сделать что-то другое, кроме создания одного окна, например, для создания двух окон, одно из которых становится панелью инструментов для управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

## <a name="ccomcontrolfireonchanged"></a><a name="fireonchanged"></a>CComControl::FireonChanged

Уведомляет раковину контейнера о том, что элемент управления изменился.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Параметры

*dispID*<br/>
(в) Идентификация измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если ваш класс управления происходит от [iPropertyNotifySink,](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)этот метод вызывает [CFirePropNotifyEvent::FireOnChanged,](cfirepropnotifyevent-class.md#fireonchanged) чтобы уведомить все подключенные `IPropertyNotifySink` интерфейсы о том, что указанное свойство управления изменилось. Если ваш класс управления `IPropertyNotifySink`не вытекает из, этот метод возвращается S_OK.

Этот метод можно позвонить, даже если ваш элемент управления не поддерживает точки соединения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

## <a name="ccomcontrolfireonrequestedit"></a><a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit

Уведомляет раковину контейнера о том, что элемент управления вот-вот изменится и что объект запрашивает раковину, как действовать.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Параметры

*dispID*<br/>
(в) Идентификатор свойства вот-вот изменится.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если ваш класс управления происходит от [iPropertyNotifySink,](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)этот метод вызывает [CFirePropNotifyEvent::FireOnRequestEdit,](cfirepropnotifyevent-class.md#fireonrequestedit) чтобы уведомить все подключенные `IPropertyNotifySink` интерфейсы о том, что указанное свойство управления вот-вот изменится. Если ваш класс управления `IPropertyNotifySink`не вытекает из, этот метод возвращается S_OK.

Этот метод можно позвонить, даже если ваш элемент управления не поддерживает точки соединения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

## <a name="ccomcontrolmessagebox"></a><a name="messagebox"></a>CComControl::MessageBox

Вызовите этот метод для создания, отображения и эксплуатации ящика сообщений.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Текст, который будет отображаться в поле сообщения.

*lpszCaption*<br/>
Название диалогового окна. Если NULL (по умолчанию) используется название "Ошибка".

*nType*<br/>
Определяет содержимое и поведение диалогового окна. Ознакомьтесь с записью [В СДК Windows](/windows/win32/api/winuser/nf-winuser-messagebox) для получения списка различных доступных ящиков сообщений. По умолчанию предусмотрена простая **кнопка OK.**

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указанное в одном из значений пункта меню, перечисленных в [документации SDK](/windows/win32/api/winuser/nf-winuser-messagebox) Windows.

### <a name="remarks"></a>Примечания

`MessageBox`полезна как во время разработки, так и как простой способ отображения ошибки или предупреждения пользователя.

## <a name="see-also"></a>См. также раздел

[Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComControlBase](../../atl/reference/ccomcontrolbase-class.md)<br/>
[Класс CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)
