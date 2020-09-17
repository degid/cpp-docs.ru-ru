---
title: calloc
description: Функция библиотеки времени выполнения C calloc выделяет нуль-инициализированную память.
ms.date: 4/2/2020
api_name:
- calloc
- _o_calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 067ce6f347f4b24ad8c85990e70fe4d79305535c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213636"
---
# <a name="calloc"></a>calloc

Выделяет массив в памяти и инициализирует его элементы значением 0.

## <a name="syntax"></a>Синтаксис

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*number*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**calloc** возвращает указатель на выделенное пространство. Пространство в хранилище, на которое указывает возвращаемое значение, гарантированно выровнено подходящим для хранения любого типа объектов образом. Чтобы получить указатель на тип, отличный от **`void`** , используйте приведение типа к возвращаемому значению.

## <a name="remarks"></a>Примечания

Функция **calloc** выделяет место для хранения массива *числовых* элементов, каждый из которых имеет *Размер* в байтах. Каждый элемент инициализируется значением 0.

**calloc** устанавливает **значение** **еномем** , если выделение памяти завершается ошибкой или объем запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В реализации Майкрософт, если *Number* или *size* равны нулю, **calloc** возвращает указатель на выделенный блок ненулевого размера. Попытка чтения или записи по возвращенному указателю приводит к неопределенному поведению.

**calloc** использует функцию C++ [_set_new_mode](set-new-mode.md) для установки *нового режима обработчика*. Новый режим обработчика указывает, будет ли в случае сбоя **calloc** вызывать новую подпрограммы обработчика, заданную [_set_new_handler](set-new-handler.md). По умолчанию **calloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что, когда **calloc** не сможет выделить память, он вызывает новую подпрограммы обработчика так же, как **`new`** если бы он не выйдет по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или свяжите с *использованием NEWMODE. OBJ* (см. раздел [Параметры связи](../../c-runtime-library/link-options.md)).

Если приложение связано с отладочной версией библиотек времени выполнения C, **calloc** разрешается в [_calloc_dbg](calloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**calloc** помечается `__declspec(noalias)` и `__declspec(restrict)` , что означает, что функция гарантированно не изменяет глобальные переменные и что возвращенный указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**calloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[свободный](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
