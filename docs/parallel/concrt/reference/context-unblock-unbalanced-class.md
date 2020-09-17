---
title: Класс context_unblock_unbalanced
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: 261ec96c1a83fbec423e6dbbfe403c4db53a2962
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143100"
---
# <a name="context_unblock_unbalanced-class"></a>Класс context_unblock_unbalanced

Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.

## <a name="syntax"></a>Синтаксис

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Перегружен. Формирует объект `context_unblock_unbalanced`.|

## <a name="remarks"></a>Примечания

Вызовы методов `Block` и `Unblock` объекта `Context` должны всегда быть парными. Среда выполнения с параллелизмом позволяет операциям выполняться в любом порядке. Например, за вызовом `Block` может следовать вызов `Unblock`, или наоборот. Это исключение возникает, если, например, два вызова метода `Unblock` были внесены в строку на `Context` объекте, который не был заблокирован.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="ctor"></a>context_unblock_unbalanced

Формирует объект `context_unblock_unbalanced`.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
