---
title: Класс CDynamicChain
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 4a72b3b4308ed83dfdc4a2895a04d1fe9a177ce5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327030"
---
# <a name="cdynamicchain-class"></a>Класс CDynamicChain

Этот класс предоставляет методы, поддерживающие динамическое цепочку карт сообщений.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CDynamicChain
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Конструктор.|
|[CDynamicChain::CDynamicChain](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDynamicChain:CallChain](#callchain)|Направляет сообщение Windows на карту сообщений другого объекта.|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Удаляет запись карты сообщения из коллекции.|
|[CDynamicChain::SetChainEntry](#setchainentry)|Добавляет запись на карту сообщений в коллекцию или изменяет существующую запись.|

## <a name="remarks"></a>Примечания

`CDynamicChain`управляет коллекцией карт сообщений, что позволяет направлять сообщение Windows во время выполнения на карту сообщений другого объекта.

Чтобы добавить поддержку динамической цепочки карт сообщений, сделайте следующее:

- Выизвуйте свой класс из `CDynamicChain`. На карте сообщений укажите [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) макрос акцепировать к карте сообщения по умолчанию другого объекта.

- Вывести каждый класс, который вы хотите, чтобы цепи к от [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`позволяет объекту разоблачать свои карты сообщений другим объектам.

- Позвоните, `CDynamicChain::SetChainEntry` чтобы определить, какой объект и на какую карту сообщений вы хотите приковать.

Например, предположим, что ваш класс определяется следующим образом:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

Затем клиент `CMyWindow::SetChainEntry`звонит:

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

где `chainedObj` находится цепной объект и является экземпляром `CMessageMap`класса, полученного из . Теперь, `myCtl` если получает сообщение, которое не обрабатывается `OnPaint` или `OnSetFocus`, `chainedObj`процедура окна направляет сообщение на карту сообщения по умолчанию.

Для получения дополнительной информации о цепочке карты сообщений смотрите [Карты сообщений](../../atl/message-maps-atl.md) в статье «Классы окон ATL».

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a>CDynamicChain:CallChain

Направляет сообщение Windows на карту сообщений другого объекта.

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>Параметры

*dwChainID*<br/>
(в) Уникальный идентификатор, связанный с цепным объектом и его картой сообщений.

*Hwnd*<br/>
(в) Ручка к окну, получающая сообщение.

*uMsg*<br/>
(в) Сообщение, отправленное в окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lResult*<br/>
(ваут) Результат обработки сообщений.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если сообщение полностью обработано; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Для того чтобы процедура `CallChain`окна была вызвать, необходимо указать [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) макрос на карте сообщений. Например, [см.](../../atl/reference/cdynamicchain-class.md)

`CallChain`Требуется предыдущий вызов [SetChainEntry,](#setchainentry) чтобы связать значение *dwChainID* с объектом и его картой сообщений.

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CDynamicChain::CDynamicChain

Конструктор.

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a>CDynamicChain::CDynamicChain

Деструктор

```
~CDynamicChain();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CDynamicChain::RemoveChainEntry

Удаляет указанную карту сообщений из коллекции.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Параметры

*dwChainID*<br/>
(в) Уникальный идентификатор, связанный с цепным объектом и его картой сообщений. Первоначально это значение определяется через вызов [в SetChainEntry.](#setchainentry)

### <a name="return-value"></a>Возвращаемое значение

TRUE, если карта сообщений успешно удалена из коллекции. В противном случае — значение FALSE.

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CDynamicChain::SetChainEntry

Добавляет указанную карту сообщения в коллекцию.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Параметры

*dwChainID*<br/>
(в) Уникальный идентификатор, связанный с цепным объектом и его картой сообщений.

*pObject*<br/>
(в) Указатель на цепной объект, объявляющий карту сообщения. Этот объект должен быть получен из [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
(в) Идентификатор карты сообщений в цепном объекте. Значение по умолчанию составляет 0, что определяет карту сообщения по умолчанию, заявленную [с BEGIN_MSG_MAP.](message-map-macros-atl.md#begin_msg_map) Чтобы указать альтернативную карту сообщений, объявленную `msgMapID`с [ALT_MSG_MAP (msgMapID),](message-map-macros-atl.md#alt_msg_map)пройти .

### <a name="return-value"></a>Возвращаемое значение

TRUE, если карта сообщений успешно добавлена в коллекцию. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если значение *dwChainID* уже существует в коллекции, связанный с ним объект и карта сообщений заменяются *pObject* и *dwMsgMapID*соответственно. В противном случае добавляется новая запись.

## <a name="see-also"></a>См. также раздел

[Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
