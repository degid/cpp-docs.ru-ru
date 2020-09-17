---
title: Класс critical_section
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: f7df639a879bad7af1b4de401460ff298e466c78
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215820"
---
# <a name="critical_section-class"></a>Класс critical_section

Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class critical_section;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`native_handle_type`|Ссылка на объект `critical_section`.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс critical_section::scoped_lock](#critical_section__scoped_lock_class)|Защищенная от исключения оболочка RAII для `critical_section` объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[critical_section](#ctor)|Конструирует новую критическую секцию.|
|[Деструктор ~ critical_section](#dtor)|Уничтожает критическую секцию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Получает этот критический раздел.|
|[native_handle](#native_handle)|Возвращает собственный машинный код, зависящий от платформы, если он существует.|
|[try_lock](#try_lock)|Пытается получить блокировку без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.|
|[блокирован](#unlock)|Разблокирует критическую секцию.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`critical_section`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="critical_section"></a><a name="ctor"></a>critical_section

Конструирует новую критическую секцию.

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a>~ critical_section

Уничтожает критическую секцию.

```cpp
~critical_section();
```

### <a name="remarks"></a>Примечания

Ожидается, что блокировка больше не удерживается при выполнении деструктора. Разрешение критической секции, уничтожения с блокировкой, по-прежнему приводит к неопределенному поведению.

## <a name="lock"></a><a name="lock"></a>скрыть

Получает этот критический раздел.

```cpp
void lock();
```

### <a name="remarks"></a>Примечания

Часто безопаснее использовать конструкцию [scoped_lock](#critical_section__scoped_lock_class) для получения и освобождения `critical_section` объекта в безопасном для исключения виде.

Если блокировка уже удерживается вызывающим контекстом, будет выдано исключение [improper_lock](improper-lock-class.md) .

## <a name="native_handle"></a><a name="native_handle"></a>native_handle

Возвращает собственный машинный код, зависящий от платформы, если он существует.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на критическую секцию.

### <a name="remarks"></a>Примечания

`critical_section`Объект не связан с платформой машинного кода, зависящей от платформы, для операционной системы Windows. Метод просто возвращает ссылку на сам объект.

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a>Класс critical_section:: scoped_lock

Защищенная от исключения оболочка RAII для `critical_section` объекта.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock:: scoped_lock

Создает `scoped_lock` объект и получает `critical_section` объект, переданный в `_Critical_section` параметре. Если критическая секция удерживается другим потоком, этот вызов блокируется.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Параметры

*_Critical_section*<br/>
Критическая секция для блокировки.

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock

Уничтожает `scoped_lock` объект и освобождает критическую секцию, заданную в его конструкторе.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Пытается получить блокировку без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, если блокировка была получена; в **`true`** противном случае — значение **`false`** .

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Количество миллисекунд перед истечением времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Значение, если блокировка была получена; в **`true`** противном случае — значение **`false`** .

## <a name="unlock"></a><a name="unlock"></a>блокирован

Разблокирует критическую секцию.

```cpp
void unlock();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс reader_writer_lock](reader-writer-lock-class.md)
