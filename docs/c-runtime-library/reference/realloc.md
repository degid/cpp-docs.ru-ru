---
title: realloc
description: Справочник по API для перераспределения (); который перераспределяет блоки памяти.
ms.date: 9/11/2020
api_name:
- realloc
- _o_realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
ms.openlocfilehash: c68909b2f5d73959465d63af522ceeb00c8ce23e
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075820"
---
# <a name="realloc"></a>realloc

Повторное выделение блоков памяти.

## <a name="syntax"></a>Синтаксис

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*`memblock`*\
Указатель на ранее выделенный блок памяти.

*`size`*\
Новый размер в байтах.

## <a name="return-value"></a>Возвращаемое значение

**`realloc`** Возвращает **`void`** указатель на перераспределенный (и, возможно, перемещенный) блок памяти.

Если недостаточно памяти для расширения блока до заданного размера, исходный блок остается без изменений и **`NULL`** возвращается.

Если *`size`* параметр равен нулю, то блок, на который указывает, *`memblock`* освобождается; возвращаемое значение равно **`NULL`** , и остается *`memblock`* указывающим на освобожденный блок.

Возвращаемое значение указывает на дисковое пространство, которое подстраивается для хранения любого типа объекта. Чтобы получить указатель на тип, отличный от **`void`** , используйте приведение типа к возвращаемому значению.

## <a name="remarks"></a>Примечания

> [!NOTE]
> **`realloc`** не было обновлено для реализации поведения C17, так как новое поведение несовместимо с операционной системой Windows.

**`realloc`** Функция изменяет размер выделенного блока памяти. *`memblock`* Аргумент указывает на начало блока памяти. Если *`memblock`* имеет значение **`NULL`** , **`realloc`** ведет себя так же, как **`malloc`** и, и выделяет новый блок *`size`* байтов. Если *`memblock`* параметр не равен **`NULL`** , это должен быть указатель, возвращенный предыдущим вызовом функции **`calloc`** , **`malloc`** или **`realloc`** .

*`size`* Аргумент задает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным, хотя новый блок может находиться в другом расположении. Так как новый блок может находиться в новом месте в памяти, указатель, возвращенный, **`realloc`** не обязательно должен быть указателем, передаваемым через *`memblock`* аргумент. **`realloc`** не приводит к обнулению выделенной памяти в случае роста буфера.

**`realloc`** Задает **`errno`** значение, равное **`ENOMEM`** , если выделение памяти завершается ошибкой или объем запрошенной памяти превышает **`_HEAP_MAXREQ`** . Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**`realloc`** вызывает метод **`malloc`** , чтобы использовать функцию [_set_new_mode](set-new-mode.md) C++ для установки нового режима обработчика. Новый режим обработчика указывает, будет ли при сбое **`malloc`** вызывать новую подпрограммы обработчика, заданную [_set_new_handler](set-new-handler.md). По умолчанию не **`malloc`** вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что при **`realloc`** сбое выделения памяти **`malloc`** вызывает новую подпрограммы обработчика таким же образом, как и **`new`** оператор, когда он завершается сбоем по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием NEWMODE.OBJ (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Если приложение связано с отладочной версией библиотек времени выполнения C, **`realloc`** разрешается в [_realloc_dbg](realloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**`realloc`** помечается `__declspec(noalias)` и `__declspec(restrict)` , что означает, что функция гарантированно не изменяет глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**`realloc`**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)\
[calloc](calloc.md)\
[свободный](free.md)\
[malloc](malloc.md)
