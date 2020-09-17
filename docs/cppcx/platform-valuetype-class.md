---
title: Platform::ValueType - класс
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: f4ce34fa3f197424833d34bdb866712d412e69c3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846554"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType - класс

Базовый класс для экземпляров типов значений.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Открытые методы

| Имя | Описание |
|--|--|
| [ValueType:: ToString](#tostring) | Возвращает строковое представление объекта. Наследуется от [Platform:: Object](../cppcx/platform-object-class.md). |

### <a name="remarks"></a>Примечания

Класс ValueType используется для создания типов значений. Класс ValueType является производным от класса Object, который содержит базовые элементы. Однако компилятор отсоединяет эти базовые элементы от типов значений, которые являются производными от класса ValueType. При упаковке типа значения компилятор снова присоединяет эти базовые элементы.

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** Platform. winmd

## <a name="valuetypetostring-method"></a><a name="tostring"></a> Метод ValueType:: ToString

Возвращает строковое представление объекта.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка Platform:: String, представляющая значение.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
