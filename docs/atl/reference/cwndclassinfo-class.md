---
title: Класс Квндклассинфо
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: c1b516f6e92f98d660f7757870a3e634dcef4518
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835510"
---
# <a name="cwndclassinfo-class"></a>Класс Квндклассинфо

Этот класс предоставляет методы для регистрации сведений для класса окна.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWndClassInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Зарегистрировать](#register)|Регистрирует класс окна.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|[m_atom](#m_atom)|Уникально идентифицирует зарегистрированный класс окна.|
|[m_bSystemCursor](#m_bsystemcursor)|Указывает, относится ли ресурс курсора к системному курсору или к курсору, содержащемуся в ресурсе модуля.|
|[m_lpszCursorID](#m_lpszcursorid)|Указывает имя ресурса курсора.|
|[m_lpszOrigName](#m_lpszorigname)|Содержит имя существующего класса Window.|
|[m_szAutoName](#m_szautoname)|Содержит имя класса окна, сформированное библиотекой ATL.|
|[m_wc](#m_wc)|Сохраняет сведения о классе окна в `WNDCLASSEX` структуре.|
|[пвндпрок](#pwndproc)|Указывает на процедуру окна существующего класса окна.|

## <a name="remarks"></a>Примечания

`CWndClassInfo` управляет информацией класса окна. Обычно используется `CWndClassInfo` один из трех макросов: DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX или DECLARE_WND_SUPERCLASS, как описано в следующей таблице.

|Макрос|Описание|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` регистрирует сведения для нового класса окна.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` регистрирует сведения для нового класса окна, включая параметры класса.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` регистрирует сведения для класса окна, основанного на существующем классе, но с использованием другой процедуры окна. Этот метод называется «подклассом».|

По умолчанию [квиндовимпл](../../atl/reference/cwindowimpl-class.md) включает `DECLARE_WND_CLASS` макрос для создания окна на основе нового класса окна. DECLARE_WND_CLASS предоставляет стили по умолчанию и цвет фона для элемента управления. Если вы хотите самостоятельно указать стиль и цвет фона, создайте класс, производный от класса, `CWindowImpl` и включите макрос DECLARE_WND_CLASS_EX в определение класса.

Если вы хотите создать окно на основе существующего класса окна, создайте класс, производный от класса, `CWindowImpl` и включите макрос DECLARE_WND_SUPERCLASS в определение класса. Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Дополнительные сведения о классах окон см. в разделе [классы окон](/windows/win32/winmsg/window-classes) в Windows SDK.

Дополнительные сведения об использовании Windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a> Квндклассинфо:: m_atom

Содержит уникальный идентификатор для зарегистрированного класса окна.

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a> Квндклассинфо:: m_bSystemCursor

Если значение — TRUE, ресурс системного курсора будет загружен при регистрации класса окна.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Примечания

В противном случае будет загружен ресурс курсора, содержащийся в вашем модуле.

`CWndClassInfo` используется `m_bSystemCursor` только в том случае, если указан [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (значение по умолчанию в [квиндовимпл](../../atl/reference/cwindowimpl-class.md)) или макрос [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) . В этом случае `m_bSystemCursor` инициализируется ЗНАЧЕНИЕМ true. Дополнительные сведения см. в обзоре [квндклассинфо](../../atl/reference/cwndclassinfo-class.md) .

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a> Квндклассинфо:: m_lpszCursorID

Указывает либо имя ресурса курсора, либо идентификатор ресурса в слове с низким порядком и ноль в слове в высоком порядке.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Примечания

Когда класс Window зарегистрирован, маркер курсора, идентифицируемого, `m_lpszCursorID` извлекается и сохраняется в [m_wc](#m_wc).

`CWndClassInfo` используется `m_lpszCursorID` только в том случае, если указан [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (значение по умолчанию в [квиндовимпл](../../atl/reference/cwindowimpl-class.md)) или макрос [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) . В этом случае `m_lpszCursorID` инициализируется значением IDC_ARROW. Дополнительные сведения см. в обзоре [квндклассинфо](../../atl/reference/cwndclassinfo-class.md) .

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a> Квндклассинфо:: m_lpszOrigName

Содержит имя существующего класса Window.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` используется `m_lpszOrigName` только при включении макроса [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) в определение класса. В этом случае `CWndClassInfo` регистрирует класс окна на основе класса с именем `m_lpszOrigName` . Дополнительные сведения см. в обзоре [квндклассинфо](../../atl/reference/cwndclassinfo-class.md) .

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a> Квндклассинфо:: m_szAutoName

Содержит имя класса окна.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` использует `m_szAutoName` только в том случае, если параметру передается значение `WndClassName` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) или [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass). ATL будет создавать имя при регистрации класса окна.

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a> Квндклассинфо:: m_wc

Сохраняет сведения о классе окна в структуре [вндклассекс](/windows/win32/api/winuser/ns-winuser-wndclassexw) .

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Примечания

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (значение по умолчанию в [квиндовимпл](../../atl/reference/cwindowimpl-class.md)) или макрос [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) , `m_wc` содержит сведения о новом классе окна.

Если вы указали макрос [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) , `m_wc` содержит сведения о суперклассе — классе окна, основанном на существующем классе, но использующем другую процедуру окна. [m_lpszOrigName](#m_lpszorigname) и [пвндпрок](#pwndproc) сохраняют имя и процедуру окна существующего класса окна соответственно.

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a> Квндклассинфо::p WndProc

Указывает на процедуру окна существующего класса окна.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` используется `pWndProc` только при включении макроса [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) в определение класса. В этом случае `CWndClassInfo` регистрирует класс окна, основанный на существующем классе, но использует другую процедуру окна. Процедура окна существующего класса Window сохраняется в `pWndProc` . Дополнительные сведения см. в обзоре [квндклассинфо](../../atl/reference/cwndclassinfo-class.md) .

## <a name="cwndclassinforegister"></a><a name="register"></a> Квндклассинфо:: Register

Вызывается методом [квиндовимпл:: Create](../../atl/reference/cwindowimpl-class.md#create) для регистрации класса окна, если он еще не зарегистрирован.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Параметры

*ппрок*<br/>
заполняет Задает исходную процедуру окна для существующего класса окна.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха атом, однозначно определяющий регистрируемый класс окна. В противном случае флагу присваивается значение 0.

### <a name="remarks"></a>Примечания

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [квиндовимпл](../../atl/reference/cwindowimpl-class.md)) или макрос [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) , `Register` регистрирует новый класс окна. В этом случае параметр *ппрок* не используется.

Если вы указали макрос [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) , `Register` регистрирует суперкласс — класс окна, основанный на существующем классе, но использующий другую процедуру окна. Процедура окна существующего класса Window возвращается в *ппрок*.

## <a name="see-also"></a>См. также раздел

[Класс Ккомконтрол](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
