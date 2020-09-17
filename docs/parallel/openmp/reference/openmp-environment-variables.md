---
title: Переменные среды OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: bee9b0fbdf147ee962ff92d0b3b9ff57d4209f84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363876"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP

Предоставляет ссылки на переменные среды, используемые в API OpenMP.

Реализация стандарта OpenMP в изобразительного си-З включает в себя следующие переменные среды. Эти переменные среды считываются при запуске программы, а изменения в их значениях игнорируются во время выполнения (например, с использованием [_putenv, _wputenv).](../../../c-runtime-library/reference/putenv-wputenv.md)

|Переменная среды|Описание|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|Изменяет поведение положения [о расписании,](openmp-clauses.md#schedule) `for` когда `parallel for` `schedule(runtime)` она указана в директиве или директиве.|
|[OMP_NUM_THREADS](#omp-num-threads)|Устанавливает максимальное количество потоков в параллельной области, если не перекрывается [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads.](openmp-clauses.md#num-threads)|
|[OMP_DYNAMIC](#omp-dynamic)|Определяет, может ли время выполнения OpenMP регулировать количество потоков в параллельной области.|
|[OMP_NESTED](#omp-nested)|Определяет, включен ли вложенный параллелизм, если только вложенный `omp_set_nested`параллелизм не включен или отключен с помощью .|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a>OMP_DYNAMIC

Определяет, может ли время выполнения OpenMP регулировать количество потоков в параллельной области.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Примечания

Переменная `OMP_DYNAMIC` среды может быть перекрыта [функцией omp_set_dynamic.](openmp-functions.md#omp-set-dynamic)

Значение по умолчанию в реализации стандарта Visual `OMP_DYNAMIC=FALSE`C '.

Для получения дополнительной информации см [OMP_DYNAMIC.](../../../parallel/openmp/4-3-omp-dynamic.md)

### <a name="example"></a>Пример

Следующая команда `OMP_DYNAMIC` устанавливает переменную среды к TRUE:

```cmd
set OMP_DYNAMIC=TRUE
```

Следующая команда отображает текущую `OMP_DYNAMIC` настройку переменной среды:

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a>OMP_NESTED

Определяет, включен ли вложенный параллелизм, если только вложенный `omp_set_nested`параллелизм не включен или отключен с помощью .

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Примечания

Переменная `OMP_NESTED` среды может быть перекрыта [функцией omp_set_nested.](openmp-functions.md#omp-set-nested)

Значение по умолчанию в реализации стандарта Visual `OMP_DYNAMIC=FALSE`C '.

Для получения дополнительной информации см [OMP_NESTED.](../../../parallel/openmp/4-4-omp-nested.md)

### <a name="example"></a>Пример

Следующая команда `OMP_NESTED` устанавливает переменную среды к TRUE:

```cmd
set OMP_NESTED=TRUE
```

Следующая команда отображает текущую `OMP_NESTED` настройку переменной среды:

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a>OMP_NUM_THREADS

Устанавливает максимальное количество потоков в параллельной области, если не перекрывается [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads.](openmp-clauses.md#num-threads)

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Параметры

*num*<br/>
Максимальное количество потоков, которые вы хотите в параллельной области, до 64 в реализации Visual C.

### <a name="remarks"></a>Примечания

Переменная `OMP_NUM_THREADS` среды может быть перекрыта функцией [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads.](openmp-clauses.md#num-threads)

Значение по `num` умолчанию в реализации стандарта OpenMP visual C' — это количество виртуальных процессоров, включая гипертоники процессоров.

Для получения дополнительной информации см [OMP_NUM_THREADS.](../../../parallel/openmp/4-2-omp-num-threads.md)

### <a name="example"></a>Пример

Следующая команда `OMP_NUM_THREADS` устанавливает переменную среды на: `16`

```cmd
set OMP_NUM_THREADS=16
```

Следующая команда отображает текущую `OMP_NUM_THREADS` настройку переменной среды:

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a>OMP_SCHEDULE

Изменяет поведение положения [о расписании,](openmp-clauses.md#schedule) `for` когда `parallel for` `schedule(runtime)` она указана в директиве или директиве.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
(Необязательно) Определяет размер итераций. *размер* должен быть положительным рядом. По `1`умолчанию, за исключением случаев, когда *тип* статичен. Не действителен, `runtime`когда *тип* .

*тип*<br/>
Вид планирования, либо `dynamic` `guided`, `runtime`, `static`или .

### <a name="remarks"></a>Примечания

Значение по умолчанию в реализации стандарта Visual `OMP_SCHEDULE=static,0`C '.

Для получения дополнительной информации см [OMP_SCHEDULE.](../../../parallel/openmp/4-1-omp-schedule.md)

### <a name="example"></a>Пример

Следующая команда `OMP_SCHEDULE` устанавливает переменную среды:

```cmd
set OMP_SCHEDULE="guided,2"
```

Следующая команда отображает текущую `OMP_SCHEDULE` настройку переменной среды:

```cmd
set OMP_SCHEDULE
```
