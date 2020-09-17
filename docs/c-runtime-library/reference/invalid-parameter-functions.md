---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 4/2/2020
api_name:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
- _o__invalid_parameter_noinfo
- _o__invalid_parameter_noinfo_noreturn
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
ms.openlocfilehash: 7138e9cb7381e4d40911054e1473536b6e639e2d
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919824"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Эти функции используются библиотекой времени выполнения C для обработки недопустимых параметров, передаваемых в функции библиотеки CRT. Эти функции также могут использоваться в коде для поддержки определенных по умолчанию или настраиваемых механизмов обработки недопустимых параметров.

## <a name="syntax"></a>Синтаксис

```C
extern "C" void __cdecl
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);

extern "C" void __cdecl
_invalid_parameter_noinfo(void);

extern "C" __declspec(noreturn) void __cdecl
_invalid_parameter_noinfo_noreturn(void);

extern "C" __declspec(noreturn) void __cdecl
_invoke_watson(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="parameters"></a>Параметры

*expression*<br/>
Строка, представляющая выражение параметра исходного кода, которое не является допустимым.

*function_name*<br/>
Имя функции, которая вызвала обработчик.

*file_name*<br/>
Файл исходного кода, в котором был вызван обработчик.

*line_number*<br/>
Номер строки в исходном коде, где был вызван обработчик.

*процессу*<br/>
Не используется.

## <a name="return-value"></a>Возвращаемое значение

Эти функции не возвращают значения. Функции **_invalid_parameter_noinfo_noreturn** и **_invoke_watson** не возвращают вызывающему объекту, а в некоторых случаях **_invalid_parameter** и **_invalid_parameter_noinfo** могут не возвращать вызывающему объекту.

## <a name="remarks"></a>Примечания

Если функциям библиотеки времени выполнения C передаются недопустимые параметры, они вызывают *обработчик недопустимого параметра*. Он представляет собой функцию, в которой программист задает выполнение определенных действий. Например, обработчик может сообщить о проблеме пользователю, записать данные в журнал, установить прерывание в отладчике, завершить работу программы или не выполнять никаких действий. Если программист не указал функцию, вызывается обработчик по умолчанию **_invoke_watson**.

По умолчанию, если в коде отладки указан недопустимый параметр, функции библиотеки CRT вызывают функцию, **_invalid_parameter** с помощью подробных параметров. В неотладочном коде вызывается функция **_invalid_parameter_noinfo** , которая вызывает функцию **_invalid_parameter** , используя пустые параметры. Если функция библиотеки CRT, не относящаяся к отладке, требует завершения программы, вызывается функция **_invalid_parameter_noinfo_noreturn** , которая вызывает функцию **_invalid_parameter** с использованием пустых параметров, за которым следует вызов функции **_invoke_watson** для принудительного завершения программы.

Функция **_invalid_parameter** проверяет, установлен ли заданный пользователем обработчик недопустимых параметров, и, если да, вызывает его. Например, если в текущем потоке пользователь определил локальный для потока обработчик, вызвав функцию [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. Если пользователь определил глобальный обработчик недопустимого параметра, вызвав функцию [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. В противном случае вызывается обработчик по умолчанию **_invoke_watson** . Поведение **_invoke_watson** по умолчанию — завершение программы. Определенные пользователем обработчики могут завершать работу программы или выполнять возврат. В тех случаях, когда восстановление работоспособности программы не гарантировано, рекомендуется завершать ее.

При вызове обработчика по умолчанию **_invoke_watson** , если процессор поддерживает операцию [__fastfail](../../intrinsics/fastfail.md) , он вызывается с помощью параметра **FAST_FAIL_INVALID_ARG** и процесс завершается. В противном случае возникает исключение с быстрым прекращением, которое может быть перехвачено с помощью связанного отладчика. Если процесс может продолжаться, он завершается вызовом функции Windows **терминатепроцесс** с использованием состояния кода исключения **STATUS_INVALID_CRUNTIME_PARAMETER**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Проверка параметров](../../c-runtime-library/parameter-validation.md)<br/>
