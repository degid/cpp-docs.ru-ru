---
title: typeid (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
ms.openlocfilehash: 56319fb773b8398f85f5fd82c812f0efdb7dde15
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225115"
---
# <a name="typeid--ccli-and-ccx"></a>typeid (C++/CLI и C++/CX)

Получает значение, указывающее nbg объекта.

> [!NOTE]
> Этот раздел относится к версии typeid расширений компонентов C++. Описание версии ISO C++ этого ключевого слова см. в статье [typeid Operator](../cpp/typeid-operator.md) (Оператор typeid).

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="syntax"></a>Синтаксис

```cpp
T::typeid
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа.

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="syntax"></a>Синтаксис

```cpp
Platform::Type^ type = T::typeid;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа.

### <a name="remarks"></a>Примечания

В C++/CX typeid возвращает значение [Platform::Type](../cppcx/platform-type-class.md), создаваемое из данных типа во время выполнения.

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="syntax"></a>Синтаксис

```
type::typeid
```

### <a name="parameters"></a>Параметры

*type*<br/>
Имя типа (абстрактный декларатор), для которого требуется объект `System::Type`.

### <a name="remarks"></a>Примечания

**`typeid`** используется для получения <xref:System.Type> для типа во время компиляции.

**`typeid`** аналогичен получению `System::Type` для типа во время выполнения с помощью <xref:System.Type.GetType%2A> или <xref:System.Object.GetType%2A> . Однако в **`typeid`** качестве параметра принимается только имя типа.  Если вы хотите использовать экземпляр типа для получения его `System::Type` имени, используйте `GetType` .

**`typeid`** должен иметь возможность оценивать имя типа (тип) во время компиляции, в то время как GetType вычисляет тип, возвращаемый во время выполнения.

**`typeid`** может принимать собственное имя типа или псевдоним среды CLR для имени собственного типа; Дополнительные сведения см. [в разделе .NET Framework эквиваленты для собственных типов c++ (c++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) .

**`typeid`** также работает с собственными типами, хотя он по-прежнему будет возвращать `System::Type` .  Чтобы получить структуру type_info, используйте [ `typeid` оператор](../cpp/typeid-operator.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере сравнивается ключевое слово typeid с элементом `GetType()`.

```cpp
// keyword__typeid.cpp
// compile with: /clr
using namespace System;

ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   Type ^ pType = pG->GetType();
   Type ^ pType2 = G::typeid;

   if (pType == pType2)
      Console::WriteLine("typeid and GetType returned the same System::Type");
   Console::WriteLine(G::typeid);

   typedef float* FloatPtr;
   Console::WriteLine(FloatPtr::typeid);
}
```

```Output
typeid and GetType returned the same System::Type
G

System.Single*
```

Следующий пример демонстрирует использование переменной типа System::Type для получения атрибутов типа.  Он также показывает, что для некоторых типов потребуется создать определение типа для использования **`typeid`** .

```cpp
// keyword__typeid_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

typedef int ^ handle_to_int;
typedef int * pointer_to_int;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref class AtClass {
public:
   AtClass(Type ^) {
      Console::WriteLine("in AtClass Type ^ constructor");
   }
};

[attribute(AttributeTargets::All)]
ref class AtClass2 {
public:
   AtClass2() {
      Console::WriteLine("in AtClass2 constructor");
   }
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
ref class B : Attribute {};

int main() {
   Type ^ MyType = B::typeid;

   Console::WriteLine(MyType->IsClass);

   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);
   for (int i = 0 ; i < MyArray->Length ; i++ )
      Console::WriteLine(MyArray[i]);

   if (int::typeid != pointer_to_int::typeid)
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");

   if (int::typeid == handle_to_int::typeid)
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");
}
```

```Output
True

in AtClass2 constructor

in AtClass Type ^ constructor

AtClass2

System.AttributeUsageAttribute

AtClass

int::typeid != pointer_to_int::typeid, as expected

int::typeid == handle_to_int::typeid, as expected
```

## <a name="see-also"></a>См. также статью

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
