---
title: Класс CAxWindow2T
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: 14080b624132979df533135bc1eef108dc793398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318697"
---
# <a name="caxwindow2t-class"></a>Класс CAxWindow2T

Этот класс предоставляет методы для манипулирования окном, в котором размещается элемент управления ActiveX, а также имеет поддержку для хостинга лицензированных элементов управления ActiveX.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Параметры

*TBase*<br/>
Класс, из `CAxWindowT` которого вытекает.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Формирует объект `CAxWindow2T`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T::Создание](#create)|Создает окно-хост.|
|[CAxWindow2T::CreateControllic](#createcontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает его в указанном окне и извлекает указатель интерфейса (или указателей) из элемента управления.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Статический метод, который получает имя класса окна.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T:оператор](#operator_eq)|Присваивает HWND `CAxWindow2T` существующему объекту.|

## <a name="remarks"></a>Примечания

`CAxWindow2T`предоставляет методы для манипулирования окном, в котором размещается элемент управления ActiveX. `CAxWindow2T`также имеет поддержку для хостинга лицензированных элементов управления ActiveX. Хостинг предоставляется " **AtlAxWinLic80**", который `CAxWindow2T`обернут .

Класс `CAxWindow2` реализован как специализация `CAxWindow2T` класса. Эта специализация заявлена как:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT`члены задокументированы в [соответствии с CAxWindow](../../atl/reference/caxwindow-class.md).

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует членов этого класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

Формирует объект `CAxWindow2T`.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Ручка существующего окна.

## <a name="caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::Создание

Создает окно-хост.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="remarks"></a>Примечания

`CAxWindow2T::Create`звонки [CWindow::Создание](../../atl/reference/cwindow-class.md#create) с LPCTSTR *lpstrWndClass* параметр, установленный`AtlAxWinLic80`в окне класса, который обеспечивает контроль хостинга ( ).

Ознакомьтесь `CWindow::Create` с описанием параметров и значением возврата.

**Заметка** Если 0 используется в качестве значения для параметра *MenuOrID,* оно должно быть указано как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `CAxWindow2T::Create`

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::CreateControllic

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Параметры

*bstrLicKey*<br/>
Ключ лицензии для управления; NULL при создании нелицензированного элемента управления.

### <a name="remarks"></a>Примечания

Смотрите [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) для описания оставшихся параметров и значения возврата.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `CAxWindow2T::CreateControlLic`

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx

Создает лицензированный элемент управления ActiveX, инициализирует его, размещает его в указанном окне и извлекает указатель интерфейса (или указателей) из элемента управления.

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>Параметры

*bstrLicKey*<br/>
Ключ лицензии для управления; NULL при создании нелицензированного элемента управления.

### <a name="remarks"></a>Примечания

Смотрите [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) для описания оставшихся параметров и значения возврата.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `CAxWindow2T::CreateControlLicEx`

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName

Извлекает название класса окон.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя`AtlAxWinLic80`класса окон (), которая может хостов лицензированных и нелицензированных элементов управления ActiveX.

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T:оператор

Присваивает HWND `CAxWindow2T` существующему объекту.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Ручка существующего окна.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)
