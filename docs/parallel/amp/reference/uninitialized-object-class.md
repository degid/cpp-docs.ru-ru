---
title: uninitialized_object - класс
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: ef7ded0bf925d3430b70064c4979b75e08f9cf45
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127703"
---
# <a name="uninitialized_object-class"></a>uninitialized_object - класс

Исключение, возникающее при использовании неинициализированного объекта.

## <a name="syntax"></a>Синтаксис

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор uninitialized_object](#uninitialized_object)|Инициализирует новый экземпляр класса `uninitialized_object`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт.h

**Пространство имен** : Concurrency

## <a name="uninitialized_object"></a>uninitialized_object

Конструирует новый экземпляр исключения `uninitialized_object`.

### <a name="syntax"></a>Синтаксис

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Текстовое описание ошибки.

### <a name="return-value"></a>Возвращаемое значение

Объект исключения `uninitialized_object`.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
