---
title: ИнжектСобытие
description: Ссылка на функцию SDK InjectEvent.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c82aad5923eff60e5c72ceccaa39aa136f942665
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324035"
---
# <a name="injectevent"></a>ИнжектСобытие

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `InjectEvent` вызывается в перелогере, реализуя интерфейс [IRelogger.](../other-types/irelogger-class.md) Он используется для записи события Отслеживания для Windows (ETW) событие в файле вывода следа сеанса relogging.

## <a name="syntax"></a>Синтаксис

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>Параметры

*relogСессия*\
Указатель на сеанс перезаписи. Сеанс перезаписи предоставляется перелогерам, реализующим `IRelogger` интерфейс. Для получения дополнительной [IRelogger](../other-types/irelogger-class.md)информации см.

*providerId*\
Отслеживание событий для поставщика УСЛУГ Windows (ETW), в соответствии с которым событие ETW перерегистрируется.

*eventDescriptor*\
Дескриптор события ETW для перезаписи события ETW.

*processId*\
Идентификатор процесса (PID) для перезаписи события ETW.

*threadId*\
Идентификатор потока (TID) для перезаписи события ETW.

*процессорИндекс*\
Перезагруженный индекс процессора для события ETW.

*Timestamp*\
Отметка времени для перезавеченного события ETW.

*Данных*\
Указатель на данные, которые должны быть включены в перезаписи события ETW.

*byteCount*\
Размер данных, в байтах, указывается на *данные*.

## <a name="remarks"></a>Примечания

Для получения дополнительной информации о концепциях ETW, таких как [ETW documentation](/windows/win32/etw/about-event-tracing) *провайдер GUID* и *дескриптор событий,* см. Для получения подробной информации о том, как начать сеанс перезаписи [Relog](relog.md)с помощью SDK Build Insights, см.

::: moniker-end
