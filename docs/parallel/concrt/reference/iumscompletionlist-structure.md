---
title: Структура IUMSCompletionList
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: c388cc98aedbd35b2d0e00a4653a85a47abcb838
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368125"
---
# <a name="iumscompletionlist-structure"></a>Структура IUMSCompletionList

Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IUMSCompletionList::GetUnblockУведомления](#getunblocknotifications)|Извлекает цепочку `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, прокси-данные которых были разблокированы с момента последнего вызова этого метода.|

## <a name="remarks"></a>Примечания

Планировщик должен быть чрезвычайно осторожным в отношении того, какие действия выполняются после использования этого интерфейса для разграничения элементов из списка завершения. Элементы должны быть помещены в список планировщиков runnable контекстов и быть в целом доступны как можно скорее. Вполне возможно, что один из разогнаных предметов получил право собственности на произвольный замок. Планировщик не может совершать произвольные вызовы функций, которые могут блокировать между вызовом для разложения элементов и размещением этих элементов в списке, к которым обычно можно получить доступ из планировщика.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSCompletionList`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>ИСТОЧНИК:GetUnblockУведомления Метод

Извлекает цепочку `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, прокси-данные которых были разблокированы с момента последнего вызова этого метода.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Цепочка `IUMSUnblockNotification` интерфейсов.

### <a name="remarks"></a>Примечания

Возвратные уведомления недействительны после переноса контекстов выполнения.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSUnblockNotification](iumsunblocknotification-structure.md)
