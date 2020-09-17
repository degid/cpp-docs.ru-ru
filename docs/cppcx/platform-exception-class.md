---
title: Класс Platform::Exception
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
ms.openlocfilehash: 4604769d9d1bc5fa848d15459327dc87d82f7016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363772"
---
# <a name="platformexception-class"></a>Класс Platform::Exception

Представляет ошибки, которые происходят во время выполнения приложения. Пользовательские классы исключений не могут быть производными от класса `Platform::Exception`. Если требуется пользовательское исключение, можно использовать класс `Platform::COMException` и указать относящееся к приложению значение HRESULT.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Участники

Класс `Exception` наследуется от класса `Object` и интерфейсов `IException`, `IPrintable`и `IEquatable` .

Класс `Exception` имеет также следующие типы членов.

### <a name="constructors"></a>Конструкторы

|Участник|Описание|
|------------|-----------------|
|[Исключение::Исключение](#ctor)|Инициализирует новый экземпляр класса `Exception`.|

### <a name="methods"></a>Методы

Класс `Exception` наследует методы `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`и `ToString()` из [Platform::Object Class](../cppcx/platform-object-class.md). Класс `Exception` содержит также следующий метод.

|Участник|Описание|
|------------|-----------------|
|[Исключение::СозданиеИсключение](#createexception)|Создает исключение, представляющее указанное значение HRESULT.|

### <a name="properties"></a>Свойства

Класс Exception также содержит следующие свойства.

|Участник|Описание|
|------------|-----------------|
|[Исключение::Результат](#hresult)|Значение HRESULT, соответствующее исключению.|
|[Исключение::Сообщение](#message)|Сообщение, описывающее исключение. Это значение доступно только для чтения, его нельзя изменить после создания `Exception` .|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="exceptioncreateexception-method"></a><a name="createexception"></a>Исключение::СоздатьМетод Исключения

Создает Platform::Exception^ из указанного значения HRESULT.

### <a name="syntax"></a>Синтаксис

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>Параметры

*Hr*<br/>
Значение HRESULT, которое, как правило, получается из вызова метода COM. Если значение 0, что равно S_OK, этот метод бросает [Платформу::InvalidArgumentException,](../cppcx/platform-invalidargumentexception-class.md) потому что успешные методы COM не должны бросать исключения.

*Сообщение*<br/>
Строка с описанием ошибки.

### <a name="return-value"></a>Возвращаемое значение

Исключение, представляющее HRESULT ошибки.

### <a name="remarks"></a>Примечания

Используйте этот метод для создания исключения из значения HRESULT, возвращаемого, например, из вызова интерфейса COM. Можно использовать перегруженный метод, принимающий параметр String^, чтобы предоставить пользовательское сообщение.

Настоятельно рекомендуется использовать CreateException для создания сильно набранного исключения, а не для создания [платформы::COMException,](../cppcx/platform-comexception-class.md) которая просто содержит HRESULT.

## <a name="exceptionexception-constructor"></a><a name="ctor"></a>Исключение::Исключение конструктор

Инициализирует новый экземпляр класса Exception.

### <a name="syntax"></a>Синтаксис

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>Параметры

*Hresult*<br/>
HRESULT ошибки, представляемый этим исключением.

*Сообщение*<br/>
Задаваемое пользователем сообщение (например, текст рекомендаций), связанное с исключением. В общем случае следует выбирать вторую перегрузку, чтобы предоставить максимально подробное описание того, как и почему произошла конкретная ошибка.

## <a name="exceptionhresult-property"></a><a name="hresult"></a>Исключение::HResult Недвижимость

Значение HRESULT, соответствующее исключению.

### <a name="syntax"></a>Синтаксис

```cpp
public:
    property int HResult { int get(); }
```

## <a name="property-value"></a>Значение свойства

Значение HRESULT.

### <a name="remarks"></a>Примечания

Большинство исключений создаются как ошибки модели COM, которые возвращаются в виде значений HRESULT. C++/CX преобразует эти значения в объекты Platform::Exception^, и это свойство сохраняет значение исходного кода ошибки.

## <a name="exceptionmessage-property"></a><a name="message"></a>Исключение::Свойство сообщений

Сообщение с описанием ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
public:property String^ Message;
```

## <a name="property-value"></a>Значение свойства

В исключениях, создаваемых в среде выполнения Windows, это предоставляемое системой описание ошибки.

### <a name="remarks"></a>Примечания

В Windows 8 это свойство читается только потому, что исключения в этой версии Windows Runtime перевозятся через ABI только в качестве HRESULTS. В Windows 8.1 через интерфейс ABI передается более подробная информация об исключениях, и можно задать пользовательское сообщение, к которому другие компоненты могут обращаться программным образом. Для получения дополнительной [информации см.](../cppcx/exceptions-c-cx.md)

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
