---
title: Операторы отношения _variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: 6e0296a2bf4ce97e41fdf6208c3dd1c6b91215dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226948"
---
# <a name="_variant_t-relational-operators"></a>Операторы отношения _variant_t

**Блок, относящийся только к системам Microsoft**

Сравнивает два объекта `_variant_t` и определяет, равны ли они.

## <a name="syntax"></a>Синтаксис

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект, `VARIANT` сравниваемый с `_variant_t` объектом.

*pSrc*<br/>
Указатель на `VARIANT` объект, сравниваемый с `_variant_t` объектом.

## <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** , если сравнение содержит, **`false`** Если нет.

## <a name="remarks"></a>Примечания

Сравнивает `_variant_t` объект с объектом `VARIANT` , проверяя на равенство или неравенство.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)
