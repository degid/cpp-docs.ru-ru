---
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: a0108cff3d6b98fd929b7888d2ad718e7b6b3a64
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213259"
---
# <a name="restrict"></a>restrict

**Блок, относящийся только к системам Microsoft**

При применении к объявлению или определению функции, возвращающему тип указателя, **`restrict`** сообщает компилятору, что функция возвращает объект, который не имеет *псевдонима*, то есть на него ссылаются любые другие указатели. Это позволяет компилятору выполнять дополнительные оптимизации.

## <a name="syntax"></a>Синтаксис

> **`__declspec(restrict)`***pointer_return_type* *функция*pointer_return_type ();

## <a name="remarks"></a>Примечания

Компилятор распространяет **`__declspec(restrict)`** . Например, `malloc` функция CRT имеет **`__declspec(restrict)`** декорирование, поэтому компилятор предполагает, что указатели, инициализированные в области памяти, `malloc` также не имеют псевдонимов ранее существующих указателей.

Компилятор не проверяет, что возвращаемый указатель не является псевдонимом. Ответственность разработчика в том, чтобы программа не применяет псевдоним, помеченный модификатором **restrict __declspec** .

Аналогичные семантики для переменных см. в разделе [__restrict](../cpp/extension-restrict.md).

Другие аннотации, применяемые к псевдонимам в функции, см. в разделе [__declspec (псевдоним)](../cpp/noalias.md).

Дополнительные сведения о **`restrict`** ключевом слове, которое является частью C++ amp, см. в разделе [restrict (C++ amp)](../cpp/restrict-cpp-amp.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется использование **`__declspec(restrict)`** .

Если **`__declspec(restrict)`** применяется к функции, возвращающей указатель, это указывает компилятору, что память, на которую указывает возвращаемое значение, не имеет псевдонима. В этом примере указатели `mempool` и `memptr` являются глобальными, поэтому компилятор не может гарантировать, что память, на которую они ссылаются, не имеет псевдонимов. Однако они используются в `ma` и вызывающем объекте `init` таким образом, что возвращает память, которая не ссылается программой, поэтому для оптимизатора используется **__decslpec (restrict)** . Это аналогично тому, как заголовки CRT выделяют функции выделения, например с `malloc` помощью, **`__declspec(restrict)`** чтобы указать, что они всегда возвращают память, которая не может быть псевдонимом существующих указателей.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

__declspec(restrict) float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

__declspec(restrict) float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);

    multiply(a, b, c);
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec (псевдоним)](../cpp/noalias.md)
