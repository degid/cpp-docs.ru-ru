---
title: Класс scheduler_not_attached
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: a3b1c113e5c6c5feb5b2fa1940ee9b984233e4af
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142198"
---
# <a name="scheduler_not_attached-class"></a>Класс scheduler_not_attached

Этот класс описывает исключение, создаваемое при выполнении операции, при которой планировщик должен был присоединен к текущему контексту, а он не присоединен.

## <a name="syntax"></a>Синтаксис

```cpp
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Перегружен. Формирует объект `scheduler_not_attached`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="ctor"></a>scheduler_not_attached

Формирует объект `scheduler_not_attached`.

```cpp
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс Scheduler](scheduler-class.md)
