---
title: Средства извлечения _variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: a1b7c713b5d82ff54250b622f2d4afe17abac468
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185610"
---
# <a name="_variant_t-extractors"></a>Средства извлечения _variant_t

**Блок, относящийся только к системам Microsoft**

Извлечение данных из инкапсулированного `VARIANT` объекта.

## <a name="syntax"></a>Синтаксис

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>Примечания

Извлекает необработанные данные из инкапсулированного объекта `VARIANT` . Если `VARIANT` тип не является правильным, `VariantChangeType` используется для попытки преобразования, а при сбое возникает ошибка:

- **оператор Short ()** Извлекает **`short`** целочисленное значение.

- **оператор Long ()** Извлекает **`long`** целочисленное значение.

- **оператор float ()** Извлекает **`float`** числовое значение.

- **оператор Double ()** Извлекает **`double`** целочисленное значение.

- **оператор CY ()** Извлекает `CY` объект.

- **operator bool ()** Извлекает **`bool`** значение.

- **оператор Decimal ()** Извлекает `DECIMAL` значение.

- **Byte оператора ()** Извлекает `BYTE` значение.

- **оператор _bstr_t ()** Извлекает строку, инкапсулированную в `_bstr_t` объекте.

- **оператор IDispatch \* ()** извлекает указатель disp-интерфейса из инкапсулированного `VARIANT` . `AddRef`метод вызывается для полученного указателя, поэтому его можно вызвать `Release` для освобождения.

- **оператор IUnknown \* ()** ИЗВЛЕКАЕТ указатель интерфейса COM из инкапсулированного объекта `VARIANT` . `AddRef`метод вызывается для полученного указателя, поэтому его можно вызвать `Release` для освобождения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)
