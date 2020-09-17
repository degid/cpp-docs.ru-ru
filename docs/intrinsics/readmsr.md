---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 029119bc47d0172c7e9cc5fbf8cd20c4ee23e0f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219655"
---
# <a name="__readmsr"></a>__readmsr

**Блок, относящийся только к системам Microsoft**

Формирует `rdmsr` инструкцию, которая считывает регистр, зависящий от модели, **`register`** и возвращает его значение.

## <a name="syntax"></a>Синтаксис

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Параметры

*зарегистрировать*\
окне Зависящий от модели регистр для чтения.

## <a name="return-value"></a>Возвращаемое значение

Значение в указанном регистре.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Эта функция доступна только в режиме ядра, и подпрограммы доступны только в качестве встроенных.

Дополнительные сведения см. в документации по AMD.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
