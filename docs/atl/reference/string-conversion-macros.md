---
title: Макросы преобразования строк
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 60cccebf4e1db8369ea5a88f04a37b96838ff49f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835159"
---
# <a name="string-conversion-macros"></a>Макросы преобразования строк

Эти макросы предоставляют функции преобразования строк.

## <a name="atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a> Макросы преобразования строк ATL и MFC

Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строк MFC см. в разделе [TN059. Использование макросов преобразования с помощью MFC MBCS/Unicode](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [макросов и глобальных библиотек MFC](../../mfc/reference/mfc-macros-and-globals.md).

## <a name="devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a> Макросы преобразования строк DEVMODE и ТЕКСТМЕТРИК

Эти макросы создают копию структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) или [текстметрик](/windows/win32/api/wingdi/ns-wingdi-textmetricw) и преобразуют строки в новой структуре в новый строковый тип. Макросы выделяют память в стеке для новой структуры и возвращают указатель на новую структуру.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Примечания

Пример:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

В именах макросов строковый тип в исходной структуре находится слева (например **,),** а тип строки в целевой структуре — справа (например, **W**). **А** означает LPSTR, **OLE** означает ЛПОЛЕСТР, **T** означает LPTSTR, а **W** — для LPWSTR.

Таким образом, DEVMODEA2W копирует `DEVMODE` структуру с строками LPSTR в `DEVMODE` структуру со строками LPWSTR, TEXTMETRICOLE2T копирует `TEXTMETRIC` структуру с лполестр строками в `TEXTMETRIC` структуру с строками LPTSTR и т. д.

Две строки, преобразованные в `DEVMODE` структуру, — это имя устройства ( `dmDeviceName` ) и имя формы ( `dmFormName` ). `DEVMODE`Макросы преобразования строк также обновляют размер структуры ( `dmSize` ).

Четыре строки, преобразованные в `TEXTMETRIC` структуру, являются первым символом ( `tmFirstChar` ), последним символом ( `tmLastChar` ), символом по умолчанию ( `tmDefaultChar` ) и символом разрыва ( `tmBreakChar` ).

Поведение `DEVMODE` `TEXTMETRIC` макросов преобразования строк и зависит от применяемой директивы компилятора (при наличии). Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора меняются **T** и **OLE** следующим образом:

|Действующая директива компилятора|T становится|OLE становится|
|----------------------------------|---------------|-----------------|
|нет|**А**|**W**|
|**\_UNICODE**|**W**|**W**|
|**OLE2ANSI**|**А**|**А**|
|** \_ Юникод** и **OLE2ANSI**|**W**|**А**|

В следующей таблице перечислены `DEVMODE` `TEXTMETRIC` макросы и преобразования строк.

|`DEVMODE` макровирусах|`TEXTMETRIC` макровирусах|
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
