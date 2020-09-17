---
title: Исключение bad_cast
ms.date: 10/04/2019
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 2efe5be5e44751831a56b29cfc629df2d21843f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229185"
---
# <a name="bad_cast-exception"></a>Исключение bad_cast

**Bad_cast** исключение создается **`dynamic_cast`** оператором в результате неудачного приведения к ссылочному типу.

## <a name="syntax"></a>Синтаксис

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Примечания

Интерфейс для **bad_cast** :

```cpp
class bad_cast : public exception
```

Следующий код содержит пример сбоя **`dynamic_cast`** , который вызывает исключение **bad_cast** .

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class Shape {
public:
   virtual void virtualfunc() const {}
};

class Circle: public Shape {
public:
   virtual void virtualfunc() const {}
};

using namespace std;
int main() {
   Shape shape_instance;
   Shape& ref_shape = shape_instance;
   try {
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);
   }
   catch (bad_cast b) {
      cout << "Caught: " << b.what();
   }
}
```

Исключение возникает, так как объект, который поддается (Shape), не является производным от указанного типа приведения (Circle). Чтобы исключение не создавалось, добавьте в функцию `main` следующие объявления:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Затем следует обратить смысл приведения в **`try`** блоке следующим образом:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[bad_cast](#bad_cast)|Конструктор для объектов типа `bad_cast`.|

### <a name="functions"></a>Функции

|Компонент|Описание:|
|-|-|
|[What](#what)|TBD|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Оператор присваивания, который присваивает один `bad_cast` объект другому.|

## <a name="bad_cast"></a><a name="bad_cast"></a>bad_cast

Конструктор для объектов типа `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="operator"></a><a name="op_eq"></a>Оператор =

Оператор присваивания, который присваивает один `bad_cast` объект другому.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a><a name="what"></a>What

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>См. также статью

[Оператор dynamic_cast](../cpp/dynamic-cast-operator.md)\
[Словами](../cpp/keywords-cpp.md)\
[Современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)
