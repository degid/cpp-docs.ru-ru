---
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: d705029c30fdbc117c4c6e96923691e43e072e23
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221071"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Блок, относящийся только к системам Microsoft**

Предоставляет адрес расположения в памяти, в котором содержится обратный адрес текущей функции. Этот адрес не может использоваться для доступа к другим расположениям в памяти (например, аргументы функции).

## <a name="syntax"></a>Синтаксис

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64, ARM, ARM64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Если `_AddressOfReturnAddress` используется в программе, скомпилированной с [параметром/CLR](../build/reference/clr-common-language-runtime-compilation.md), `_AddressOfReturnAddress` то функция, содержащая вызов, компилируется как собственная функция. Если функция, скомпилированная как управляемые вызовы в функцию, `_AddressOfReturnAddress`содержащую `_AddressOfReturnAddress` , может работать не так, как ожидалось.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
