---
title: Изменяемые члены данных (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 9370952f503850fbc296c3df912d4a0fafe163f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227352"
---
# <a name="mutable-data-members-c"></a>Изменяемые члены данных (C++)

Это ключевое слово может применяться только к данным-членам класса, которые не являются статическими или константами. Если объявлен элемент данных **`mutable`** , ему допустимо присвоить значение этому элементу данных из **`const`** функции-члена.

## <a name="syntax"></a>Синтаксис

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Примечания

Например, следующий код будет компилироваться без ошибок, поскольку `m_accessCount` объявлен как **`mutable`** , и поэтому может быть изменен, `GetFlag` даже если `GetFlag` является константной функцией-членом.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>См. также статью

[Ключевые слова](../cpp/keywords-cpp.md)
