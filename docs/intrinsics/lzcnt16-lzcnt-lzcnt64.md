---
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 09/02/2019
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: fcd801717974a230fbd19cc7802d8f6a011774f7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221799"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Блок, относящийся только к системам Microsoft**

Подсчитывает количество начальных нулей в 16-, 32-или 64-разрядном числе.

## <a name="syntax"></a>Синтаксис

```C
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Параметры

*value*\
окне 16-, 32-или 64-разрядное целое число без знака для поиска начальных нулей.

## <a name="return-value"></a>Возвращаемое значение

Число начальных нулей в `value` параметре. Если `value` равен нулю, возвращаемое значение является размером входного операнда (16, 32 или 64). Если наиболее значащий бит `value` является одним, возвращаемое значение равно нулю.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__lzcnt16`|ПРОЦЕССОРА Расширенная обработка битов (АБМ)<br /><br /> Сервер Haswell|
|`__lzcnt`|ПРОЦЕССОРА Расширенная обработка битов (АБМ)<br /><br /> Сервер Haswell|
|`__lzcnt64`|ПРОЦЕССОРА Расширенная обработка битов (АБМ) в 64-разрядном режиме.<br /><br /> Сервер Haswell|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Каждая из встроенных функций формирует `lzcnt` инструкцию.  Размер значения, `lzcnt` возвращаемого инструкцией, совпадает с размером аргумента.  В 32-разрядном режиме нет 64-битных регистров общего назначения, поэтому 64-bit `lzcnt` не поддерживается.

Чтобы определить аппаратную поддержку для `lzcnt` инструкции, `__cpuid` вызовите встроенную `InfoType=0x80000001` функцию с и проверьте бит `CPUInfo[2] (ECX)`5 из. Этот бит будет равен 1, если инструкция поддерживается, и 0 в противном случае. Если запустить код, использующий встроенное на оборудовании, которое `lzcnt` не поддерживает эту инструкцию, результаты будут непредсказуемыми.

На процессорах Intel, которые не `lzcnt` поддерживают эту инструкцию, байтовая кодировка `bsr` инструкции выполняется как (обратная проверка битового файла). Если переносимость кода является проблемой, рекомендуется использовать `_BitScanReverse` встроенную вместо нее. Дополнительные сведения см. в разделе [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Пример

```cpp
// Compile this test with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**Завершение блока, относящегося только к системам Майкрософт**

Фрагменты этого содержимого имеют авторские права на 2007 по опыту Micro Devices, Inc. Все права защищены. Воспроизводить с разрешением от расширенных микроустройств, Inc.

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
