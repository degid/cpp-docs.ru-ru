---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: e279184322c239e7768eb8fd4321ee451b2cb94c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213233"
---
# `selectany`

**Блок, относящийся только к системам Microsoft**

Сообщает компилятору, что объявленный элемент глобальных данных (переменная или объект) является универсальным COMDAT (упакованной функцией).

## <a name="syntax"></a>Синтаксис

> **`__declspec( selectany )`***декларатор*

## <a name="remarks"></a>Примечания

Во время компоновки, если отображается несколько определений COMDAT, компоновщик выбирает один из них и игнорирует остальные. Если выбран параметр компоновщика [`/OPT:REF`](../build/reference/opt-optimizations.md) (оптимизации), то будет удалено исключение COMDAT, чтобы удалить все элементы данных, которые не ссылаются на выходные данные компоновщика.

Конструкторы и назначение с помощью глобальной функции или статических методов в объявлении не создадут ссылку и не предотвратят исключение /OPT:REF. Побочные эффекты такого кода не должны быть зависимыми, если не существует других ссылок на данные.

Для динамически инициализированных глобальных объектов **`selectany`** будет также удален код инициализации нессылающегося объекта.

Обычно элемент глобальных данных можно инициализировать только один раз в проекте EXE или DLL. **`selectany`** может использоваться при инициализации глобальных данных, определенных заголовками, когда один и тот же заголовок отображается в нескольких исходных файлах. **`selectany`** доступен в компиляторах C и C++.

> [!NOTE]
> **`selectany`** может применяться только к фактической инициализации элементов глобальных данных, видимых извне.

## <a name="example"></a>Пример

В этом коде показано, как использовать **`selectany`** атрибут:

```cpp
//Correct - x1 is initialized and externally visible
__declspec(selectany) int x1=1;

//Incorrect - const is by default static in C++, so
//x2 is not visible externally (This is OK in C, since
//const is not by default static in C)
const __declspec(selectany) int x2 =2;

//Correct - x3 is extern const, so externally visible
extern const __declspec(selectany) int x3=3;

//Correct - x4 is extern const, so it is externally visible
extern const int x4;
const __declspec(selectany) int x4=4;

//Incorrect - __declspec(selectany) is applied to the uninitialized
//declaration of x5
extern __declspec(selectany) int x5;

// OK: dynamic initialization of global object
class X {
public:
X(int i){i++;};
int i;
};

__declspec(selectany) X x(1);
```

## <a name="example"></a>Пример

В этом коде показано, как с помощью **`selectany`** атрибута обеспечить сворачивание данных COMDAT при использовании [`/OPT:ICF`](../build/reference/opt-optimizations.md) параметра компоновщика. Обратите внимание, что данные должны быть помечены **`selectany`** и помещены в **`const`** раздел (ReadOnly). Раздел, доступный только для чтения, необходимо указать явно.

```cpp
// selectany2.cpp
// in the following lines, const marks the variables as read only
__declspec(selectany) extern const int ix = 5;
__declspec(selectany) extern const int jx = 5;
int main() {
   int ij;
   ij = ix + jx;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[`__declspec`](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
