---
title: Класс Platform::ArrayReference
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: e9dd16ad6c3f53c5562b0419197a582c06fbc642
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354791"
---
# <a name="platformarrayreference-class"></a>Класс Platform::ArrayReference

`ArrayReference` — тип оптимизации, который можно заменить на [Platform::Array^](../cppcx/platform-array-class.md) во входных параметрах, если требуется заполнить входными данными массив в стиле языка C.

## <a name="syntax"></a>Синтаксис

```cpp
class ArrayReference
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ArrayСправка::ArrayСправка](#ctor)|Инициализирует новый экземпляр класса `ArrayReference`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ArrayСправка:Оператор() Оператор](#operator-call)|Преобразует этот объект `ArrayReference` в `Platform::Array<T>^*`.|
|[Оператор ArrayReference::operator=](#operator-assign)|Назначает содержимое другой ссылки `ArrayReference` этому экземпляру.|

## <a name="exceptions"></a>Исключения

### <a name="remarks"></a>Примечания

Использование `ArrayReference` для заполнения массива в стиле языка C позволяет избежать дополнительной операции копирования, которая потребовалось бы при копировании сначала в переменную `Platform::Array` , а затем в массив в стиле языка C. При использовании `ArrayReference`выполняется только одна операция копирования. Для примера кода см. [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Заголовок:** vccorlib.h

## <a name="arrayreferencearrayreference-constructor"></a><a name="ctor"></a>ArrayСправка::ArrayReference Конструктор

Инициализирует новый экземпляр [платформы::ArrayReference](../cppcx/platform-arrayreference-class.md) класса.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Параметры

*dataArg*<br/>
Указатель на данные массива.

*sizeArg*<br/>
Количество элементов в исходном массиве.

*otherArg*<br/>
Объект `ArrayReference`, данные которого будут перемещены для инициализации нового экземпляра.

### <a name="remarks"></a>Примечания

## <a name="arrayreferenceoperator-operator"></a><a name="operator-assign"></a>ArrayСправка::Оператор » Оператор

Присваивает указанный объект текущей [платформе::ArrayReference](../cppcx/platform-arrayreference-class.md) object с помощью семантики перемещения.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Параметры

*otherArg*<br/>
Присваивает перемещенный объект текущему объекту `ArrayReference`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект типа `ArrayReference`.

### <a name="remarks"></a>Примечания

`Platform::ArrayReference` — это стандартный шаблон класса C++, а не ссылочный класс.

## <a name="arrayreferenceoperator-operator"></a><a name="operator-call"></a>ArrayСправка:Оператор() Оператор

Преобразует текущую [платформу::ArrayReference](../cppcx/platform-arrayreference-class.md) объект обратно в [платформу::Array](../cppcx/platform-array-class.md) класса.

### <a name="syntax"></a>Синтаксис

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для объекта типа `Array<TArg>^`

### <a name="remarks"></a>Примечания

[Платформа::ArrayReference](../cppcx/platform-arrayreference-class.md) является стандартным шаблоном класса СЗ, а [платформа::Array](../cppcx/platform-array-class.md) - это класс рефери.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
