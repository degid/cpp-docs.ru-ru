---
title: Класс error_code
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
helpviewer_keywords:
- std::error_code
- std::error_code::value_type
- std::error_code::assign
- std::error_code::category
- std::error_code::clear
- std::error_code::default_error_condition
- std::error_code::message
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
ms.openlocfilehash: 5bbd67d2967a1a6d070ece54ea464a2a5a2deac9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844461"
---
# <a name="error_code-class"></a>Класс error_code

Представляет системные ошибки низкого уровня, относящиеся к конкретной специализации.

## <a name="syntax"></a>Синтаксис

```cpp
class error_code;
```

## <a name="remarks"></a>Примечания

Объект типа `error_code` сохраняет значение кода ошибки и указатель на объект, представляющий [категорию](../standard-library/error-category-class.md) кодов ошибок, которые описывают сообщенные низкоуровневые системные ошибки.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[error_code](#error_code)|Создает объект типа `error_code`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[value_type](#value_type)|Тип, представляющий сохраненное значение кода ошибки.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[assign](#assign)|Присваивает коду ошибки значение кода ошибки и категорию.|
|[category](#category)|Возвращает категорию ошибки.|
|[clear](#clear)|Очищает значение кода ошибки и категорию.|
|[default_error_condition](#default_error_condition)|Возвращает условие ошибки по умолчанию.|
|[message](#message)|Возвращает имя кода ошибки.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator==](#op_eq_eq)|Проверяет равенство между объектами `error_code`.|
|[operator!=](#op_neq)|Проверяет неравенство между объектами `error_code`.|
|[operator<](#op_lt)|Проверяет, меньше ли объект `error_code` переданного для сравнения объекта `error_code`.|
|[operator=](#op_eq)|Присваивает новое значение перечисления объекту `error_code`.|
|[operator bool](#op_bool)|Преобразует переменную типа `error_code`.|

### <a name="assign"></a><a name="assign"></a> назначать

Присваивает коду ошибки значение кода ошибки и категорию.

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

#### <a name="remarks"></a>Примечания

### <a name="clear"></a><a name="clear"></a> clear

Очищает значение кода ошибки и категорию.

```cpp
clear();
```

#### <a name="remarks"></a>Примечания

Функция-член сохраняет нулевое значение кода ошибки и указатель на объект [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="default_error_condition"></a><a name="default_error_condition"></a> default_error_condition

Возвращает условие ошибки по умолчанию.

```cpp
error_condition default_error_condition() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Условие [error_condition](../standard-library/error-condition-class.md), задаваемое условием [default_error_condition](../standard-library/error-category-class.md#default_error_condition).

#### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение `category().default_error_condition(value())`.

### <a name="error_code"></a><a name="error_code"></a> error_code

Создает объект типа `error_code`.

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Параметры

*val*\
Значение кода ошибки для хранения в `error_code`.

*_Cat*\
Категория ошибки для хранения в `error_code`.

*_Errcode*\
Значение перечисления для хранения в `error_code`.

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

Проверяет равенство между объектами `error_code`.

```cpp
bool operator==(const error_code& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на равенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты равны; значение **`false`** , если объекты не равны.

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `category() == right.category() && value == right.value()`.

### <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство между объектами `error_code`.

```cpp
bool operator!=(const error_code& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект для проверки на неравенство.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_code` объект не равен объекту, `error_code` переданному по *правому краю*; в противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `!(*this == right)`.

### <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект `error_code` переданного для сравнения объекта `error_code`.

```cpp
bool operator<(const error_code& right) const;
```

#### <a name="parameters"></a>Параметры

*right*\
Объект error_code для сравнения.

#### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `error_code` объект меньше, чем `error_code` объект, переданный для сравнения; В противном случае — **`false`** .

#### <a name="remarks"></a>Примечания

Оператор-член возвращает `category() < right.category() || category() == right.category() && value < right.value()`.

### <a name="operator"></a><a name="op_eq"></a> operator=

Присваивает новое значение перечисления объекту `error_code`.

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value, error_code>::type&
    operator=(_Enum _Errcode);
```

#### <a name="parameters"></a>Параметры

*_Errcode*\
Значение перечисления для присвоения объекту `error_code`.

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `error_code`, которому функцией-членом присваивается новое значение перечисления.

#### <a name="remarks"></a>Примечания

Функция-член сохраняет `(value_type)_Errcode` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category). Он возвращает **`*this`** .

### <a name="operator-bool"></a><a name="op_bool"></a> operator bool

Преобразует переменную типа `error_code`.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Логическое значение объекта `error_code`.

#### <a name="remarks"></a>Примечания

Оператор возвращает значение, которое можно преобразовать в, **`true`** только если [значение](#value) не равно нулю. Тип возвращаемого значения можно преобразовать только в **`bool`** , а не в `void *` или другие известные скалярные типы.

### <a name="value"></a>Значение <a name="value"></a>

Возвращает сохраненное значение кода ошибки.

```cpp
value_type value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение кода ошибки типа [value_type](#value_type).

### <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий сохраненное значение кода ошибки.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Примечания

Это определение типа является синонимом для **`int`** .
