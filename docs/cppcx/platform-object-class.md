---
title: Класс Platform::Object
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
ms.openlocfilehash: dded4602eda9653f50d26ef1b4aae86af96a262b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213038"
---
# <a name="platformobject-class"></a>Класс Platform::Object

Предоставляет общее поведение для ссылочных классов и структур ссылок в среда выполнения Windows приложениях. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Object : Object
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Object::Object](#ctor)|Инициализирует новый экземпляр класса Object.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Object::Equals](#equals)|Определяет, равен ли указанный объект текущему объекту.|
|[Object::GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|
|[Object::ReferenceEquals](#referenceequals)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|
|[ToString](#tostring)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|
|[GetType](#gettype)|Получает объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий текущий экземпляр.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Object`

`Object`

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

**Пространство имен:** Platform

## <a name="objectequals-method"></a><a name="equals"></a>Метод Object:: Equals

Определяет, равен ли указанный объект текущему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты равны; в противном случае — **`false`** .

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a>Метод Object:: GetHashCode

Возвращает значение идентификатора `IUnknown`* для этого экземпляра, если это COM-объект, или вычисляемое хэш-значение, если это не COM-объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Числовое значение, которое однозначно идентифицирует этот объект.

### <a name="remarks"></a>Примечания

Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Сравнить хэш-коды можно с помощью [Object:: Equals](#equals). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей `IUnknown` в неуправляемом коде.

## <a name="objectgettype-method"></a><a name="gettype"></a>Метод Object:: GetType

Возвращает объект [Platform:: Type](../cppcx/platform-type-class.md) , описывающий тип объекта во время выполнения.

### <a name="syntax"></a>Синтаксис

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Объект [Platform:: Type](../cppcx/platform-type-class.md) , описывающий тип объекта во время выполнения.

### <a name="remarks"></a>Примечания

Статический [Тип:: GetTypeCode](../cppcx/platform-type-class.md#gettypecode) можно использовать для получения значения [перечисления Platform:: TypeCode](../cppcx/platform-typecode-enumeration.md) , представляющего текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса ссылки помимо [Platform:: String](../cppcx/platform-string-class.md) — Object (1).

Класс [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) используется в интерфейсах API Windows как независимый от языка способ передачи сведений о типах между компонентами Windows и приложениями. Класс T[Platform:: Type](../cppcx/platform-type-class.md) имеет операторы для преобразования между `Type` и `TypeName` .

Используйте оператор [typeid](../extensions/typeid-cpp-component-extensions.md) для возврата `Platform::Type` объекта для имени класса, например при переходе между страницами XAML:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a>Конструктор объекта:: Object

Инициализирует новый экземпляр класса Object.

### <a name="syntax"></a>Синтаксис

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a>Метод Object:: ReferenceEquals

Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.

### <a name="syntax"></a>Синтаксис

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>Параметры

*obj1*<br/>
Первый объект для сравнения.

*obj2*<br/>
Второй объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если два объекта одинаковы; в противном случае — **`false`** .

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a>Метод Object:: ToString (C++/CX)

Возвращает строку, представляющую текущий объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, представляющая текущий объект. Этот метод можно переопределить, чтобы ссылочный класс или структура содержали пользовательскую строку сообщения:

```cpp
public ref class Tree sealed
{
public:
    Tree(){}
    virtual Platform::String^ ToString() override
    {
      return "I’m a Tree";
    };
};
```

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Класс Platform:: Type](platform-type-class.md)<br/>
[Система типов](type-system-c-cx.md)
