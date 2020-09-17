---
title: Предупреждение компилятора (уровень 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 601b99eec4625e9b598ece4cbb74d0039ad04bf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161793"
---
# <a name="compiler-warning-level-2-c4412"></a>Предупреждение компилятора (уровень 2) C4412

> "*функция*": сигнатура функции содержит тип "*тип*"; C++ объекты ненадежны для передачи между чистым и смешанным или машинным кодом.

## <a name="remarks"></a>Примечания

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017. Если у вас есть код, который должен быть чистым, рекомендуется перенести его в C#.

Компилятор обнаружил потенциально небезопасную ситуацию, которая может привести к ошибке времени выполнения: вызов выполняется из компилируемого объекта **/clr: pure** в функцию, которая была импортирована с помощью dllimport, а сигнатура функции содержит небезопасный тип. Тип является ненадежным, если он содержит функцию-член или имеет член данных, который является ненадежным типом или косвенным обращением к ненадежному типу.

Это небезопасный из-за различий в соглашениях о вызовах по умолчанию между чистым и машинным кодом (или смешанным машинным и управляемым). При импорте (с помощью `dllimport`) функции в **параметр/clr: pure** компилируемого объекта убедитесь, что объявления каждого типа в сигнатуре идентичны элементам в компилируемого объекта, которые экспортируют функцию (особенно внимательны в отношении различий в соглашениях о неявном вызове).

Виртуальная функция-член особенно подвержена непредвиденным результатам.  Однако даже невиртуальную функцию следует протестировать, чтобы убедиться, что вы получаете правильные результаты. Если вы уверены, что получаете правильные результаты, это предупреждение можно проигнорировать.

По умолчанию C4412 отключен. Дополнительные сведения см. [в разделе предупреждения компилятора, отключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) и [dllexport, dllimport](../../cpp/dllexport-dllimport.md) .

Чтобы устранить это предупреждение, удалите все функции из типа.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4412.

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

## <a name="example"></a>Пример

Следующий пример представляет собой заголовочный файл, объявляющий два типа. Ненадежный тип `Unsafe`, так как он содержит функцию-член.

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

## <a name="example"></a>Пример

Этот пример экспортирует функции с типами, определенными в файле заголовка.

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

## <a name="example"></a>Пример

Соглашение о вызовах по умолчанию в компиляции **/clr: pure** отличается от компиляции в машинном код.  При включении C4412.h `Test` значение по умолчанию `__clrcall`. Если скомпилировать и запустить эту программу (не использовать **/c**), программа выдаст исключение.

Следующий пример приводит к возникновению ошибки C4412.

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```
