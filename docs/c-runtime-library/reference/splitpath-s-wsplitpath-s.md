---
title: _splitpath_s, _wsplitpath_s
ms.date: 4/2/2020
api_name:
- _wsplitpath_s
- _splitpath_s
- _o__splitpath_s
- _o__wsplitpath_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: 984b55737e575656670f561c45f528265800f214
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920288"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

Разбивает имя пути на компоненты. Это версии функции [_splitpath, _wsplitpath](splitpath-wsplitpath.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>Параметры

*path*<br/>
Полный путь.

*диск*<br/>
Буква диска, за которой следует двоеточие (**:**). Если буква диска не нужна, можно передать **значение NULL** для этого параметра.

*дривенумберофелементс*<br/>
Размер буфера *диска* в однобайтовых или расширенных символах. Если параметр *Drive* имеет **значение NULL**, это значение должно быть равно 0.

*dir*<br/>
Путь к каталогу, включая заключительную косую черту. Можно использовать символы косой **/** черты (), обратные косые черты ( **\\** ) или и то, и другое. Если путь к каталогу не требуется, можно передать **значение NULL** для этого параметра.

*дирнумберофелементс*<br/>
Размер буфера *dir* в однобайтовых или расширенных символах. Если параметр *dir* имеет **значение NULL**, это значение должно быть равно 0.

*fname*<br/>
Базовое имя файла (без расширения). Если имя файла не требуется, можно передать **значение NULL** для этого параметра.

*наменумберофелементс*<br/>
Размер буфера *fname* в однобайтовых или расширенных символах. Если параметр *fname* имеет **значение NULL**, это значение должно быть равно 0.

*WLAN*<br/>
Расширение имени файла, включая начальную точку (**.**). Если расширение имени файла не требуется, можно передать **значение NULL** для этого параметра.

*екстнумберофелементс*<br/>
Размер *ext* buffer в однобайтовых или расширенных символах. Если *ext* имеет **значение NULL**, это значение должно быть равно 0.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|Условие|Возвращаемое значение|
|---------------|------------------|
|*путь* имеет **значение NULL**|**еинвал**|
|*диск* имеет **значение NULL**, *дривенумберофелементс* не равен нулю|**еинвал**|
|*диск* не равен**null**, *дривенумберофелементс* равен нулю|**еинвал**|
|*dir* имеет **значение NULL**, *дирнумберофелементс* не равен нулю|**еинвал**|
|*dir* не имеет**значение NULL**, *дирнумберофелементс* равен нулю|**еинвал**|
|*fname* имеет **значение NULL**, *наменумберофелементс* не равен нулю|**еинвал**|
|*fname* не равен**null**, *наменумберофелементс* равен нулю|**еинвал**|
|*ext* имеет **значение NULL**, *екстнумберофелементс* не равно нулю|**еинвал**|
|*ext* не имеет**значение NULL**, *екстнумберофелементс* равен нулю|**еинвал**|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают **еинвал**.

Если какой-либо из буферов слишком короткий для хранения результата, эти функции очищают все буферы до пустых строк **, устанавливают значение** очистки **ERANGE**и возвращают **ERANGE**.

## <a name="remarks"></a>Примечания

Функция **_splitpath_s** разбивает путь на четыре компонента. **_splitpath_s** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с используемой в данный момент многобайтовой кодовой страницей. **_wsplitpath_s** — это версия **_splitpath_s**для расширенных символов; аргументы для **_wsplitpath_s** являются строками расширенных символов. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Каждый компонент полного пути хранится в отдельном буфере. константы манифеста **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**и **_MAX_EXT** (определяются в STDLIB. З) укажите максимально допустимый размер для каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

В приведенной ниже таблице перечислены значения констант манифеста.

|Имя|Значение|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Если полный путь не содержит компонент (например, имя файла), **_splitpath_s** присваивает соответствующему буферу пустую строку.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
