---
title: '&lt;memory&gt;'
ms.date: 08/04/2019
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
helpviewer_keywords:
- memory header
ms.openlocfilehash: 0e3ce4a4411bd6d4c352802a96c97e93c66491df
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836469"
---
# <a name="ltmemorygt"></a>&lt;memory&gt;

Определяет класс, оператор и несколько шаблонов, позволяющих выделять и освобождать объекты.

## <a name="requirements"></a>Требования

**Заголовок:**\<memory>

**Пространство имен:** std

## <a name="members"></a>Элементы

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[AddressOf](../standard-library/memory-functions.md#addressof)|Получает истинный адрес объекта.|
|[align](../standard-library/memory-functions.md#align)|Возвращает указатель на диапазон заданного размера на основе указанного выравнивания и начального адреса.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Создает `shared_ptr` для объектов, выделенных и созданных для заданного типа с указанным распределителем.|
|[atomic_compare_exchange_strong](../standard-library/memory-functions.md#atomic_compare_exchange_strong)||
|[atomic_compare_exchange_weak](../standard-library/memory-functions.md#atomic_compare_exchange_weak)||
|[atomic_compare_exchange_strong_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_strong_explicit)||
|[atomic_compare_exchange_weak_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_weak_explicit)||
|[atomic_exchange](../standard-library/memory-functions.md#atomic_exchange)||
|[atomic_exchange_explicit](../standard-library/memory-functions.md#atomic_exchange_explicit)||
|[atomic_is_lock_free](../standard-library/memory-functions.md#atomic_is_lock_free)||
|[atomic_load](../standard-library/memory-functions.md#atomic_load)||
|[atomic_load_explicit](../standard-library/memory-functions.md#atomic_load_explicit)||
|[atomic_store](../standard-library/memory-functions.md#atomic_store)||
|[atomic_store_explicit](../standard-library/memory-functions.md#atomic_store_explicit)||
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Постоянное приведение к `shared_ptr`.|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Сообщает сборщику мусора, что символы, начинающиеся с указанного адреса и попадающие в блок указанного размера, не содержат трассируемых указателей.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Уведомляет сборщик мусора, что указанный адрес относится к выделенной памяти и является доступным.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|Удаляет объекты, выделенные с помощью `operator new`. Подходит для использования с `unique_ptr`.|
|[destroy_at](../standard-library/memory-functions.md#destroy_at)|Сокращенный `destroy` метод.|
|[завершить](../standard-library/memory-functions.md#destroy)|Сокращенный `destroy` метод.|
|[destroy_n](../standard-library/memory-functions.md#destroy_n)|Сокращенный `destroy` метод.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Динамическое приведение к `shared_ptr`.|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Получение метода удаления из `shared_ptr`.|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Возвращает тип безопасности указателя, подразумеваемый любым сборщиком мусора.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Выделяет временное хранилище для последовательности элементов, которая не превышает заданное число элементов.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|Создает и возвращает `shared_ptr`, указывающий на объект, для которого выделена память, созданный из нуля или нескольких аргументов с помощью распределителя по умолчанию.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Создает и возвращает [unique_ptr](../standard-library/unique-ptr-class.md), указывающий на выделенный объект, созданный из нуля или нескольких аргументов.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|Перечисление всех возможных возвращаемых значений для `get_pointer_safety`.|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Отменяет выделение временной памяти, выделенной с помощью функции шаблона `get_temporary_buffer`.|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Статическое приведение к `shared_ptr`.|
|[swap](../standard-library/memory-functions.md#swap)|Обмен двух объектов `shared_ptr` или `weak_ptr`.|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, теперь могут содержать трассируемые указатели.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Уведомляет `garbage_collector`, что указанная область памяти является недоступной.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Копирует объекты из указанного входного диапазона в неинициализированный конечный диапазон.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Создает копию заданного числа элементов из итератора ввода. Копии помещаются в прямой итератор.|
|[uninitialized_default_construct](../standard-library/memory-functions.md#uninitialized_default_construct)|Сокращенный `uninitialized_default_construct` метод.|
|[uninitialized_default_construct_n](../standard-library/memory-functions.md#uninitialized_default_construct_n)|Сокращенный `uninitialized_construct` метод.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Копирует объекты с указанным значением в неинициализированный конечный диапазон.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Копирует объекты с указанным значением в указанное число элементов в неинициализированном конечном диапазоне.|
|[uninitialized_move](../standard-library/memory-functions.md#uninitialized_move)|Сокращенный `uninitialized_move` метод.|
|[uninitialized_move_n](../standard-library/memory-functions.md#uninitialized_move_n)|Сокращенный `uninitialized_move` метод.|
|[uninitialized_value_construct](../standard-library/memory-functions.md#uninitialized_value_construct)|Сокращенный `uninitialized_value_construct` метод.|
|[uninitialized_value_construct_n](../standard-library/memory-functions.md#uninitialized_value_construct_n)|Сокращенный `uninitialized_value_construct` метод.|
|[uses_allocator_v](../standard-library/memory-functions.md#uses_allocator_v)||

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/memory-operators.md#op_neq)|Проверяет на неравенство между объектами распределителя указанного класса.|
|[operator==](../standard-library/memory-operators.md#op_eq_eq)|Проверяет на равенство объекты распределителя указанного класса.|
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Проверяет, является ли один объект распределителя больше или равным второму объекту распределителя указанного класса.|
|[operator<](../standard-library/memory-operators.md#op_lt)|Проверяет, является ли один объект распределителя меньше или равным второму объекту распределителя указанного класса.|
|[operator\<=](../standard-library/memory-operators.md#op_gt_eq)|Проверяет, является ли один объект меньше или равным второму объекту указанного класса.|
|[operator>](../standard-library/memory-operators.md#op_gt)|Проверяет, является ли один объект больше второго объекта указанного класса.|
|[operator<<](../standard-library/memory-operators.md#op_lt_lt)|Вставляет `shared_ptr`.|

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[allocator](../standard-library/allocator-class.md)|Шаблон класса описывает объект, который управляет выделением и освобождением памяти для массивов объектов типа **Type**.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Описывает объект, определяющий все сведения, необходимые контейнеру с распределителем.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|Шаблон класса описывает объект, хранящий указатель на выделенный объект типа **Type** <strong>\*</strong> , который гарантирует, что объект, на который он указывает, удаляется, когда его включающий auto_ptr уничтожается.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Сообщает о необрабатываемом исключении weak_ptr.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Помогает сформировать `shared_ptr`.|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|Предоставляет сведения, необходимые объекту типа `allocator_traits` для описания распределителя с типом указателя `Ptr` .|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Класс-адаптер, который предоставляется, чтобы алгоритмы могли сохранять свои результаты в неинициализированной памяти.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Помещает объект с динамическим выделением памяти в оболочку интеллектуального указателя с подсчитанными ссылками.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Хранит указатель на собственный объект. Указатель не принадлежит никаким другим `unique_ptr`. `unique_ptr` удаляется при удалении владельца.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Создает оболочку слабо связанного указателя.|

### <a name="structures"></a>Структуры

|Имя|Описание|
|-|-|
|[allocator_arg_t](../standard-library/allocator-class.md#allocator_arg_t)||
|[default_delete](../standard-library/default-delete-struct.md)||
|hash|Предоставляет перегрузки, специализированные для `unique_ptr` и `shared_ptr` .|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Разрешает смешанные сравнения общих и слабых указателей на основе собственности.|
|[uses_allocator](../standard-library/allocator-class.md#uses_allocator)||

### <a name="specializations"></a>Специализации

|Имя|Описание|
|-|-|
|[allocator\<void>](../standard-library/allocator-void-class.md)|Специализация распределителя шаблонов класса для типа **`void`** , определяющая только типы элементов, имеющие смысл в этом специализированном контексте.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
