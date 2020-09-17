---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: da438c65256d9a7e5bf5b02e108fee1385171d2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181217"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Блок, относящийся только к системам Microsoft**

Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Возвращаемое значение

Начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.

## <a name="remarks"></a>Примечания

Значение **BSTR** влияет на все объекты `_bstr_t`, которые совместно используют `BSTR`. Несколько `_bstr_t` могут совместно использовать `BSTR` с помощью конструктора копирования и **оператора =** .

## <a name="example"></a>Пример

См. раздел [_bstr_t:: Assign](../cpp/bstr-t-assign.md) в качестве примера с помощью функции **BSTR**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)
