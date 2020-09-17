---
title: Класс progress_reporter
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: bd8f50a8c9829ff9de3e2412b89aa4de88d90db6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138773"
---
# <a name="progress_reporter-class"></a>Класс progress_reporter

Класс формирования отчетов о ходе выполнения позволяет формировать уведомления о ходе выполнения определенного типа. Каждый объект progress_reporter привязан к конкретному асинхронному действию или операции.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>Параметры

*_ProgressType*<br/>
О типе полезных данных каждого уведомления о ходе выполнения сообщается посредством формирования отчетов о ходе выполнения.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[передачи](#report)|Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.|

## <a name="remarks"></a>Примечания

Этот тип доступен только для среда выполнения Windows приложений.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`progress_reporter`

## <a name="requirements"></a>Требования

**Заголовок:** из ppltasks.h

**Пространство имен:** concurrency

## <a name="ctor"></a>progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a>передачи

Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Полезные данные для отчета о ходе выполнения.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
