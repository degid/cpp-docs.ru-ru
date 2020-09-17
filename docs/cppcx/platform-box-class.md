---
title: Класс Platform::Box
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: 6afc12dbc3f6980bb7fd42d7f0a8fdc9e6d0e284
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232174"
---
# <a name="platformbox-class"></a>Класс Platform::Box

Включает тип значения, например `Windows::Foundation::DateTime` или скалярный тип, например, **`int`** для хранения в `Platform::Object` типе. Как правило, нет необходимости использовать `Box` явным образом, так как процесс упаковки выполняется неявно при приведении значения типа к `Object^`.

### <a name="syntax"></a>Синтаксис

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

### <a name="members"></a>Элементы

|Член|Описание|
|------------|-----------------|
|[Box](#ctor) | Создает объект `Box`, который может инкапсулировать значение указанного типа. |
|[Поле оператора &lt; const T&gt;^](#box-const-t) | Включает преобразование упаковки из **`const`** класса `T` или класса значения **`enum`** `T` в `Box<T>` . |
|[Поле оператора &lt; const volatile T&gt;^](#box-const-volatile-t) | Включает преобразования упаковки из **`const volatile`** класса значения `T` или **`enum`** типа `T` в `Box<T>` . |
|[Поле оператора &lt; T&gt;^](#box-t) | Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`. |
|[Поле оператора &lt; volatile T&gt;^](#box-volatile-t) | Включает преобразования упаковки из **`volatile`** класса значения `T` или **`enum`** типа `T` в `Box<T>` . |
|[Box:: оператор T](#t) | Включает преобразование упаковки из класса `T` или класса значения **`enum`** `T` в `Box<T>` . |
|[Value, свойство](#value) | Возвращает значение, которое инкапсулируется в объекте `Box`. |

## <a name="boxbox-constructor"></a><a name="ctor"></a>Конструктор Box:: Box

Создает объект `Box`, который может инкапсулировать значение указанного типа.

### <a name="syntax"></a>Синтаксис

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>Параметры

*валуеарг*<br/>
Тип значения для упаковки, например,,, **`int`** **`bool`** `float64` `DateTime` .

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a>Box:: оператор Box &lt; const T &gt; ^

Включает преобразование упаковки из **`const`** класса `T` или класса значения **`enum`** `T` в `Box<T>` .

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой класс значений, структура значений или тип перечисления. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).

### <a name="return-value"></a>Возвращаемое значение

`Platform::Box<T>^`Экземпляр, представляющий исходное значение, упакованное в класс ссылки.

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a>Оператор Box:: оператор &lt; const volatile T &gt; ^

Включает преобразования упаковки из **`const volatile`** класса значения `T` или **`enum`** типа `T` в `Box<T>` .

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).

### <a name="return-value"></a>Возвращаемое значение

`Platform::Box<T>^`Экземпляр, представляющий исходное значение, упакованное в класс ссылки.

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a>Оператор Box:: оператор Box &lt; T &gt; ^

Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`.

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).

### <a name="return-value"></a>Возвращаемое значение

`Platform::Box<T>^`Экземпляр, представляющий исходное значение, упакованное в класс ссылки.

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a>Оператор Box:: оператор &lt; volatile T &gt; ^

Включает преобразования упаковки из **`volatile`** класса значения `T` или **`enum`** типа `T` в `Box<T>` .

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).

### <a name="return-value"></a>Возвращаемое значение

`Platform::Box<T>^`Экземпляр, представляющий исходное значение, упакованное в класс ссылки.

## <a name="boxoperator-t-operator"></a><a name="t"></a>Оператор Box::operator T

Включает преобразование упаковки из класса `T` или класса значения **`enum`** `T` в `Box<T>` .

### <a name="syntax"></a>Синтаксис

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).

### <a name="return-value"></a>Возвращаемое значение

`Platform::Box<T>^`Экземпляр, представляющий исходное значение, упакованное в класс ссылки.

## <a name="boxvalue-property"></a><a name="value"></a>Свойство box:: value

Возвращает значение, которое инкапсулируется в объекте `Box`.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает упакованное значение с тем же типом, который у него был до упаковки.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)<br/>
[Упаковка-преобразование](../cppcx/boxing-c-cx.md)
