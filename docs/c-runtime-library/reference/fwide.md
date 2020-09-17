---
title: fwide
ms.date: 11/04/2016
api_name:
- fwide
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
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: 652aee03bfb5504a51d74efb326cc7a3d7c28649
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171207"
---
# <a name="fwide"></a>fwide

Не реализовано.

## <a name="syntax"></a>Синтаксис

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **файла** (игнорируется).

*mode*<br/>
Новая ширина потока: положительное значение для расширенных символов, отрицательное для байта, ноль, чтобы оставить без изменений. (Это значение игнорируется.)

## <a name="return-value"></a>Возвращаемое значение

В настоящее время эта функция просто возвращает *режим*.

## <a name="remarks"></a>Примечания

Текущая версия этой функции не соответствует стандарту.

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).
