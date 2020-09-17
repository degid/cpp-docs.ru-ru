---
title: Оператор reinterpret_cast
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 33da7427adeb0a0cade2a369664d7fbd34790681
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233604"
---
# <a name="reinterpret_cast-operator"></a>Оператор reinterpret_cast

Позволяет преобразовывать любой указатель в указатель любого другого типа. Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.

## <a name="syntax"></a>Синтаксис

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Примечания

Неправильное использование **`reinterpret_cast`** оператора может быть ненадежным. Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.

**`reinterpret_cast`** Оператор можно использовать для преобразований **`char*`** , например, в **`int*`** , или `One_class*` в `Unrelated_class*` , которые по своей природе являются небезопасными.

Результат **`reinterpret_cast`** нельзя безопасно использовать ни для чего, кроме приведения обратно к исходному типу. Другие применения в лучшем случае будут непереносимыми.

**`reinterpret_cast`** Оператор не может привести к отделам **`const`** **`volatile`** атрибуты, или **`__unaligned`** . Сведения об удалении этих атрибутов см. в разделе [оператор const_cast](../cpp/const-cast-operator.md) .

**`reinterpret_cast`** Оператор преобразует нулевое значение указателя в значение указателя null целевого типа.

Одним из практических **`reinterpret_cast`** способов использования функции является функция хэширования, которая сопоставляет значение с индексом таким образом, чтобы два различных значения редко применялись к одному и тому же индексу.

```cpp
#include <iostream>
using namespace std;

// Returns a hash code based on an address
unsigned short Hash( void *p ) {
   unsigned int val = reinterpret_cast<unsigned int>( p );
   return ( unsigned short )( val ^ (val >> 16));
}

using namespace std;
int main() {
   int a[20];
   for ( int i = 0; i < 20; i++ )
      cout << Hash( a + i ) << endl;
}

Output:
64641
64645
64889
64893
64881
64885
64873
64877
64865
64869
64857
64861
64849
64853
64841
64845
64833
64837
64825
64829
```

**`reinterpret_cast`** Позволяет обрабатывать указатель как целочисленный тип. Затем для получения уникального индекса (уникального с высокой степенью вероятности) к результату применяется побитовый сдвиг и операция XOR с самим собой. Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.

## <a name="see-also"></a>См. также статью

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
