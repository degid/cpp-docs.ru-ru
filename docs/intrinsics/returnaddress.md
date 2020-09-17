---
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: 2a830ff1e8a2c9551dec52cf10a3d5cf126bde3b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218062"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Блок, относящийся только к системам Microsoft**

`_ReturnAddress` Встроенная функция предоставляет адрес инструкции в вызывающей функции, которая будет выполняться после возврата управления вызывающему объекту.

Создайте следующую программу и пошаговую отладку в отладчике. При пошаговом выполнении программы обратите внимание на адрес, который возвращается `_ReturnAddress`из. Затем сразу после возврата из функции, в которой `_ReturnAddress` использовался, [откройте окно как: Используйте окно](/visualstudio/debugger/how-to-use-the-disassembly-window) дизассемблирования и обратите внимание, что адрес следующей инструкции, которая должна быть выполнена, соответствует адресу `_ReturnAddress`, возвращенному из.

Такие оптимизации, как встраивание, могут повлиять на обратный адрес. Например, если пример программы, приведенный ниже, компилируется с помощью [/Ob1](../build/reference/ob-inline-function-expansion.md),`inline_func` будет встроен в вызывающую функцию `main`. Таким образом, вызовы `_ReturnAddress` из `inline_func` и `main` будут возвращать одно и то же значение.

Если `_ReturnAddress` используется в программе, скомпилированной с [параметром/CLR](../build/reference/clr-common-language-runtime-compilation.md), функция, `_ReturnAddress` содержащая вызов, будет компилироваться как собственная функция. Если функция, скомпилированная как управляемые вызовы в функцию, `_ReturnAddress`содержащую `_ReturnAddress` , может работать не так, как ожидалось.

## <a name="requirements"></a>Требования

**Заголовочный файл** \<> Intrin.h

## <a name="example"></a>Пример

```cpp
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
