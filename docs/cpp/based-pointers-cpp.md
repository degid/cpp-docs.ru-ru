---
title: Основанные указатели (C++)
ms.date: 10/09/2018
f1_keywords:
- __based
- _based
- __based_cpp
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
ms.openlocfilehash: a76fe56e0e6bd0501bbc3e23e138cb2e75055c73
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229146"
---
# <a name="based-pointers-c"></a>Основанные указатели (C++)

**`__based`** Ключевое слово позволяет объявлять указатели на основе указателей (указателей, которые смещены от существующих указателей). **`__based`** Ключевое слово относится только к Microsoft.

## <a name="syntax"></a>Синтаксис

```
type __based( base ) declarator
```

## <a name="remarks"></a>Примечания

Указатели, основанные на адресах указателей, являются единственной формой **`__based`** ключевого слова, допустимого в 32-разрядных или 64-разрядных компиляциях. В 32-разрядном компиляторе Microsoft C/C++ относительный указатель имеет 32-разрядное смещение от 32-разрядной базы указателя. То же ограничение действует и для 64-разрядных сред, где относительный указатель имеет 64-разрядное смещение от 64-разрядной базы указателя.

Указатели на основе указателей, в частности, используются для постоянных идентификаторов, которые содержат указатели. Связанный список, состоящий из указателей на основе указателей, можно сохранить на диск, а затем перезагрузить в другое место в памяти. При этом все указатели останутся действительными. Например:

```cpp
// based_pointers1.cpp
// compile with: /c
void *vpBuffer;
struct llist_t {
   void __based( vpBuffer ) *vpData;
   struct llist_t __based( vpBuffer ) *llNext;
};
```

Указателю `vpBuffer` назначается адрес в памяти, который выделяется на более позднем этапе программы. Связанный список перемещается относительно значения `vpBuffer`.

> [!NOTE]
> Сохранение идентификаторов, содержащих указатели, также можно выполнить с помощью [отображенных в память файлов](/windows/win32/Memory/file-mapping).

Когда выполняется разыменовывание относительных указателей, база должна быть либо явно указана, либо неявно известна из объявления.

Для совместимости с предыдущими версиями **_based** является синонимом, **`__based`** если только параметр компилятора [/Za не \( отключил расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указан.

## <a name="example"></a>Пример

В следующем примере демонстрируется изменение относительного указателя путем изменения его базы.

```cpp
// based_pointers2.cpp
// compile with: /EHsc
#include <iostream>

int a1[] = { 1,2,3 };
int a2[] = { 10,11,12 };
int *pBased;

typedef int __based(pBased) * pBasedPtr;

using namespace std;
int main() {
   pBased = &a1[0];
   pBasedPtr pb = 0;

   cout << *pb << endl;
   cout << *(pb+1) << endl;

   pBased = &a2[0];

   cout << *pb << endl;
   cout << *(pb+1) << endl;
}
```

```Output
1
2
10
11
```

## <a name="see-also"></a>См. также статью

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[alloc_text](../preprocessor/alloc-text.md)
