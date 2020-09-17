---
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: 3b9df2ee2abcaca1c7c11c08ef73ae795a84310d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232252"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Синтаксис

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Примечания

Когда список членов класса предшествует, **`private`** ключевое слово указывает, что эти элементы доступны только в функциях-членах и друзьях класса. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.

При предшествующем имени базового класса **`private`** ключевое слово указывает, что открытые и защищенные члены базового класса являются закрытыми членами производного класса.

Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.

Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.

Дополнительные сведения см. в разделе [дружественная](../cpp/friend-cpp.md), [открытая](../cpp/public-cpp.md), [защищенная](../cpp/protected-cpp.md)и таблица доступа к членам в разделе [Управление доступом к членам класса](member-access-control-cpp.md).

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова спецификатора доступа C++ ( **`public`** , **`private`** и **`protected`** ) могут влиять на видимость типов и методов относительно сборок. Дополнительные сведения см. в разделе [Управление доступом к членам](member-access-control-cpp.md).

> [!NOTE]
> Это поведение не влияет на файлы, скомпилированные с параметром [/LN](../build/reference/ln-create-msil-module.md) . В этом случае все управляемые классы (открытые или закрытые) будут видны.

## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr

## <a name="example"></a>Пример

```cpp
// keyword_private.cpp
class BaseClass {
public:
   // privMem accessible from member function
   int pubFunc() { return privMem; }
private:
   void privMem;
};

class DerivedClass : public BaseClass {
public:
   void usePrivate( int i )
      { privMem = i; }   // C2248: privMem not accessible
                         // from derived class
};

class DerivedClass2 : private BaseClass {
public:
   // pubFunc() accessible from derived class
   int usePublic() { return pubFunc(); }
};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   DerivedClass2 aDerived2;
   aBase.privMem = 1;     // C2248: privMem not accessible
   aDerived.privMem = 1;  // C2248: privMem not accessible
                          //    in derived class
   aDerived2.pubFunc();   // C2247: pubFunc() is private in
                          //    derived class
}
```

## <a name="see-also"></a>См. также раздел

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
