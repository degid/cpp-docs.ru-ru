---
title: Ошибка компилятора C2705
description: Описывает ошибку компилятора Microsoft C/C++ C2705.
ms.date: 08/25/2020
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 40d0f70ee379f5d1347b7443817713a53e097f89
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898753"
---
# <a name="compiler-error-c2705"></a>Ошибка компилятора C2705

> "*Метка*": недопустимый переход в область видимости блока обработчика исключений

## <a name="remarks"></a>Примечания

Выполнение переходит к метке внутри **`try`** / **`catch`** **`__try`** / **`__except`** блока, или **`__try`** / **`__finally`** . Компилятор не разрешает такое поведение. Дополнительные сведения см. в разделе [обработка исключений](../../cpp/exception-handling-in-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2705:

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
