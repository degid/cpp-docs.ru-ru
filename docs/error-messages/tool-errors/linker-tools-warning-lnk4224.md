---
title: Предупреждение средств компоновщика LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 9e52dd533d897e729aba5f2b43ea6c019a024d43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182985"
---
# <a name="linker-tools-warning-lnk4224"></a>Предупреждение средств компоновщика LNK4224

> *параметр* больше не поддерживается; игнорируют

## <a name="remarks"></a>Примечания

Указан недопустимый устаревший параметр компоновщика, который не учитывается.

Например, LNK4224 может возникать, если в OBJ-файле присутствует директива/Comment. Директива/Comment была бы добавлена с помощью директивы pragma [comment (C++C/)](../../preprocessor/comment-c-cpp.md) с использованием нерекомендуемого параметра exestr. Используйте DUMPBIN [/ALL](../../build/reference/all.md) для просмотра директив компоновщика в OBJ-файле.

По возможности измените источник для obj и удалите директиву pragma. Если пропустить это предупреждение, возможно, исполняемый файл, скомпилированный с **параметром/clr: pure** , не будет выполняться должным образом. Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4224.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```
