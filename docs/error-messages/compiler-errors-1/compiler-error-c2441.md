---
title: Ошибка компилятора C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: aa55392e9f58caa4292cf5f96ef97f65a53bf913
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207957"
---
# <a name="compiler-error-c2441"></a>Ошибка компилятора C2441

> "*переменная*": символ, объявленный с __declspec (Process), должен быть константой в режиме/clr: pure

## <a name="remarks"></a>Примечания

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

По умолчанию переменные задаются для каждого домена приложения в **параметре/CLR: pure**. Переменная, помеченная как `__declspec(process)` **/clr: pure** , подвержена ошибкам, если она изменена в одном домене приложения и считывается в другом.

Таким образом, компилятор принудительно применяет переменные для каждого процесса в режиме **`const`** **/clr: pure**, делая их только для чтения во всех доменах приложений.

Дополнительные сведения см. в разделе [Process](../../cpp/process.md) и [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2441.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
