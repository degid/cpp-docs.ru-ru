---
title: Класс accelerator_view_removed
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: 9a3f6f349fc3103893639fe209dcf23a07ffec56
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127128"
---
# <a name="accelerator_view_removed-class"></a>Класс accelerator_view_removed

Исключение, возникающее при сбое базового вызова DirectX из-за обнаружения времени ожидания Windows и механизма восстановления.

## <a name="syntax"></a>Синтаксис

```cpp
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор accelerator_view_removed](#ctor)|Инициализирует новый экземпляр класса `accelerator_view_removed`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|Возвращает код ошибки HRESULT, указывающий на причину удаления объекта `accelerator_view`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт.h

**Пространство имен** : Concurrency

## <a name="ctor"></a>accelerator_view_removed

Инициализирует новый экземпляр класса [accelerator_view_removed](accelerator-view-removed-class.md) .

### <a name="syntax"></a>Синтаксис

```cpp
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>Параметры

*message*<br/>
Текстовое описание ошибки.

*view_removed_reason*<br/>
Код ошибки HRESULT, указывающий причину удаления объекта `accelerator_view`.

### <a name="return-value"></a>Возвращаемое значение

Новый экземпляр класса `accelerator_view_removed`.

## <a name="get_view_removed_reason"></a>get_view_removed_reason

Возвращает код ошибки HRESULT, указывающий на причину удаления объекта `accelerator_view`.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
