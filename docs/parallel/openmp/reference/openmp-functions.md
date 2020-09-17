---
title: Функции OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
ms.openlocfilehash: 0475a83ba259ed00bbcb9ddaba99a1556b35f613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317143"
---
# <a name="openmp-functions"></a>Функции OpenMP

Предоставляет ссылки на функции, используемые в API OpenMP.

Реализация стандарта OpenMP в изобразительного сена включает в себя следующие функции и типы данных.

Для выполнения среды:

|Компонент|Описание|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|Устанавливает количество потоков в предстоящих параллельных регионах, если не перекрывается [num_threads](openmp-clauses.md#num-threads) положением.|
|[omp_get_num_threads](#omp-get-num-threads)|Возвращает количество потоков в параллельной области.|
|[omp_get_max_threads](#omp-get-max-threads)|Возвращает целый ряд, равный или превышающий количество потоков, которые будут доступны, если на этом этапе код был определен параллельный регион без [num_threads.](openmp-clauses.md#num-threads)|
|[omp_get_thread_num](#omp-get-thread-num)|Возвращает номер потока, исполняемого потоком, в команде потоков.|
|[omp_get_num_procs](#omp-get-num-procs)|Возвращает количество процессоров, доступных при вызове функции.|
|[omp_in_parallel](#omp-in-parallel)|Возвращает ненулевой, если вызов из параллельной области.|
|[omp_set_dynamic](#omp-set-dynamic)|Означает, что количество потоков, доступных в предстоящих параллельных регионах, может быть скорректировано к времени выполнения.|
|[omp_get_dynamic](#omp-get-dynamic)|Возвращает значение, указывающее, можно ли скорректировать количество потоков, доступных в предстоящих параллельных регионах, к времени выполнения.|
|[omp_set_nested](#omp-set-nested)|Позволяет вложенный параллелизм.|
|[omp_get_nested](#omp-get-nested)|Возвращает значение, указывающее, включен о включении вложенного параллеля.|

Для блокировки:

|Компонент|Описание|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|Инициализирует простой замок.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Инициализирует замок.|
|[omp_destroy_lock](#omp-destroy-lock)|Не инициирует блокировку.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Не инициирует сяочку.|
|[omp_set_lock](#omp-set-lock)|Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.|
|[omp_unset_lock](#omp-unset-lock)|Выпускает замок.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Выпускает вложенный замок.|
|[omp_test_lock](#omp-test-lock)|Попытки установить блокировку, но не блокирует выполнение потока.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Попытки установить блокировку, но не блокирует выполнение потока.|

|Тип данных|Описание|
|---------|-----------|
|`omp_lock_t`|Тип, который сохраняет статус блокировки, доступен ли блокировка или если поток владеет замком.|
|`omp_nest_lock_t`|Тип, в котором содержится одна из следующих частей информации о блокировке: доступен ли блокировка, и личность потока, который владеет замком и количеством вложений.|

Для процедур синхронизации:

|Компонент|Описание|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|Возвращает значение в секундах времени, прошедшего с какой-то точки.|
|[omp_get_wtick](#omp-get-wtick)|Возвращает количество секунд между тиками часов процессора.|

## <a name="omp_destroy_lock"></a><a name="omp-destroy-lock"></a>omp_destroy_lock

Не инициирует блокировку.

```cpp
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_lock_t` которая была инициализирована с [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_destroy_nest_lock omp_destroy_lock.](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)

### <a name="example"></a>Пример

Смотрите [omp_init_lock](#omp-init-lock) примериспользования `omp_destroy_lock`за использование .

## <a name="omp_destroy_nest_lock"></a><a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Не инициирует сяочку.

```cpp
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_nest_lock_t` которая была инициализирована с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_destroy_nest_lock omp_destroy_lock.](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)

### <a name="example"></a>Пример

Смотрите [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_destroy_nest_lock`.

## <a name="omp_get_dynamic"></a><a name="omp-get-dynamic"></a>omp_get_dynamic

Возвращает значение, указывающее, можно ли скорректировать количество потоков, доступных в предстоящих параллельных регионах, к времени выполнения.

```cpp
int omp_get_dynamic();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает, что потоки будут динамически скорректированы.

### <a name="remarks"></a>Примечания

Динамическая регулировка потоков указана [с omp_set_dynamic](#omp-set-dynamic) и [OMP_DYNAMIC.](openmp-environment-variables.md#omp-dynamic)

Для получения дополнительной информации см [omp_set_dynamic.](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)

### <a name="example"></a>Пример

См [omp_set_dynamic](#omp-set-dynamic) примере `omp_get_dynamic`использования .

## <a name="omp_get_max_threads"></a><a name="omp-get-max-threads"></a>omp_get_max_threads

Возвращает целый ряд, равный или превышающий количество потоков, которые будут доступны, если на этом этапе код был определен параллельный регион без [num_threads.](openmp-clauses.md#num-threads)

```cpp
int omp_get_max_threads( )
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_get_max_threads.](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)

### <a name="example"></a>Пример

```cpp
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp_get_nested"></a><a name="omp-get-nested"></a>omp_get_nested

Возвращает значение, указывающее, включен о включении вложенного параллеля.

```cpp
int omp_get_nested( );
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает включен овложение параллелизма.

### <a name="remarks"></a>Примечания

Вложенный параллелизм указан [с omp_set_nested](#omp-set-nested) и [OMP_NESTED.](openmp-environment-variables.md#omp-nested)

Для получения дополнительной информации см [omp_get_nested.](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)

### <a name="example"></a>Пример

Смотрите [omp_set_nested](#omp-set-nested) примериспользования `omp_get_nested`за использованием .

## <a name="omp_get_num_procs"></a><a name="omp-get-num-procs"></a>omp_get_num_procs

Возвращает количество процессоров, доступных при вызове функции.

```cpp
int omp_get_num_procs();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_get_num_procs.](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)

### <a name="example"></a>Пример

```cpp
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp_get_num_threads"></a><a name="omp-get-num-threads"></a>omp_get_num_threads

Возвращает количество потоков в параллельной области.

```cpp
int omp_get_num_threads( );
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_get_num_threads.](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)

### <a name="example"></a>Пример

```cpp
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp_get_thread_num"></a><a name="omp-get-thread-num"></a>omp_get_thread_num

Возвращает номер потока, исполняемого потоком, в команде потоков.

```cpp
int omp_get_thread_num( );
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_get_thread_num.](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)

### <a name="example"></a>Пример

См [параллель](openmp-directives.md#parallel) `omp_get_thread_num`для примера использования .

## <a name="omp_get_wtick"></a><a name="omp-get-wtick"></a>omp_get_wtick

Возвращает количество секунд между тиками часов процессора.

```cpp
double omp_get_wtick( );
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_get_wtick.](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md)

### <a name="example"></a>Пример

См [omp_get_wtime](#omp-get-wtime) примере `omp_get_wtick`использования .

## <a name="omp_get_wtime"></a><a name="omp-get-wtime"></a>omp_get_wtime

Возвращает значение в секундах времени, прошедшего с какой-то точки.

```cpp
double omp_get_wtime( );
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение в течение нескольких секунд, прошедшее из какой-то произвольной, но последовательной точки.

### <a name="remarks"></a>Примечания

Этот момент будет оставаться последовательным во время выполнения программы, что делает предстоящие сравнения возможными.

Для получения дополнительной информации см [omp_get_wtime.](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)

### <a name="example"></a>Пример

```cpp
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp_in_parallel"></a><a name="omp-in-parallel"></a>omp_in_parallel

Возвращает ненулевой, если вызов из параллельной области.

```cpp
int omp_in_parallel( );
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_in_parallel.](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md)

### <a name="example"></a>Пример

```cpp
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp_init_lock"></a><a name="omp-init-lock"></a>omp_init_lock

Инициализирует простой замок.

```cpp
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_init_nest_lock omp_init_lock.](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)

### <a name="example"></a>Пример

```cpp
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp_init_nest_lock"></a><a name="omp-init-nest-lock"></a>omp_init_nest_lock

Инициализирует замок.

```cpp
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`.

### <a name="remarks"></a>Примечания

Первоначальный отсчет гнездования равен нулю.

Для получения дополнительной информации см [omp_init_nest_lock omp_init_lock.](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)

### <a name="example"></a>Пример

```cpp
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp_set_dynamic"></a><a name="omp-set-dynamic"></a>omp_set_dynamic

Означает, что количество потоков, доступных в предстоящих параллельных регионах, может быть скорректировано к времени выполнения.

```cpp
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Параметры

*Валь*<br/>
Значение, указывающее, можно ли скорректировать количество потоков, доступных в предстоящих параллельных регионах, с помощью времени выполнения. Если ненулевое время выполнения может регулировать число потоков, если ноль, время выполнения не будет динамически регулировать количество потоков.

### <a name="remarks"></a>Примечания

Количество потоков никогда не превысит значения, установленного [omp_set_num_threads](#omp-set-num-threads) или [OMP_NUM_THREADS.](openmp-environment-variables.md#omp-num-threads)

Используйте [omp_get_dynamic](#omp-get-dynamic) для отображения текущей настройки. `omp_set_dynamic`

Установка для `omp_set_dynamic` переопределения параметра [переменной среды OMP_DYNAMIC.](openmp-environment-variables.md#omp-dynamic)

Для получения дополнительной информации см [omp_set_dynamic.](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)

### <a name="example"></a>Пример

```cpp
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp_set_lock"></a><a name="omp-set-lock"></a>omp_set_lock

Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.

```cpp
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_lock_t` которая была инициализирована с [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_set_nest_lock omp_set_lock.](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)

### <a name="examples"></a>Примеры

Смотрите [omp_init_lock](#omp-init-lock) примериспользования `omp_set_lock`за использование .

## <a name="omp_set_nest_lock"></a><a name="omp-set-nest-lock"></a>omp_set_nest_lock

Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.

```cpp
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_nest_lock_t` которая была инициализирована с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_set_nest_lock omp_set_lock.](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)

### <a name="examples"></a>Примеры

Смотрите [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_set_nest_lock`.

## <a name="omp_set_nested"></a><a name="omp-set-nested"></a>omp_set_nested

Позволяет вложенный параллелизм.

```cpp
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Параметры

*Валь*<br/>
Ненулевое значение позволяет вложенный параллелизм, в то время как ноль отлиний вложенных параллелизм.

### <a name="remarks"></a>Примечания

Вложенный параллелизм OMP `omp_set_nested`можно завернуть с помощью или путем установки переменной [OMP_NESTED](openmp-environment-variables.md#omp-nested) среды.

Установка для `omp_set_nested` переопределения параметра `OMP_NESTED` переменной среды.

Включение переменной среды может нарушить в противном случае оперативную программу, поскольку количество потоков увеличивается в геометрической прогрессии при вложении параллельных регионов. Например, функция, которая повторно переизвеплена шесть раз с числом потоков OMP, установленных на 4, требует 4096 (4 к силе 6) потоков. За исключением приложений, связанных с вводом/ой, производительность приложения обычно ухудшается, если потоков больше, чем процессоров.

Используйте [omp_get_nested](#omp-get-nested) для отображения текущей настройки. `omp_set_nested`

Для получения дополнительной информации [omp_set_nested](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)см.

### <a name="example"></a>Пример

```cpp
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="omp_set_num_threads"></a><a name="omp-set-num-threads"></a>omp_set_num_threads

Устанавливает количество потоков в предстоящих параллельных регионах, если не перекрывается [num_threads](openmp-clauses.md#num-threads) положением.

```cpp
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Параметры

*num_threads*<br/>
Количество потоков в параллельной области.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_set_num_threads.](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)

### <a name="example"></a>Пример

См [omp_get_num_threads](#omp-get-num-threads) примере `omp_set_num_threads`использования .

## <a name="omp_test_lock"></a><a name="omp-test-lock"></a>omp_test_lock

Попытки установить блокировку, но не блокирует выполнение потока.

```cpp
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_lock_t` которая была инициализирована с [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_test_nest_lock omp_test_lock.](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)

### <a name="example"></a>Пример

```cpp
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp_test_nest_lock"></a><a name="omp-test-nest-lock"></a>omp_test_nest_lock

Попытки установить блокировку, но не блокирует выполнение потока.

```cpp
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_nest_lock_t` которая была инициализирована с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_test_nest_lock omp_test_lock.](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)

### <a name="example"></a>Пример

```cpp
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp_unset_lock"></a><a name="omp-unset-lock"></a>omp_unset_lock

Выпускает замок.

```cpp
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_lock_t` которая была инициализирована с [omp_init_lock,](#omp-init-lock)принадлежащих потоку и выполнения в функции.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_unset_nest_lock omp_unset_lock.](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)

### <a name="example"></a>Пример

Смотрите [omp_init_lock](#omp-init-lock) примериспользования `omp_unset_lock`за использование .

## <a name="omp_unset_nest_lock"></a><a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Выпускает вложенный замок.

```cpp
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа, `omp_nest_lock_t` которая была инициализирована с [omp_init_nest_lock,](#omp-init-nest-lock)принадлежащих потоку и выполнения в функции.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см [omp_unset_nest_lock omp_unset_lock.](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)

### <a name="example"></a>Пример

Смотрите [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_unset_nest_lock`.
