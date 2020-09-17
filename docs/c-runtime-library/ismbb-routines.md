---
title: Процедуры _ismbb
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbb
- ismbb
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
ms.openlocfilehash: b8828018040b8b6b7b13c88c08599333dc1124d0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839378"
---
# <a name="_ismbb-routines"></a>Процедуры _ismbb

Проверяет заданное целочисленное значение `c` на выполнение определенного условия, используя текущий языковой стандарт или указанную категорию состояния преобразования LC_CTYPE.

:::row:::
   :::column span="":::
      [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)\
      [_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)\
      [_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)\
      [_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)\
      [_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)\
      [_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)\
   :::column-end:::
   :::column span="":::
      [_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)\
      [_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)\
      [_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)\
      [_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)\
      [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)\
      [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)\
   :::column-end:::
:::row-end:::

## <a name="remarks"></a>Примечания

Каждая из подпрограмм семейства `_ismbb` проверяет заданное целочисленное значение `c` на выполнение определенного условия. Результат проверки зависит от действующей многобайтовой кодовой страницы. По умолчанию в качестве многобайтовой кодовая страницы установлена кодовая страница ANSI, полученная от операционной системы при запуске программы. Можно использовать [_getmbcp](../c-runtime-library/reference/getmbcp.md), чтобы запросить использующуюся в данный момент многобайтовую кодовую страницу, или [_setmbcp](../c-runtime-library/reference/setmbcp.md), чтобы изменить ее.

Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого зависящего от языкового стандарта поведения; версии с суффиксом **_l** идентичны им за тем исключением, что они используют переданный в них параметр языкового стандарта.

Подпрограммы семейства `_ismbb` проверяют заданное целое число `c` следующим образом.

|Подпрограмма|Условие проверки байта|
|-------------|-------------------------|
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|То же, что и `_ismbbprint`, но `_ismbbgraph` не включает символ пробела (0x20).|
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Не входящий в набор ASCII текстовый символ, отличный от знака препинания. Например, только для кодовой страницы 932, функция `_ismbbkalnum` проверяет на принадлежность к алфавитно-цифровым символам катаканы.|
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Катакана (0xA1–0xDF). Применяется только к кодовой странице 932.|
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Не входящие в набор ASCII текстовые и пунктуационные символы. Например, только для кодовой страницы 932, `_ismbbkprint` проверяет на принадлежность к алфавитно-цифровым или пунктуационным символам катаканы (диапазон: 0xA1–0xDF).|
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Не входящий в набор ASCII знак препинания. Например, только для кодовой страницы 932, `_ismbbkpunct` проверяет на принадлежность к пунктуационным символам катаканы.|
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Первый байт многобайтового символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x81–0x9F, 0xE0–0xFC.|
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** содержит символ пробела (0x20).|
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Второй байт многобайтового символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x40–0x7E, 0x80–0xEC.|

В следующей таблице приведены значения ORed, составляющие условия проверки для этих подпрограмм. Константы манифеста `_BLANK`, `_DIGIT`, `_LOWER`, `_PUNCT`и `_UPPER` определены в Ctype.h.

|Подпрограмма|_BLANK|_DIGIT|LOWER|_PUNCT|UPPER|Не-<br /><br /> ASCII<br /><br /> text|Не-<br /><br /> ASCII<br /><br /> punct|
|-------------|-------------|-------------|-----------|-------------|-----------|------------------------------|-------------------------------|
|`_ismbbalnum`|—|x|x|—|x|x|—|
|`_ismbbalpha`|—|—|x|—|x|x|—|
|`_ismbbblank`|x|—|—|—|—|—|—|
|`_ismbbgraph`|—|x|x|x|x|x|x|
|`_ismbbkalnum`|—|—|—|—|—|x|—|
|`_ismbbkprint`|—|—|—|—|—|x|x|
|`_ismbbkpunct`|—|—|—|—|—|—|x|
|`_ismbbprint`|x|x|x|x|x|x|x|
|`_ismbbpunct`|—|—|—|x|—|—|x|

Подпрограммы `_ismbb` реализованы и как функции, и как макросы. Дополнительные сведения о выборе любой реализации см. в разделе [Рекомендации по выбору между функциями и макросами](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../c-runtime-library/byte-classification.md)<br/>
[является, подпрограммы isw](../c-runtime-library/is-isw-routines.md)<br/>
[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)<br/>
[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)
