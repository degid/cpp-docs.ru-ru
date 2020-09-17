---
title: Оператор alignof
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 6a2046774674858211ae89abb9b4cfc7b09c0a6d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227638"
---
# <a name="alignof-operator"></a>Оператор alignof

**`alignof`** Оператор возвращает выравнивание в байтах указанного типа в виде значения типа **`size_t`** .

## <a name="syntax"></a>Синтаксис

```cpp
alignof( type )
```

## <a name="remarks"></a>Примечания

Пример:

| Выражение | Значение |
|--|--|
| **`alignof( char )`** | 1 |
| **`alignof( short )`** | 2 |
| **`alignof( int )`** | 4 |
| **`alignof( long long )`** | 8 |
| **`alignof( float )`** | 4 |
| **`alignof( double )`** | 8 |

Значение совпадает со **`alignof`** значением для **`sizeof`** базовых типов. Однако рассмотрим следующий пример.

```cpp
typedef struct { int a; double b; } S;
// alignof(S) == 8
```

В этом случае **`alignof`** значение является требованием выравнивания для самого крупного элемента в структуре.

Аналогичным образов, в

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`alignof(S)` равно `32`.

Одним из них будет использование в **`alignof`** качестве параметра для одной из собственных подпрограмм выделения памяти. Например, в следующей определенной структуре `S` можно вызвать подпрограмму выделения памяти с именем `aligned_malloc` для выделения памяти на определенной границе выравнивания.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), alignof(S));
```

Дополнительные сведения об изменении выравнивания см. в следующих разделах.

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (выравнивание членов структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/x64-software-conventions.md#examples-of-structure-alignment) (только для x64)

Дополнительные сведения о различиях в выравнивании в коде для 32- (x86) и 64-разрядных (x64) сред см. в статье

- [Конфликтует с компилятором x86](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

### <a name="microsoft-specific"></a>Специально для систем Майкрософт

**`alignof`** и **`__alignof`** являются синонимами в компиляторе Майкрософт. До того, как она стала частью стандарта в C++ 11, оператор, предоставляемый корпорацией Майкрософт, **`__alignof`** предоставил эти функциональные возможности. Для максимальной переносимости следует использовать **`alignof`** оператор вместо оператора, относящегося к Microsoft **`__alignof`** .

Для совместимости с предыдущими версиями аргумент **`_alignof`** является синонимом, **`__alignof`** если только параметр компилятора не [ `/Za` \( отключает расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
