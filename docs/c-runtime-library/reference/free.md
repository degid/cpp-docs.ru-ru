---
title: свободный
ms.date: 4/2/2020
api_name:
- free
- _o_free
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: 0e0a53dd9d24634442c8dd456e4f9d38f742e292
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920426"
---
# <a name="free"></a>свободный

Освобождает блок памяти.

## <a name="syntax"></a>Синтаксис

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Ранее выделенный блок памяти, который требуется освободить.

## <a name="remarks"></a>Примечания

Функция **Free освобождает** блок памяти (*мемблокк*), который был ранее выделен вызовом **calloc**, **malloc**или **realloc**. Число освобожденных байтов эквивалентно числу байтов, запрошенных при выделении или повторном выделении блока (в случае **перераспределения**). Если *мемблокк* имеет **значение NULL**, указатель пропускается, и функция **Free** немедленно возвращается. Попытка освободить недопустимый указатель (указатель на блок памяти, который не был выделен с помощью **calloc**, **malloc**или **перераспределения**) может повлиять на последующие запросы на выделение и привести к ошибкам.

Если при освобождении памяти произошла ошибка, то параметру "очистить" **задается** информация из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

После освобождения блока памяти функция [_heapmin](heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.

Если приложение связано с отладочной версией библиотек времени выполнения C, **Free** разрешается в [_free_dbg](free-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Функция **Free** помечена `__declspec(noalias)`, а это означает, что функции гарантированно не изменяют глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

Для освобождения памяти, которая выделена функцией [_malloca](malloca.md), используйте функцию [_freea](freea.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**свободный**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [malloc](malloc.md).

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
