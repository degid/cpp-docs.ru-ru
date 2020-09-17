---
title: _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
ms.date: 4/2/2020
api_name:
- _findfirst
- _wfindfirst
- _findfirst32
- _wfindfirst32
- _findfirst32i64
- _wfindfirst32i64
- _findfirst64
- _wfindfirst64
- _findfirst64i32
- _wfindfirst64i32
- _findfirsti64
- _wfindfirsti64
- _o__findfirst32
- _o__findfirst32i64
- _o__findfirst64
- _o__findfirst64i32
- _o__wfindfirst32
- _o__wfindfirst32i64
- _o__wfindfirst64
- _o__wfindfirst64i32
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- findfirst32i64
- wfindfirst32i64
- tfindfirst64
- _findfirst64i32
- _wfindfirst32i64
- _wfindfirsti64
- wfindfirst
- _tfindfirsti64
- findfirst32
- _tfindfirst32
- _findfirsti64
- findfirst
- wfindfirst64
- wfindfirst32
- tfindfirst32
- _wfindfirst64i32
- findfirst64i32
- tfindfirst64i32
- _wfindfirst
- findfirsti64
- _findfirst32i64
- wfindfirst64i32
- _wfindfirst32
- _findfirst32
- _tfindfirst32i64
- tfindfirst
- _tfindfirst64i32
- findfirst64
- _tfindfirst
- _findfirst64
- _tfindfirst64
- tfindfirst32i64
- _findfirst
- _wfindfirst64
helpviewer_keywords:
- _tfindfirst64 function
- _wfindfirst64i32 function
- _wfindfirst32i64 function
- wfindfirst32 function
- _findfirst function
- wfindfirst64 function
- _wfindfirst function
- _findfirst64i32 function
- wfindfirst function
- _findfirst64 function
- tfindfirst32 function
- _tfindfirst64i32 function
- findfirst function
- findfirst32i64 function
- tfindfirst64 function
- _tfindfirst32 function
- tfindfirst32i64 function
- tfindfirst64i32 function
- _wfindfirsti64 function
- _findfirst32i64 function
- findfirst32 function
- findfirsti64 function
- findfirst64i32 function
- tfindfirsti64 function
- tfindfirst function
- _wfindfirst32 function
- wfindfirsti64 function
- _tfindfirsti64 function
- _tfindfirst function
- _tfindfirst32i64 function
- findfirst64 function
- _findfirst32 function
- _findfirsti64 function
- wfindfirst32i64 function
- wfindfirst64i32 function
- _wfindfirst64 function
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
ms.openlocfilehash: 879a84b14f612992ae7ed3a96211637aaf5c4783
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911739"
---
# <a name="_findfirst-_findfirst32-_findfirst32i64-_findfirst64-_findfirst64i32-_findfirsti64-_wfindfirst-_wfindfirst32-_wfindfirst32i64-_wfindfirst64-_wfindfirst64i32-_wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64

Укажите сведения о первом экземпляре имени файла, который соответствует файлу, указанному в аргументе *filespec* .

## <a name="syntax"></a>Синтаксис

