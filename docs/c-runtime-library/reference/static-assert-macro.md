---
title: Макрос _STATIC_ASSERT
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
- _STATIC_ASSERT
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
ms.openlocfilehash: 78544424b727797158109fa3000ee2ebf8066cf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229328"
---
# <a name="_static_assert-macro"></a>Макрос _STATIC_ASSERT

Вычисление выражения во время компиляции и создание ошибки, когда результат равен **false**.

## <a name="syntax"></a>Синтаксис

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Параметры

*булеанекспрессион*<br/>
Выражение (включая указатели), результатом вычисления которого является ненулевое**значение (true**) или 0 (**false**).

## <a name="remarks"></a>Примечания

Этот макрос напоминает [_ASSERT и _ASSERTE макросы](assert-asserte-assert-expr-macros.md), за исключением того, что *булеанекспрессион* вычисляется во время компиляции, а не в среде выполнения. Если *булеанекспрессион* принимает **значение false** (0), создается [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) .

## <a name="example"></a>Пример

В этом примере мы проверяем, имеет ли значение [sizeof](../../c-language/sizeof-operator-c.md) значение, **`int`** большее или равное 2 байтам, и является ли значение [sizeof](../../c-language/sizeof-operator-c.md) a **`long`** равным 1 байтом. Программа не будет компилироваться, и она создаст [ошибку компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) , так как значение превышает **`long`** 1 байт.

```C
// crt__static_assert.c

#include <crtdbg.h>
#include <stdio.h>

_STATIC_ASSERT(sizeof(int) >= 2);
_STATIC_ASSERT(sizeof(long) == 1);  // C2466

int main()
{
    printf("I am sure that sizeof(int) will be >= 2: %d\n",
        sizeof(int));
    printf("I am not so sure that sizeof(long) == 1: %d\n",
        sizeof(long));
}
```

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>См. также статью

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[Макросы _ASSERT, _ASSERTE и _ASSERT_EXPR](assert-asserte-assert-expr-macros.md)<br/>
