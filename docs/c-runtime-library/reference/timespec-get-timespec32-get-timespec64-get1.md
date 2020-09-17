---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 4/2/2020
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
- _o__timespec32_get
- _o__timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: 7e3c56805b3af9bb5e739bd74d03bce015c65895
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233929"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

Устанавливает интервал, на который указывает первый аргумент, в текущее календарное время в соответствии с заданной базой времени.

## <a name="syntax"></a>Синтаксис

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);
```

### <a name="parameters"></a>Параметры

*time_spec*<br/>
Указатель на структуру, которой присваивается время в секундах и наносекундах с начала эпохи.

*base*<br/>
Зависящее от реализации ненулевое значение, определяющее базу времени.

## <a name="return-value"></a>Возвращаемое значение

Значение *base* в случае успеха, в противном случае возвращается ноль.

## <a name="remarks"></a>Примечания

Функции **timespec_get** устанавливают текущее время в структуре, на которую указывает аргумент *time_spec* . Все версии этой структуры имеют два члена: **tv_sec** и **tv_nsec**. Значение **tv_sec** задается равным целому числу секунд, а **tv_nsec** — целому числу наносекунд, округленному до разрешения системных часов с начала эпохи, заданной *базовым*.

**Блок, относящийся только к системам Microsoft**

Эти функции поддерживают только **TIME_UTC** в качестве *базового* значения. Этот параметр задает для *time_spec* значение, равное количеству секунд и наносекундах с момента начала эпохи, полночь 1 января 1970 г., время в формате UTC. В **`struct`** **_timespec32** **tv_sec** является значением **__time32_t** . В **`struct`** **_timespec64** **tv_sec** является значением **__time64_t** . В **`struct`** **timespec** **tv_sec** является типом **time_t** , длина которого 32 бит или 64 бит в зависимости от того, определен ли макрос препроцессора _USE_32BIT_TIME_T. Функция **timespec_get** является встроенной функцией, которая вызывает **_timespec32_get** , если определен _USE_32BIT_TIME_T. в противном случае он вызывает **_timespec64_get**.

**Завершение Microsoft для конкретных**

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get** **_timespec64_get**|C: \<time.h> , C++: \<ctime> или\<time.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также статью

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
