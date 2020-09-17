---
title: Класс CMessageMap
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: a822f36d6b6fd49301d8240324e27f0ad9ce52e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326725"
---
# <a name="cmessagemap-class"></a>Класс CMessageMap

Этот класс позволяет картам сообщений объекта быть доступными для другого объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Доступ к карте сообщений `CMessageMap`в классе -выведенных.|

## <a name="remarks"></a>Примечания

`CMessageMap`— это абстрактный базовый класс, позволяющий доступ к картам сообщений объекта к другому объекту. Для того, чтобы объект разоблачил свои карты `CMessageMap`сообщений, его класс должен вытекать из .

ATL `CMessageMap` используется для поддержки содержащихся окон и динамических цепей карты сообщений. Например, любой класс, содержащий объект `CMessageMap` [CContainedWindow,](../../atl/reference/ccontainedwindowt-class.md) должен вытекать из. Следующий код взят из образца [SUBEDIT.](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) Через [CComControl](../../atl/reference/ccomcontrol-class.md) `CAtlEdit` класс автоматически происходит `CMessageMap`от .

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

Потому что `m_EditCtrl`содержащееся окно, , будет `CAtlEdit` использовать `CMessageMap`карту сообщений в содержащем классе, вытекает из .

Для получения дополнительной информации о картах сообщений смотрите [Карты сообщений](../../atl/message-maps-atl.md) в статье «Классы окон ATL».

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage

Получает доступ к карте сообщений, идентифицированной `CMessageMap` *dwMsgMapID* в классе-производные.

```
virtual BOOL ProcessWindowMessage(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```

### <a name="parameters"></a>Параметры

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

*dwMsgMapID*<br/>
(в) Идентификатор карты сообщений, которая будет обрабатывать сообщение. Карта сообщений по умолчанию, объявленная [с BEGIN_MSG_MAP,](message-map-macros-atl.md#begin_msg_map)идентифицируется по 0. Альтернативная карта сообщений, объявленная с [ALT_MSG_MAP (msgMapID),](message-map-macros-atl.md#alt_msg_map)идентифицируется по `msgMapID`.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если сообщение полностью обработано; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Вызывается процедурой окна объекта [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) или объекта, который динамически приковывается к карте сообщений.

## <a name="see-also"></a>См. также раздел

[Класс CDynamicChain](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
