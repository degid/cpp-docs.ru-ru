---
title: Спецификатор override
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 82837ae34ab786e607df54038493b14350574a15
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188484"
---
# <a name="override-specifier"></a>Спецификатор override

Ключевое слово **override** можно использовать для обозначения функций-членов, которые переопределяют виртуальную функцию в базовом классе.

## <a name="syntax"></a>Синтаксис

```
function-declaration override;
```

## <a name="remarks"></a>Примечания

**Переопределение** является контекстно-зависимым и имеет специальное значение только в том случае, если оно используется после объявления функции-члена. в противном случае это не зарезервированное ключевое слово.

## <a name="example"></a>Пример

Для предотвращения случайного наследования в коде используйте функцию **переопределения** . В следующем примере показано, где, без использования **переопределения**, поведение функции члена производного класса может не быть предполагалось. Компилятор не выдает ошибки при использовании этого кода.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

При использовании **переопределения**компилятор создает ошибки вместо автоматического создания новых функций элементов.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

Чтобы указать, что функции не могут быть переопределены и что классы не могут быть унаследованы, используйте ключевое слово [final](../cpp/final-specifier.md) .

## <a name="see-also"></a>См. также раздел

[Описатель final](../cpp/final-specifier.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
