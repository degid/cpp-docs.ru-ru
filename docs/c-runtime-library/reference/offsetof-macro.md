---
title: Макрос offsetof
ms.date: 11/04/2016
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
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: ee6d5e56bb9f41a842e53984f754c7c07d58a125
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213506"
---
# <a name="offsetof-macro"></a>Макрос offsetof

Возвращает смещение члена относительно начала его родительской структуры.

## <a name="syntax"></a>Синтаксис

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Параметры

*structName*<br/>
Имя родительской структуры данных.

*memberName*<br/>
Имя члена в родительской структуре данных, для которого определяется смещение.

## <a name="return-value"></a>Возвращаемое значение

**offsetof** возвращает смещение в байтах указанного элемента от начала родительской структуры данных. Для битовых полей оно будет неопределенным.

## <a name="remarks"></a>Примечания

Макрос **offsetof** возвращает смещение в байтах от имени *MemberName* с начала структуры, заданной параметром *структнаме* , в качестве значения типа **size_t**. Можно указать типы с помощью **`struct`** ключевого слова.

> [!NOTE]
> **offsetof** не является функцией и не может быть описан с помощью прототипа C.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
