---
title: Класс error_condition
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
helpviewer_keywords:
- std::error_condition
- std::error_condition::value_type
- std::error_condition::assign
- std::error_condition::category
- std::error_condition::clear
- std::error_condition::message
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
ms.openlocfilehash: 1708a3f560f60fe3933406a904d95b4d29890a7f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830778"
---
# <a name="error_condition-class"></a>Класс error_condition

Представляет коды ошибок, определенные пользователем.

## <a name="syntax"></a>Синтаксис

```cpp
class error_condition;
```

## <a name="remarks"></a>Примечания

Объект типа `error_condition` сохраняет значение кода ошибки и указатель на объект, представляющий [категорию](../standard-library/error-category-class.md) кодов ошибок, используемую для сообщаемых ошибках, определяемых пользователем.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[error_condition](#error_condition)|Создает объект типа `error_condition`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[value_type](#value_type)|Тип, представляющий сохраненное значение кода ошибки.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[assign](#assign)|Присваивает условию ошибки значение кода ошибки и категорию.|
|[category](#category)|Возвращает категорию ошибки.|
|[clear](#clear)|Очищает значение кода ошибки и категорию.|
|[message](#message)|Возвращает имя кода ошибки.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator==](#op_eq_eq)|Проверяет равенство между объектами `error_condition`.|
|[operator!=](#op_neq)|Проверяет неравенство между объектами `error_condition`.|
|[operator<](#op_lt)|Проверяет, меньше ли объект `error_condition` переданного для сравнения объекта `error_code`.|
|[operator=](#op_eq)|Присваивает новое значение перечисления объекту `error_condition`.|
|[operator bool](#op_bool)|Преобразует переменную типа `error_condition`.|

### <a name="assign"></a><a name="assign"></a> назначать

Присваивает условию ошибки значение кода ошибки и категорию.

```cpp
void assign(value_type val, const error_category& _Cat);
```

#### <a name="parameters"></a>Параметры

*val*\
Значение кода ошибки для хранения в `error_code`.

*_Cat*\
Категория ошибки для хранения в `error_code`.

#### <a name="remarks"></a>Примечания

Функция-член сохраняет *Val* как значение кода ошибки и указатель на *_Cat*.

### <a name="category"></a><a name="category"></a> категори

Возвращает категорию ошибки.

```cpp
const error_category& category() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на сохраняемую категорию ошибки

#### <a name="remarks"></a>Примечания

### <a name="clear"></a><a name="clear"></a> clear

Очищает значение кода ошибки и категорию.

```cpp
clear();
```

#### <a name="remarks"></a>Примечания

Функция-член сохраняет нулевое значение кода ошибки и указатель на объект [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="error_condition"></a><a name="error_condition"></a> error_condition

Создает объект типа `error_condition`.

```cpp
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Параметры

*val*\
Значение кода ошибки для хранения в `error_condition`.

*_Cat*\
Категория ошибки для хранения в `error_condition`.

*_Errcode*\
Значение перечисления для хранения в `error_condition`.

#### <a name="remarks"></a>Примечания

Первый конструктор сохраняет нулевое значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).

Второй конструктор сохраняет *Val* как значение кода ошибки и указатель на [error_category](../standard-library/error-category-class.md).

Третий конструктор сохраняет `(value_type)_Errcode` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="message"></a><a name="message"></a> Сообщение

Возвращает имя кода ошибки.

```cpp
string message() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Значение `string`, представляющее имя кода ошибки.

#### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение `category().message(value())`.

### <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет равенство между объектами `error_condition`.

```cpp
bool operator==(const error_condition& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на равенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты равны; значение **`false`** , если объекты не равны.

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `category() == right.category() && value == right.value()`.

### <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство между объектами `error_condition`.

```cpp
bool operator!=(const error_condition& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на неравенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_condition` объект не равен объекту, `error_condition` переданному по *правому краю*; в противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `!(*this == right)`.

### <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект `error_condition` переданного для сравнения объекта `error_code`.

```cpp
bool operator<(const error_condition& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Сравниваемый объект `error_condition`.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_condition` объект меньше, чем `error_condition` объект, переданный для сравнения; В противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `category() < right.category() || category() == right.category() && value < right.value()`.

### <a name="operator"></a><a name="op_eq"></a> operator=

Присваивает новое значение перечисления объекту `error_condition`.

```cpp
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
    operator=(Enum _Errcode);
```

#### <a name="parameters"></a>Параметры

*_Errcode*\
Значение перечисления для присвоения объекту `error_condition`.

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `error_condition`, которому функцией-членом присваивается новое значение перечисления.

#### <a name="remarks"></a>Примечания

Функция-член сохраняет `(value_type)error` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category). Он возвращает **`*this`** .

### <a name="operator-bool"></a><a name="op_bool"></a> operator bool

Преобразует переменную типа `error_condition`.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Логическое значение объекта `error_condition`.

#### <a name="remarks"></a>Примечания

Оператор возвращает значение, которое можно преобразовать в, **`true`** только если [значение](#value) не равно нулю. Тип возвращаемого значения можно преобразовать только в **`bool`** , а не в `void *` или другие известные скалярные типы.

### <a name="value"></a>Значение <a name="value"></a>

Возвращает сохраненное значение кода ошибки.

```cpp
value_type value() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение кода ошибки типа [value_type](#value_type).

#### <a name="remarks"></a>Примечания

### <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий сохраненное значение кода ошибки.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Примечания

Определение типа является синонимом для **`int`** .
