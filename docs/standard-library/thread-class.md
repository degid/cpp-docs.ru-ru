---
title: Класс thread
ms.date: 11/04/2016
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.openlocfilehash: 19f7ae1fc95f531f509273f0eb9998c73fe7d47b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215586"
---
# <a name="thread-class"></a>Класс thread

Определяет объект, который позволяет наблюдать за потоком выполнения в приложении и управлять этим потоком.

## <a name="syntax"></a>Синтаксис

```cpp
class thread;
```

## <a name="remarks"></a>Примечания

Объект `thread` можно использовать для наблюдения за потоком выполнения в приложении и управления этим потоком. Объект потока, который создан с помощью конструктора по умолчанию, не связан ни с каким потоком выполнения. Объект потока, который создается с использованием вызываемого объекта, создает новый поток выполнения и вызывает вызываемый объект в этом потоке. Объекты потока можно переместить, но не копировать. Следовательно, поток выполнения может быть связан только с одним объектом потока.

Каждый поток выполнения имеет уникальный идентификатор типа `thread::id`. Функция `this_thread::get_id` возвращает идентификатор вызывающего потока. Функция-член `thread::get_id` возвращает идентификатор потока, который управляется объектом потока. Для объекта потока, созданного конструктором по умолчанию, метод `thread::get_id` возвращает объект с одинаковым значением для всех объектов потока, созданных конструктором по умолчанию; это значение отличается от значения, которое возвращается `this_thread::get_id` для любого потока выполнения, который может быть присоединен во время вызова.

## <a name="members"></a>Элементы

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс thread::id](#id_class)|Уникально идентифицирует соответствующий поток.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[поток](#thread)|Формирует объект `thread`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[соединил](#detach)|Отсоединяет связанный поток от объекта `thread`.|
|[get_id](#get_id)|Возвращает уникальный идентификатор связанного потока.|
|[hardware_concurrency](#hardware_concurrency)|Статический. Возвращает приблизительное число контекстов аппаратного потока.|
|[join](#join)|Блокируется до завершения соответствующего потока.|
|[присоединяем](#joinable)|Указывает, возможно ли присоединение связанного потока.|
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор потока.|
|[swap](#swap)|Заменяет состояние потока заданным объектом `thread`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Thread::operator=](#op_eq)|Связывает поток с текущим объектом `thread`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<thread>

**Пространство имен:** std

## <a name="threaddetach"></a><a name="detach"></a>поток::d етач

Отсоединяет связанный поток. Операционная система становится ответственной за освобождение ресурсов потока при завершении.

```cpp
void detach();
```

### <a name="remarks"></a>Примечания

После вызова `detach` последующие вызовы [get_id](#get_id) возвращают [id](#id_class).

Если поток, связанный с вызываемым объектом, присоединить невозможно, функция создает ошибку [system_error](../standard-library/system-error-class.md) с кодом `invalid_argument`.

Если поток, связанный с вызывающим объектом, является недопустимым, функция создает ошибку `system_error` с кодом `no_such_process`.

## <a name="threadget_id"></a><a name="get_id"></a>Thread:: get_id

Возвращает уникальный идентификатор связанного потока.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [thread::id](#id_class), уникально идентифицирующий связанный поток, или `thread::id()`, если с объектом не связан никакой поток.

## <a name="threadhardware_concurrency"></a><a name="hardware_concurrency"></a>Thread:: hardware_concurrency

Статический метод, который возвращает приблизительное число контекстов аппаратного потока.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Приблизительное число контекстов аппаратного потока. Если значение не может быть вычислено или не является правильно определенным, этот метод возвращает значение 0.

## <a name="threadid-class"></a><a name="id_class"></a>Класс Thread:: ID

Предоставляет уникальный идентификатор для каждого потока выполнения в процессе.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Примечания

Конструктор по умолчанию создает объект, который не равен объекту `thread::id` ни для какого из существующих потоков.

Все созданные конструктором по умолчанию объекты `thread::id` равны.

## <a name="threadjoin"></a><a name="join"></a>Thread:: Join

Блокируется до завершения потока выполнения, связанного с вызывающим объектом.

```cpp
void join();
```

### <a name="remarks"></a>Примечания

Если вызов завершается успешно, последующие вызовы [get_id](#get_id) для вызывающего объекта возвращают значение по умолчанию [thread::id](#id_class), которое не равно значению `thread::id` ни одного из существующих потоков; если вызов завершается неудачно, возвращаемое `get_id` значение остается неизменным.

## <a name="threadjoinable"></a><a name="joinable"></a>Thread:: соединение

Указывает, является ли связанный поток *соединяемым*.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если связанный поток является *соединяемым*; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Объект потока *присоединяем*, если `get_id() != id()`.

## <a name="threadnative_handle"></a><a name="native_handle"></a>Thread:: native_handle

Возвращает тип реализации, представляющий дескриптор потока. Дескриптор потока может использоваться разными способами в зависимости от реализации.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

`native_handle_type` определяется как `HANDLE` Win32, который приводится к `void *`.

## <a name="threadoperator"></a><a name="op_eq"></a>Thread::operator=

Связывает поток заданного объекта с текущим объектом.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Other*\
Объект `thread`.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

Вызовы метода удаляются окончательно, если вызывающий объект присоединяем.

После установления связи `Other` присваивается состояние, созданное по умолчанию.

## <a name="threadswap"></a><a name="swap"></a>поток:: swap

Заменяет состояние потока состоянием заданного объекта `thread`.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Other*\
Объект `thread`.

## <a name="threadthread-constructor"></a><a name="thread"></a>Конструктор потока:: Thread

Формирует объект `thread`.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Ж*\
Определяемая приложением функция, которая должна быть выполнена потоком.

*Конкретного*\
Список аргументов, передаваемых в *F*.

*Other*\
Существующий объект `thread`.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект, который не связан с потоком выполнения. Значение, возвращаемое вызовом `get_id` для созданного объекта, — это `thread::id()`.

Второй конструктор конструирует объект, связанный с новым потоком выполнения, и выполняет псевдо-функцию `INVOKE` , определенную в [\<functional>](../standard-library/functional.md) . Если не хватает ресурсов для начала нового потока, функция создает объект [system_error](../standard-library/system-error-class.md) с кодом ошибки `resource_unavailable_try_again`. Если вызов *F* завершается с неперехваченным исключением, вызывается метод [Terminate](../standard-library/exception-functions.md#terminate) .

Третий конструктор создает объект, связанный с потоком, который, в свою очередь, связан с `Other`. `Other` затем присваивается состояние, созданное по умолчанию.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)
