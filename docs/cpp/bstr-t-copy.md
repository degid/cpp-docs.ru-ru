---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: b6029e98e83b171d9ab9f8f3f0282fa3f46ca167
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227599"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Блок, относящийся только к системам Microsoft**

Создает копию инкапсулированного объекта `BSTR`.

## <a name="syntax"></a>Синтаксис

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Параметры

*фкопи*<br/>
Если значение **`true`** , **Copy** возвращает копию вложенного объекта `BSTR` , в противном случае **Copy** возвращает фактическую BSTR.

## <a name="remarks"></a>Примечания

Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.

## <a name="example"></a>Пример

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _bstr_t](../cpp/bstr-t-class.md)
