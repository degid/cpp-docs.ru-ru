---
title: Глобальные функции обработки событий
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: fde93415640ef7fa460bb363af4c3cb14b356061
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833456"
---
# <a name="event-handling-global-functions"></a>Глобальные функции обработки событий

Эта функция предоставляет обработчик событий.

> [!IMPORTANT]
> Функция, указанная в следующей таблице, не может использоваться в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает сигнала объекта, в то же время исправляет сообщения окна по мере необходимости.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a> атлваитвисмессажелуп

Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Параметры

*хевент*<br/>
окне Маркер объекта, который необходимо дождаться.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объект был сигнальным.

### <a name="remarks"></a>Примечания

Это полезно, если требуется дождаться события объекта и получать уведомления о нем, но разрешить сообщения окон в ожидании.

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
