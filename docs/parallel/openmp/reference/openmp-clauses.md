---
title: Предложения OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 1c4c7961a173eb47394d03e9aabdd14574e62b08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363900"
---
# <a name="openmp-clauses"></a>Предложения OpenMP

Предоставляет ссылки на положения, используемые в API OpenMP.

Визуальный КЗ поддерживает следующие положения OpenMP.

Для общих атрибутов:

|Предложение|Описание|
|------|-----------|
|[if](#if-openmp)|Определяет, следует ли выполнять цикл параллельно или последовательно.|
|[num_threads](#num-threads)|Устанавливает количество потоков в группе потоков.|
|[Заказать](#ordered-openmp-clauses)|Требуется на параллели [для](openmp-directives.md#for-openmp) оператора, если в цикле должна использоваться [упорядоченная](openmp-directives.md#ordered-openmp-directives) директива.|
|[Расписание](#schedule)|Применяется к [директиве.](openmp-directives.md#for-openmp)|
|[Nowait](#nowait)|Переопределяет барьер, подразумеваемый в директиве.|

Для атрибутов обмена данными:

|Предложение|Описание|
|------|-----------|
|[Частная](#private-openmp)|Уточняется, что каждый поток должен иметь свой собственный экземпляр переменной.|
|[firstprivate](#firstprivate)|Уточняется, что каждый поток должен иметь свой собственный экземпляр переменной и что переменная должна быть инициализирована со значением переменной, поскольку она существует до параллельной конструкции.|
|[lastprivate](#lastprivate)|Уточняется, что версия переменной прилагаемого контекста равна частной версии того, какой поток выполняет окончательную итерацию (для построения цикла) или последний раздел (#pragma разделов).|
|[Общий](#shared-openmp)|Упомяните, что одна или несколько переменных должны быть общими между всеми потоками.|
|[default](#default-openmp)|Определяет поведение нескопоговых переменных в параллельной области.|
|[reduction](#reduction)|Уточняется, что одна или несколько переменных, которые являются закрытыми для каждого потока, являются предметом операции сокращения в конце параллельной области.|
|[copyin](#copyin)|Позволяет потокам получить доступ к значению основного потока для переменной [threadprivate.](openmp-directives.md#threadprivate)|
|[copyprivate](#copyprivate)|Упомяните, что одна или несколько переменных должны быть общими между всеми потоками.|

## <a name="copyin"></a><a name="copyin"></a>копин

Позволяет потокам получить доступ к значению основного потока для переменной [threadprivate.](openmp-directives.md#threadprivate)

```cpp
copyin(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Переменная, `threadprivate` которая будет инициализирована со значением переменной в главном потоке, как она существует до параллельной конструкции.

### <a name="remarks"></a>Примечания

`copyin`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-2-7-copyin.md)

### <a name="example"></a>Пример

См [threadprivate](openmp-directives.md#threadprivate) на `copyin`примере использования .

## <a name="copyprivate"></a><a name="copyprivate"></a>copyprivate

Упомяните, что одна или несколько переменных должны быть общими между всеми потоками.

```cpp
copyprivate(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Одна или несколько переменных для совместного участия. Если указано несколько переменных, отдельные переменные имена с запятой.

### <a name="remarks"></a>Примечания

`copyprivate`применяется к [одной](openmp-directives.md#single) директиве.

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-2-8-copyprivate.md)

### <a name="example"></a>Пример

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default"></a><a name="default-openmp"></a>По умолчанию

Определяет поведение нескопоговых переменных в параллельной области.

```cpp
default(shared | none)
```

### <a name="remarks"></a>Примечания

`shared`, который действует, `default` если оговорка не указана, означает, что любая переменная в параллельной области будет рассматриваться как если бы она была указана в [общем](#shared-openmp) положении. `none`означает, что любые переменные, используемые в параллельной области, которые не доступны с [частным,](#private-openmp) [общим,](#shared-openmp) [сокращением,](#reduction) [firstprivate](#firstprivate), или [последним частным](#lastprivate) положением, вызовут ошибку компилятора.

`default`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-2-5-default.md)

### <a name="example"></a>Пример

[См. частный](#private-openmp) `default`пример использования .

## <a name="firstprivate"></a><a name="firstprivate"></a>firstprivate

Уточняется, что каждый поток должен иметь свой собственный экземпляр переменной и что переменная должна быть инициализирована со значением переменной, поскольку она существует до параллельной конструкции.

```cpp
firstprivate(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Переменная имеет экземпляры в каждом потоке и будет инициализирована со значением переменной, поскольку она существует до параллельной конструкции. Если указано несколько переменных, отдельные переменные имена с запятой.

### <a name="remarks"></a>Примечания

`firstprivate`применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Разделы](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-2-2-firstprivate.md)

### <a name="example"></a>Пример

Пример использования `firstprivate`см. [private](#private-openmp)

## <a name="if-openmp"></a><a name="if-openmp"></a>если (OpenMP)

Определяет, следует ли выполнять цикл параллельно или последовательно.

```cpp
if(expression)
```

### <a name="parameters"></a>Параметры

*выражение*<br/>
Интегральное выражение, которое, если оно оценивается как истинное (ненулевое), приводит к параллельному выполнению кода в параллельной области. Если выражение оценивается как ложное (ноль), параллельный регион выполняется в последовательном (одним потоком).

### <a name="remarks"></a>Примечания

`if`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-3-parallel-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a><a name="lastprivate"></a>lastprivate

Уточняется, что версия переменной прилагаемого контекста равна частной версии того, какой поток выполняет окончательную итерацию (для построения цикла) или последний раздел (#pragma разделов).

```cpp
lastprivate(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Переменная, установленная равна частной версии того, какой поток выполняет окончательную итерацию (для построения цикла) или последний раздел (#pragma разделов).

### <a name="remarks"></a>Примечания

`lastprivate`применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-7-2-3-lastprivate.md)

### <a name="example"></a>Пример

[См](#schedule) расписание для `lastprivate` примера использования клаузулы.

## <a name="nowait"></a><a name="nowait"></a>Nowait

Переопределяет барьер, подразумеваемый в директиве.

```cpp
nowait
```

### <a name="remarks"></a>Примечания

`nowait`применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Для получения дополнительной информации, [см. 2.4.1 для строительства,](../../../parallel/openmp/2-4-1-for-construct.md) [2.4.2 разделов построить,](../../../parallel/openmp/2-4-2-sections-construct.md)и [2.4.3 одной конструкции](../../../parallel/openmp/2-4-3-single-construct.md).

### <a name="example"></a>Пример

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num_threads"></a><a name="num-threads"></a>num_threads

Устанавливает количество потоков в группе потоков.

```cpp
num_threads(num)
```

### <a name="parameters"></a>Параметры

*num*<br/>
Количество потоков

### <a name="remarks"></a>Примечания

Оговорка `num_threads` имеет ту же функциональность, что и [функция omp_set_num_threads.](openmp-functions.md#omp-set-num-threads)

`num_threads`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации [см.](../../../parallel/openmp/2-3-parallel-construct.md)

### <a name="example"></a>Пример

[См. параллель](openmp-directives.md#parallel) для примера использования клаузула. `num_threads`

## <a name="ordered"></a><a name="ordered-openmp-clauses"></a>Заказать

Требуется на параллели [для](openmp-directives.md#for-openmp) оператора, если в цикле должна использоваться [упорядоченная](openmp-directives.md#ordered-openmp-directives) директива.

```cpp
ordered
```

### <a name="remarks"></a>Примечания

`ordered`относится к [директиве.](openmp-directives.md#for-openmp)

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-4-1-for-construct.md)

### <a name="example"></a>Пример

[См, заказанный](openmp-directives.md#ordered-openmp-directives) `ordered` для примера использования клаузулы.

## <a name="private"></a><a name="private-openmp"></a>Частная

Уточняется, что каждый поток должен иметь свой собственный экземпляр переменной.

```cpp
private(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Переменная имеет экземпляры в каждом потоке.

### <a name="remarks"></a>Примечания

`private`применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Разделы](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-7-2-1-private.md)

### <a name="example"></a>Пример

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a><a name="reduction"></a>Сокращение

Уточняется, что одна или несколько переменных, которые являются закрытыми для каждого потока, являются предметом операции сокращения в конце параллельной области.

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>Параметры

*Операции*<br/>
Оператор для операции, чтобы сделать на переменных *var* в конце параллельной области.

*Var*<br/>
Одна или несколько переменных, на которых можно сделать сокращение масштабов. Если указано несколько переменных, отдельные переменные имена с запятой.

### <a name="remarks"></a>Примечания

`reduction`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-7-2-6-reduction.md)

### <a name="example"></a>Пример

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a><a name="schedule"></a>Расписание

Применяется к [директиве.](openmp-directives.md#for-openmp)

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>Параметры

*тип*<br/>
Вид планирования, либо `dynamic` `guided`, `runtime`, `static`или .

*Размер*<br/>
(Необязательно) Определяет размер итераций. *размер* должен быть много. Не действителен, `runtime`когда *тип* .

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-4-1-for-construct.md)

### <a name="example"></a>Пример

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared"></a><a name="shared-openmp"></a>Общий

Упомяните, что одна или несколько переменных должны быть общими между всеми потоками.

```cpp
shared(var)
```

### <a name="parameters"></a>Параметры

*Var*<br/>
Одна или несколько переменных для совместного участия. Если указано несколько переменных, отдельные переменные имена с запятой.

### <a name="remarks"></a>Примечания

Другой способ совместного участия переменных между потоками — это оговорка [copyprivate.](#copyprivate)

`shared`применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Разделы](openmp-directives.md#sections-openmp)

Для получения дополнительной информации, [см.](../../../parallel/openmp/2-7-2-4-shared.md)

### <a name="example"></a>Пример

[См. частный](#private-openmp) `shared`пример использования .
