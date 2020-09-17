---
title: Процедуры _ismbc
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbc
helpviewer_keywords:
- ismbc routines
- _ismbc routines
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
ms.openlocfilehash: 056cc4bc5344ee8833b3f6e645616657f1958897
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839365"
---
# <a name="_ismbc-routines"></a>Процедуры _ismbc

Каждая из подпрограмм **_ismbc** проверяет определенный многобайтовый символ `c` на соответствие заданному условию.

:::row:::
   :::column span="":::
      [_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)\
      [_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)\
      [_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)\
      [_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)\
      [_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)\
      [_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)
   :::column-end:::
:::row-end:::

## <a name="remarks"></a>Примечания

Результат проверки каждой процедуры **_ismbc** зависит от действующей многобайтовой кодовой страницы. Многобайтовые кодовые страницы содержат однобайтовые буквенные символы. По умолчанию в качестве многобайтовой кодовой страницы установлена стандартная системная кодовая страница ANSI, полученная от операционной системы при запуске программы. Запросить или изменить многобайтовую кодовую страницу можно с помощью функций [_getmbcp](../c-runtime-library/reference/getmbcp.md) или [_setmbcp](../c-runtime-library/reference/setmbcp.md) соответственно.

Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта.

|Подпрограмма|Условие теста|Пример кодовой страницы 932|
|-------------|--------------------|---------------------------|
|[_ismbcalnum, _ismbcalnum_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Буквенно-цифровой|Возвращает отличное от нуля значение только в том случае, если `c` — однобайтовое представление английской буквы в коде ASCII: см. примеры для `_ismbcdigit` и `_ismbcalpha`.|
|[_ismbcalpha, _ismbcalpha_l](../c-runtime-library/reference/ismbcalnum-functions.md)|По алфавиту|Возвращает отличное от нуля значение только в том случае, если `c` — однобайтовое представление английской буквы в коде ASCII: см. примеры для `_ismbcupper` и `_ismbclower`; или буква катаканы: 0xA6<=`c`<=0xDF.|
|[_ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Цифровой|Возвращает отличное от нуля значение только в том случае, если `c` — однобайтовое представление цифры в коде ASCII: 0x30<=`c`<=0x39.|
|[_ismbcgraph, _ismbcgraph_l](../c-runtime-library/reference/ismbcgraph-functions.md)|GRAPHIC|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого печатного символа ASCII или катаканы, кроме пробела ( ). См. примеры для `_ismbcdigit`, `_ismbcalpha` и `_ismbcpunct`.|
|[_ismbclegal, _ismbclegal_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Допустимый многобайтовый символ|Возвращает ненулевое значение только в том случае, если первый байт `c` находится в диапазонах 0x81–0x9F или 0xE0–0xFC, а второй — в диапазонах 0x40–0x7E или 0x80–FC.|
|[_ismbclower, _ismbclower_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Строчные буквы|Возвращает ненулевое значение только в том случае, если `c` — однобайтовое представление английской буквы в коде ASCII в нижнем регистре: 0x61<=`c`<=0x7A.|
|[_ismbcprint, _ismbcprint_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Печатные символы|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого печатного символа ASCII или катаканы, включая пробел ( ): см. примеры для `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha` и `_ismbcpunct`.|
|[_ismbcpunct, _ismbcpunct_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Пунктуация|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого знака препинания ASCII или катаканы.|
|[_ismbcblank, _ismbcblank_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Пробелы или символы горизонтальной табуляции|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением символа пробела или горизонтальной табуляции: `c`=0x20 или `c`=0x09.|
|[_ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Пробелы|Возвращает ненулевое значение только в том случае, если `c` является символом пробела: `c`=0x20 или 0x09<=`c`<=0x0D.|
|[_ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Многобайтовый символ|Возвращает ненулевое значение только в том случае, если 0x8141<=`c`<=0x81AC.|
|[_ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Прописные буквы|Возвращает ненулевое значение только в том случае, если `c` — однобайтовое представление английской буквы в коде ASCII в верхнем регистре: 0x41<=`c`<=0x5A.|

**Раздел для кодовой страницы 932**

Следующие подпрограммы применяются только к кодовой странице 932.

|Подпрограмма|Условие теста (только для кодовой страницы 932)|
|-------------|-------------------------------------------|
|[_ismbchira, _ismbchira_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Двухбайтовые символы хираганы: 0x829F<=`c`<=0x82F1.|
|[_ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Двухбайтовые символы катаканы: 0x8340<=`c`<=0x8396.|
|[_ismbcl0, _ismbcl0_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS (не кандзи): 0x8140<=`c`<=0x889E.|
|[_ismbcl1, _ismbcl1_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS (уровень 1): 0x889F<=`c`<=0x9872.|
|[_ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS (уровень 2): 0x989F<=`c`<=0xEA9E.|

Функции `_ismbcl0`, `_ismbcl1` и `_ismbcl2` проверяют соответствие указанного значения `c` приведенным на предыдущей вкладке условиям теста, но не проверяют, является ли `c` допустимым многобайтовым символом. Если младший байт находится в диапазонах 0x00–0x3F, 0x7F или 0xFD–0xFF, эти функции возвращают ненулевое значение, указывающее, что символ удовлетворяет условию теста. Чтобы проверить, является ли символ многобайтовым, используйте функции [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md).

**КОНЕЦ раздела для кодовой страницы 932**

## <a name="see-also"></a>См. также раздел

[Классификация символов](../c-runtime-library/character-classification.md)<br/>
[является, подпрограммы isw](../c-runtime-library/is-isw-routines.md)<br/>
[подпрограммы _ismbb](../c-runtime-library/ismbb-routines.md)
