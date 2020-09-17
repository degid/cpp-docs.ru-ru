---
title: '&lt;новую&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: 0fe2d0e57c0746f25187028b85157d66ee736ca4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836430"
---
# <a name="ltnewgt"></a>&lt;новую&gt;

Определяет несколько функций и типов, управляющих выделением и освобождением памяти, которая находится под управлением программы. Он также определяет компоненты для создания отчетов об ошибках управления хранилищем.

## <a name="requirements"></a>Требования

**Заголовок:**\<new>

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Некоторые функции, объявленные в этом заголовке, можно заменить. Данная реализация предоставляет версию по умолчанию, поведение которой описано в этом документе. Однако программа может определить функцию с той же самой сигнатурой, чтобы заменить версию по умолчанию во время компоновки. Версия, на которую производится замена, должна удовлетворять требованиям, описанным в этом документе.

## <a name="members"></a>Элементы

### <a name="objects"></a>Объекты

|Имя|Описание|
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Предоставляет объект, который будет использоваться в качестве аргумента для **`nothrow`** версий **`new`** и **`delete`** .|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Тип, который указывает на функцию, подходящую для использования в качестве нового обработчика.|
|[hardware_constructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||
|[hardware_destructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[get_new_handler](../standard-library/new-functions.md#get_new_handler)||
|[лаундер](../standard-library/new-functions.md#launder)||
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Устанавливает пользовательскую функцию, вызываемую в случае сбоя оператора new при попытке выделения памяти.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[оператор DELETE](../standard-library/new-operators.md#op_delete)|Функция, вызываемая с помощью выражения delete для отмены выделения хранилища для отдельных объектов.|
|[оператор delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Функция, вызываемая с помощью выражения delete для отмены выделения хранилища для массива объектов.|
|[Оператор New](../standard-library/new-operators.md#op_new)|Функция, вызываемая с помощью выражения new для выделения хранилища для отдельных объектов.|
|[оператор new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Функция, вызываемая с помощью выражения new для выделения хранилища для массива объектов.|

### <a name="enums"></a>Перечисления

|Имя|Описание|
|-|-|
|[align_val_t](../standard-library/new-operators.md#op_align_val_t)||

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[Класс bad_alloc](../standard-library/bad-alloc-class.md)|Данный класс описывает исключение, возникновение которого указывает на то, что запрос на выделение памяти не выполнен.|
|[Класс bad_array_new_length](../standard-library/bad-array-new-length.md)||
|[Класс nothrow_t](../standard-library/nothrow-t-structure.md)|Этот класс используется как параметр функции для оператора new, чтобы показать, что для указания на ошибку выделения данная функция должна возвращать пустой указатель (NULL), а не вызывать исключение.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
