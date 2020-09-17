---
title: Ошибка средств компоновщика LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 69af2bd2c22fdb1188cf0b7119791e451e80f966
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686500"
---
# <a name="linker-tools-error-lnk1312"></a>Ошибка средств компоновщика LNK1312

Недопустимый или поврежденный файл: не удалось импортировать сборку

При построении сборки файл, отличный от модуля или сборки, скомпилированного с **параметром/CLR** , был передан параметру компоновщика **/ASSEMBLYMODULE** .  Если объектный файл был передан в **/ASSEMBLYMODULE**, просто передайте объект непосредственно в компоновщик, а не в **/ASSEMBLYMODULE**.

## <a name="examples"></a>Примеры

В следующем примере создается OBJ-файл.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

Следующий пример приводит к возникновению ошибки LNK1312.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
