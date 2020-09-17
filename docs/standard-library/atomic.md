---
title: '&lt;atomic&gt;'
description: Описывает типы и функции, доступные в заголовке Atomic стандартной библиотеки C++.
ms.date: 12/06/2019
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
ms.openlocfilehash: 3c5f732dbda701eb7744b1b25a9a8e7426f7a3e2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203907"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Определяет классы и шаблоны классов, используемые для создания типов, поддерживающих атомарные операции.

## <a name="syntax"></a>Синтаксис

```cpp
#include <atomic>
```

## <a name="remarks"></a>Примечания

> [!NOTE]
> В коде, компилируемом с помощью [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md), этот заголовок блокируется. В Visual Studio 2017 и более поздних версиях не рекомендуется использовать **/clr: pure** и **/clr: Сейф** .

Атомарная операция имеет 2 ключевых свойства, позволяющих организовать безопасный доступ к объекту из нескольких потоков без использования мьютексов.

- Так как атомарная операция неделима, вторая атомарная операция над одним и тем же объектом из другого потока может получить состояние объекта только до или после первой атомарной операции.

- На основе своего аргумента [memory_order](../standard-library/atomic-enums.md#memory_order_enum) атомарная операция устанавливает требования упорядоченности для видимости влияния других атомарных операций в том же потоке. Следовательно, она подавляет оптимизации компилятора, которые нарушают требования к упорядоченности.

На некоторых платформах бывает невозможно эффективно реализовать атомарные операции для некоторых типов без использования блокировок `mutex`. Атомарный тип является *неблокируемым* , если никакие атомарные операции с этим типом не используют блокировки.

**C++ 11**. в обработчиках сигналов можно выполнять атомарные операции с объектом, `obj` Если `obj.is_lock_free()` или имеет `atomic_is_lock_free(x)` значение true.

Класс [atomic_flag](../standard-library/atomic-flag-structure.md) предоставляет минимальный атомарный тип, который содержит **`bool`** флаг. Его операции всегда являются неблокирующими.

Шаблон класса `atomic<T>` сохраняет объект своего типа аргумента `T` и предоставляет атомарный доступ к этому сохраненному значению. Его можно создать с помощью любого типа, который может быть скопирован с помощью [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) и проверен на равенство с помощью [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md). В частности, его можно использовать с пользовательскими типами, которые соответствуют этим требованиям, и во многих случаях с типами с плавающей запятой.

Шаблон также имеет ряд специализаций для целочисленных типов и частичную специализацию для указателей. Эти специализации предоставляют дополнительные операции, которые недоступны в первичном шаблоне.

## <a name="pointer-specializations"></a>Специализации для указателей

Частичные специализации `atomic<T *>` применяются для всех типов указателей. Они предоставляют методы для расчетов с указателями.

## <a name="integral-specializations"></a>Специализации для целочисленных типов

Специализации `atomic<integral>` применяются для всех целочисленных типов. Они предоставляют дополнительные операции, которые недоступны в первичном шаблоне.

Каждый тип `atomic<integral>` имеет соответствующий макрос, который можно использовать в `if directive` для определения во время компиляции, являются ли операции этого типа неблокирующими. Если значение макроса равно нулю, операции с типом не блокируются без блокировки. Если значение равно 1, операции могут быть неблокирующими, и требуется проверка времени выполнения. Если значение равно 2, операции являются неблокирующими. Вы можете использовать функцию `atomic_is_lock_free` для определения во время выполнения, являются ли операции с типом неблокирующими.

Для каждого из целочисленных типов существует соответствующий именованный атомарный тип, который управляет объектом этого целочисленного типа. Каждый тип `atomic_integral` имеет тот же набор функций-членов, что и соответствующий экземпляр `atomic<T>`, и может быть передан в любую из атомарных функций, не являющихся членами.

|Тип `atomic_integral`|Целочисленный тип|Макрос `atomic_is_lock_free`|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**`char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**`signed char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**`unsigned char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|**`char16_t`**|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|**`char32_t`**|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**`wchar_t`**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**`short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**`unsigned short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**`int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**`unsigned int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**`long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**`unsigned long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**`long long`**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**`unsigned long long`**|ATOMIC_LLONG_LOCK_FREE|

Имена typedef существуют для специализаций атомарного шаблона для некоторых типов, определенных в заголовке \<inttypes.h> .

|Атомарный тип|Имя typedef|
|-----------------|------------------|
|`atomic_int8_t`|`atomic<int8_t>`|
|`atomic_uint8_t`|`atomic<uint8_t>`|
|`atomic_int16_t`|`atomic<int16_t>`|
|`atomic_uint16_t`|`atomic<uint16_t>`|
|`atomic_int32_t`|`atomic<int32_t>`|
|`atomic_uint32_t`|`atomic<uint32_t>`|
|`atomic_int64_t`|`atomic<int64_t>`|
|`atomic_uint64_t`|`atomic<uint64_t>`|
|`atomic_int_least8_t`|`atomic<int_least8_t>`|
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|
|`atomic_int_least16_t`|`atomic<int_least16_t>`|
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|
|`atomic_int_least32_t`|`atomic<int_least32_t>`|
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|
|`atomic_int_least64_t`|`atomic<int_least64_t>`|
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|
|`atomic_intptr_t`|`atomic<intptr_t>`|
|`atomic_uintptr_t`|`atomic<uintptr_t>`|
|`atomic_size_t`|`atomic<size_t>`|
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|
|`atomic_intmax_t`|`atomic<intmax_t>`|
|`atomic_uintmax_t`|`atomic<uintmax_t>`|

## <a name="structs"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[Структура atomic](../standard-library/atomic-structure.md)|Описывает объект, который выполняет атомарные операции с сохраненным значением.|
|[Структура atomic_flag](../standard-library/atomic-flag-structure.md)|Описывает объект, который атомарно задает и очищает **`bool`** флаг.|

## <a name="enums"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление memory_order](../standard-library/atomic-enums.md#memory_order_enum)|Предоставляет символьные имена для операций синхронизации в областях памяти. Эти операции влияют на то, как присвоения в одном потоке становятся видимыми в другом.|

## <a name="functions"></a>Функции

В следующем списке функции, которые не заканчиваются на, `_explicit` имеют семантику соответствующего объекта `_explicit` , за исключением того, что у них есть неявные [memory_order](../standard-library/atomic-enums.md#memory_order_enum) аргументы `memory_order_seq_cst` .

|Имя|Описание|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|Выполняет *атомарную операцию сравнения и обмена*.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|Выполняет *атомарную операцию сравнения и обмена*.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|Выполняет *слабую атомарную операцию сравнения и обмена*.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|Выполняет *слабую атомарную операцию сравнения и обмена*.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Заменяет сохраненное значение.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Заменяет сохраненное значение.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Добавляет указанное значение к существующему хранимому значению.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Добавляет указанное значение к существующему хранимому значению.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Выполняет побитовую операцию `and` с указанным значением и существующим хранимым значением.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Выполняет побитовую операцию `and` с указанным значением и существующим хранимым значением.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Выполняет побитовую операцию `or` с указанным значением и существующим хранимым значением.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Выполняет побитовую операцию `or` с указанным значением и существующим хранимым значением.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Вычитает указанное значение из существующего хранимого значения.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Вычитает указанное значение из существующего хранимого значения.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Выполняет побитовую операцию `exclusive or` с указанным значением и существующим хранимым значением.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Выполняет побитовую операцию `exclusive or` с указанным значением и существующим хранимым значением.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Устанавливает флаг в `atomic_flag` объекте в значение **`false`** .|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Устанавливает флаг в `atomic_flag` объекте в значение **`false`** .|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Устанавливает флаг в `atomic_flag` объекте в значение **`true`** .|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Устанавливает флаг в `atomic_flag` объекте в значение **`true`** .|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|Задает сохраненное значение в объекте `atomic`.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Указывает, являются ли атомарные операции с указанным объектом неблокирующими.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Атомарным образом получает значение.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Атомарным образом получает значение.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Действует как *граница*, устанавливающая требования упорядочивания памяти между границами в вызывающем потоке, который имеет обработчики сигнала, выполняющиеся в том же потоке.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Атомарным образом сохраняет значение.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Атомарным образом сохраняет значение.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|Действует как *граница*, которая устанавливает требования упорядочивания относительно других границ.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Разрывает возможную цепочку зависимостей.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