```C
intptr_t _findfirst(
   const char *filespec,
   struct _finddata_t *fileinfo
);
intptr_t _findfirst32(
   const char *filespec,
   struct _finddata32_t *fileinfo
);
intptr_t _findfirst64(
   const char *filespec,
   struct _finddata64_t *fileinfo
);
intptr_t _findfirsti64(
   const char *filespec,
   struct _finddatai64_t *fileinfo
);
intptr_t _findfirst32i64(
   const char *filespec,
   struct _finddata32i64_t *fileinfo
);
intptr_t _findfirst64i32(
   const char *filespec,
   struct _finddata64i32_t *fileinfo
);
intptr_t _wfindfirst(
   const wchar_t *filespec,
   struct _wfinddata_t *fileinfo
);
intptr_t _wfindfirst32(
   const wchar_t *filespec,
   struct _wfinddata32_t *fileinfo
);
intptr_t _wfindfirst64(
   const wchar_t *filespec,
   struct _wfinddata64_t *fileinfo
);
intptr_t _wfindfirsti64(
   const wchar_t *filespec,
   struct _wfinddatai64_t *fileinfo
);
intptr_t _wfindfirst32i64(
   const wchar_t *filespec,
   struct _wfinddata32i64_t *fileinfo
);
intptr_t _wfindfirst64i32(
   const wchar_t *filespec,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Параметры

*filespec*<br/>
Спецификация целевого файла (может содержать подстановочные знаки).

*FileInfo*<br/>
Буфер сведений о файле.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **_findfirst** Возвращает уникальный описатель поиска, идентифицирующий файл или группу файлов, которые соответствуют спецификации *filespec* , которую можно использовать при последующем вызове метода [_findnext](findnext-functions.md) или для [_findclose](findclose.md). В противном случае **_findfirst** **возвращает значение-1 и устанавливает одно** из следующих значений.

| Значение errno | Условие |
|-|-|
| **еинвал** | Недопустимый параметр: *filespec* или *FileInfo* имеет **значение NULL**. Или операционная система возвратила непредвиденную ошибку. |
| **еноент** | Нет соответствий для спецификации файла. |
| **еномем** | Недостаточно памяти. |
| **еинвал** | Недопустимая спецификация имени файла, или указанное имя файла превышает **MAX_PATH**. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Если передан недопустимый параметр, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Примечания

После завершения работы с функцией **_findfirst** или [_findnext](findnext-functions.md) (или любыми вариантами) необходимо вызвать [_findclose](findclose.md) . Она освобождает ресурсы, используемые этими функциями в приложении.

Варианты этих функций с префиксом **w** — это версии для расширенных символов; в противном случае они идентичны соответствующим однобайтовым функциям.

Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные размеры файлов. Первый числовой суффикс (**32** или **64**) указывает размер типа времени; Вторым суффиксом является либо **I32** , либо **I64**, и указывает, представляется ли размер файла как 32-разрядное или 64-разрядное целое число. Сведения о том, какие версии поддерживают 32- и 64-разрядные типы времени и размеры файлов, см. в следующей таблице. Суффикс **I32** или **I64** опускается, если он совпадает с размером типа времени, поэтому **_findfirst64** также поддерживает 64-разрядную длину файлов и **_findfirst32** поддерживает только 32-разрядные длины файлов.

Эти функции используют различные формы структуры **_finddata_t** для параметра *FileInfo* . Дополнительные сведения о структуре см. в разделе [Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md).

Варианты, использующие 64-разрядный тип времени, допускают даты создания файлов до 23:59:59 31-го декабря 3000 года, время в формате UTC. Те, что используют 32-разрядные типы времени, представляют даты только до 23:59:59 18 января 2038 года, время в формате UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.

Если нет особой причины использовать версии, которые указывают размер времени явным образом, используйте **_findfirst** или **_wfindfirst** или, если требуется поддержка размеров файлов размером более 3 ГБ, используйте **_findfirsti64** или **_wfindfirsti64**. Все эти функции используют 64-разрядный тип времени. В более ранних версиях этих функций использовался 32-разрядный тип времени. Если это критическое изменение для приложения, можно определить **_USE_32BIT_TIME_T** , чтобы вернуться к старому поведению. Если определено **_USE_32BIT_TIME_T** , **_findfirst**, **_finfirsti64**и соответствующие версии Юникода используют 32-разрядное время.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="time-type-and-file-length-type-variations-of-_findfirst"></a>Варианты типов времени и типов длины файлов в функции _findfirst

|Функции|**_USE_32BIT_TIME_T** определено?|Тип времени|Тип длины файла|
|---------------|----------------------------------|---------------|----------------------|
|**_findfirst**, **_wfindfirst**|Не определено|64-разрядная версия|32-разрядная версия|
|**_findfirst**, **_wfindfirst**|Определено|32-разрядная версия|32-разрядная версия|
|**_findfirst32**, **_wfindfirst32**|Не затрагивается определением макроса|32-разрядная версия|32-разрядная версия|
|**_findfirst64**, **_wfindfirst64**|Не затрагивается определением макроса|64-разрядная версия|64-разрядная версия|
|**_findfirsti64**, **_wfindfirsti64**|Не определено|64-разрядная версия|64-разрядная версия|
|**_findfirsti64**, **_wfindfirsti64**|Определено|32-разрядная версия|64-разрядная версия|
|**_findfirst32i64**, **_wfindfirst32i64**|Не затрагивается определением макроса|32-разрядная версия|64-разрядная версия|
|**_findfirst64i32**, **_wfindfirst64i32**|Не затрагивается определением макроса|64-разрядная версия|32-разрядная версия|

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindfirst**|**_findfirst**|**_findfirst**|**_wfindfirst**|
|**_tfindfirst32**|**_findfirst32**|**_findfirst32**|**_wfindfirst32**|
|**_tfindfirst64**|**_findfirst64**|**_findfirst64**|**_wfindfirst64**|
|**_tfindfirsti64**|**_findfirsti64**|**_findfirsti64**|**_wfindfirsti64**|
|**_tfindfirst32i64**|**_findfirst32i64**|**_findfirst32i64**|**_wfindfirst32i64**|
|**_tfindfirst64i32**|**_findfirst64i32**|**_findfirst64i32**|**_wfindfirst64i32**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_findfirst**|\<io.h>|
|**_findfirst32**|\<io.h>|
|**_findfirst64**|\<io.h>|
|**_findfirsti64**|\<io.h>|
|**_findfirst32i64**|\<io.h>|
|**_findfirst64i32**|\<io.h>|
|**_wfindfirst**|\<io.h> или \<wchar.h>|
|**_wfindfirst32**|\<io.h> или \<wchar.h>|
|**_wfindfirst64**|\<io.h> или \<wchar.h>|
|**_wfindfirsti64**|\<io.h> или \<wchar.h>|
|**_wfindfirst32i64**|\<io.h> или \<wchar.h>|
|**_wfindfirst64i32**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Системные вызовы](../../c-runtime-library/system-calls.md)<br/>
[Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)<br/>
