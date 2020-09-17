---
title: Ошибка компилятора C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: cc3c124f1a4daea0f2517a93c6b354b8233aa5e5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205989"
---
# <a name="compiler-error-c2393"></a>Ошибка компилятора C2393

> "*символ*": символ для каждого домена приложения не может быть выделен в сегменте "*сегмент*"

## <a name="remarks"></a>Примечания

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Использование переменных [AppDomain](../../cpp/appdomain.md) предполагает, что компиляция выполняется с **параметрами/clr: pure** или **/clr: Сейф**, а безопасный или чистый образ не может содержать сегменты данных.

Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2393. Чтобы устранить эту проблему, не создавайте сегмент данных.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```
