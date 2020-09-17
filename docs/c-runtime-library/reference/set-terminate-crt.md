---
title: set_terminate (CRT)
ms.date: 4/2/2020
api_name:
- set_terminate
- _o_set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 70ed4adb7ceada53205fd69f111c8976fe95c711
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234020"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

Устанавливает собственную подпрограммы завершения для вызова методом **Terminate**.

## <a name="syntax"></a>Синтаксис

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Параметры

*термфунктион*<br/>
Указатель на пользовательскую функцию завершения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию, зарегистрированную **set_terminate** , чтобы предыдущую функцию можно было восстановить позже. Если Предыдущая функция не задана, то возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **равно NULL**.

## <a name="remarks"></a>Примечания

Функция **set_terminate** устанавливает *термфунктион* в качестве функции, вызываемой методом **Terminate**. **set_terminate** используется с обработкой исключений C++ и может вызываться в любой точке программы до возникновения исключения. **terminate** по умолчанию [прерывания вызовов прерывается](abort.md) . Это значение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_terminate** с именем функции в качестве аргумента. Функция **Terminate** вызывает последнюю функцию, заданную в качестве аргумента для **set_terminate**. После выполнения любых необходимых задач очистки *термфунктион* должен выйти из программы. Если он не завершает работу (если он возвращается вызывающему объекту), вызывается метод [Abort](abort.md) .

В многопоточной среде функции завершения поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции завершения. Таким образом, каждый поток отвечает за собственную обработку завершения.

Тип **terminate_function** ОПРЕДЕЛЕН в EH. H в качестве указателя на определяемую пользователем функцию завершения, *термфунктион* , которая возвращает **`void`** . Пользовательская функция *термфунктион* может не принимать аргументы и не должна возвращать ее вызывающему объекту. Если это так, вызывается [Abort](abort.md) . Исключение не может быть вызвано в *термфунктион*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> Функция **set_terminate** работает только вне отладчика.

Для всех динамически связанных библиотек DLL или exe существует один обработчик **set_terminate** ; даже при вызове **set_terminate** обработчик может быть заменен другим или же вы можете заменить обработчик, заданный другой библиотекой DLL или exe.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [terminate](terminate-crt.md).

## <a name="see-also"></a>См. также статью

[Подпрограммы обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[заканчива](terminate-crt.md)<br/>
[известно](unexpected-crt.md)<br/>
