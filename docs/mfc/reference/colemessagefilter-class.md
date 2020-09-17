---
title: Класс COleMessageFilter
ms.date: 11/04/2016
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
ms.openlocfilehash: 8a6c160a76ae27059238c3e8e26b5bea87a87f7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753830"
---
# <a name="colemessagefilter-class"></a>Класс COleMessageFilter

Управляет параллелизмом, требуемым для взаимодействия приложений OLE.

## <a name="syntax"></a>Синтаксис

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeMessageFilter::COleMessageFilter](#colemessagefilter)|Формирует объект `COleMessageFilter`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeMessageFilter::BeginBusyState](#beginbusystate)|Помещает приложение в загруженное состояние.|
|[ColeMessageFilter::EnableBusyДиалог](#enablebusydialog)|Включает и отстраняет диалоговое окно, которое появляется, когда вызывается приложение занято.|
|[ColeMessageFilter::EnableNotRespondingДиалог](#enablenotrespondingdialog)|Включает и отстраняет диалоговое окно, которое появляется, когда вызванное приложение не отвечает.|
|[ColeMessageFilter::EndBusyState](#endbusystate)|Прекращает занятое состояние приложения.|
|[ColeMessagefilter::Onmessage](#onmessagepending)|Вызывается инфраструктурой для обработки сообщений во время выполнения вызова OLE.|
|[ColeMessageFilter::Регистрация](#register)|Регистрирует фильтр сообщений с помощью DLL системы OLE.|
|[ColeMessageFilter::Revoke](#revoke)|Отменяет регистрацию фильтра сообщений с помощью DLL системы OLE.|
|[ColeMessageFilter::SetBusyReply](#setbusyreply)|Определяет ответ загруженного приложения на вызов OLE.|
|[ColeMessageFilter::SetMessage](#setmessagependingdelay)|Определяет, как долго приложение ждет ответа на вызов OLE.|
|[ColeMessagefilter::SetretryReply](#setretryreply)|Определяет ответ приложения вызова на загруженное приложение.|

## <a name="remarks"></a>Примечания

Класс `COleMessageFilter` полезен в приложениях для визуального редактирования серверов и контейнеров, а также в приложениях автоматизации OLE. Для используемых серверных приложений этот класс может использоваться для того, чтобы сделать приложение «занятым», чтобы входящие вызовы из других контейнерных приложений были либо отменены, либо повторены позже. Этот класс также может быть использован для определения действия, которое должно быть принято вызывающей приложением, когда вызываемый приложение занят.

Обычно приложение сервера вызывает [BeginBusyState](#beginbusystate) и [EndBusyState,](#endbusystate) когда будет опасно, чтобы документ или другой доступный объект OLE был уничтожен. Эти звонки делаются в [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) во время обновления пользовательского интерфейса.

По умолчанию `COleMessageFilter` объект выделяется при инициализации приложения. Он может быть извлечен с [Помощью AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

Это продвинутый класс; Вы редко должны работать с ним напрямую.

Для получения дополнительной информации см. [Servers: Implementing a Server](../../mfc/servers-implementing-a-server.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a>ColeMessageFilter::BeginBusyState

Вызовите эту функцию, чтобы начать занятое состояние.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Примечания

Он работает совместно с [EndBusyState](#endbusystate) для управления загруженным состоянием приложения. Функция [SetBusyReply](#setbusyreply) определяет ответ приложения на вызов приложений, когда он занят.

И `BeginBusyState` `EndBusyState` вызывает приращения и decrement, соответственно, счетчик, который определяет, занят ли приложение. Например, два `BeginBusyState` вызова и `EndBusyState` один вызов, чтобы все еще привести к занятому состоянию. Чтобы отменить занятое состояние, необходимо вызвать `EndBusyState` такое же количество звонков. `BeginBusyState`

По умолчанию фреймворк входит в загруженное состояние во время простоя обработки, которая выполняется [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). В то время как приложение обрабатывает ON_COMMANDUPDATEUI уведомлений, входящие вызовы обрабатываются позже, после завершения обработки простоя.

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a>ColeMessageFilter::COleMessageFilter

Создает объект `COleMessageFilter`.

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a>ColeMessageFilter::EnableBusyДиалог

Включает и отключает занятого диалогового окна, которое отображается при истечении срока действия задержки с ожиданием сообщения (см. [SetRetryReply)](#setretryreply)во время вызова OLE.

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableBusy*<br/>
Определяет, включен о его отключение или отключено поле диалогового журнала «занят».

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a>ColeMessageFilter::EnableNotRespondingДиалог

Включает и отключает диалоговое окно "не отвечая", которое отображается, если сообщение клавиатуры или мыши находится на рассмотрении во время вызова OLE и вызов приурочен.

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableNotResponding*<br/>
Определяет, включен о включен о включено или отключено поле диалога "не отвечая".

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a>ColeMessageFilter::EndBusyState

Вызовите эту функцию, чтобы закончить загруженное состояние.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Примечания

Он работает совместно с [BeginBusyState](#beginbusystate) для управления загруженным состоянием приложения. Функция [SetBusyReply](#setbusyreply) определяет ответ приложения на вызов приложений, когда он занят.

И `BeginBusyState` `EndBusyState` вызывает приращения и decrement, соответственно, счетчик, который определяет, занят ли приложение. Например, два `BeginBusyState` вызова и `EndBusyState` один вызов, чтобы все еще привести к занятому состоянию. Чтобы отменить занятое состояние, необходимо вызвать `EndBusyState` такое же количество звонков. `BeginBusyState`

По умолчанию фреймворк входит в загруженное состояние во время простоя обработки, которая выполняется [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). В то время как приложение обрабатывает ON_UPDATE_COMMAND_UI уведомлений, входящие вызовы обрабатываются после завершения обработки простоя.

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a>ColeMessagefilter::Onmessage

Вызывается инфраструктурой для обработки сообщений во время выполнения вызова OLE.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на ожидавщее сообщение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Когда вызывающая заявка ждет завершения вызова, платформа `OnMessagePending` вызывает с указателем на ожидавщееся сообщение. По умолчанию система отправляет WM_PAINT сообщений, так что обновление окна может происходить во время вызова, который занимает много времени.

Вы должны зарегистрировать свой фильтр сообщений с помощью вызова [для регистрации,](#register) прежде чем он может стать активным.

## <a name="colemessagefilterregister"></a><a name="register"></a>ColeMessageFilter::Регистрация

Регистрирует фильтр сообщений с помощью DLL системы OLE.

```
BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Фильтр сообщений не имеет эффекта, если он не зарегистрирован в системе DLLs. Обычно код инициализации приложения регистрирует фильтр сообщений приложения. Любой другой фильтр сообщений, зарегистрированный вашим приложением, должен быть отозван до того, как программа прекратится по вызову [об отзыве.](#revoke)

Фильтр сообщения по умолчанию регистрируется во время инициализации и аннулируется при прекращении.

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a>ColeMessageFilter::Revoke

Отменяет предыдущую регистрацию, выполненную по вызову [в регистрацию.](#register)

```cpp
void Revoke();
```

### <a name="remarks"></a>Примечания

Фильтр сообщений должен быть отменен до завершения программы.

Фильтр сообщения по умолчанию, который создается и регистрируется автоматически инфраструктурой, также автоматически отменяется.

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a>ColeMessageFilter::SetBusyReply

Эта функция устанавливает "занятый ответ" приложения.

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Параметры

*nBusyReply*<br/>
Значение из `SERVERCALL` перечисления, которое определено в COMPOBJ. H. Он может иметь любое из следующих значений:

- SERVERCALL_ISHANDLED приложение может принимать вызовы, но может выполнить неудачу при обработке конкретного вызова.

- SERVERCALL_REJECTED приложение, вероятно, никогда не сможет обрабатывать вызов.

- SERVERCALL_RETRYLATER приложение временно находится в состоянии, в котором оно не может обрабатывать вызов.

### <a name="remarks"></a>Примечания

Функции [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) управляют загруженным состоянием приложения.

Когда приложение было занято `BeginBusyState`вызовом, оно отвечает на звонки из DLL системы OLE со `SetBusyReply`значением, определяемым последним параметром . Приложение вызова использует этот занятый ответ, чтобы определить, какие действия следует предпринять.

По умолчанию, занятый ответ SERVERCALL_RETRYLATER. Этот ответ приводит к тому, что вызываемый вызов как можно скорее повторно опробует вызов.

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a>ColeMessageFilter::SetMessage

Определяет, как долго вызываемый приложение ждет ответа от вызываемого приложения, прежде чем предпринимать дальнейшие действия.

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Параметры

*nTimeout*<br/>
Количество миллисекунд для задержки с сообщением.

### <a name="remarks"></a>Примечания

Эта функция работает в сотрудничестве с [SetRetryReply](#setretryreply).

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a>ColeMessagefilter::SetretryReply

Определяет действие вызывающей приложения, когда оно получает многоразовый ответ от вызываемого приложения.

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Параметры

*nRetryReply*<br/>
Количество миллисекунд между повторами.

### <a name="remarks"></a>Примечания

Когда вызываемый приложение указывает, что оно занято, вызываемый приложение может решить подождать, пока сервер больше не будет занят, повторить попытку сразу или повторить попытку после определенного интервала. Он также может принять решение об отмене вызова в целом.

Ответ вызывающего абонента контролируется `SetRetryReply` функциями и [SetMessagePendingDelay.](#setmessagependingdelay) `SetRetryReply`определяет, как долго приложение вызова должно ждать между повторами для заданного вызова. `SetMessagePendingDelay`определяет, как долго вызываемый приложение ждет ответа от сервера, прежде чем предпринимать дальнейшие действия.

Обычно по умолчанию являются приемлемыми и не должны быть изменены. Фреймов повторно заверяет вызов каждый *nRetryReply* миллисекунды, пока вызов проходит или сообщение ожидания задержки истек. Значение 0 для *nRetryReply* указывает на немедленную повторную попытку, и - 1 указывает на отмену вызова.

По истечении срока действия задержки с ожиданием сообщения отображается "занятое диалоговое поле" OLE (см. [COleBusyDialog),](../../mfc/reference/colebusydialog-class.md)чтобы пользователь мог отменить или повторить вызов. Позвоните [EnableBusyDialog,](#enablebusydialog) чтобы включить или отключить этот диалоговый ящик.

Когда сообщение клавиатуры или мыши находится на рассмотрении во время вызова и вызов приурочен (превысил задержку с ожиданием сообщения), отображается диалоговое окно "не отвечая". Позвоните [EnableNotRespondingDialog,](#enablenotrespondingdialog) чтобы включить или отключить этот диалоговый ящик. Обычно такое положение дел указывает на то, что что-то пошло не так, и пользователь становится нетерпеливым.

Когда диалоги отключены, текущий "ответ на повторную попытку" всегда используется для вызовов в загруженные приложения.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
