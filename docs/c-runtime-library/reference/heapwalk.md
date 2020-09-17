---
title: _heapwalk
ms.date: 11/04/2016
api_name:
- _heapwalk
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- heapwalk
- _heapwalk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
ms.openlocfilehash: 8dc7ee9335f227bde93a414748ff70b165c44f8d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954774"
---
# <a name="_heapwalk"></a>_heapwalk

Выполняет обход кучи и возвращает сведения о следующей записи.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows, за исключением отладочных сборок. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Параметры

*ентринфо*<br/>
Буфер, который будет содержать данные кучи.

## <a name="return-value"></a>Возвращаемое значение

**_heapwalk** возвращает одну из следующих целочисленных констант манифеста, определенных в malloc.h.

|Возвращаемое значение|Значение|
|-|-|
|**_HEAPBADBEGIN**| Начальные сведения о заголовке недопустимы или не найдены.|
|**_HEAPBADNODE**| Куча повреждена или обнаружен плохой узел.|
|**_HEAPBADPTR**| Поле **_pentry** структуры **_HEAPINFO** не содержит допустимый указатель в куче, или *ентринфо* является пустым указателем.|
|**_HEAPEND**| Успешно достигнут конец кучи.|
|**_HEAPEMPTY**| Куча еще не инициализирована.|
|**_HEAPOK**| Нет ошибок на данный момент; *ентринфо* обновляется информацией о следующей записи кучи.|

Кроме того, при возникновении ошибки **_heapwalk** **устанавливает значение** «от» до **еносис**.

## <a name="remarks"></a>Примечания

Функция **_heapwalk** помогает отладить проблемы, связанные с кучей, в программах. Функция проходит через кучу, просматривает одну запись на вызов и возвращает указатель на структуру типа **_HEAPINFO** , содержащую сведения о следующей записи кучи. Тип **_HEAPINFO** , определенный в malloc.h, содержит следующие элементы.

|Поле|Значение|
|-|-|
|`int *_pentry`|Указатель записи кучи.|
|`size_t _size`|Размер записи кучи.|
|`int _useflag`|Флаг, указывающий, используется ли запись кучи.|

Вызов **_heapwalk** , который возвращает **_HEAPOK** , сохраняет размер записи в поле **_size** и задает для поля **_useflag** значение **_FREEENTRY** или **_USEDENTRY** (оба являются константами, определенными в malloc.h). Чтобы получить эти сведения о первой записи в куче, передайте **_heapwalk** указатель на структуру **_HEAPINFO** , член **_pentry** которой имеет **значение NULL**. Если операционная система не поддерживает **_heapwalk**(например, Windows 98), функция возвращает **_HEAPEND** **и устанавливает значение** переводится в **еносис**.

Эта функция проверяет свои параметры. Если *ентринфо* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** задается значение, а функция возвращает **_HEAPBADPTR**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
