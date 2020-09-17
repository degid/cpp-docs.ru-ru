---
title: Директивы OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- parallel
- section
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: 569419b3422b155afc6e9692efaecd4e5a06f188
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366445"
---
# <a name="openmp-directives"></a>Директивы OpenMP

Предоставляет ссылки на директивы, используемые в API OpenMP.

Визуальный СЗ поддерживает следующие директивы OpenMP.

Для параллельного совместного использования работы:

|Директива|Описание|
|---------|-----------|
|[parallel](#parallel)|Определяет параллельный регион, код, который будет выполняться несколькими потоками параллельно.|
|[for](#for-openmp)|Вызывает разделение работы `for` в цикле внутри параллельной области между потоками.|
|[Разделы](#sections-openmp)|Определяет разделы кода, которые должны быть разделены между всеми потоками.|
|[single](#single)|Позволяет указать, что раздел кода должен выполняться на одном потоке, не обязательно на главном потоке.|

Для мастер-и синхронизации:

|Директива|Описание|
|---------|-----------|
|[master](#master)|Уточняется, что только основной поток должен выполнять раздел программы.|
|[Критических](#critical)|Уфиксирует, что код выполняется только по одному потоку за раз.|
|[Барьер](#barrier)|Синхронизирует все потоки в команде; все потоки приостанавливаются на барьере, пока все потоки не выполнят барьер.|
|[атомарная](#atomic)|Упомянет, что местоположение памяти будет обновляться атомарно.|
|[flush](#flush-openmp)|Уфиксирует, что все потоки имеют одинаковое представление памяти для всех общих объектов.|
|[Заказать](#ordered-openmp-directives)|Указать, что код под `for` параллельным циклом должен выполняться как последовательный цикл.|

Для среды данных:

|Директива|Описание|
|---------|-----------|
|[threadprivate](#threadprivate)|Упомянет, что переменная является частной для потока.|

## <a name="atomic"></a><a name="atomic"></a>Атомной

Упомянет, что местоположение памяти будет обновляться атомарно.

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Параметры

*выражение*<br/>
Заявление, которое имеет *lvalue*, чье местоположение памяти вы хотите защитить от более чем одной записи.

### <a name="remarks"></a>Примечания

Директива `atomic` не содержит никаких оговорок.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-4-atomic-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="barrier"></a><a name="barrier"></a>Барьер

Синхронизирует все потоки в команде; все потоки приостанавливаются на барьере, пока все потоки не выполнят барьер.

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>Примечания

Директива `barrier` не содержит никаких оговорок.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-3-barrier-directive.md)

### <a name="example"></a>Пример

Для примера того, `barrier`как использовать, см. [master](#master)

## <a name="critical"></a><a name="critical"></a>Критических

Уфиксирует, что код выполняется только по одному потоку за раз.

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*name*<br/>
(Необязательно) Имя для идентификации критического кода. Имя должно быть заключено в скобки.

### <a name="remarks"></a>Примечания

Директива `critical` не содержит никаких оговорок.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-2-critical-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush"></a><a name="flush-openmp"></a>Флеш

Уфиксирует, что все потоки имеют одинаковое представление памяти для всех общих объектов.

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Параметры

*Var*<br/>
(Необязательно) Разделенный запятой список переменных, представляющих объекты, которые необходимо синхронизировать. Если *var* не указан, вся память промыта.

### <a name="remarks"></a>Примечания

Директива `flush` не содержит никаких оговорок.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-5-flush-directive.md)

### <a name="example"></a>Пример

```cpp
// omp_flush.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void read(int *data) {
   printf_s("read data\n");
   *data = 1;
}

void process(int *data) {
   printf_s("process data\n");
   (*data)++;
}

int main() {
   int data;
   int flag;

   flag = 0;

   #pragma omp parallel sections num_threads(2)
   {
      #pragma omp section
      {
         printf_s("Thread %d: ", omp_get_thread_num( ));
         read(&data);
         #pragma omp flush(data)
         flag = 1;
         #pragma omp flush(flag)
         // Do more work.
      }

      #pragma omp section
      {
         while (!flag) {
            #pragma omp flush(flag)
         }
         #pragma omp flush(data)

         printf_s("Thread %d: ", omp_get_thread_num( ));
         process(&data);
         printf_s("data = %d\n", data);
      }
   }
}
```

```Output
Thread 0: read data
Thread 1: process data
data = 2
```

## <a name="for"></a><a name="for-openmp"></a>Для

Вызывает разделение работы `for` в цикле внутри параллельной области между потоками.

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Параметры

*Предложений*<br/>
(Необязательно) Ноль или более положений, **см.**

*for_statement*<br/>
Петля. `for` Неопределенное поведение приведет, если `for` пользовательский код в цикле изменит переменную индекса.

### <a name="remarks"></a>Примечания

Директива `for` поддерживает следующие положения:

- [Частная](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Заказать](openmp-clauses.md#ordered-openmp-clauses)
- [Расписание](openmp-clauses.md#schedule)
- [Nowait](openmp-clauses.md#nowait)

Если `parallel` также `clauses` указано, может быть `parallel` любой пункт, принятый или `for` директивы, за исключением `nowait`.

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-4-1-for-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a><a name="master"></a>Мастер

Уточняется, что только основной поток должен выполнять раздел программы.

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Примечания

Директива `master` не содержит никаких оговорок.

[Единая](#single) директива позволяет указать, что раздел кода должен выполняться на одном потоке, не обязательно на главном потоке.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-1-master-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered"></a><a name="ordered-openmp-directives"></a>Заказать

Указать, что код под `for` параллельным циклом должен выполняться как последовательный цикл.

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Примечания

Директива `ordered` должна находиться в динамическом `parallel for` объеме `ordered` положения [или](#for-openmp) конструкции.

Директива `ordered` не содержит никаких оговорок.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-6-6-ordered-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a><a name="parallel"></a>Параллельных

Определяет параллельный регион, код, который будет выполняться несколькими потоками параллельно.

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*Предложений*<br/>
(Необязательно) Ноль или более положений, **см.**

### <a name="remarks"></a>Примечания

Директива `parallel` поддерживает следующие положения:

- [if](openmp-clauses.md#if-openmp)
- [Частная](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [Общий](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel`также может быть использован с директивами [«за»](#for-openmp) и [разделами.](#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-3-parallel-construct.md)

### <a name="example"></a>Пример

В следующем примере показано, как установить количество потоков и определить параллельный регион. Количество потоков по умолчанию равно числу логических процессоров на машине. Например, если у вас есть машина с одним физическим процессором с включенным гиперпотоком, она будет иметь два логических процессора и два потока. Порядок вывода может варьироваться на разных машинах.

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections"></a><a name="sections-openmp"></a>Разделы

Определяет разделы кода, которые должны быть разделены между всеми потоками.

```cpp
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>Параметры

*Предложений*<br/>
(Необязательно) Ноль или более положений, **см.**

### <a name="remarks"></a>Примечания

Директива `sections` может содержать `section` ноль или более директив.

Директива `sections` поддерживает следующие положения:

- [Частная](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Nowait](openmp-clauses.md#nowait)

Если `parallel` также `clauses` указано, может быть `parallel` любой пункт, принятый или `sections` директивы, за исключением `nowait`.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-4-2-sections-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a><a name="single"></a>Одного

Позволяет указать, что раздел кода должен выполняться на одном потоке, не обязательно на главном потоке.

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*Предложений*<br/>
(Необязательно) Ноль или более положений, **см.**

### <a name="remarks"></a>Примечания

Директива `single` поддерживает следующие положения:

- [Частная](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [Nowait](openmp-clauses.md#nowait)

[В основной](#master) директиве указывается, что раздел кода должен выполняться только на основной потоке.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-4-3-single-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a><a name="threadprivate"></a>Threadprivate

Упомянет, что переменная является частной для потока.

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Список переменных, разделенных запятой, которые вы хотите сделать закрытыми для потока. *var* должен быть либо глобальной или областью действия пространства имен, либо локальной статической переменной.

### <a name="remarks"></a>Примечания

Директива `threadprivate` не содержит никаких оговорок.

Директива `threadprivate` основана на атрибуте [потока](../../../cpp/thread.md) с использованием [__declspec](../../../cpp/declspec.md) ключевого слова; ограничения на `__declspec(thread)` применение `threadprivate`к . Например, `threadprivate` в любом потоке, начатом в процессе, будет существовать переменная, а не только те потоки, которые являются частью группы потоков, порожденных параллельным регионом. Будьте в курсе этой детали реализации; вы можете заметить, что `threadprivate` конструкторы для пользовательского типа называются чаще, чем ожидалось.

Вы можете `threadprivate` использовать в DLL, который статично загружается при `threadprivate` запуске процесса, однако вы не можете использовать в любом DLL, который будет загружен через [LoadLibrary,](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) таких как DLLs, которые загружаются с [/DELAYLOAD (задержка импорта нагрузки)](../../../build/reference/delayload-delay-load-import.md), который также использует. `LoadLibrary`

Переменная `threadprivate` *разрушаемого* типа не гарантирует сяртовое название ее деструктора. Пример:

```cpp
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Пользователи не имеют никакого контроля в отношении того, когда потоки, составляющие параллельный регион, будут завершены. Если эти потоки существуют при выходе процесса, потоки не будут уведомлены о выходе процесса, и деструктор не будет вызван ни `threaded_var` на один поток, кроме того, который выходит (здесь, основной поток). Поэтому код не должен рассчитывать `threadprivate` на правильное разрушение переменных.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-1-threadprivate-directive.md)

### <a name="example"></a>Пример

Для примера `threadprivate`использования, [см.](openmp-clauses.md#private-openmp)
