---
title: Класс nested_scheduler_missing_detach
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: 8c9553b036890c4ce28f1060bfe2f58ee1904935
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138859"
---
# <a name="nested_scheduler_missing_detach-class"></a>Класс nested_scheduler_missing_detach

Этот класс описывает исключение, которое возникает, когда исполняющая среда с параллелизмом обнаруживает, что вы не вызвали метод `CurrentScheduler::Detach` для контекста, который присоединился ко второму планировщику с помощью метода `Attach` объекта `Scheduler`.

## <a name="syntax"></a>Синтаксис

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Перегружен. Формирует объект `nested_scheduler_missing_detach`.|

## <a name="remarks"></a>Примечания

Это исключение возникает, только когда один планировщик вложен внутрь другого путем вызова метода `Attach` объекта `Scheduler` для контекста, которым уже владеет другой планировщик или к которому он уже прикреплен. Среда выполнения с параллелизмом создает это исключение, рационально, когда он может обнаружить сценарий как вспомогательный для поиска проблемы. Не все экземпляры, которые не вызывают метод `CurrentScheduler::Detach`, гарантированно вызовут это исключение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="ctor"></a>nested_scheduler_missing_detach

Формирует объект `nested_scheduler_missing_detach`.

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс Scheduler](scheduler-class.md)
