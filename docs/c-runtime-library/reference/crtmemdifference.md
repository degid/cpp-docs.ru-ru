---
title: _CrtMemDifference
ms.date: 11/04/2016
api_name:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: 51bfa014d54f55843fcb112f318f143774abf8f3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938710"
---
# <a name="_crtmemdifference"></a>_CrtMemDifference

Сравнивает два состояния памяти и возвращает их различия (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Параметры

*статедифф*<br/>
Указатель на структуру **_CrtMemState** , которая используется для хранения различий между двумя состояниями памяти (возвращаемым).

*олдстате*<br/>
Указатель на более раннее состояние памяти (структура **_CrtMemState** ).

*newState*<br/>
Указатель на более позднее состояние памяти (структура **_CrtMemState** ).

## <a name="return-value"></a>Возвращаемое значение

Если состояния памяти значительно отличаются, **_CrtMemDifference** возвращает значение true. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

Функция **_CrtMemDifference** сравнивает *олдстате* и *NewState* и сохраняет их различия в *статедифф*, который затем может использоваться приложением для обнаружения утечек памяти и других проблем с памятью. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtMemDifference** удаляются во время предварительной обработки.

*NewState* и *олдстате* должны быть допустимыми указателями на структуру **_Crtmemstate** , определенные в файле Crtdbg.h, заполненном [_CrtMemCheckpoint](crtmemcheckpoint.md) перед вызовом **_CrtMemDifference**. *статедифф* должен быть указателем на ранее выделенный экземпляр структуры **_CrtMemState** . Если *статедифф*, *NewState*или *олдстате* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для параметра [_doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) устанавливается значение **еинвал** , а функция возвращает значение false.

**_CrtMemDifference** сравнивает значения полей **_Crtmemstate** блоков в *олдстате* с ними в *NewState* и сохраняет результат в *статедифф*. Если количество выделенных типов блоков или общее количество выделенных блоков каждого типа различается в двух состояниях памяти, считается, что состояния значительно отличаются. Разница между наибольшим объемом, когда-либо выделено за один раз для двух состояний, и разность между общими распределениями для двух состояний также хранится в *статедифф*.

По умолчанию внутренние блоки времени выполнения C ( **_CRT_BLOCK**) не включаются в операции состояния памяти. Функцию [_CrtSetDbgFlag](crtsetdbgflag.md) можно использовать, чтобы включить **_CRTDBG_CHECK_CRT_DF** бит **_crtDbgFlag** , чтобы включить эти блоки в обнаружение утечек и другие операции состояния памяти. Освобожденные блоки памяти ( **_FREE_BLOCK**) не приводят к тому, что **_CrtMemDifference** возвращает значение true.

Дополнительные сведения о функциях состояния кучи и структуре **_CrtMemState** см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Libraries** Только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
