---
title: Ошибка компилятора C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 5c11133fbf28cfb98de1367955c00c899e8b1042
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214533"
---
# <a name="compiler-error-c3646"></a>Ошибка компилятора C3646

> "спецификатор": Неизвестный спецификатор переопределения

## <a name="remarks"></a>Примечания

Компилятор обнаружил маркер в том месте, где ожидалось найти спецификатор переопределения, но маркер не был распознан компилятором.

Например, если нераспознанный *спецификатор* **_NOEXCEPT**, замените его ключевым словом **`noexcept`** .

Дополнительные сведения см. в разделе [Описатели переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3646 и демонстрирует способ исправления:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
