---
title: Класс Platform::Type
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: f94e1b37cf198f92d49efc793753892c1b138d69
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846567"
---
# <a name="platformtype-class"></a>Класс Platform::Type

Содержит сведения среды выполнения о типе — в частности, имя строки и код типа. Получается путем вызова [Object:: GetType](../cppcx/platform-object-class.md#gettype) для любого объекта или с помощью оператора [typeid](../extensions/typeid-cpp-component-extensions.md) для имени класса или структуры.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Примечания

`Type`Класс полезен в приложениях, которые должны напрямую обрабатываться с помощью **`if`** **`switch`** оператора или, который выполняет ветвление на основе типа объекта во время выполнения. Код типа, описывающий категорию типа, извлекается с помощью функции-члена [Type:: GetTypeCode](#gettypecode) .

## <a name="public-methods"></a>Открытые методы

| Имя | Описание |
|--|--|
| [Метод Type:: GetTypeCode](#gettypecode) | Возвращает значение [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) для объекта. |
| [Метод Type:: ToString](#tostring) | Возвращает имя типа, как указано в его метаданных. |

## <a name="public-properties"></a>Открытые свойства

| Имя | Описание |
|--|--|
| [Тип:: FullName](#fullname) | Возвращает [Класс Platform::String](../cppcx/platform-string-class.md)^, который представляет полное имя типа и использует . (точка) как разделитель, а не:: (двойное двоеточие), например `MyNamespace.MyClass` . |

## <a name="conversion-operators"></a>Операторы преобразования

| Имя | Описание |
|--|--|
| [Тип оператора ^](../cppcx/operator-type-hat.md) | Обеспечивает преобразование `Windows::UI::Xaml::Interop::TypeName` в `Platform::Type`. |
| [оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md) | Обеспечивает преобразование `Platform::Type` в `Windows::UI::Xaml::Interop::TypeName`. |

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** Platform. winmd

## <a name="typefullname-property"></a><a name="fullname"></a> Свойство Type::FullName

Возвращает полное имя текущего типа в форме `Namespace.Type` .

### <a name="syntax"></a>Синтаксис

```cpp
String^ FullName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа.

### <a name="example"></a>Пример

```cpp
//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="typegettypecode-method"></a><a name="gettypecode"></a> Метод Type::GetTypeCode

Возвращает числовой тип категории встроенных типов.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления Platform::TypeCode.

### <a name="remarks"></a>Примечания

Эквивалентом метода члена GetTypeCode () является **`typeid`** свойство.

## <a name="typetostring-method"></a><a name="tostring"></a> Метод Type:: ToString

Возвращает имя типа.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа, как указано в метаданных.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
