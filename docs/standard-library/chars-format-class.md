---
title: Перечисление chars_format
ms.date: 08/03/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: d7f95d9bd1522fa0896ccdbac6c1dbc770f2b272
ms.sourcegitcommit: 4eda68a0b3c23d8cefa56b7ba11583412459b32f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87565941"
---
# <a name="chars_format-enum"></a>Перечисление chars_format

Используется с [\<charconv>](charconv.md) библиотекой для указания формата с плавающей запятой для числовых преобразований типа "примитив".

## <a name="syntax"></a>Синтаксис

```cpp
enum class chars_format {
    scientific = unspecified,
    fixed = unspecified,
    hex = unspecified,
    general = fixed | scientific
};
```

### <a name="members"></a>Участники

|Элемент|Описание|
|-|-|
| `scientific` | Приводит `from_chars()` к ожиданию и синтаксическому анализу экспоненты. Он похож на `printf()` описатель формата `'e'` , который форматируется для экспоненциального представления, например `"1.729e+01"` . |
| `fixed` | `from_chars()`Не приводит к ожиданиям или синтаксическому анализу экспоненты. Он похож на `printf()` описатель формата `'f'` , который форматирует для операций с плавающей запятой, например `"17.29"` .|
| `hex` | Приводит `from_chars()` к ожиданию числа в шестнадцатеричном формате, но без ведущего `0x` . |
| `general` | Приводит к тому, `from_chars()` что функция принимает (но не требует) показатель степени. Для `to_chars()` он похож на `printf()` описатель формата `'g'` , который переключается между экспоненциальной нотацией или фиксированной. Он учитывает, что может быть экспонентой для создания достаточно компактного вывода. Например: `1e-5` результаты в `"1e-05"` , но `1e-4` результат `"0.001"` . `1e5`приводит к результату `100000` , а `1e6` в результате `1e+06` . `1e0`создает `1` .|

## <a name="remarks"></a>Примечания

Для функций [from_chars](charconv-functions.md#from_chars) это перечисление описывает предполагаемый тип входных данных.
Для функций [to_chars](charconv-functions.md#to_chars) он описывает, какой тип выходных данных следует выдавать.

## <a name="requirements"></a>Требования

**Заголовок:**\<charconv>

**Пространство имен:** std

/std: требуется c++ 17 или более поздней версии.

## <a name="see-also"></a>См. также раздел

[\<charconv>](../standard-library/charconv.md)  
[описатели формата printf ()](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
