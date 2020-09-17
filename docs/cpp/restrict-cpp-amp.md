---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 31db9e8c6f18879e65596593c10a8b3413c5cea9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213272"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Спецификатор ограничения может применяться к объявлениям функций и лямбда-выражений. Он реализует ограничения на код функции и на ее поведение в приложениях, в которых используется среда выполнения C++ AMP.

> [!NOTE]
> Дополнительные сведения о **`restrict`** ключевом слове, которое является частью **`__declspec`** атрибутов класса хранения, см. в разделе [restrict](../cpp/restrict.md).

**`restrict`** Предложение принимает следующие формы:

|Предложение|Описание|
|------------|-----------------|
|`restrict(cpu)`|В функции могут использоваться все возможности языка C++. Вызывать ее могут только другие функции, объявленные с помощью функции restrict(cpu).|
|`restrict(amp)`|В функции может использоваться только то подмножество языка C++, выполнение которого может ускорить C++ AMP.|
|Последовательность функций `restrict(cpu)` и `restrict(amp)`.|Функция должна соблюдать ограничения, устанавливаемые обеими функциями: и `restrict(cpu)`, и `restrict(amp)`. Вызывать ее могут функции, объявленные при помощи `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` или `restrict(amp, cpu)`.<br /><br /> Форма `restrict(A) restrict(B)` может быть записана в виде `restrict(A,B)`.|

## <a name="remarks"></a>Примечания

**`restrict`** Ключевое слово является контекстным. Спецификаторы ограничения `cpu` и `amp` не являются зарезервированными словами. Список спецификаторов не может быть расширен. Функция, у которой нет предложения, совпадает с функцией **`restrict`** , имеющей `restrict(cpu)` предложение.

Для функции с предложением `restrict(amp)` действуют следующие ограничения:

- Функция может вызывать только функции с предложением `restrict(amp)`.

- Функция должна поддерживать подстановку.

- Функция может объявлять только **`int`** переменные, **`unsigned int`** , **`float`** и **`double`** , а также классы и структуры, содержащие только эти типы. **`bool`** параметр также разрешен, но при использовании его в составном типе он должен иметь тип, сопоставленный с 4 байтами.

- Лямбда-функции не могут захватывать по ссылке и не могут захватывать указатели.

- Указатели с одним косвенным обращением и ссылки поддерживаются только как локальные переменные, аргументы функций и типы возвращаемых значений.

- Следующие возможности не допускаются:

  - Рекурсия.

  - Переменные, объявленные с ключевым словом [volatile](../cpp/volatile-cpp.md) .

  - Виртуальные функции.

  - Указатели на функции.

  - Указатели на функции-члены.

  - Указатели в структурах.

  - Указатели на указатели.

  - **`goto`** инструкции.

  - Операторы с метками.

  - **`try`****`catch`** операторы,, или **`throw`** .

  - Глобальные переменные.

  - Статические переменные. Вместо этого используйте [ключевое слово tile_static](../cpp/tile-static-keyword.md) .

  - **`dynamic_cast`** приведения.

  - **`typeid`** Оператор.

  - Объявления asm.

  - Использование vararg.

Описание ограничений функций см. в разделе [ограничения ограничения (amp)](/archive/blogs/nativeconcurrency/restrictamp-restrictions-part-0-of-n-introduction).

## <a name="example"></a>Пример

В следующем примере показано, как использовать `restrict(amp)` предложение.

```cpp
void functionAmp() restrict(amp) {}
void functionNonAmp() {}

void callFunctions() restrict(amp)
{
    // int is allowed.
    int x;
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.
    // long long int y;

    // Calling an amp-restricted function is allowed.
    functionAmp();

    // Calling a non-amp-restricted function is not allowed.
    // functionNonAmp();
}
```

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)
