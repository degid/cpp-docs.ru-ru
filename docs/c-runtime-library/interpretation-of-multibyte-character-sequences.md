---
title: "Интерпретация последовательностей в многобайтовой кодировке | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.character.multibyte
dev_langs: C++
helpviewer_keywords: MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca454b0087bd9cc1b8ded6f7b2d4ccb201373dc4
ms.sourcegitcommit: 2a5d0e9e6829150cbc22c6de3395ec13008e3266
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Интерпретация последовательностей в многобайтной кодировке
Большинство подпрограмм для многобайтовых символов в библиотеке времени выполнения Microsoft распознают последовательности многобайтовых символов, относящиеся к многобайтовой кодовой странице. Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данного поведения, зависимого от языкового стандарта. Версии с суффиксом `_l` идентичны, однако они используют переданный параметр языкового стандарта.  
  
### <a name="locale-dependent-multibyte-routines"></a>Подпрограммы для многобайтовых символов, зависящие от языкового стандарта  
  
|Подпрограмма|Применение|  
|-------------|---------|  
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Проверить и вернуть количество байтов в многобайтовом символе|  
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Для строк многобайтовой кодировки: проверить каждый символ в строке и вернуть длину строки. Для строки расширенных символов: вернуть длину строки.|  
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|  
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|  
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Преобразовать последовательность расширенных символов в соответствующую последовательность многобайтовых символов|  
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|  
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Преобразуют многобайтовый символ в эквивалентный символ UTF-16 или UTF-32|  
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Преобразуют символ UTF-16 или UTF-32 в эквивалентный многобайтовый символ|  
  
## <a name="see-also"></a>См. также  
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)