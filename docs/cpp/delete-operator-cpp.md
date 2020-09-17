---
title: Оператор delete (C++)
ms.date: 08/12/2019
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 19f92e2aa62adf1ede4c0e6ab1187fd9e4106e68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221696"
---
# <a name="delete-operator-c"></a>Оператор delete (C++)

Отменяет выделение блока памяти.

## <a name="syntax"></a>Синтаксис

> [ `::` ] `delete` *приведение выражения*\
> [ `::` ] `delete []` *приведение выражения*

## <a name="remarks"></a>Примечания

Аргумент *Cast-Expression* должен быть указателем на блок памяти, выделенный ранее для объекта, созданного с помощью [оператора New](../cpp/new-operator-cpp.md). **`delete`** Оператор имеет результат типа **`void`** и поэтому не возвращает значение. Пример:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

Использование **`delete`** в указателе на объект, не выделенный с помощью, **`new`** дает непредсказуемые результаты. Однако можно использовать **`delete`** для указателя со значением 0. Такая инициализация означает, что если **`new`** в случае сбоя возвращается значение 0, Удаление результата неудачной **`new`** операции является безвредным. Дополнительные сведения см. [в разделе операторы new и DELETE](../cpp/new-and-delete-operators.md).

**`new`** Операторы и **`delete`** можно также использовать для встроенных типов, включая массивы. Если `pointer` ссылается на массив, поместите пустые скобки ( `[]` ) перед `pointer` :

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

Использование **`delete`** оператора для объекта освобождает его память. Программа, которая разыменовывает указатель после удаления объекта, может создать непрогнозируемый результат или вызвать сбой.

Если **`delete`** используется для освобождения памяти для объекта класса C++, деструктор объекта вызывается до освобождения памяти объекта (если у объекта есть деструктор).

Если операнд **`delete`** оператора является изменяемым l-значением, его значение не определено после удаления объекта.

Если указан параметр компилятора [/SDL (включить дополнительные проверки безопасности)](/cpp/build/reference/sdl-enable-additional-security-checks) , операнду оператора присваивается **`delete`** недопустимое значение после удаления объекта.

## <a name="using-delete"></a>Использование оператора delete

Существует два синтаксических варианта для [оператора delete](../cpp/delete-operator-cpp.md): один для единичных объектов, а другой для массивов объектов. В следующем фрагменте кода показано, как они отличаются:

```cpp
// expre_Using_delete.cpp
struct UDType
{
};

int main()
{
   // Allocate a user-defined object, UDObject, and an object
   //  of type double on the free store using the
   //  new operator.
   UDType *UDObject = new UDType;
   double *dObject = new double;
   // Delete the two objects.
   delete UDObject;
   delete dObject;
   // Allocate an array of user-defined objects on the
   // free store using the new operator.
   UDType (*UDArr)[7] = new UDType[5][7];
   // Use the array syntax to delete the array of objects.
   delete [] UDArr;
}
```

Следующие два варианта приводят к неопределенным результатам: использование формы массива delete ( `delete []` ) для объекта и использование немассивного класса DELETE в массиве.

## <a name="example"></a>Пример

Примеры использования см **`delete`** . в разделе [оператор New](../cpp/new-operator-cpp.md).

## <a name="how-delete-works"></a>Принцип работы delete

Оператор delete вызывает **оператор функции Delete**.

Для объектов, не имеющих тип класса ([класс](../cpp/class-cpp.md), [Структура](../cpp/struct-cpp.md)или [объединение](../cpp/unions.md)), вызывается оператор глобального удаления. Для объектов типа класса имя функции освобождения разрешается в глобальной области, если выражение delete начинается с оператора унарного разрешения области ( `::` ). В противном случае перед освобождением памяти оператор удаления вызывает деструктор объекта (если указатель не имеет значения null). Оператор удаления можно определять отдельно для каждого класса; если для некоторого класса такое определение отсутствует, вызывается глобальный оператор удаления. Если выражение удаления используется для освобождения объекта класса, статический тип которого имеет виртуальный деструктор, функция освобождение разрешается через виртуальный деструктор динамического типа объекта.

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)\
[Словами](../cpp/keywords-cpp.md)\
[Операторы создания и удаления](../cpp/new-and-delete-operators.md)
