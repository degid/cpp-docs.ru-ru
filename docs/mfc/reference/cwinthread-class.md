---
title: Класс CWinThread
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: 6dbe4c4d3ed5edaf0563abf589cd844cca6803f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182776"
---
# <a name="cwinthread-class"></a>Класс CWinThread

Класс, представляющий поток исполнения в приложении.

## <a name="syntax"></a>Синтаксис

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinThread:: CWinThread](#cwinthread)|Формирует объект `CWinThread`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinThread:: CreateThread](#createthread)|Запускает выполнение `CWinThread` объекта.|
|[CWinThread:: ExitInstance](#exitinstance)|Переопределите для очистки при завершении потока.|
|[CWinThread:: Жетмаинвнд](#getmainwnd)|Получает указатель на главное окно для потока.|
|[CWinThread:: Жетсреадприорити](#getthreadpriority)|Возвращает приоритет текущего потока.|
|[CWinThread:: InitInstance](#initinstance)|Переопределение для выполнения инициализации экземпляра потока.|
|[CWinThread:: Исидлемессаже](#isidlemessage)|Проверяет наличие специальных сообщений.|
|[CWinThread:: OnIdle](#onidle)|Переопределение для выполнения обработки времени простоя конкретного потока.|
|[CWinThread::P Остсреадмессаже](#postthreadmessage)|Отправляет сообщение в другой `CWinThread` объект.|
|[CWinThread::P Ретранслатемессаже](#pretranslatemessage)|Фильтрует сообщения до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).|
|[CWinThread::P Роцессмессажефилтер](#processmessagefilter)|Перехватывает определенные сообщения до того, как они достигают приложения.|
|[CWinThread::P Роцессвндпроцексцептион](#processwndprocexception)|Перехватывает все необработанные исключения, вызванные сообщением потока и обработчиками команд.|
|[CWinThread::P Умпмессаже](#pumpmessage)|Содержит цикл обработки сообщений потока.|
|[CWinThread:: Ресумесреад](#resumethread)|Уменьшает значение счетчика приостановки потока.|
|[CWinThread:: Run](#run)|Управление функцией для потоков с помощью конвейера сообщений. Переопределите, чтобы настроить цикл обработки сообщений по умолчанию.|
|[CWinThread:: Сетсреадприорити](#setthreadpriority)|Задает приоритет текущего потока.|
|[CWinThread:: Суспендсреад](#suspendthread)|Увеличивает значение счетчика приостановки потока.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ОБРАБОТЧИК CWinThread::operator](#operator_handle)|Получает маркер `CWinThread` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinThread:: m_bAutoDelete](#m_bautodelete)|Указывает, следует ли уничтожить объект при завершении потока.|
|[CWinThread:: m_hThread](#m_hthread)|Обработчик текущего потока.|
|[CWinThread:: m_nThreadID](#m_nthreadid)|Идентификатор текущего потока.|
|[CWinThread:: m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера, когда OLE-сервер находится в активном месте.|
|[CWinThread:: m_pMainWnd](#m_pmainwnd)|Содержит указатель на главное окно приложения.|

## <a name="remarks"></a>Примечания

Основной поток выполнения обычно предоставляется объектом, производным от класса `CWinApp` ; `CWinApp` является производным от `CWinThread` . Дополнительные `CWinThread` объекты позволяют использовать несколько потоков в определенном приложении.

Существует два общих типа потоков, которые `CWinThread` поддерживают: рабочие потоки и потоки пользовательского интерфейса. Рабочие потоки не имеют конвейера сообщений. Например, поток, выполняющий фоновые вычисления в приложении электронной таблицы. Потоки пользовательского интерфейса имеют конвейер сообщений и обрабатывают сообщения, полученные от системы. Примерами потоков пользовательского интерфейса являются [CWinApp](../../mfc/reference/cwinapp-class.md) и классы, производные от него. Другие потоки пользовательского интерфейса также могут быть получены непосредственно из `CWinThread` .

Объекты класса `CWinThread` обычно существуют на протяжении потока. Если вы хотите изменить это поведение, задайте для [m_bAutoDelete](#m_bautodelete) значение false.

`CWinThread`Класс необходим для того, чтобы код и MFC был полностью потокобезопасным. Локальные данные потока, используемые платформой для хранения информации, относящейся к конкретному потоку, управляются `CWinThread` объектами. В связи с этим зависимостью от `CWinThread` обработки локальных данных потока, любой поток, использующий MFC, должен создаваться MFC. Например, поток, созданный с помощью функции времени выполнения [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) не может использовать API-интерфейсы MFC.

Чтобы создать поток, вызовите [афксбегинсреад](application-information-and-management.md#afxbeginthread). Существует две формы, в зависимости от того, нужен ли поток рабочего или пользовательского интерфейса. Если требуется поток пользовательского интерфейса, передайте `AfxBeginThread` указатель на `CRuntimeClass` класс, `CWinThread` производный от класса. Если необходимо создать рабочий поток, передайте `AfxBeginThread` указатель на функцию управления и параметр в функцию управления. Для рабочих потоков и потоков пользовательского интерфейса можно указать необязательные параметры, которые изменяют приоритет, размер стека, флаги создания и атрибуты безопасности. `AfxBeginThread`вернет указатель на новый `CWinThread` объект.

Вместо вызова `AfxBeginThread` можно создать `CWinThread` объект, производный от, и затем вызвать метод `CreateThread` . Этот метод создания двух этапов полезен, если необходимо повторно использовать `CWinThread` объект между последовательным созданием и завершением выполнения потоков.

Дополнительные сведения о см `CWinThread` . в статьях [многопоточность в C++ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [многопоточность. Создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md), [многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md)и [многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a>CWinThread:: CreateThread

Создает поток для выполнения в адресном пространстве вызывающего процесса.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Параметры

*двкреатефлагс*<br/>
Задает дополнительный флаг, управляющий созданием потока. Этот флаг может содержать одно из двух значений:

- CREATE_SUSPENDED запустить поток с числом приостановки, равным одному. Используйте CREATE_SUSPENDED, если требуется инициализировать все данные элементов `CWinThread` объекта, такие как [m_bAutoDelete](#m_bautodelete) , или любые члены производного класса перед запуском потока. После завершения инициализации используйте параметр [CWinThread:: ресумесреад](#resumethread) , чтобы запустить поток. Поток не будет выполняться до `CWinThread::ResumeThread` вызова метода.

- **0** . Запустите поток сразу после создания.

*нстакксизе*<br/>
Задает размер стека в байтах для нового потока. Если значение **равно 0**, размер стека по умолчанию совпадает с размером основного потока процесса.

*лпсекуритяттрс*<br/>
Указывает на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) , указывающую атрибуты безопасности для потока.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если поток успешно создан; в противном случае — 0.

### <a name="remarks"></a>Примечания

Используйте `AfxBeginThread` , чтобы создать объект потока и выполнить его за один шаг. Используйте `CreateThread` , если необходимо повторно использовать объект потока между последовательным созданием и завершением выполнения потоков.

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread:: CWinThread

Формирует объект `CWinThread`.

```
CWinThread();
```

### <a name="remarks"></a>Примечания

Чтобы начать выполнение потока, вызовите функцию члена функции [CreateThread](#createthread) . Обычно потоки создаются путем вызова [афксбегинсреад](application-information-and-management.md#afxbeginthread), который будет вызывать этот конструктор и `CreateThread` .

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread:: ExitInstance

Вызвано структурой из редко переопределенной функции-члена [запуска](#run) для выхода из этого экземпляра потока или при сбое вызова [InitInstance](#initinstance) .

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Код выхода потока; 0 означает отсутствие ошибок, а значения больше 0 указывают на ошибку. Это значение можно получить путем вызова [жетекситкодесреад](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию члена из любого места, но внутри `Run` функции члена. Эта функция-член используется только в потоках пользовательского интерфейса.

Реализация по умолчанию этой функции удаляет `CWinThread` объект, если [m_bAutoDelete](#m_bautodelete) имеет значение true. Переопределите эту функцию, если вы хотите выполнить дополнительную очистку после завершения потока. Ваша реализация `ExitInstance` должна вызывать версию базового класса после выполнения кода.

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread:: Жетмаинвнд

Если приложение является сервером OLE, вызовите эту функцию, чтобы получить указатель на активное главное окно приложения, а не напрямую ссылаться на `m_pMainWnd` член объекта приложения.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает указатель на один из двух типов окон. Если ваш поток является частью OLE-сервера и имеет объект, который находится в активном контейнере на месте, эта функция возвращает элемент данных [CWinApp:: m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) `CWinThread` .

Если в контейнере нет объекта, который находится в активном месте или приложение не является сервером OLE, эта функция возвращает элемент данных [m_pMainWnd](#m_pmainwnd) объекта потока.

### <a name="remarks"></a>Примечания

Для потоков пользовательского интерфейса это эквивалентно непосредственной ссылке на `m_pActiveWnd` член объекта приложения.

Если приложение не является сервером OLE, то вызов этой функции эквивалентен непосредственному обращению к `m_pMainWnd` члену объекта приложения.

Переопределите эту функцию, чтобы изменить поведение по умолчанию.

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread:: Жетсреадприорити

Возвращает текущий уровень приоритета потока данного потока.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий уровень приоритета потока в его классе приоритета. Возвращаемое значение будет одним из следующих: от наивысшего приоритета к наименьшему.

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Дополнительные сведения об этих приоритетах см. в разделе [сетсреадприорити](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в Windows SDK.

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread:: InitInstance

`InitInstance`должен быть переопределен для инициализации каждого нового экземпляра потока пользовательского интерфейса.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Как правило, переопределяется `InitInstance` для выполнения задач, которые должны быть выполнены при первом создании потока.

Эта функция-член используется только в потоках пользовательского интерфейса. Выполните инициализацию рабочих потоков в функции управления, передаваемой в [афксбегинсреад](application-information-and-management.md#afxbeginthread).

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread:: Исидлемессаже

Переопределите эту функцию, чтобы предотвратить `OnIdle` ее вызов после создания определенных сообщений.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
Указывает на текущее обрабатываемое сообщение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое `OnIdle` значение, если должно вызываться после обработки сообщения; в противном случае — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не вызывается `OnIdle` после избыточных сообщений мыши и сообщений, созданных мигающими крышки.

Если приложение создало короткий таймер, `OnIdle` будет вызываться часто, что приведет к проблемам с производительностью. Чтобы повысить производительность такого приложения, переопределите `IsIdleMessage` в классе, производном от приложения, `CWinApp` проверку на WM_TIMER сообщения следующим образом:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Обработка WM_TIMER таким образом повысит производительность приложений, использующих короткие таймеры.

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a>CWinThread:: m_bAutoDelete

Указывает, `CWinThread` должен ли объект автоматически удаляться при завершении потока.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Примечания

`m_bAutoDelete`Элемент данных является открытой переменной типа bool.

Значение `m_bAutoDelete` не влияет на то, как закрывается базовый обработчик потока, но он влияет на время закрытия маркера. Маркер потока всегда закрывается при `CWinThread` уничтожении объекта.

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a>CWinThread:: m_hThread

Обработчик для потока, присоединенного к этому потоку `CWinThread` .

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Примечания

`m_hThread`Элемент данных является открытой переменной типа Handle. Он допустим только в том случае, если базовый объект потока ядра существует, и этот обработчик еще не закрыт.

Деструктор CWinThread вызывает функцию CloseHandle в `m_hThread` . Если [m_bAutoDelete](#m_bautodelete) имеет значение true при завершении потока, объект CWinThread уничтожается, что делает недействительными все указатели на объект CWinThread и его переменные-члены. Может потребоваться, `m_hThread` чтобы элемент мог проверить значение выхода потока или дождаться сигнала. Чтобы объект CWinThread и его член оставался в `m_hThread` процессе выполнения потока и после его завершения, установите значение `m_bAutoDelete` false, прежде чем разрешить продолжение выполнения потока. В противном случае поток может завершиться, уничтожить объект CWinThread и закрыть этот обработчик, прежде чем пытаться его использовать. При использовании этого метода вы несете ответственность за удаление объекта CWinThread.

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a>CWinThread:: m_nThreadID

Идентификатор потока, присоединенного к этому объекту `CWinThread` .

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Примечания

`m_nThreadID`Элемент данных является открытой переменной типа DWORD. Он допустим только в том случае, если уже существует базовый объект потока ядра.
См. также замечания о времени жизни [m_hThread](#m_hthread) .

### <a name="example"></a>Пример

  См. пример для [афксжетсреад](application-information-and-management.md#afxgetthread).

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinThread:: m_pActiveWnd

Используйте этот элемент данных для хранения указателя на объект активного окна потока.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Примечания

Библиотека Microsoft Foundation Class будет автоматически завершать ваш поток, когда окно, на которое ссылается, будет `m_pActiveWnd` закрыто. Если этот поток является основным потоком для приложения, приложение также будет завершено. Если этот элемент данных имеет значение NULL, активное окно для `CWinApp` объекта приложения будет унаследовано. `m_pActiveWnd`— Это открытая переменная типа `CWnd*` .

Как правило, эта переменная члена задается при переопределении `InitInstance` . В рабочем потоке значение этого члена данных наследуется от родительского потока.

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a>CWinThread:: m_pMainWnd

Используйте этот элемент данных для хранения указателя на объект главного окна потока.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Примечания

Библиотека Microsoft Foundation Class будет автоматически завершать ваш поток, когда окно, на которое ссылается, будет `m_pMainWnd` закрыто. Если этот поток является основным потоком для приложения, приложение также будет завершено. Если этот элемент данных имеет значение NULL, то для `CWinApp` определения момента завершения потока будет использоваться главное окно для объекта приложения. `m_pMainWnd`— Это открытая переменная типа `CWnd*` .

Как правило, эта переменная члена задается при переопределении `InitInstance` . В рабочем потоке значение этого члена данных наследуется от родительского потока.

## <a name="cwinthreadonidle"></a><a name="onidle"></a>CWinThread:: OnIdle

Переопределите эту функцию-член для выполнения обработки во время простоя.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Счетчик, увеличивающийся каждый раз, `OnIdle` вызывается, когда очередь сообщений потока пуста. Этот счетчик сбрасывается в 0 каждый раз при обработке нового сообщения. С помощью параметра *lCount* можно определить относительный срок простоя потока без обработки сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение для получения более длительного времени обработки; 0, если не требуется больше времени на простое время обработки.

### <a name="remarks"></a>Примечания

`OnIdle`вызывается в цикле сообщений по умолчанию, если очередь сообщений потока пуста. Используйте переопределение для вызова собственных задач обработчика бездействия в фоновом режиме.

`OnIdle`должен возвращать значение 0, чтобы указать, что дополнительное время простоя не требуется. Параметр *lCount* увеличивается каждый раз, `OnIdle` когда очередь сообщений пуста и сбрасывается в 0 каждый раз при обработке нового сообщения. В зависимости от этого числа можно вызывать различные подпрограммы бездействия.

Реализация по умолчанию этой функции члена освобождает временные объекты и неиспользуемые библиотеки динамической компоновки из памяти.

Эта функция-член используется только в потоках пользовательского интерфейса.

Так как приложение не может обрабатывать сообщения до тех пор, пока не будет `OnIdle` возвращено, не выполняйте длительные задачи в этой функции.

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a>ОБРАБОТЧИК CWinThread::operator

Получает маркер `CWinThread` объекта.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения маркер объекта потока; в противном случае значение NULL.

### <a name="remarks"></a>Примечания

Используйте этот маркер для прямого вызова интерфейсов API Windows.

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::P Остсреадмессаже

Вызывается для публикации определяемого пользователем сообщения в другой `CWinThread` объект.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор определяемого пользователем сообщения.

*wParam*<br/>
Первый параметр сообщения.

*lParam*<br/>
Второй параметр сообщения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Отправленное сообщение сопоставляется с соответствующим обработчиком сообщений ON_THREAD_MESSAGE макросом схемы сообщений.

> [!NOTE]
> При вызове [постсреадмессаже](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)сообщение помещается в очередь сообщений потока. Однако поскольку сообщения, размещенные таким способом, не связаны с окном, MFC не будет отправлять их в обработчики сообщений или команд. Чтобы справиться с этими сообщениями, переопределите `PreTranslateMessage()` функцию класса, производного от CWinApp, и обработайте сообщения вручную.

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::P Ретранслатемессаже

Переопределите эту функцию, чтобы отфильтровать сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
Указывает на [структуру MSG](/windows/win32/api/winuser/ns-winuser-msg) , содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение полностью обработано в `PreTranslateMessage` и не должно обрабатываться дальше. Нуль, если сообщение должно обрабатываться обычным образом.

### <a name="remarks"></a>Примечания

Эта функция-член используется только в потоках пользовательского интерфейса.

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::P Роцессмессажефилтер

Функция-ловушка платформы вызывает эту функцию-член для фильтрации и реагирования на определенные сообщения Windows.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*code*<br/>
Указывает код обработчика. Эта функция члена использует код, чтобы определить, как обрабатывать *лпмсг.*

*лпмсг*<br/>
Указатель на [структуру сообщения](/windows/win32/api/winuser/ns-winuser-msg)Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обрабатывается; в противном случае — 0.

### <a name="remarks"></a>Примечания

Функция-обработчик обрабатывает события перед их отправкой в обычную обработку сообщений приложения.

При переопределении этой дополнительной функции не забудьте вызвать версию базового класса, чтобы обеспечить обработку обработчика.

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::P Роцессвндпроцексцептион

Платформа вызывает эту функцию члена всякий раз, когда обработчик не перехватывает исключение, выдаваемое в одном из сообщений или обработчиков команд в потоке.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*e*<br/>
Указывает на необработанное исключение.

*пмсг*<br/>
Указывает на [структуру MSG](/windows/win32/api/winuser/ns-winuser-msg) , содержащую сведения о сообщении Windows, которое привело к созданию исключения платформой.

### <a name="return-value"></a>Возвращаемое значение

значение-1, если создается исключение WM_CREATE; в противном случае — 0.

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию члена напрямую.

Реализация по умолчанию этой функции члена обрабатывает только исключения, созданные из следующих сообщений:

|Команда|Действие|
|-------------|------------|
|WM_CREATE|Неудача.|
|WM_PAINT|Проверьте затронутое окно, тем самым предотвращая создание другого сообщения WM_PAINT.|

Переопределите эту функцию члена, чтобы обеспечить глобальную обработку исключений. Вызывайте базовую функциональность только в том случае, если требуется отобразить поведение по умолчанию.

Эта функция-член используется только в потоках, имеющих конвейер сообщений.

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::P Умпмессаже

Содержит цикл обработки сообщений потока.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Примечания

`PumpMessage`содержит цикл обработки сообщений потока. `PumpMessage`метод вызывается методом `CWinThread` для передачи сообщений потока. Можно вызвать метод `PumpMessage` напрямую, чтобы принудительно обрабатывать сообщения, или же можно переопределить, `PumpMessage` чтобы изменить поведение по умолчанию.

Вызов `PumpMessage` напрямую и переопределение его поведения по умолчанию рекомендуется только для опытных пользователей.

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread:: Ресумесреад

Вызывается для возобновления выполнения потока, который был приостановлен функцией-членом [суспендсреад](#suspendthread) , или потока, созданного с помощью флага CREATE_SUSPENDED.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Возвращаемое значение

При успешном выполнении предыдущего счетчика приостановки потока; `0xFFFFFFFF`в противном случае — значение. Если возвращаемое значение равно нулю, текущий поток не был приостановлен. Если возвращаемое значение равно единице, то поток был приостановлен, но теперь перезапущен. Любое возвращаемое значение больше единицы означает, что поток остается приостановленным.

### <a name="remarks"></a>Примечания

Число приостановок текущего потока уменьшается на единицу. Если счетчик приостановок сокращается до нуля, поток возобновляет выполнение. в противном случае поток остается приостановленным.

## <a name="cwinthreadrun"></a><a name="run"></a>CWinThread:: Run

Предоставляет цикл сообщений по умолчанию для потоков пользовательского интерфейса.

```
virtual int Run();
```

### <a name="return-value"></a>Возвращаемое значение

**`int`** Значение, возвращаемое потоком. Это значение можно получить путем вызова [жетекситкодесреад](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Примечания

`Run`получение и отправка сообщений Windows до тех пор, пока приложение не получит [WM_QUIT](/windows/win32/winmsg/wm-quit) сообщение. Если очередь сообщений потока в настоящий момент не содержит сообщений, `Run` вызовы `OnIdle` осуществляют обработку времени простоя. Входящие сообщения переходят в функцию члена [претранслатемессаже](#pretranslatemessage) для специальной обработки, а затем в функцию Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) для стандартного перевода с клавиатуры. Наконец, вызывается функция Windows [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) .

`Run`нередко переопределяется, но его можно переопределить для реализации специального поведения.

Эта функция-член используется только в потоках пользовательского интерфейса.

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread:: Сетсреадприорити

Эта функция задает уровень приоритета текущего потока в пределах его класса приоритета.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Параметры

*нприорити*<br/>
Указывает новый уровень приоритета потока в пределах его класса приоритета. Этот параметр должен иметь одно из следующих значений, перечисленных от наивысшего приоритета к наименьшему:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Дополнительные сведения об этих приоритетах см. в разделе [сетсреадприорити](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Его можно вызвать только после того, как функция [CreateThread](#createthread) успешно возвращает значение.

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread:: Суспендсреад

Увеличивает значение счетчика приостановки текущего потока.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Возвращаемое значение

При успешном выполнении предыдущего счетчика приостановки потока; `0xFFFFFFFF`в противном случае — значение.

### <a name="remarks"></a>Примечания

Если число приостановок в каком-либо потоке превышает ноль, этот поток не выполняется. Поток можно возобновить, вызвав функцию члена [ресумесреад](#resumethread) .

## <a name="see-also"></a>См. также раздел

[Класс от CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)<br/>
[Класс от CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
