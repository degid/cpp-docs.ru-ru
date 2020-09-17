---
title: Класс scheduler_resource_allocation_error
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 2955320b443fb61f26d9f07ca336a45c620e2aa9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143339"
---
# <a name="scheduler_resource_allocation_error-class"></a>Класс scheduler_resource_allocation_error

Этот класс описывает исключение, возникающее из-за сбоя получения критического ресурса в исполняющей среде с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Перегружен. Формирует объект `scheduler_resource_allocation_error`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_error_code](#get_error_code)|Возвращает код ошибки, вызвавший исключение.|

## <a name="remarks"></a>Примечания

Это исключение обычно возникает при сбое вызова операционной системы из среда выполнения с параллелизмом. Код ошибки, который обычно возвращается из вызова метода Win32 `GetLastError`, преобразуется в значение типа `HRESULT` и может быть получен посредством метода `get_error_code`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="get_error_code"></a>get_error_code

Возвращает код ошибки, вызвавший исключение.

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`HRESULT` значение ошибки, вызвавшей исключение.

## <a name="ctor"></a>scheduler_resource_allocation_error

Формирует объект `scheduler_resource_allocation_error`.

```cpp
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

*_Hresult*<br/>
`HRESULT` значение ошибки, вызвавшей исключение.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
