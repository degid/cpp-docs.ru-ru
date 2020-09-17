---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: f3f6c4886d22c7cd12b29950c114fbcde8905c28
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845748"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Включите стандартный заголовок \<iomanip> объекта `iostreams` для определения нужного числа манипуляторов, каждый из которых принимает один аргумент.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Примечания

Каждый из этих манипуляторов возвращает неуказанный тип, вызываемый с `T1` помощью `T10` , который перегружает `basic_istream` \<**Elem**, **Tr**> `::` [Операторы>>](../standard-library/istream-operators.md#op_gt_gt) и `basic_ostream` \<**Elem**, **Tr**> `::` [operator<<](../standard-library/ostream-operators.md#op_lt_lt).

### <a name="manipulators"></a>Манипуляторы

|Имя|Описание|
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Получает денежную сумму (при необходимости в международном формате).|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Получает время в структуре времени с использованием указанного формата.|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Предоставляет денежную сумму (при необходимости в международном формате).|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Предоставляет время в структуре времени и строку формата, которую следует использовать.|
|[в кавычках](../standard-library/iomanip-functions.md#quoted)|Обеспечивает удобное обращение строк с помощью операторов вставки и извлечения.|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Удаляет указанные флаги.|
|[сетбасе](../standard-library/iomanip-functions.md#setbase)|Задает основание целых чисел.|
|[сетфилл](../standard-library/iomanip-functions.md#setfill)|Задает символ, который будет использоваться для заполнения пробелов на экране с выравниванием по правому краю.|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Задает указанные флаги.|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Задает точность для значений с плавающей запятой.|
|[setw](../standard-library/iomanip-functions.md#setw)|Задает ширину отображаемого поля.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
