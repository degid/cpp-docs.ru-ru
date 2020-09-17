---
title: _CrtSetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtSetDumpClient
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: fd2b037ce10f708ab133f31a20636438b0d04b93
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234267"
---
# <a name="_crtsetdumpclient"></a>_CrtSetDumpClient

Устанавливает определяемую приложением функцию для дампа блоков памяти **_CLIENT_BLOCK** типа (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Параметры

*думпклиент*<br/>
Новая, определяемая клиентом функция дампа памяти, которую необходимо прикрепить к отладочному процессу дампа памяти среды выполнения C.

## <a name="return-value"></a>Возвращаемое значение

Возвращает определенную ранее функцию дампа клиентских блоков.

## <a name="remarks"></a>Примечания

Функция **_CrtSetDumpClient** позволяет приложению подключать собственную функцию для дампа объектов, хранящихся в **_CLIENT_BLOCK** блоках памяти, в процесс дампа памяти отладки среды выполнения C. В результате каждый раз, когда функция дампа отладки, например [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) или [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) , выводит дамп **_CLIENT_BLOCK** блока памяти, также вызывается функция дампа приложения. **_CrtSetDumpClient** предоставляет приложению простой способ обнаружения утечек памяти и проверки или сообщения содержимого данных, хранящихся в блоках **_CLIENT_BLOCK** . Если [_DEBUG](../../c-runtime-library/debug.md) не определено, вызовы **_CrtSetDumpClient** удаляются во время предварительной обработки.

Функция **_CrtSetDumpClient** устанавливает новую определяемую приложением функцию дампа, указанную в *думпклиент* , и возвращает ранее определенную функцию дампа. Пример функции дампа клиентского блока выглядит следующим образом:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

Аргумент *усерпортион* — это указатель на начало части данных в блоке памяти, а размер выделяемого блока *памяти — в* байтах. Функция дампа клиентского блока должна возвращать значение **`void`** . Указатель на функцию дампа клиента, которая передается в **_CrtSetDumpClient** , имеет тип **_CRT_DUMP_CLIENT**, как определено в Crtdbg.h:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Дополнительные сведения о функциях, которые работают с блоками памяти **_CLIENT_BLOCK** типа, см. в разделе [функции-ловушки клиентского блока](/visualstudio/debugger/client-block-hook-functions). Функцию [_CrtReportBlockType](crtreportblocktype.md) можно использовать для получения сведений о типах и подтипов блоков.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также статью

[Отладочные подпрограммы](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
