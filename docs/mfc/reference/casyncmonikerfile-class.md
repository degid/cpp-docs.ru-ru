---
title: Класс Касинкмоникерфиле
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: 259d31b9c1e198b326ba616481dbbf5315225546
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845943"
---
# <a name="casyncmonikerfile-class"></a>Класс Касинкмоникерфиле

Предоставляет функции для использования асинхронных моникеров в элементах управления ActiveX (ранее элементах управления OLE).

## <a name="syntax"></a>Синтаксис

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Касинкмоникерфиле:: Касинкмоникерфиле](#casyncmonikerfile)|Формирует объект `CAsyncMonikerFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Касинкмоникерфиле:: Close](#close)|Закрывает и освобождает все ресурсы.|
|[Касинкмоникерфиле:: DataBindings](#getbinding)|Получает указатель на привязку асинхронной пересылки.|
|[Касинкмоникерфиле:: Жетформатетк](#getformatetc)|Возвращает формат данных в потоке.|
|[Касинкмоникерфиле:: Open](#open)|Открывает файл асинхронно.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Касинкмоникерфиле:: Креатебиндстатускаллбакк](#createbindstatuscallback)|Создает COM-объект, реализующий интерфейс `IBindStatusCallback` .|
|[Касинкмоникерфиле:: GetBindInfo](#getbindinfo)|Вызывается системной библиотекой OLE для запроса информации о типе создаваемой привязки.|
|[Касинкмоникерфиле:: предшествовал](#getpriority)|Вызывается системной библиотекой OLE для получения приоритета привязки.|
|[Касинкмоникерфиле:: Ондатааваилабле](#ondataavailable)|Вызывается для предоставления данных в том виде, в котором они становятся доступными клиенту во время асинхронных операций привязки.|
|[Касинкмоникерфиле:: Онловресаурце](#onlowresource)|Вызывается, когда ресурсы имеют низкий уровень.|
|[Касинкмоникерфиле:: OnProgress](#onprogress)|Вызывается для указания хода выполнения процесса загрузки данных.|
|[Касинкмоникерфиле:: Онстартбиндинг](#onstartbinding)|Вызывается при запуске привязки.|
|[Касинкмоникерфиле:: Онстопбиндинг](#onstopbinding)|Вызывается при остановке асинхронной пересылки.|

## <a name="remarks"></a>Примечания

Производный от [кмоникерфиле](../../mfc/reference/cmonikerfile-class.md), который, в свою очередь, является производным от [колестреамфиле](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` использует интерфейс [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) для асинхронного доступа к любому потоку данных, включая загрузку файлов в асинхронном режиме из URL-адреса. Это могут быть свойства пути к файлам элементов управления ActiveX.

Асинхронные моникеры используются преимущественно в приложениях с поддержкой Интернета и элементах управления ActiveX, чтобы обеспечить реагирование пользовательского интерфейса во время передачи файлов. Простым примером этого является использование [кдатапаспроперти](../../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронных свойств для элементов управления ActiveX. `CDataPathProperty`Объект будет многократно получать обратный вызов для указания доступности новых данных во время длительного процесса обмена свойствами.

Дополнительные сведения об использовании асинхронных моникеров и элементов управления ActiveX в веб – приложениях см. в следующих статьях:

- [Первые действия через Интернет: асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)

- [Первые действия в Интернете: элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле.h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a> Касинкмоникерфиле:: Касинкмоникерфиле

Формирует объект `CAsyncMonikerFile`.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Примечания

Он не создает `IBindHost` интерфейс. `IBindHost` используется только в том случае, если вы предоставляете его в `Open` функции-члене.

Описание `IBindHost` интерфейса см. в Windows SDK.

## <a name="casyncmonikerfileclose"></a><a name="close"></a> Касинкмоникерфиле:: Close

Вызовите эту функцию, чтобы закрыть и освободить все ресурсы.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Может вызываться для неоткрытых или уже закрытых файлов.

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a> Касинкмоникерфиле:: Креатебиндстатускаллбакк

Создает COM-объект, реализующий интерфейс `IBindStatusCallback` .

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Параметры

*пункконтроллинг*<br/>
Указатель на управление неизвестным (внешним `IUnknown` ) или null, если агрегат не используется.

### <a name="return-value"></a>Возвращаемое значение

Если *пункконтроллинг* не равно null, функция возвращает указатель на внутреннее значение `IUnknown` в новом COM-объекте, поддерживающем `IBindStatusCallback` . Если значение `pUnkControlling` равно null, функция возвращает указатель на `IUnknown` Новый COM-объект, поддерживающий `IBindStatusCallback` .

### <a name="remarks"></a>Примечания

`CAsyncMonikerFile` требуется COM-объект, реализующий `IBindStatusCallback` . MFC реализует такой объект, и он может быть агрегирован. Можно переопределить `CreateBindStatusCallback` , чтобы вернуть собственный COM-объект. COM-объект может агрегировать реализацию MFC путем вызова `CreateBindStatusCallback` с помощью управления неизвестным объектом COM. COM-объекты, реализованные с помощью `CCmdTarget` поддержки COM, могут извлекать неизвестное управление с помощью `CCmdTarget::GetControllingUnknown` .

Кроме того, COM-объект может делегировать реализацию MFC путем вызова `CreateBindStatusCallback( NULL )` .

Вызовы [касинкмоникерфиле:: Open](#open) `CreateBindStatusCallback` .

Дополнительные сведения о асинхронных моникерах и асинхронной привязке см. в разделе интерфейс [метода интерфейса IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) и [работа асинхронной привязки и хранилища](/windows/win32/Stg/how-asynchronous-binding-and-storage-work). Обсуждение статистической обработки см. в разделе [агрегирование](/windows/win32/com/aggregation). Все три раздела находятся в Windows SDK.

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a> Касинкмоникерфиле:: GetBindInfo

Вызывается из клиента асинхронного моникера, чтобы сообщить асинхронному моникеру, как он хочет выполнить привязку.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает параметры для `IBindStatusCallBack` . Описание `IBindStatusCallback` интерфейса см. в Windows SDK.

### <a name="remarks"></a>Примечания

Реализация по умолчанию задает для привязки значение асинхронно, для использования среды хранения (потока) и для использования модели принудительной передачи данных. Переопределите эту функцию, если необходимо изменить поведение привязки.

Одной из причин для этого является привязка с использованием модели извлечения данных, а не модели передачи данных. В модели с извлечением данных клиент выполняет операцию привязки, и моникер предоставляет клиенту данные только при считывании. В модели принудительной передачи данных моникер выполняет операцию асинхронной привязки и постоянно уведомляет клиента каждый раз, когда доступны новые данные.

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a> Касинкмоникерфиле:: DataBindings

Вызовите эту функцию, чтобы получить указатель на привязку асинхронной пересылки.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, `IBinding` указанный при начале асинхронной пересылки. Возвращает значение NULL, если по какой бы то ни было причине невозможно сделать перемещение асинхронно.

### <a name="remarks"></a>Примечания

Это позволяет управлять процессом обмена данными через `IBinding` интерфейс, например с помощью `IBinding::Abort` , `IBinding::Pause` и `IBinding::Resume` .

Описание `IBinding` интерфейса см. в Windows SDK.

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a> Касинкмоникерфиле:: Жетформатетк

Вызовите эту функцию, чтобы получить формат данных в потоке.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру Windows [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) для текущего открытого потока. Возвращает значение NULL, если моникер не был привязан, если он не является асинхронным или если асинхронная операция не началась.

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a> Касинкмоникерфиле:: предшествовал

Вызывается из клиента асинхронного моникера, так как процесс привязки начинает получение приоритета, переданного потоку для операции привязки.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Возвращаемое значение

Приоритет, с которым будет осуществляться асинхронная перенаправление. Один из стандартных флагов приоритета потока: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL и THREAD_PRIORITY_TIME_CRITICAL. Описание этих значений см. в описании функции Windows [сетсреадприорити](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) .

### <a name="remarks"></a>Примечания

`GetPriority` не следует вызывать напрямую. THREAD_PRIORITY_NORMAL возвращается реализацией по умолчанию.

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a> Касинкмоникерфиле:: Ондатааваилабле

Асинхронные вызовы моникера `OnDataAvailable` для предоставления данных клиенту по мере доступности, во время асинхронных операций привязки.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Параметры

*двсизе*<br/>
Совокупный объем данных (в байтах), доступный с начала привязки. Может быть равен нулю, что означает, что объем данных не связан с операцией или не стал доступной определенной суммы.

*бскффлаг*<br/>
Значение перечисления БСКФ. Может иметь одно или несколько из следующих значений:

- BSCF_FIRSTDATANOTIFICATION определяет первый вызов `OnDataAvailable` для данной операции привязки.

- BSCF_INTERMEDIATEDATANOTIFICATION идентифицирует промежуточный вызов для `OnDataAvailable` операции привязки.

- BSCF_LASTDATANOTIFICATION определяет последний вызов `OnDataAvailable` для операции привязки.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Пример реализации см. в следующем примере.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a> Касинкмоникерфиле:: Онловресаурце

Вызывается моникером, когда ресурсы имеют низкий уровень.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает `GetBinding( )-> Abort( )` .

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a> Касинкмоникерфиле:: OnProgress

Вызывается моникером многократно для указания текущего хода выполнения этой операции привязки, обычно в разумных интервалах во время длительной операции.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Параметры

*улпрогресс*<br/>
Указывает текущий ход выполнения операции привязки относительно ожидаемого максимума, указанного в *улпрогрессмакс*.

*улпрогрессмакс*<br/>
Указывает ожидаемое максимальное значение *улпрогресс* для длительности вызовов для `OnProgress` данной операции.

*улстатускоде*<br/>
Предоставляет дополнительные сведения о ходе выполнения операции привязки. Допустимые значения берутся из `BINDSTATUS` перечисления. Возможные значения см. в разделе "Примечания".

*сзстатустекст*<br/>
Сведения о текущем ходе выполнения в зависимости от значения *улстатускоде*. Возможные значения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Возможные значения для *улстатускоде* (и *сзстатустекст* для каждого значения):

| Значение | Описание |
|--|--|
| BINDSTATUS_FINDINGRESOURCE | Операция привязки находит ресурс, содержащий объект или хранилище, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя искомого ресурса (например, "www.Microsoft.com"). |
| BINDSTATUS_CONNECTING | Операция привязки подключается к ресурсу, содержащему объект или хранилище, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя ресурса, к которому выполняется подключение (например, IP-адрес). |
| BINDSTATUS_SENDINGREQUEST | Операция привязки запрашивает объект или хранилище, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя объекта (например, имя файла). |
| BINDSTATUS_REDIRECTING | Операция привязки была перенаправлена в другое расположение данных. *Сзстатустекст* предоставляет отображаемое имя нового расположения данных. |
| BINDSTATUS_USINGCACHEDCOPY | Операция привязки извлекает запрошенный объект или хранилище из кэшированной копии. *Сзстатустекст* имеет значение null. |
| BINDSTATUS_BEGINDOWNLOADDATA | Операция привязки начала получение объекта или хранилища, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя расположения данных. |
| BINDSTATUS_DOWNLOADINGDATA | Операция привязки продолжит получение объекта или хранилища, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя расположения данных. |
| BINDSTATUS_ENDDOWNLOADDATA | Операция привязки завершила получение объекта или хранилища, к которому выполняется привязка. *Сзстатустекст* предоставляет отображаемое имя расположения данных. |
| BINDSTATUS_CLASSIDAVAILABLE | Экземпляр объекта, к которому выполняется привязка, — это все, что будет создано. *Сзстатустекст* предоставляет CLSID нового объекта в строковом формате, позволяя клиенту отменить операцию привязки при необходимости. |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a> Касинкмоникерфиле:: Онстартбиндинг

Переопределяйте эту функцию в производных классах для выполнения действий при запуске привязки.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается обратно моникером. Реализация по умолчанию не выполняет никаких действий.

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a> Касинкмоникерфиле:: Онстопбиндинг

Вызывается моникером в конце операции привязки.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Параметры

*состав*<br/>
Значение HRESULT, которое является значением ошибки или предупреждения.

*сзеррорт*<br/>
Символьная строка, описывающая ошибку.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для выполнения действий при остановке перемещения. По умолчанию функция выпусков `IBinding` .

Описание `IBinding` интерфейса см. в Windows SDK.

## <a name="casyncmonikerfileopen"></a><a name="open"></a> Касинкмоникерфиле:: Open

Вызовите эту функцию-член для асинхронного открытия файла.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзурл*<br/>
Указатель на файл, который должен быть открыт асинхронно. Файл может быть любым допустимым URL-адресом или именем файла.

*pError*<br/>
Указатель на исключения файла. В случае ошибки будет задана причина.

*пмоникер*<br/>
Указатель на интерфейс асинхронного моникера `IMoniker` , точный моникер, являющийся сочетанием собственного моникера документа, который можно получить с помощью `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)` , и моникер, созданный на основе имени пути. Элемент управления может использовать это моникер для привязки, но это не является моникером, который элемент управления должен сохранить.

*пбиндхост*<br/>
Указатель на `IBindHost` интерфейс, который будет использоваться для создания моникера из потенциально относительных путей. Если узел привязки является недопустимым или не предоставляет моникер, по умолчанию вызывается `Open(lpszFileName,pError)` . Описание `IBindHost` интерфейса см. в Windows SDK.

*псервицепровидер*<br/>
Указатель на интерфейс `IServiceProvider` . Если поставщик услуг является недопустимым или не удается предоставить службу для `IBindHost` , по умолчанию вызывается `Open(lpszFileName,pError)` .

*pUnknown*<br/>
Указатель на интерфейс `IUnknown` . Если `IServiceProvider` найден, функция запрашивает `IBindHost` . Если поставщик услуг является недопустимым или не удается предоставить службу для `IBindHost` , по умолчанию вызывается `Open(lpszFileName,pError)` .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если файл открыт успешно. в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот вызов инициирует процесс привязки.

Для параметра *лпсзурл* можно использовать URL-адрес или имя файла. Пример:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- или -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс Кмоникерфиле](../../mfc/reference/cmonikerfile-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кмоникерфиле](../../mfc/reference/cmonikerfile-class.md)<br/>
[Класс Кдатапаспроперти](../../mfc/reference/cdatapathproperty-class.md)
