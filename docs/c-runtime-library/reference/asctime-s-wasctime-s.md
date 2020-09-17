---
title: asctime_s, _wasctime_s
ms.date: 4/2/2020
api_name:
- _wasctime_s
- asctime_s
- _o__wasctime_s
- _o_asctime_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- asctime_s
- _wasctime_s
- _tasctime_s
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
ms.openlocfilehash: 529663a8c36a1b934a4dd99852aee19fb1a1e6e6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217016"
---
# <a name="asctime_s-_wasctime_s"></a>asctime_s, _wasctime_s

Преобразование структуры времени **TM** в символьную строку. Это версии функций [asctime, _wasctime](asctime-wasctime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t asctime_s(
   char* buffer,
   size_t numberOfElements,
   const struct tm *tmSource
);
errno_t _wasctime_s(
   wchar_t* buffer,
   size_t numberOfElements
   const struct tm *tmSource
);
template <size_t size>
errno_t asctime_s(
   char (&buffer)[size],
   const struct tm *tmSource
); // C++ only
template <size_t size>
errno_t _wasctime_s(
   wchar_t (&buffer)[size],
   const struct tm *tmSource
); // C++ only
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Указатель на буфер для хранения результата символьной строки. Эта функция принимает указатель на допустимое расположение в памяти с размером, заданным параметром *numberOfElements*.

*numberOfElements*<br/>
Размер буфера, используемого для хранения результата.

*тмсаурце*<br/>
Структура даты/времени. Эта функция принимает указатель на допустимый объект **`struct`** **TM** .

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае отказа вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки. Коды ошибок определенны в ERRNO.H. Дополнительные сведения см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md). Фактические коды ошибок, возвращаемые для каждого условия ошибки, приведены в следующей таблице.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*двойной*|*numberOfElements*|*тмсаурце*|Возвращает|Значение в *буфере*|
|--------------|------------------------|----------|------------|-----------------------|
|**NULL**|Любой|Любой|**еинвал**|Без изменений|
|Not **null** (указывает на допустимый объем памяти)|0|Любой|**еинвал**|Без изменений|
|Не **null**|0< size < 26|Любой|**еинвал**|Пустая строка.|
|Не **null**|>= 26|**NULL**|**еинвал**|Пустая строка.|
|Не **null**|>= 26|Недопустимая структура времени или компоненты времени выходят за пределы допустимого диапазона|**еинвал**|Пустая строка.|

> [!NOTE]
> Условия ошибок для **wasctime_s** похожи на **asctime_s** с исключением, что ограничение размера измеряется в словах.

## <a name="remarks"></a>Примечания

Функция **asctime** преобразует время, хранящееся в виде структуры, в символьную строку. Значение *тмсаурце* обычно получается из вызова **gmtime** или **localtime**. Обе функции можно использовать для заполнения структуры **TM** , как определено во времени. Высоты.

|Член timeptr|Значение|
|--------------------|-----------|
|**tm_hour**|Часов после полуночи (0-23)|
|**tm_isdst**|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).|
|**tm_mday**|День месяца (1-31)|
|**tm_min**|Минут после часа (0-59)|
|**tm_mon**|Месяц (0-11; Январь = 0)|
|**tm_sec**|Секунды после минуты (0-59)|
|**tm_wday**|День недели (0-6; Воскресенье = 0)|
|**tm_yday**|День года (0-365; 1 января = 0)|
|**tm_year**|Год (текущий год минус 1900)|

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Обратитесь к функциям [time, _time32, _time64](time-time32-time64.md), [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) и [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md) за сведениями о настройке местного времени и к функции [_tzset](tzset.md) за сведениями об определении среды часового пояса и глобальных переменных.

Строковый результат, полученный **asctime_s** , содержит ровно 26 символов и имеет форму `Wed Jan 02 02:03:55 1980\n\0` . Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки и нуль-символ занимают две последние позиции строки. Значение, переданное в качестве второго параметра, должно иметь по крайней мере такое значение. Если он меньше, будет возвращен код ошибки **еинвал**.

**_wasctime_s** — это версия **asctime_s**для расширенных символов. в противном случае **_wasctime_s** и **asctime_s** ведут себя одинаково.

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**asctime_s**|\<time.h>|
|**_wasctime_s**|\<time.h> или \<wchar.h>|

## <a name="security"></a>Безопасность

Если указатель буфера не равен **null** и указатель не указывает на допустимый буфер, функция будет перезаписывать все, что находится в расположении. Это также может привести к нарушению прав доступа.

Если переданный аргумент size превышает фактический размер буфера, может возникать ошибка [переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

## <a name="example"></a>Пример

Эта программа помещает системное время в длинное целое число **аклокк**, преобразует его в структуру **невтиме** и преобразовывает в виде строки для вывода с помощью функции **asctime_s** .

```C
// crt_asctime_s.c
#include <time.h>
#include <stdio.h>

struct tm newtime;
__time32_t aclock;

int main( void )
{
   char buffer[32];
   errno_t errNum;
   _time32( &aclock );   // Get time in seconds.
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.

   // Print local time as a string.

   errNum = asctime_s(buffer, 32, &newtime);
   if (errNum)
   {
       printf("Error code: %d", (int)errNum);
       return 1;
   }
   printf( "Current date and time: %s", buffer );
   return 0;
}
```

```Output
Current date and time: Wed May 14 15:30:17 2003
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
