---
title: Предупреждение компилятора (уровень 1) C4691
ms.date: 11/04/2016
f1_keywords:
- C4691
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
ms.openlocfilehash: 6a4d1de621983794acfae4de7707ba127df9a1b7
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685571"
---
# <a name="compiler-warning-level-1-c4691"></a>Предупреждение компилятора (уровень 1) C4691

"тип": в сборке "файл", на которую нет ссылки, ожидался тип, вместо этого используется тип, определенный в текущей записи преобразования

Файл метаданных, содержащий определение исходного типа, не упоминается, и компилятор использует определение локального типа.

В случае перестроения *файла*C4691 можно пропускать или отключать с помощью pragma [warning](../../preprocessor/warning.md).  То есть, если создаваемый файл совпадает с файлом, в котором компилятору требуется найти определение типа, можно пропустить C4691.

Однако непредвиденное поведение может произойти, если компилятор использует определение, не связанное с той же сборкой, на которую имеются ссылки в метаданных. Типы CLR вводятся не только именем типа, но и сборкой.  Это значит, что тип Z от z.dll сборки отличается от типа Z от сборки y.dll.

## <a name="examples"></a>Примеры

Этот образец содержит определение исходного типа.

```cpp
// C4691_a.cpp
// compile with: /clr /LD /W1
public ref class Original_Type {};
```

Этот образец ссылается на C4691_a.dll и объявляет поле типа Original_Type.

```cpp
// C4691_b.cpp
// compile with: /clr /LD
#using "C4691_a.dll"
public ref class Client {
public:
   Original_Type^ ot;
};
```

Следующий пример приводит к возникновению ошибки C4691.  Обратите внимание, что этот пример содержит определение для Original_Type и не ссылается на C4691a.dll.

Чтобы устранить эту проблему, соберите ссылку на файл метаданных, содержащий определение исходного типа, и удалите локальное объявление и определение.

```cpp
// C4691_c.cpp
// compile with: /clr /LD /W1
// C4691 expected

// Uncomment the following line to resolve.
// #using "C4691_a.dll"
#using "C4691_b.dll"

// Delete the following line to resolve.
ref class Original_Type;

public ref class MyClass : Client {};
```
