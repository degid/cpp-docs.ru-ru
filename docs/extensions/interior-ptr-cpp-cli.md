---
title: interior_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
ms.openlocfilehash: affec6dcd88290b24a92cd9035a131baee38bcf1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214273"
---
# <a name="interior_ptr-ccli"></a>interior_ptr (C++/CLI)

*Внутренний указатель* объявляет указатель на внутреннюю часть ссылочного типа, но не на сам объект. Он может указывать на дескриптор ссылки, тип значения, дескриптор упакованного типа, член управляемого типа или элемент управляемого массива.

## <a name="all-runtimes"></a>Все среды выполнения

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

В следующем примере синтаксиса показан внутренний указатель.

### <a name="syntax"></a>Синтаксис

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>Параметры

*cv_qualifier*<br/>
**`const`** или **`volatile`** квалификаторы.

*type*<br/>
Тип *инициализатора*.

*var*<br/>
Имя переменной **interior_ptr**.

*initializer*<br/>
Член ссылочного типа, элемент управляемого массива или любой другой объект, который можно присвоить собственному указателю.

### <a name="remarks"></a>Примечания

Собственный указатель не может отслеживать элемент, если его расположение изменяется в управляемой куче в результате перемещения экземпляров объекта сборщиком мусора. Чтобы указатель правильно ссылался на экземпляр, среде выполнения необходимо обновить его, соориентировав на вновь расположенный объект.

**interior_ptr** представляет надмножество функциональности собственного указателя.  Таким образом, все, что можно присвоить собственному указателю, можно также присвоить указателю **interior_ptr**.  Внутреннему указателю разрешается выполнять тот же набор операций, что и собственному указателю, включая сравнение и вычисления с указателями.

Внутренний указатель можно объявлять только в стеке.  Его нельзя объявлять в качестве члена класса.

Поскольку внутренние указатели существуют только в стеке, при получении адреса внутреннего указателя создается неуправляемый указатель.

**interior_ptr** имеет неявное преобразование в **`bool`** , которое позволяет использовать его в условных инструкциях.

Дополнительные сведения об объявлении внутреннего указателя, указывающего на объект, который нельзя перемещать в куче со сбором мусора, см. в разделе [pin_ptr](pin-ptr-cpp-cli.md).

**interior_ptr** находится в пространстве имен CLI.  Дополнительные сведения см. в статье [Platform, default, and cli Namespaces (C++/CLI and C++/CX)](platform-default-and-cli-namespaces-cpp-component-extensions.md) (Пространства имен Platform, default и cli (C++/CLI и C++/CX)).

Дополнительные сведения о внутренних указателях см. в следующих разделах:

- [Практическое руководство. Объявление и использование внутренних указателей и управляемых массивов (C++/CLI)](how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)](how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [Практическое руководство. Перегрузка функций с внутренними и собственными указателями (C++/CLI)](how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [Практическое руководство. Объявление внутренних указателей с использованием ключевого слова const (C++/CLI)](how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере показаны объявление и использование внутреннего указателя на ссылочный тип.

```cpp
// interior_ptr.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   int data;
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   h_MyClass->data = 1;
   Console::WriteLine(h_MyClass->data);

   interior_ptr<int> p = &(h_MyClass->data);
   *p = 2;
   Console::WriteLine(h_MyClass->data);

   // alternatively
   interior_ptr<MyClass ^> p2 = &h_MyClass;
   (*p2)->data = 3;
   Console::WriteLine((*p2)->data);
}
```

```Output
1
2
3
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
