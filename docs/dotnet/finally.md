---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: b3331c17fc2313cbd6146db3beb015cd8d8c1eeb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221462"
---
# <a name="finally"></a>finally

Помимо **`try`** **`catch`** предложений и, обработка исключений CLR поддерживает **`finally`** предложение. Семантика идентична **`__finally`** блоку в структурированной обработке исключений (SEH). **`__finally`** Блок может следовать за **`try`** **`catch`** блоком или.

## <a name="remarks"></a>Примечания

Целью этого **`finally`** блока является очистка всех ресурсов, оставшихся после возникновения исключения. Обратите внимание, что **`finally`** блок всегда выполняется, даже если исключение не было создано. **`catch`** Блок выполняется только в том случае, если управляемое исключение создается в связанном **`try`** блоке.

`finally`контекстно-зависимое ключевое слово; Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../extensions/context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="example"></a>Пример

В следующем примере показан простой **`finally`** блок:

```cpp
// keyword__finally.cpp
// compile with: /clr
using namespace System;

ref class MyException: public System::Exception{};

void ThrowMyException() {
   throw gcnew MyException;
}

int main() {
   try {
      ThrowMyException();
   }
   catch ( MyException^ e ) {
      Console::WriteLine(  "in catch" );
      Console::WriteLine( e->GetType() );
   }
   finally {
      Console::WriteLine(  "in finally" );
   }
}
```

```Output
in catch
MyException
in finally
```

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
