---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 8ce0e9ea6a39ef7760c7a6d0802913326433cf68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227274"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Блок, относящийся только к системам Microsoft**

**`__declspec`** Расширенный атрибут, который может использоваться в объявлении функций.

## <a name="syntax"></a>Синтаксис

> __declspec *возвращаемого типа* (throw) [*соглашение о вызовах*] *функция-имя* ([*Argument-List*])

## <a name="remarks"></a>Примечания

Рекомендуется, чтобы в новом коде использовался оператор [except](noexcept-cpp.md) , а не `__declspec(nothrow)` .

Этот атрибут сообщает компилятору, что и объявленная функция, и функции, которые она вызывает, никогда не создают исключений. Однако директива не применяется. Иными словами, он никогда не вызывает [std::terminate](../standard-library/exception-functions.md#terminate) , в отличие от **`noexcept`** , или в режиме **std: C++ 17** (Visual Studio 2017 версии 15,5 и более поздней версии) `throw()` .

Поскольку по умолчанию теперь используется модель синхронной обработки исключений, то компилятор может исключить механизм, позволяющий отслеживать время существования удаляемых объектов в такой функции, и значительно уменьшить объем кода. При наличии следующей директивы препроцессора три приведенные ниже объявления функций эквивалентны в режиме **/std: c++ 14** :

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

В **/std: режим c++ 17** `throw()` не эквивалентен другим, которые используют, `__declspec(nothrow)` так как вызывается `std::terminate` при возникновении исключения из функции.

В `void __stdcall f3() throw();` объявлении используется синтаксис, определенный стандартом C++. В C++ 17 `throw()` ключевое слово является устаревшим.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
