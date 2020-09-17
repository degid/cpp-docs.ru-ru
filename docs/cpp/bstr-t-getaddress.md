---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: ca78bd1b607ba4a86bbc824887a7ec767cd5476e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181256"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Блок, относящийся только к системам Microsoft**

Освобождает любую существующую строку и возвращает адрес новой строки, которой была выделена память.

## <a name="syntax"></a>Синтаксис

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку `BSTR`, инкапсулированную объектом `_bstr_t`.

## <a name="remarks"></a>Примечания

Действие " **Субадрес** " влияет на все объекты `_bstr_t`, которые совместно используют `BSTR`. Несколько `_bstr_t` могут совместно использовать `BSTR` с помощью конструктора копирования и **оператора =** .

## <a name="example"></a>Пример

Пример использования метода- **Address**см. в разделе [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)
