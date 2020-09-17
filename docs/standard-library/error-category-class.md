---
title: Класс error_category
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 218596ff5b81e99f4787efe2582fdc2752533cec
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840171"
---
# <a name="error_category-class"></a>Класс error_category

Представляет абстрактный, общий базовый класс для объектов, который описывает категорию кодов ошибок.

## <a name="syntax"></a>Синтаксис

```cpp
class error_category;

constexpr error_category() noexcept;
virtual ~error_category();
error_category(const error_category&) = delete
```

## <a name="remarks"></a>Примечания

`error_category` реализуют два стандартных объекта: [generic_category](../standard-library/system-error-functions.md#generic_category) и [system_category](../standard-library/system-error-functions.md#system_category).

## <a name="members"></a>Элементы

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[value_type](#value_type)|Тип, представляющий сохраненное значение кода ошибки.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[default_error_condition](#default_error_condition)|Сохраняет значение кода ошибки для объекта условия ошибки.|
|[equivalent](#equivalent)|Возвращает значение, указывающее, эквивалентны ли объекты ошибок.|
|[generic_category](#generic)||
|[message](#message)|Возвращает имя указанного кода ошибки.|
|[name](#name)|Возвращает имя категории.|
|[system_category](#system)||

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_as)|Оператор присвоения.|
|[operator==](#op_eq_eq)|Проверяет равенство между объектами `error_category`.|
|[operator!=](#op_neq)|Проверяет неравенство между объектами `error_category`.|
|[operator<](#op_lt)|Проверяет, меньше ли объект [error_category](../standard-library/error-category-class.md) переданного для сравнения объекта `error_category`.|

## <a name="default_error_condition"></a><a name="default_error_condition"></a> default_error_condition

Сохраняет значение кода ошибки для объекта условия ошибки.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Параметры

`_Errval`\
Значение кода ошибки для хранения в [error_condition](../standard-library/error-condition-class.md).

### <a name="return-value"></a>Возвращаемое значение

Возвращает `error_condition(_Errval, *this)`.

### <a name="remarks"></a>Примечания

### <a name="equivalent"></a><a name="equivalent"></a> equivalent

Возвращает значение, указывающее, эквивалентны ли объекты ошибок.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

#### <a name="parameters"></a>Параметры

*_Errval*\
Значение кода ошибки для сравнения.

*_Cond*\
Объект [error_condition](../standard-library/error-condition-class.md) для сравнения.

*_Code*\
Объект [error_code](../standard-library/error-code-class.md) для сравнения.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** , если категория и значение равны; в противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Первая функция-член возвращает значение `*this == _Cond.category() && _Cond.value() == _Errval`.

Вторая функция-член возвращает значение `*this == _Code.category() && _Code.value() == _Errval`.

### <a name="generic_category"></a><a name="generic"></a> generic_category

```cpp
const error_category& generic_category();
```

### <a name="message"></a><a name="message"></a> Сообщение

Возвращает имя указанного кода ошибки.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

#### <a name="parameters"></a>Параметры

*val*\
Значение кода ошибки для описания.

#### <a name="return-value"></a>Возвращаемое значение

Возвращает описательное имя кода ошибки *Val* для категории. Если код ошибки не распознан, возвращает `"unknown error"` .

#### <a name="remarks"></a>Примечания

### <a name="name"></a>Имя в <a name="name"></a>

Возвращает имя категории.

```cpp
virtual const char *name() const = 0;
```

#### <a name="return-value"></a>Возвращаемое значение

Возвращает имя категории как строку байтов, заканчивающуюся нулем.

### <a name="operator"></a><a name="op_as"></a> operator=

```cpp
error_category& operator=(const error_category&) = delete;
```

### <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет равенство между объектами `error_category`.

```cpp
bool operator==(const error_category& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на равенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты равны; **`false`** значение, если объекты не равны.

#### <a name="remarks"></a>Примечания

Этот оператор-член возвращает `this == &right`.

### <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство между объектами `error_category`.

```cpp
bool operator!=(const error_category& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на неравенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_category` объект не равен объекту, `error_category` переданному по *правому краю*; в противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `(!*this == right)`.

### <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект [error_category](../standard-library/error-category-class.md) переданного для сравнения объекта `error_category`.

```cpp
bool operator<(const error_category& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Сравниваемый объект `error_category`.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_category` объект меньше, чем `error_category` объект, переданный для сравнения; В противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `this < &right`.

### <a name="system_category"></a><a name="system"></a> system_category

```cpp
const error_category& system_category();
```

### <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий сохраненное значение кода ошибки.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Примечания

Это определение типа является синонимом для **`int`** .
