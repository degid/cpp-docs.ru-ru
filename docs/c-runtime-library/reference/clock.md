---
title: clock
ms.date: 11/04/2016
api_name:
- clock
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clock
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
ms.openlocfilehash: 03d1a9ece92dbedfdceb89488e5d0440dc64f7ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220734"
---
# <a name="clock"></a>clock

Вычисляет реальное прошедшее время для процесса.

## <a name="syntax"></a>Синтаксис

```C
clock_t clock( void );
```

## <a name="return-value"></a>Возвращаемое значение

Время, прошедшее с момента инициализации CRT в начале процесса, измеряется в **CLOCKS_PER_SEC** единицах в секунду. Если затраченное время недоступно или превышает максимальное положительное время, которое можно записать как тип **clock_t** , функция возвращает значение `(clock_t)(-1)` .

## <a name="remarks"></a>Примечания

Функция **Clock** сообщает, сколько времени пропускной способности прошло с момента инициализации CRT во время запуска процесса. Обратите внимание на то, что эта функция не является строго соответствующей стандарту ISO C, который определяет возвращаемое значение как чистое время ЦП. Чтобы получить время ЦП, используйте функцию [GetProcessTimes](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getprocesstimes) Win32. Чтобы определить затраченное время в секундах, разделите значение, возвращаемое функцией **Clock** , на **CLOCKS_PER_SEC**макроса.

Учитывая достаточное время, значение, возвращаемое **часами** , может превышать максимальное положительное значение **clock_t**. Когда процесс выполняется дольше, значение, возвращаемое **часами** , всегда равно `(clock_t)(-1)` , как указано в стандарте ISO C99 Standard (7.23.2.1) и ISO C11 Standard (7.27.2.1). Корпорация Майкрософт реализует **clock_t** как **`long`** , 32-разрядное целое число со знаком, а макрос **CLOCKS_PER_SEC** определяется как 1000. Это дает максимальное значение, возвращаемое функцией **Clock** , равное 2147483,647 секундам, или около 24,8 дней. Не полагайтесь на значение, возвращаемое **часами** в процессах, которые выполнялись дольше данного периода времени. Вы можете использовать функцию 64-разрядного [времени](time-time32-time64.md) или функцию Windows [QueryPerformanceCounter](/windows/win32/api/profileapi/nf-profileapi-queryperformancecounter) для записи времени, прошедшего в течение многих лет.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**clock**|\<time.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_clock.c
// This sample uses clock() to 'sleep' for three
// seconds, then determines how long it takes
// to execute an empty loop 600000000 times.

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Pauses for a specified number of clock cycles.
void do_sleep( clock_t wait )
{
   clock_t goal;
   goal = wait + clock();
   while( goal > clock() )
      ;
}

const long num_loops = 600000000L;

int main( void )
{
   long    i = num_loops;
   clock_t start, finish;
   double  duration;

   // Delay for a specified time.
   printf( "Delay for three seconds\n" );
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );
   printf( "Done!\n" );

   // Measure the duration of an event.
   start = clock();
   while( i-- )
      ;
   finish = clock();
   duration = (double)(finish - start) / CLOCKS_PER_SEC;
   printf( "Time to do %ld empty loops is ", num_loops );
   printf( "%2.3f seconds\n", duration );
}
```

```Output
Delay for three seconds
Done!
Time to do 600000000 empty loops is 1.354 seconds
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[difftime, _difftime32, _difftime64](difftime-difftime32-difftime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
