---
title: Класс CAtlExeModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: b678c8a46f56337d76ec192869449797a4f66fb3
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168801"
---
# <a name="catlexemodulet-class"></a>Класс CAtlExeModuleT

Этот класс представляет модуль для приложения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный `CAtlExeModuleT`от.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT:: CAtlExeModuleT](#catlexemodulet)|Конструктор.|
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT:: Инитиализеком](#initializecom)|Инициализирует COM.|
|[CAtlExeModuleT::P Арсекоммандлине](#parsecommandline)|Анализирует командную строку и при необходимости выполняет регистрацию.|
|[CAtlExeModuleT::P Остмессажелуп](#postmessageloop)|Этот метод вызывается сразу после завершения работы цикла сообщений.|
|[CAtlExeModuleT::P Ремессажелуп](#premessageloop)|Этот метод вызывается непосредственно перед входом в цикл обработки сообщений.|
|[CAtlExeModuleT:: Регистерклассобжектс](#registerclassobjects)|Регистрирует объект класса.|
|[CAtlExeModuleT:: Ревокеклассобжектс](#revokeclassobjects)|Отменяет объект класса.|
|[CAtlExeModuleT:: Run](#run)|Этот метод выполняет код в модуле EXE для инициализации, выполнения цикла обработки сообщений и очистки.|
|[CAtlExeModuleT:: Рунмессажелуп](#runmessageloop)|Этот метод выполняет цикл обработки сообщений.|
|[CAtlExeModuleT:: Унинитиализеком](#uninitializecom)|Отменяет инициализацию COM.|
|[CAtlExeModuleT:: Unlock](#unlock)|Уменьшает счетчик блокировок модуля.|
|[CAtlExeModuleT:: WinMain](#winmain)|Этот метод реализует код, необходимый для запуска EXE.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT:: m_bDelayShutdown](#m_bdelayshutdown)|Флаг, указывающий на задержку завершения работы модуля.|
|[CAtlExeModuleT:: m_dwPause](#m_dwpause)|Значение паузы, используемое для обеспечения освобождения всех объектов до завершения работы.|
|[CAtlExeModuleT:: m_dwTimeOut](#m_dwtimeout)|Значение времени ожидания, используемое для задержки выгрузки модуля.|

## <a name="remarks"></a>Примечания

`CAtlExeModuleT`представляет модуль для приложения (EXE) и содержит код, который поддерживает создание EXE-файла, обработку командной строки, регистрацию объектов класса, выполнение цикла обработки сообщений и очистку при выходе.

Этот класс предназначен для повышения производительности при постоянном создании и удалении COM-объектов на сервере EXE. После освобождения последнего объекта COM EXE-файл ожидает длительности, заданной элементом данных [CAtlExeModuleT:: m_dwTimeOut](#m_dwtimeout) . Если в течение этого периода действия не выполняются (то есть объекты COM не создаются), инициируется процесс завершения работы.

Элемент данных [CAtlExeModuleT:: m_bDelayShutdown](#m_bdelayshutdown) — это флаг, используемый для определения того, должен ли EXE-файл использовать механизм, определенный выше. Если задано значение false, модуль немедленно завершит работу.

Дополнительные сведения о модулях в ATL см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[катлмодуле](../../atl/reference/catlmodule-class.md)

[катлмодулет](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT:: CAtlExeModuleT

Конструктор.

```cpp
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Примечания

Если не удалось инициализировать модуль EXE, то WinMain немедленно вернется без дальнейшей обработки.

## <a name="catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT

Деструктор

```cpp
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="catlexemoduletinitializecom"></a><a name="initializecom"></a>CAtlExeModuleT:: Инитиализеком

Инициализирует COM.

```cpp
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод вызывается из конструктора и может быть переопределен для инициализации COM способом, отличным от реализации по умолчанию. Реализация по умолчанию либо `CoInitializeEx(NULL, COINIT_MULTITHREADED)` вызывает `CoInitialize(NULL)` , либо в зависимости от конфигурации проекта.

Для переопределения этого метода обычно требуется переопределение [CAtlExeModuleT:: унинитиализеком](#uninitializecom).

## <a name="catlexemoduletm_bdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT:: m_bDelayShutdown

Флаг, указывающий на задержку завершения работы модуля.

```cpp
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в [обзоре CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) .

## <a name="catlexemoduletm_dwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT:: m_dwPause

Значение паузы, используемое для проверки того, что все объекты исчезают перед завершением работы.

```cpp
DWORD m_dwPause;
```

### <a name="remarks"></a>Примечания

Измените это значение после вызова [CAtlExeModuleT:: инитиализеком](#initializecom) , чтобы задать количество миллисекунд, используемых в качестве значения приостановки для завершения работы сервера. Значение по умолчанию — 1000 миллисекунд.

## <a name="catlexemoduletm_dwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT:: m_dwTimeOut

Значение времени ожидания, используемое для задержки выгрузки модуля.

```cpp
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Примечания

Измените это значение после вызова [CAtlExeModuleT:: инитиализеком](#initializecom) , чтобы определить количество миллисекунд, использованных в качестве значения времени ожидания при завершении работы сервера. Значение по умолчанию — 5000 миллисекунд. Дополнительные сведения см. в [обзоре CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) .

## <a name="catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::P Арсекоммандлине

Анализирует командную строку и при необходимости выполняет регистрацию.

```cpp
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*лпкмдлине*<br/>
Командная строка, передаваемая приложению.

*пнреткоде*<br/>
Значение HRESULT, соответствующее регистрации (если оно было принято).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если приложение должно продолжать работу; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод вызывается из [CAtlExeModuleT:: WinMain](#winmain) и может быть переопределен для управления параметрами командной строки. Реализация по умолчанию проверяет аргументы командной строки **/regserver** и **/UnRegServer** и выполняет регистрацию или отмену регистрации.

## <a name="catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::P Остмессажелуп

Этот метод вызывается сразу после завершения работы цикла сообщений.

```cpp
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Переопределите этот метод для выполнения пользовательской очистки приложения. Реализация по умолчанию вызывает [CAtlExeModuleT:: ревокеклассобжектс](#revokeclassobjects).

## <a name="catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::P Ремессажелуп

Этот метод вызывается непосредственно перед входом в цикл обработки сообщений.

```cpp
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Значение, передаваемое в качестве параметра *ншовкмд* в WinMain.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы добавить пользовательский код инициализации для приложения. Реализация по умолчанию регистрирует объекты класса.

## <a name="catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT:: Регистерклассобжектс

Регистрирует объект класса в OLE, чтобы другие приложения могли подключаться к нему.

```cpp
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Параметры

*двклсконтекст*<br/>
Задает контекст, в котором будет выполняться объект класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER.

*dwFlags*<br/>
Определяет типы соединения с объектом класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении, S_FALSE, если отсутствуют классы для регистрации, или ошибку HRESULT при сбое.

## <a name="catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>CAtlExeModuleT:: Ревокеклассобжектс

Удаляет объект класса.

```cpp
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении, S_FALSE, если отсутствуют классы для регистрации, или ошибку HRESULT при сбое.

## <a name="catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT:: Run

Этот метод выполняет код в модуле EXE для инициализации, выполнения цикла обработки сообщений и очистки.

```cpp
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Указывает способ отображения окна. Этот параметр может принимать одно из значений, описанных в разделе [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) . Значение по умолчанию — SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод можно переопределить. Однако на практике лучше переопределить [CAtlExeModuleT::P ремессажелуп](#premessageloop), [CAtlExeModuleT:: рунмессажелуп](#runmessageloop)или [CAtlExeModuleT::P остмессажелуп](#postmessageloop) .

## <a name="catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT:: Рунмессажелуп

Этот метод выполняет цикл обработки сообщений.

```cpp
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Примечания

Этот метод можно переопределить, чтобы изменить поведение цикла обработки сообщений.

## <a name="catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT:: Унинитиализеком

Отменяет инициализацию COM.

```cpp
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод просто вызывает метод [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize) и вызывается из деструктора. Переопределите этот метод при переопределении [CAtlExeModuleT:: инитиализеком](#initializecom).

## <a name="catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT:: Unlock

Уменьшает счетчик блокировок модуля.

```cpp
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT:: WinMain

Этот метод реализует код, необходимый для запуска EXE.

```cpp
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Указывает способ отображения окна. Этот параметр может принимать одно из значений, описанных в разделе [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает возвращаемое значение исполняемого объекта.

### <a name="remarks"></a>Примечания

Этот метод можно переопределить. Если переопределение [CAtlExeModuleT::P ремессажелуп](#premessageloop), [CAtlExeModuleT::P остмессажелуп](#postmessageloop)или [CAtlExeModuleT:: рунмессажелуп](#runmessageloop) не предоставляет достаточно гибкости, можно переопределить `WinMain` функцию с помощью этого метода.

## <a name="see-also"></a>См. также

[Пример ATLDuck](../../overview/visual-cpp-samples.md)<br/>
[Класс Катлмодулет](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
