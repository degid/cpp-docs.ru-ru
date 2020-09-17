---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2194e0e54a93d3227b84d893f9d3f208d972d09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180515"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Блок, относящийся только к системам Microsoft**

Сопоставляет 16-разрядное *wCode* с 32-БИТНЫМ значением HRESULT.

## <a name="syntax"></a>Синтаксис

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Параметры

*wCode*<br/>
16-разрядный *wCode* сопоставляется с 32-БИТНЫМ значением HRESULT.

## <a name="return-value"></a>Возвращаемое значение

32-разрядный HRESULT, сопоставленный из 16-разрядного *wCode*.

## <a name="remarks"></a>Примечания

См. функцию члена [wCode](../cpp/com-error-wcode.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[Класс _com_error](../cpp/com-error-class.md)
