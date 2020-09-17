---
title: Интерфейс ICommandSource
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 6a03c46c972f7746f39a3c5c65ca9b5509983d59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356980"
---
# <a name="icommandsource-interface"></a>Интерфейс ICommandSource

Управляет командами, отправленными с объекта исходного кода команды в пользовательский элемент управления.

## <a name="syntax"></a>Синтаксис

```cpp
interface class ICommandSource
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Добавляет обработчик команды в объект исходного кода команды.|
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Добавляет группу обработчиков команд к объекту исходного кода команды.|
|[ICommandSource:AddCommandRangeUIHandler](#addcommandrangeuihandler)|Добавляет группу обработчиков командных сообщений пользовательского интерфейса к объекту исходного кода команды.|
|[ICommandSource:AddCommandUIHandler](#addcommandrangeuihandler)|Добавляет обработчик сообщения командного сообщения пользовательского интерфейса к объекту исходного кода команды.|
|[ICommandSource::PostCommand](#postcommand)|Публикует сообщение, не дожидаясь его обработки.|
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Удаляет обработчик команды из объекта исходного кода команды.|
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Удаляет группу обработчиков команд с объекта исходного кода команды.|
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Удаляет группу обработчиков командных сообщений пользовательского интерфейса с объекта исходного кода команды.|
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Удаляет обработчик командного сообщения пользовательского интерфейса с объекта исходного кода команды.|
|[ICommandSource::SendCommand](#sendcommand)|Отправляет сообщение и ждет его обработки перед возвращением.|

### <a name="remarks"></a>Примечания

Когда вы размещаете управление пользователем в представлении MFC, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) маршрутирует команды и обновляете сообщения пользовательского интерфейса для управления пользователем, чтобы позволить ему обрабатывать команды MFC (например, элементы меню кадра и кнопки панели инструментов). Реализуя [интерфейс ICommandTarget,](../../mfc/reference/icommandtarget-interface.md)вы даете `ICommandSource` пользователю управление ссылкой на объект.

[Узнайте, как: Добавьте командную раминю](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) в управление `ICommandTarget`формами Windows для примера использования.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a>ICommandSource::AddCommandHandler

Добавляет обработчик команды в объект исходного кода команды.

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
*cmdHandler*<br/>
Ручка для метода обработчика команд.

### <a name="remarks"></a>Примечания

Этот метод добавляет обработчик команды cmdHandler к объекту исходного кода команды и отображает обработчик в cmdID.
[Узнайте, как: Добавьте командную раминю в систему управления windows,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) чтобы пример использования AddCommandHandler.

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

Добавляет группу обработчиков команд к объекту исходного кода команды.

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатора команд.
*cmdIDMax*<br/>
Индекс окончания диапазона идентификатора команд.
*cmdHandler*<br/>
Ручка к методу обработчика сообщений, с которым отображаются команды.

### <a name="remarks"></a>Примечания

Этот метод отображает смежный диапазон идентиверев команд в один обработчик сообщений и добавляет их к объекту исходного кода команды. Это используется для обработки группы связанных кнопок одним методом.

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a>ICommandSource:AddCommandRangeUIHandler

Добавляет группу обработчиков командных сообщений пользовательского интерфейса к объекту исходного кода команды.

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатора команд.
*cmdIDMax*<br/>
Индекс окончания диапазона идентификатора команд.
*cmdHandler*<br/>
Ручка к методу обработчика сообщений, с которым отображаются команды.

### <a name="remarks"></a>Примечания

Этот метод отображает смежный диапазон идентиверев команд для одного обработчика командных сообщений пользовательского интерфейса и добавляет его к объекту исходного кода команды. Это используется для обработки группы связанных кнопок одним методом.

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a>ICommandSource:AddCommandUIHandler

Добавляет обработчик сообщения командного сообщения пользовательского интерфейса к объекту исходного кода команды.

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
*cmdUIHandler*<br/>
Ручка для метода обработчика сообщений командного интерфейса пользователя.

### <a name="remarks"></a>Примечания

Этот метод добавляет обработчик сообщения команды пользователя cmdHandler к объекту исходного кода команды и отображает обработчик амдификатор а также отображает обработчик в cmdID.

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a>ICommandSource::PostCommand

Публикует сообщение, не дожидаясь его обработки.

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*Команды*<br/>
Идентификатор команды сообщения, который будет размещен.

### <a name="remarks"></a>Примечания

Этот метод асинхронно публикует сообщение, отображеное на идентификатор, указанный командой. Он вызывает CWnd::PostMessage, чтобы поместить сообщение в очередь сообщения окна, а затем возвращается, не дожидаясь соответствующего окна для обработки сообщения.

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler

Удаляет обработчик команды из объекта исходного кода команды.

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик команды, отображеный на cmdID, из объекта исходного кода команды.

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler

Удаляет группу обработчиков команд с объекта исходного кода команды.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатора команд.
*cmdIDMax*<br/>
Индекс окончания диапазона идентификатора команд.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу обработчиков сообщений, отображаемых на идентификаторах команд, указанных cmdIDMin и cmdIDMax, с объекта исходного кода команды.

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler

Удаляет группу обработчиков командных сообщений пользовательского интерфейса с объекта исходного кода команды.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатора команд.
*cmdIDMax*<br/>
Индекс окончания диапазона идентификатора команд.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу обработчиков командных сообщений пользовательского интерфейса, отображаемых на идентификаторах команд, указанных cmdIDMin и cmdIDMax, с объекта исходного кода команды.

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler

Удаляет обработчик командного сообщения пользовательского интерфейса с объекта исходного кода команды.

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик сообщения командного сообщения пользовательского интерфейса, отображемый с cmdID, с объекта исходного кода команды.

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a>ICommandSource::SendCommand

Отправляет сообщение и ждет его обработки перед возвращением.

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*Команды*<br/>
Идентификатор команды сообщения, который будет отправлен.

### <a name="remarks"></a>Примечания

Этот метод синхронно отправляет сообщение, отображеное на идентификатор, указанный командой. Он вызывает CWnd::SendMessage для размещения сообщения в очереди сообщений окна и ждет, пока эта процедура окна не обработает сообщение перед возвращением.

## <a name="see-also"></a>См. также раздел

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md)
