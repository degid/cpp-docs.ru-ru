---
title: Сведения о приложении и управление им
description: Ссылка на сведения о приложениях и функциях управления библиотеки Microsoft Foundation Class Library (MFC).
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 3412ed3f02e93d3e8c947d4f730355c219493a77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832311"
---
# <a name="application-information-and-management"></a>Сведения о приложении и управление им

При написании приложения создается один объект, производный от [CWinApp](../../mfc/reference/cwinapp-class.md). Иногда может потребоваться получить сведения об этом объекте извне `CWinApp` объекта, производного от. Также может потребоваться доступ к другим глобальным объектам "Manager".

Библиотека Microsoft Foundation Class предоставляет следующие глобальные функции, помогающие выполнить эти задачи:

## <a name="application-information-and-management-functions"></a>Сведения о приложении и функции управления

| Имя | Описание |
|-|-|
|[AfxBeginThread](#afxbeginthread)|Создает новый поток.|
|[афксконтекстменуманажер](#afxcontextmenumanager)|Указатель на глобальный [Диспетчер контекстных меню](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Завершает текущий поток.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Просматривает цепочку ресурсов и находит конкретный ресурс по ИДЕНТИФИКАТОРу ресурса и типу ресурса. |
|[AfxFreeLibrary](#afxfreelibrary)|Уменьшает число ссылок загруженного модуля библиотеки динамической компоновки (DLL). Когда счетчик ссылок достигнет нуля, модуль не будет сопоставлен.|
|[AfxGetApp](#afxgetapp)|Возвращает указатель на единичный `CWinApp` объект приложения.|
|[AfxGetAppName](#afxgetappname)|Возвращает строку, содержащую имя приложения.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Возвращает значение HINSTANCE, представляющее данный экземпляр приложения.|
|[AfxGetMainWnd](#afxgetmainwnd)|Возвращает указатель на текущее окно "Main" приложения, не являющегося приложением OLE, или в окне фрейма на месте серверного приложения.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Используйте эту функцию, чтобы определить, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Возвращает значение HINSTANCE для источника ресурсов приложения по умолчанию. Используйте для прямого доступа к ресурсам приложения.|
|[AfxGetThread](#afxgetthread)|Извлекает указатель на текущий объект [CWinThread](../../mfc/reference/cwinthread-class.md) .|
|[AfxInitRichEdit](#afxinitrichedit)|Инициализирует элемент управления Rich Edit для приложения версии 1,0.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Инициализирует для приложения элемент управления редактирования с расширенными возможностями версии 2,0 и более поздних версий.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Определяет, является ли заданное окно расширенным объектом фрейма.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Определяет, является ли заданное окно объектом панели инструментов.|
|[афкскэйбоардманажер](#afxkeyboardmanager)|Указатель на глобальный [Диспетчер клавиатуры](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Сопоставляет модуль DLL и возвращает маркер, который можно использовать для получения адреса функции DLL.|
|[афкслоадлибрарекс](#afxloadlibraryex)|Сопоставляет модуль DLL с указанными параметрами и возвращает маркер, который можно использовать для получения адреса функции DLL.|
|[афксменутеароффманажер](#afxmenutearoffmanager)|Указатель на глобальный [Диспетчер меню](cmenutearoffmanager-class.md).|
|[афксмаусеманажер](#afxmousemanager)|Указатель на глобальный [диспетчер мыши](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|Регистрирует класс окна в библиотеке DLL, использующей MFC.|
|[AfxRegisterWndClass](#afxregisterwndclass)|Регистрирует класс окна Windows, чтобы дополнять объекты, автоматически регистрируемые MFC.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Определяет, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Задает обработчик HINSTANCE, в котором загружаются ресурсы по умолчанию приложения.|
|[афксшеллманажер](#afxshellmanager)|Указатель на глобальный [Диспетчер оболочки](cshellmanager-class.md). |
|[AfxSocketInit](#afxsocketinit)|Вызывается в `CWinApp::InitInstance` переопределении для инициализации сокетов Windows.|
|[афксусертулсманажер](#afxusertoolsmanager)|Указатель на диспетчер глобальных [пользовательских инструментов](cusertoolsmanager-class.md).|
|[AfxWinInit](#afxwininit)|Вызывается предоставляемой MFC `WinMain` функцией в рамках инициализации [CWinApp](../../mfc/reference/cwinapp-class.md) приложения на основе графического пользовательского интерфейса для инициализации MFC. Должен вызываться напрямую для консольных приложений, использующих MFC.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a> афксбегинсреад

Вызовите эту функцию, чтобы создать новый поток.

```cpp
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Параметры

*пфнсреадпрок*\
Указывает на функцию управления для рабочего потока. Указатель не может иметь значение NULL. Эта функция должна быть объявлена следующим образом:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*псреадкласс*\
RUNTIME_CLASS объекта, производного от [CWinThread](../../mfc/reference/cwinthread-class.md).

*ппарам*\
Параметр, передаваемый функции управления.

*нприорити*\
Приоритет, заданный для потока. Полный список и описание доступных приоритетов см. в разделе [сетсреадприорити](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в Windows SDK.

*нстакксизе*\
Задает размер стека в байтах для нового потока. Если значение равно 0, то размер стека по умолчанию совпадает с размером стека создания потока.

*двкреатефлагс*\
Задает дополнительный флаг, управляющий созданием потока. Этот флаг может содержать одно из двух значений:

- CREATE_SUSPENDED запустить поток с числом приостановки, равным одному. Используйте CREATE_SUSPENDED, если требуется инициализировать все данные элементов `CWinThread` объекта, такие как [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) , или любые члены производного класса перед запуском потока. После завершения инициализации используйте команду [CWinThread:: ресумесреад](../../mfc/reference/cwinthread-class.md#resumethread) , чтобы запустить поток. Поток не будет выполняться до `CWinThread::ResumeThread` вызова метода.

- **0** . Запустите поток сразу после создания.

*лпсекуритяттрс*\
Указывает на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) , указывающую атрибуты безопасности для потока. Если значение равно NULL, используются те же атрибуты безопасности, что и при создании потока. Дополнительные сведения об этой структуре см. в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный объект потока или значение NULL, если происходит сбой.

### <a name="remarks"></a>Примечания

Первая форма `AfxBeginThread` создает рабочий поток. Вторая форма создает поток, который может выступать в качестве потока пользовательского интерфейса или рабочего потока.

`AfxBeginThread` создает новый `CWinThread` объект, вызывает его функцию [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) , чтобы начать исполнение потока, и возвращает указатель на поток. Проверки выполняются на протяжении всей процедуры, чтобы убедиться, что все объекты освобождены должным образом, в случае сбоя любой части создания. Чтобы завершить поток, вызовите [афксендсреад](#afxendthread) из потока или вернитесь из управляющей функции рабочего потока.

Многопоточность должна быть включена приложением; в противном случае эта функция завершится ошибкой. Дополнительные сведения о включении многопоточности см. в разделе [/MD,/MT,/LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md).

Дополнительные сведения о см. `AfxBeginThread` в статьях [многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Пример

См. пример для [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a> афксконтекстменуманажер

Указатель на глобальный [Диспетчер контекстных меню](ccontextmenumanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афксконтекстменуманажер.h

## <a name="afxendthread"></a><a name="afxendthread"></a> афксендсреад

Вызовите эту функцию, чтобы завершить выполняющийся в данный момент поток.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Параметры

*некситкоде*\
Указывает код выхода потока.

*бделете*\
Удаляет объект потока из памяти.

### <a name="remarks"></a>Примечания

Должен вызываться из потока для завершения.

Дополнительные сведения о см `AfxEndThread` . в статье [многопоточность. прерывание потоков](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a> афксфиндресаурцехандле

Используйте `AfxFindResourceHandle` для прохода по цепочке ресурсов и нахождение определенного ресурса по идентификатору ресурса и типу ресурса.

### <a name="syntax"></a>Синтаксис

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Параметры

*лпсзнаме*\
Указатель на строку, содержащую идентификатор ресурса.
*лпсзтипе*\
Указатель на тип ресурса. Список типов ресурсов см. в разделе [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Обработчик для модуля, содержащего ресурс.

### <a name="remarks"></a>Примечания

`AfxFindResourceHandle` находит конкретный ресурс и возвращает маркер модуля, содержащего ресурс. Ресурс может находиться в любой загружаемой библиотеке DLL расширения MFC. `AfxFindResourceHandle` Указывает, какой из них имеет ресурс.

Поиск модулей выполняется в следующем порядке:

1. Главный модуль, если это библиотека DLL расширения MFC.

1. Несистемные модули.

1. Модули, зависящие от языка.

1. Основной модуль, если это системная библиотека DLL.

1. Системные модули.

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a> AfxFreeLibrary

`AfxFreeLibrary`И `AfxLoadLibrary` поддерживают счетчик ссылок для каждого загруженного модуля библиотеки.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Параметры

*хинстлиб*\
Маркер загруженного модуля библиотеки. [Афкслоадлибрари](#afxloadlibrary) возвращает этот маркер.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если функция выполнена. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`AfxFreeLibrary` уменьшает число ссылок загруженного модуля библиотеки динамической компоновки (DLL). Когда счетчик ссылок достигает нуля, модуль не сопоставляется с адресным пространством вызывающего процесса, и этот маркер становится недействительным. Этот счетчик ссылок увеличивается каждый раз, когда `AfxLoadLibrary` вызывается.

Перед удалением сопоставления модуля библиотеки система позволяет библиотеке DLL отсоединяться от процессов, использующих ее. Это дает библиотеке DLL возможность очищать ресурсы, выделенные для текущего процесса. После возврата функции точки входа модуль библиотеки удаляется из адресного пространства текущего процесса.

Используйте `AfxLoadLibrary` для отображения модуля DLL.

Обязательно используйте `AfxFreeLibrary` и `AfxLoadLibrary` (вместо функций Win32 `FreeLibrary` и `LoadLibrary` ), если приложение использует несколько потоков. Использование `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, выполняемый при загрузке и ВЫГРУЗКЕ библиотеки DLL расширения MFC, не повреждает глобальное состояние MFC.

### <a name="example"></a>Пример

См. пример для [афкслоадлибрари](#afxloadlibrary).

### <a name="requirements"></a>Требования

  **Заголовок** AFXDLL_.h

## <a name="afxgetapp"></a><a name="afxgetapp"></a> афксжетапп

Указатель, возвращаемый этой функцией, может использоваться для доступа к сведениям о приложении, таким как основной код диспетчеризации сообщений или самое верхнее окно.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на один `CWinApp` объект для приложения.

### <a name="remarks"></a>Примечания

Если этот метод возвращает значение NULL, это может означать, что главное окно приложения еще не полностью инициализировано. Это также может указывать на проблему.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a> афксжетаппнаме

Возвращаемая строка может использоваться для диагностических сообщений или в качестве корня для имен временных строк.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, заканчивающаяся нулем и содержащая имя приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a> афксжетинстанцехандле

Эта функция позволяет получить экземпляр обработчика текущего приложения.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

Значение HINSTANCE для текущего экземпляра приложения. Если вызывается из библиотеки DLL, связанной с УСРДЛЛ версией MFC, возвращается значение HINSTANCE для библиотеки DLL.

### <a name="remarks"></a>Примечания

`AfxGetInstanceHandle` всегда возвращает значение HINSTANCE для исполняемого файла (. EXE), если только он не вызывается из библиотеки DLL, связанной с УСРДЛЛ версией MFC. В этом случае он возвращает значение HINSTANCE для библиотеки DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a> афксжетмаинвнд

Если приложение является сервером OLE, вызовите эту функцию, чтобы получить указатель на активное главное окно приложения. Используйте этот результат вместо непосредственного обращения к элементу [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) объекта приложения.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на объект окна фрейма, содержащий активный документ на месте, если сервер содержит объект, который находится на месте в активном контейнере.

Если в контейнере отсутствует объект, активный в месте, или ваше приложение не является сервером OLE, эта функция возвращает *m_pMainWnd* объекта приложения.

Если `AfxGetMainWnd` вызывается из основного потока приложения, он возвращает главное окно приложения согласно приведенным выше правилам. Если функция вызывается из вторичного потока в приложении, функция возвращает главное окно, связанное с потоком, который выполнил вызов.

### <a name="remarks"></a>Примечания

Если приложение не является сервером OLE, то вызов этой функции эквивалентен непосредственной ссылке на *m_pMainWnd* элемент объекта приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a> афксжетперусеррегистратион

Используйте эту функцию, чтобы определить, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что данные реестра направляются на узел HKCU. Значение FALSE указывает, что приложение записывает сведения о реестре в узел по умолчанию. Узел по умолчанию — **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="remarks"></a>Примечания

Если включить перенаправление реестра, платформа перенаправит доступ из **HKCR** в **HKEY_CURRENT_USER \софтваре\классес**. Перенаправление затрагивает только платформы MFC и ATL.

Чтобы изменить, будет ли приложение перенаправлено на доступ к реестру, используйте [афкссетперусеррегистратион](#afxsetperuserregistration).

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a> афксжетресаурцехандле

Используйте маркер HINSTANCE, возвращенный этой функцией, для доступа к ресурсам приложения напрямую, например, в вызовах функции Windows `FindResource` .

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик HINSTANCE, в котором загружаются ресурсы по умолчанию приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a> афксжетсреад

Вызовите эту функцию, чтобы получить указатель на объект [CWinThread](../../mfc/reference/cwinthread-class.md) , представляющий выполняющийся в данный момент поток.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на выполняющийся в данный момент поток; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Должен вызываться из потока.

> [!NOTE]
> При переносе проекта MFC, вызывающего `AfxGetThread` из Visual C++ версий 4,2, 5,0 или 6,0, `AfxGetThread` вызывает [афксжетапп](#afxgetapp) , если поток не найден. В более поздних версиях компилятора `AfxGetThread` возвращает значение null, если поток не найден. Если требуется поток приложения, необходимо вызвать `AfxGetApp` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a> афксинитричедит

Вызовите эту функцию, чтобы инициализировать элемент управления Rich Edit (версия 1,0) для приложения.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Примечания

Эта функция предоставляется для обеспечения обратной совместимости. Новые приложения должны использовать [требуется метод afxinitrichedit2](#afxinitrichedit2).

`AfxInitRichEdit` загружает RICHED32.DLL для инициализации элемента управления расширенного редактирования версии 1,0. Для использования элемента управления Rich Edit (версия 2,0 и 3,0) необходимо загрузить RICHED20.DLL. Он загружается путем выполнения вызова [требуется метод afxinitrichedit2](#afxinitrichedit2).

Чтобы обновить элементы управления Rich Edit в существующих Visual C++ приложениях до версии 2,0, откройте. RC-файла в виде текста измените имя класса для каждого элемента управления Rich Edit с "RICHEDIT" на "RichEdit20a". Затем замените вызов на `AfxInitRichEdit` `AfxInitRichEdit2` .

Эта функция также инициализирует библиотеку Common Controls, если библиотека еще не была инициализирована для процесса. Если вы используете элемент управления Rich Edit непосредственно из приложения MFC, вызовите эту функцию, чтобы убедиться в том, что MFC правильно Инициализирует среду выполнения элемента управления Rich Edit. При вызове `Create` метода [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)обычно не требуется вызывать эту функцию, но в некоторых случаях это может потребоваться.

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a> Требуется метод afxinitrichedit2

Вызывайте эту функцию для инициализации элемента управления Rich Edit (версии 2,0 и более поздней) для приложения.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы загрузить RICHED20.DLL и инициализировать версию 2,0 элемента управления Rich Edit. При вызове `Create` метода [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)обычно не требуется вызывать эту функцию, но в некоторых случаях это может потребоваться.

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a> афксисекстендедфрамекласс

Определяет, является ли заданное окно расширенным объектом фрейма.

### <a name="syntax"></a>Синтаксис

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Параметры

*Приводится*\
окне Указатель на объект, производный от `CWnd` .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если предоставленное окно является расширенным объектом Frame; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если *приводится* является производным от одного из следующих классов:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Этот метод полезен, когда требуется проверить, что параметр функции или метода является окном расширенного фрейма.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a> афксисмфктулбар

Определяет, является ли заданное окно объектом панели инструментов.

### <a name="syntax"></a>Синтаксис

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*\
окне Указатель на объект, производный от `CWnd` .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если предоставленное окно является объектом панели инструментов; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение `TRUE` , если *приводится* является производным от `CMFCToolBar` . Этот метод полезен при проверке того, что параметр функции или метода является `CMFCToolBar` объектом.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a> афкскэйбоардманажер

Указатель на глобальный [Диспетчер клавиатуры](ckeyboardmanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афкскэйбоардманажер.h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a> афкслоадлибрари

Используйте `AfxLoadLibrary` для отображения модуля DLL.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Параметры

*лпсзмодуленаме*\
Указывает на строку, завершающуюся нулем, которая содержит имя модуля (или. DLL или. EXE-файл). Указанное имя является именем файла модуля.

Если строка указывает путь, но файл не существует в указанном каталоге, функция завершается ошибкой.

Если путь не указан и расширение имени файла пропущено, используется расширение по умолчанию. DLL добавляется. Однако строка filename может содержать символ завершающей точки (.), указывающий, что имя модуля не имеет расширения. Если путь не указан, функция использует [Порядок поиска для классических приложений](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications).

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение является обработчиком модуля. При сбое возвращаемое значение равно NULL.

### <a name="remarks"></a>Примечания

Он возвращает маркер, который можно использовать в [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) для получения адреса функции DLL. `AfxLoadLibrary` также может использоваться для отображения других исполняемых модулей.

Каждый процесс поддерживает счетчик ссылок для каждого загруженного модуля библиотеки. Этот счетчик ссылок увеличивается каждый раз, когда вызывается `AfxLoadLibrary` и уменьшается каждый раз `AfxFreeLibrary` . Когда счетчик ссылок достигает нуля, модуль не сопоставляется с адресным пространством вызывающего процесса, и этот маркер становится недействительным.

Обязательно используйте `AfxLoadLibrary` и `AfxFreeLibrary` (вместо функций Win32 `LoadLibrary` и `FreeLibrary` ), если приложение использует несколько потоков, и если оно динамически загружает библиотеку DLL расширения MFC. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантируется, что код запуска и завершения работы, выполняемый при загрузке и ВЫГРУЗКЕ библиотеки DLL расширения MFC, не повреждает глобальное состояние MFC.

Для использования `AfxLoadLibrary` в приложении необходимо динамически связываться с DLL-версией MFC. Файл заголовка для `AfxLoadLibrary` , Afxdll_.h, включается, только если MFC связан с приложением в качестве библиотеки DLL. Это требование обусловлено проектированием, поскольку для использования или создания библиотек DLL расширения MFC необходимо создать ссылку на библиотеку DLL MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXDLL_.h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a> афкслоадлибрарекс

Используйте `AfxLoadLibraryEx` для отображения модуля DLL.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*\
Указывает на строку, завершающуюся нулем, которая содержит имя модуля (или. DLL или. EXE-файл). Указанное имя является именем файла модуля.

Если строка указывает путь, но файл не существует в указанном каталоге, функция завершается ошибкой.

Если путь не указан и расширение имени файла пропущено, используется расширение по умолчанию. DLL добавляется. Однако строка filename может содержать символ завершающей точки (.), указывающий, что имя модуля не имеет расширения. Если путь не указан, функция использует [Порядок поиска для классических приложений](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications).

*hFile*\
Этот параметр зарезервирован для использования в будущем. Оно должно быть равно NULL.

*dwFlags*\
Действие, предпринимаемое при загрузке модуля. Если флаги не указаны, поведение этой функции идентично `AfxLoadLibrary` функции. Возможные значения этого параметра описаны в документации по [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) .

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение является обработчиком модуля. При сбое возвращаемое значение равно NULL.

### <a name="remarks"></a>Примечания

`AfxLoadLibraryEx` Возвращает маркер, который можно использовать в [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) для получения адреса функции DLL. `AfxLoadLibraryEx` также может использоваться для отображения других исполняемых модулей.

Каждый процесс поддерживает счетчик ссылок для каждого загруженного модуля библиотеки. Этот счетчик ссылок увеличивается каждый раз, когда вызывается `AfxLoadLibraryEx` и уменьшается каждый раз `AfxFreeLibrary` . Когда счетчик ссылок достигает нуля, модуль не сопоставляется с адресным пространством вызывающего процесса, и этот маркер становится недействительным.

Обязательно используйте `AfxLoadLibraryEx` и `AfxFreeLibrary` (вместо функций Win32 `LoadLibraryEx` и `FreeLibrary` ), если приложение использует несколько потоков и динамически загружает библиотеку DLL расширения MFC. Использование `AfxLoadLibraryEx` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, выполняемый при загрузке и ВЫГРУЗКЕ библиотеки DLL расширения MFC, не повреждает глобальное состояние MFC.

Для использования `AfxLoadLibraryEx` в приложении необходимо динамически связываться с DLL-версией MFC. Файл заголовка для `AfxLoadLibraryEx` , Afxdll_.h, включается, только если MFC связан с приложением в качестве библиотеки DLL. Это требование обусловлено проектированием, поскольку для использования или создания библиотек DLL расширения MFC необходимо создать ссылку на библиотеку DLL MFC.

### <a name="requirements"></a>Требования

  **Заголовок** AFXDLL_.h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a> афксменутеароффманажер

Указатель на глобальный [Диспетчер меню](cmenutearoffmanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афксменутеароффманажер.h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a> афксмаусеманажер

Указатель на глобальный [диспетчер мыши](cmousemanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афксмаусеманажер.h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a> афксрегистеркласс

Эта функция используется для регистрации классов окон в библиотеке DLL, использующей MFC.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Параметры

*лпвндкласс*\
Указатель на структуру [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw) , содержащую сведения о классе окна для регистрации. Дополнительные сведения об этой структуре см. в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если класс успешно зарегистрирован; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

При использовании этой функции класс автоматически отменяет регистрацию при выгрузке библиотеки DLL.

В сборках, отличных от DLL, `AfxRegisterClass` идентификатор определяется как макрос, сопоставляемый с функцией Windows `RegisterClass` , так как классы, зарегистрированные в приложении, автоматически не регистрируются. Если вы используете `AfxRegisterClass` вместо `RegisterClass` , код можно использовать без изменения как в приложении, так и в библиотеке DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a> афксрегистервндкласс

Позволяет регистрировать собственные классы окон.

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Параметры

*нклассстиле*\
Задает стиль класса Windows или сочетание стилей, созданных с помощью оператора побитового или (**&#124;**) для класса Window. Список стилей классов см. в разделе Структура [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw) в Windows SDK. Если значение равно NULL, значения по умолчанию задаются следующим образом:

- Задает для стиля мыши CS_DBLCLKS, который отправляет сообщения двойного щелчка в процедуру окна, когда пользователь дважды щелкает мышью.

- Задает стиль курсора со стрелкой для стандартного IDC_ARROW Windows.

- Устанавливает значение NULL для фоновой кисти, поэтому окно не удаляет его фон.

- Задает значок стандартного машет-флага эмблемы Windows.

*хкурсор*\
Задает обработчик для ресурса курсора, который должен быть установлен в каждом окне, созданном из класса Window. Если вы используете значение по умолчанию **0**, вы получите стандартный IDC_ARROW курсор.

*хбрбаккграунд*\
Задает дескриптор ресурса кисти, который должен быть установлен в каждом окне, созданном из класса Window. Если вы используете значение по умолчанию **0**, то у вас будет пустая кисть фона, и по умолчанию окно не будет очищать свой фон при обработке [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd).

*хикон*\
Задает маркер для ресурса значка, который должен быть установлен в каждом окне, созданном из класса Window. Если вы используете значение по умолчанию **0**, вы получите стандартный значок логотипа Windows машет-Flag.

### <a name="return-value"></a>Возвращаемое значение

Строка, заканчивающаяся нулем и содержащая имя класса. Это имя класса можно передать `Create` функции-члену в `CWnd` или других классах, производных **от CWnd**, для создания окна. Имя создается библиотека Microsoft Foundation Class.

> [!NOTE]
> Возвращаемое значение является указателем на статический буфер. Чтобы сохранить эту строку, присвойте ее `CString` переменной.

### <a name="remarks"></a>Примечания

Библиотека Microsoft Foundation Class автоматически регистрирует несколько стандартных классов окон. Вызывайте эту функцию, если требуется зарегистрировать собственные классы окон.

Имя, зарегистрированное для класса, `AfxRegisterWndClass` зависит только от параметров. Если `AfxRegisterWndClass` несколько раз вызывается с одинаковыми параметрами, то он регистрируется только при первом вызове. Последующие вызовы `AfxRegisterWndClass` с с идентичными параметрами возвращают уже зарегистрированное значение ClassName.

При вызове `AfxRegisterWndClass` нескольких классов, производных от CWnd, с одинаковыми параметрами вместо того, чтобы получать отдельный класс окна для каждого класса, каждый класс использует один и тот же класс окна. Такой общий доступ может вызвать проблемы при использовании стиля класса CS_CLASSDC. Вместо нескольких классов окон CS_CLASSDC можно получить только один класс CS_CLASSDC окон. Все окна C++, использующие этот класс, используют один и тот же контроллер домена. Чтобы избежать этой проблемы, вызовите [афксрегистеркласс](#afxregisterclass) , чтобы зарегистрировать класс.

Дополнительные сведения о регистрации класса Window и функции см. в техническом примечании [TN001: регистрация класса окна](../../mfc/tn001-window-class-registration.md) `AfxRegisterWndClass` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a> афкссетперусеррегистратион

Определяет, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*бенабле*\
окне Значение TRUE указывает, что данные реестра направляются на узел HKCU. Значение FALSE указывает, что приложение записывает сведения о реестре в узел по умолчанию. Узел по умолчанию — **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="remarks"></a>Примечания

До Windows Vista приложения, которые обращаются к реестру, часто использовали узел **HKEY_CLASSES_ROOT** . Однако в Windows Vista или более поздних операционных системах необходимо запустить приложение в режиме с повышенными правами для записи в раздел HKCR.

Этот метод позволяет приложению выполнять чтение и запись в реестр без запуска в режиме с повышенными правами. Он работает путем перенаправления доступа к реестру из раздела HKCR в HKCU. Дополнительные сведения см. в разделе [Linker Property Pages](../../build/reference/linker-property-pages.md).

Если включить перенаправление реестра, платформа перенаправит доступ из HKCR в **HKEY_CURRENT_USER \софтваре\классес**. Перенаправление затрагивает только платформы MFC и ATL.

Реализация по умолчанию обращается к реестру в разделе HKCR.

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a> афкссетресаурцехандле

Эта функция используется для задания обработчика HINSTANCE, который определяет, где загружаются ресурсы по умолчанию приложения.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Параметры

*хинстресаурце*\
Обработчик экземпляра или модуля для. Файл EXE или DLL, из которого загружаются ресурсы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a> афксшеллманажер

Указатель на глобальный [Диспетчер оболочки](cshellmanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афксшеллманажер.h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a> афкссоккетинит

Вызовите эту функцию в `CWinApp::InitInstance` переопределении для инициализации сокетов Windows.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Параметры

*лпвсадата*\
Указатель на структуру [всадата](/windows/win32/api/winsock2/ns-winsock2-wsadata) . Если *лпвсадата* не равно null, адрес `WSADATA` структуры заполняется вызовом метода `WSAStartup` . Эта функция также гарантирует, что она `WSACleanup` будет вызываться перед завершением работы приложения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

При использовании сокетов MFC во вторичных потоках в статическом связанном приложении MFC необходимо вызвать `AfxSocketInit` в каждом потоке, использующем сокеты для инициализации библиотек сокетов. По умолчанию `AfxSocketInit` метод вызывается только в основном потоке.

### <a name="requirements"></a>Требования

  **Заголовок** афкссокк.h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a> афксусертулсманажер

Указатель на диспетчер глобальных [пользовательских инструментов](cusertoolsmanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** афксусертулсманажер.h

## <a name="afxwininit"></a><a name="afxwininit"></a> афксвининит

Эта функция вызывается предоставляемой MFC функцией в `WinMain` рамках инициализации [CWinApp](../../mfc/reference/cwinapp-class.md) приложения на основе графического пользовательского интерфейса для инициализации MFC.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Параметры

*hInstance*\
Маркер выполняющегося в данный момент модуля.

*хпревинстанце*\
Маркер предыдущего экземпляра приложения. Для приложения на основе Win32 этот параметр всегда имеет **значение NULL**.

*лпкмдлине*\
Указывает на строку, завершающуюся нулем, указывая командную строку для приложения.

*нкмдшов*\
Указывает, как будет отображаться главное окно приложения с графическим пользовательским интерфейсом.

### <a name="remarks"></a>Примечания

Для консольного приложения, которое не использует предоставляемую MFC `WinMain` функцию, необходимо напрямую вызвать метод `AfxWinInit` для инициализации MFC.

Если вы вызываете `AfxWinInit` себя самостоятельно, следует объявить экземпляр `CWinApp` класса. Для консольного приложения вы можете не создавать собственный класс из `CWinApp` и вместо этого использовать экземпляр `CWinApp` напрямую. Этот метод подходит, если вы решили оставить все функциональные возможности для своего приложения в реализации **Main**.

> [!NOTE]
> При создании контекста активации для сборки MFC использует ресурс манифеста, предоставленный модулем пользователя. Контекст активации создается в `AfxWinInit` . Дополнительные сведения см. [в разделе Поддержка контекстов активации в состоянии модуля MFC](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFXWIN.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные](mfc-macros-and-globals.md)\
[Класс CWinApp](cwinapp-class.md)\
[Класс Кконтекстменуманажер](ccontextmenumanager-class.md)\
[CWnd, класс](cwnd-class.md)\
[Класс CFrameWndEx](cframewndex-class.md)\
[Класс CMFCToolBar](cmfctoolbar-class.md)\
[Класс CKeyboardManager](ckeyboardmanager-class.md)\
[Класс Кменутеароффманажер](cmenutearoffmanager-class.md)\
[Класс Кмаусеманажер](cmousemanager-class.md)\
[Класс Кшеллманажер](cshellmanager-class.md)\
[Класс Кусертулсманажер](cusertoolsmanager-class.md)
