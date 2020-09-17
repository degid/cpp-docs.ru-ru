---
title: Структура once_flag
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 55c3f90f72857a4e4cd3f9075ce5bae10e14d218
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202731"
---
# <a name="once_flag-structure"></a>Структура once_flag

Представляет объект **`struct`** , используемый с функцией шаблона [call_once](../standard-library/mutex-functions.md#call_once) , чтобы код инициализации вызывался только один раз, даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

Структура once_flag {constexpr once_flag () не except;};

## <a name="remarks"></a>Примечания

`once_flag` **`struct`** Имеет только конструктор по умолчанию.

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:**\<mutex>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
