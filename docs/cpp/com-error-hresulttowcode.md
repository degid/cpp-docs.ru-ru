---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 35a497c273f15c9755d3607e7907a3a48dad8dc8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180567"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Блок, относящийся только к системам Microsoft**

Сопоставляет 32-разрядное значение HRESULT с 16-разрядным `wCode`.

## <a name="syntax"></a>Синтаксис

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Параметры

*кадров*<br/>
32-разрядное значение HRESULT для сопоставления с 16-разрядным `wCode`.

## <a name="return-value"></a>Возвращаемое значение

16-разрядный `wCode` сопоставляется с 32-битным значением HRESULT.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [_com_error:: wCode](../cpp/com-error-wcode.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[Класс _com_error](../cpp/com-error-class.md)
