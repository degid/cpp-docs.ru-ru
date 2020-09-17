---
title: vector&lt;bool&gt;::reference::operator bool
ms.date: 11/04/2016
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
ms.openlocfilehash: bb757fee9d6ec824a99557c409b1c4f02f48db5d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215391"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Обеспечивает неявное преобразование из `vector<bool>::reference` в **`bool`** .

## <a name="syntax"></a>Синтаксис

```cpp
operator bool() const;
```

## <a name="return-value"></a>Возвращаемое значение

Логическое значение элемента объекта [vector \<bool> ](../standard-library/vector-bool-class.md) .

## <a name="remarks"></a>Примечания

Объект `vector<bool>` невозможно изменить при помощи данного оператора.

## <a name="requirements"></a>Требования

**Заголовок:**\<vector>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[\<bool>класс Vector:: Reference](../standard-library/vector-bool-reference-class.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
