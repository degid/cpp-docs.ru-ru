---
title: '&lt;необязательный параметр&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: 31a3d9aad539e45bb835331a4ef63690d0e16f49
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842680"
---
# <a name="ltoptionalgt"></a>&lt;необязательный параметр&gt;

Определяет шаблон класса контейнера `optional` и несколько вспомогательных шаблонов.

## <a name="requirements"></a>Требования

**Заголовок:**\<optional>

**Пространство имен:** std

## <a name="members"></a>Элементы

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Проверяет, равен ли объект другому объекту.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|Проверяет, не равен ли объект другому объекту.|
|[operator<](../standard-library/optional-operators.md#op_lt)|Проверяет, что объект слева меньше объекта справа.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева меньше или равен объекту справа.|
|[operator>](../standard-library/optional-operators.md#op_gt)|Проверяет, что объект слева больше объекта справа.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева больше или равен объекту справа.|

> [!NOTE]
> Помимо реляционных сравнений, \<optional> операторы также поддерживают сравнение с **нуллопт** и `T` .

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Делает объект необязательным.|
|[swap](../standard-library/optional-functions.md#swap)|Меняет местами содержащиеся значения двух `optional` объектов.|

### <a name="classes-and-structs"></a>Классы и структуры

|Имя|Описание|
|-|-|
|hash|Возвращает хэш содержащегося объекта.|
|[необязательный класс](../standard-library/optional-class.md)|Описывает объект, который может или не может содержать значение.|
|[Структура nullopt_t](../standard-library/nullopt-t-structure.md)|Описывает объект, который не удерживает значение.|
|[класс bad_optional_access](../standard-library/bad-optional-access-class.md)|Описывает объект, вызываемый как исключение для сообщения о попытке доступа к значению, которое отсутствует.|

### <a name="objects"></a>Объекты

|Имя|Описание|
|-|-|
|[нуллопт](../standard-library/optional-functions.md#nullopt)|Экземпляр `nullopt_t` для сравнений.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
