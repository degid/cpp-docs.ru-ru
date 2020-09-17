---
title: Класс CBindStatusCallback
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 0ae7f4fcdba18be84d99140e395b6f2ac3db792a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748210"
---
# <a name="cbindstatuscallback-class"></a>Класс CBindStatusCallback

Этот класс реализует интерфейс `IBindStatusCallback`.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, содержащий функцию, которая будет вызываться по мере получения данных.

*nBindFlags*<br/>
Определяет флаги связывания, которые возвращаются [GetBindInfo](#getbindinfo). Реализация по умолчанию устанавливает привязку как асинхронную, извлекает новейшую версию данных/объекта и не хранит извлеченные данные в кэше диска.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Конструктор.|
|[CBindStatusCallback:: »Кбиндстамастокальбэк](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::D](#download)|Статический метод, который запускает `CBindStatusCallback` процесс загрузки, создает объект и вызывает. `StartAsyncDownload`|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Вызывается асинхронным прозвищем, чтобы запросить информацию о типе связывания, который будет создан.|
|[CBindStatusCallback::GetPriority](#getpriority)|Вызывается асинхронным прозвищем, чтобы получить приоритет операции связывания. Возвращает реализацию `E_NOTIMPL`ATL.|
|[CBindStatusCallback:OnData Available](#ondataavailable)|Вызывается для предоставления данных в приложение по мере его появления. Читает данные, а затем вызывает функцию, переданную ему, чтобы использовать данные.|
|[CBindstatusCallback::OnLowResource](#onlowresource)|Вызывается, когда ресурсы низки. Реализация ATL возвращает S_OK.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Вызывается асинхронным псевдонимом, чтобы передать указатель интерфейса объекта в приложение. Реализация ATL возвращает S_OK.|
|[CBindStatusCallback::OnProgress](#onprogress)|Вызывается для обозначения хода процесса загрузки данных. Реализация ATL возвращает S_OK.|
|[CBindstatusCallback::OnStartBinding](#onstartbinding)|Вызывается при начале связывания.|
|[CBindstatusCallback::OnstopBinding](#onstopbinding)|Вызывается при прекращении асинхронной передачи данных.|
|[CBindStatusCallback:StartAsyncDownload](#startasyncdownload)|Инициализация доступных байтов и байтов, читаемых до нуля, создает объект потока типа push из URL и вызывает `OnDataAvailable` каждый раз, когда данные доступны.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Количество байтов, доступных для чтения.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Общее количество прочитано байтов.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Указатель на функцию, вызванную при наличии данных.|
|[CBindStatusCallback::m_pT](#m_pt)|Указатель на объект, запрашивающий асинхронную передачу данных.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Указатель на интерфейс [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) для текущей операции связывания.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Указатель на `IBinding` интерфейс для текущей операции связывания.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Указатель на интерфейс [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) для использования URL.й.|
|[CBindStatusCallback::m_spStream](#m_spstream)|Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) для передачи данных.|

## <a name="remarks"></a>Примечания

Класс `CBindStatusCallback` реализует интерфейс `IBindStatusCallback`. `IBindStatusCallback`должно быть реализовано вашим приложением, чтобы оно мог получать уведомления от асинхронной передачи данных. Асинхронное прозвище, предоставляемое системой, использует `IBindStatusCallback` методы для отправки и получения информации о передаче асинхронных данных на объект и с вашего объекта.

Как правило, `CBindStatusCallback` объект связан с конкретной операцией связывания. Например, в примере [ASYNC](../../overview/visual-cpp-samples.md) при установке свойства `CBindStatusCallback` URL создается `Download`объект в вызове:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Асинхронное прозвище использует функцию `OnData` обратного вызова приложения, когда у него есть данные. Асинхронное прозвище предоставляется системой.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback

Конструктор.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Примечания

Создает объект для получения уведомлений о передаче асинхронных данных. Как правило, для каждой операции связывания создается один объект.

Конструктор также инициализирует [m_pT](#m_pt) и [m_pFunc](#m_pfunc) null.

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="dtor"></a>CBindStatusCallback:: »Кбиндстамастокальбэк

Деструктор

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="cbindstatuscallbackdownload"></a><a name="download"></a>CBindStatusCallback::D

Создает `CBindStatusCallback` объект и `StartAsyncDownload` призывает начать асинхронную загрузку данных из указанного URL.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
(в) Указатель на объект, запрашивающий асинхронную передачу данных. Объект `CBindStatusCallback` используется на классе этого объекта.

*pFunc*<br/>
(в) Указатель на функцию, которая получает данные, которые считываемые. Функция является членом класса типа `T`объекта. Смотрите [StartAsyncDownload](#startasyncdownload) для синтаксиса и пример.

*bstrURL*<br/>
(в) URL для получения данных. Может быть любой действительный URL или имя файла. Не может быть NULL. Пример:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
(в) Контейнер. `IUnknown` NULL по умолчанию.

*bОтносительно*<br/>
(в) Флаг, указывающий, является ли URL-адрес относительно или абсолютным. FALSE по умолчанию, то есть URL является абсолютным.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Каждый раз, когда данные доступны, они отправляются на объект через `OnDataAvailable`. `OnDataAvailable`считывает данные и вызывает функцию, на которую указывает *pFunc* (например, для хранения данных или печати на экране).

## <a name="cbindstatuscallbackgetbindinfo"></a><a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo

Позвонил, чтобы сказать прозвище, как связать.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Параметры

*pgrfBSCF*<br/>
(ваут) Указатель на значения перечисления BINDF с указанием того, как должна происходить операция связывания. По умолчанию устанавливается со следующими значениями перечисления:

BINDF_ASYNCHRONOUS асинхронная загрузка.

BINDF_ASYNCSTORAGE `OnDataAvailable` возвращает E_PENDING, когда данные еще не доступны, а не блокируются до тех пор, пока данные не будут доступны.

BINDF_GETNEWESTVERSION операция связывания должна получить новейшую версию данных.

BINDF_NOWRITECACHE Операция связывания не должна хранить извлеченные данные в кэше диска.

*pbindinfo*<br/>
(в, вне) Указатель на `BINDINFO` структуру, дающий больше информации о том, как объект хочет иметь привязку.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Реализация по умолчанию устанавливает привязку к асинхрону и использовать модель нажатия данных. В модели нажатия данных кличка приводит к работе асинхронного связывания и постоянно уведомляет клиента при наличии новых данных.

## <a name="cbindstatuscallbackgetpriority"></a><a name="getpriority"></a>CBindStatusCallback::GetPriority

Вызывается асинхронным прозвищем, чтобы получить приоритет операции связывания.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Параметры

*pnPriority*<br/>
(ваут) Адрес **переменной LONG,** которая, по успеху, получает приоритет.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="cbindstatuscallbackm_dwavailabletoread"></a><a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead

Можно использовать для хранения количества байтов, доступных для чтения.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Примечания

Инициализировано до нуля в `StartAsyncDownload`.

## <a name="cbindstatuscallbackm_dwtotalread"></a><a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead

Совокупное количество байтов, читаемых в асинхронной передаче данных.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Примечания

Приращенные каждый раз `OnDataAvailable` вызывается число байтов на самом деле читать. Инициализировано до нуля в `StartAsyncDownload`.

## <a name="cbindstatuscallbackm_pfunc"></a><a name="m_pfunc"></a>CBindStatusCallback::m_pFunc

Функция, на `m_pFunc` которую `OnDataAvailable` указывается, вызывается после считываема доступные данные (например, для хранения данных или печати их на экране).

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Примечания

Функция, на `m_pFunc` которую указывается, является членом класса вашего объекта и имеет следующий синтаксис:

```cpp
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

## <a name="cbindstatuscallbackm_pt"></a><a name="m_pt"></a>CBindStatusCallback::m_pT

Указатель на объект, запрашивающий асинхронную передачу данных.

```
T* m_pT;
```

### <a name="remarks"></a>Примечания

Объект `CBindStatusCallback` используется на классе этого объекта.

## <a name="cbindstatuscallbackm_spbindctx"></a><a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx

Указатель на интерфейс [IBindCtx,](/windows/win32/api/objidl/nn-objidl-ibindctx) обеспечивающий доступ к контексту связывания (объект, который хранит информацию о конкретной операции связывания моникера).

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Примечания

Инициализировано в `StartAsyncDownload`.

## <a name="cbindstatuscallbackm_spbinding"></a><a name="m_spbinding"></a>CBindStatusCallback::m_spBinding

Указатель на `IBinding` интерфейс текущей операции связывания.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Примечания

Инициализированы и `OnStartBinding` выпущены в `OnStopBinding`.

## <a name="cbindstatuscallbackm_spmoniker"></a><a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker

Указатель на интерфейс [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) для использования URL.й.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Примечания

Инициализировано в `StartAsyncDownload`.

## <a name="cbindstatuscallbackm_spstream"></a><a name="m_spstream"></a>CBindStatusCallback::m_spStream

Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) текущей операции связывания.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Примечания

Инициализировано `OnDataAvailable` от `STGMEDIUM` структуры, когда флаг BCSF BCSF_FIRSTDATANOTIFICATION и выпущен, когда флаг BCSF BCSF_LASTDATANOTIFICATION.

## <a name="cbindstatuscallbackondataavailable"></a><a name="ondataavailable"></a>CBindStatusCallback:OnData Available

Система, поставляемая асинхронным `OnDataAvailable` псевдонимом, требует предоставления данных объекту по мере его поступления.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Параметры

*grfBSCF*<br/>
(в) Значение перечисления BSCF. Один или несколько из следующих: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION или BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
(в) Совокупное количество (в байтах) данных, доступных с начала связывания. Может быть ноль, что указывает на то, что объем данных не имеет значения или что конкретная сумма не стала доступной.

*pformatetc*<br/>
(в) Указатель на структуру [FORMATETC,](/windows/win32/com/the-formatetc-structure) содержащую формат имеющихся данных. Если нет формата, можно CF_NULL.

*pstgmed*<br/>
(в) Указатель на структуру [STGMEDIUM,](/windows/win32/com/the-stgmedium-structure) которая содержит фактические данные, доступные в настоящее время.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`OnDataAvailable`читает данные, а затем вызывает метод класса объекта (например, для хранения данных или распечатать их на экране). Смотрите [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) для получения подробной информации.

## <a name="cbindstatuscallbackonlowresource"></a><a name="onlowresource"></a>CBindstatusCallback::OnLowResource

Вызывается, когда ресурсы низки.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="cbindstatuscallbackonobjectavailable"></a><a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable

Вызывается асинхронным псевдонимом, чтобы передать указатель интерфейса объекта в приложение.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса запрашиваемого интерфейса. Не используется.

*Панк*<br/>
Адрес интерфейса IUnknown. Не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="cbindstatuscallbackonprogress"></a><a name="onprogress"></a>CBindStatusCallback::OnProgress

Вызывается для обозначения хода процесса загрузки данных.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Параметры

*ulProgress*<br/>
Неподписанный длинный целый нисх. Не используется.

*ulProgressMax*<br/>
Неподписанный длинный целый teger Неиспользованные.

*ulStatusCode*<br/>
Неподписанный длинный целый нисх. Не используется.

*szStatusТекст*<br/>
Адрес значения строки. Не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="cbindstatuscallbackonstartbinding"></a><a name="onstartbinding"></a>CBindstatusCallback::OnStartBinding

Устанавливает член [m_spBinding](#m_spbinding) данных `IBinding` m_spBinding указателя в *pBinding*.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано для последующего использования.

*pBinding*<br/>
(в) Адрес интерфейса IBinding текущей операции связывания. Это не может быть NULL. Клиент должен вызвать AddRef по этому указателю, чтобы сохранить ссылку на обязательный объект.

## <a name="cbindstatuscallbackonstopbinding"></a><a name="onstopbinding"></a>CBindstatusCallback::OnstopBinding

Выпускает `IBinding` указатель в [m_spBinding](#m_spbinding)члена данных.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Параметры

*Hresult*<br/>
Код состояния, возвращенный из операции связывания.

*szОшибка*<br/>
Адрес значения строки. Не используется.

### <a name="remarks"></a>Примечания

Вызывается системным асинхронным моникером, чтобы указать конец операции связывания.

## <a name="cbindstatuscallbackstartasyncdownload"></a><a name="startasyncdownload"></a>CBindStatusCallback:StartAsyncDownload

Начинает загрузку данных асинхронно из указанного URL-

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
(в) Указатель на объект, запрашивающий асинхронную передачу данных. Объект `CBindStatusCallback` используется на классе этого объекта.

*pFunc*<br/>
(в) Указатель на функцию, которая получает прочитаны данные. Функция является членом класса типа `T`объекта. Смотрите **замечания** для синтаксиса и пример.

*bstrURL*<br/>
(в) URL для получения данных. Может быть любой действительный URL или имя файла. Не может быть NULL. Пример:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
(в) Контейнер. `IUnknown` NULL по умолчанию.

*bОтносительно*<br/>
(в) Флаг, указывающий, является ли URL-адрес относительно или абсолютным. FALSE по умолчанию, то есть URL является абсолютным.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Каждый раз, когда данные доступны, они отправляются на объект через `OnDataAvailable`. `OnDataAvailable`считывает данные и вызывает функцию, на которую указывает *pFunc* (например, для хранения данных или печати на экране).

Функция, на которую указывает *pFunc,* является членом класса вашего объекта и имеет следующий синтаксис:

```cpp
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

В следующем примере (взятый из образца [ASYNC)](../../overview/visual-cpp-samples.md) функция `OnData` записывает полученные данные в текстовое поле.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
