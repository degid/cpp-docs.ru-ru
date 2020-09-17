---
title: Module - класс
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
ms.openlocfilehash: f7930247c979c111a7f4798e35ebe7aa95209f37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225752"
---
# <a name="module-class"></a>Module - класс

Представляет коллекцию связанных объектов.

## <a name="syntax"></a>Синтаксис

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Параметры

*moduleType*<br/>
Сочетание одного или нескольких значений перечисления [ModuleType](moduletype-enumeration.md) .

## <a name="members"></a>Элементы

### <a name="protected-classes"></a>Защищенные классы

Имя                                                                                | Описание:
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Модуль:: GenericReleaseNotifier](module-genericreleasenotifier-class.md) | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.
[Модуль:: MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его указателем на член метода.
[Модуль:: ReleaseNotifier](module-releasenotifier-class.md)               | Вызывает обработчик событий при освобождении последнего объекта в модуле.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                             | Описание:
-------------------------------- | -----------------------------------------------------------
[Модуль:: ~ module](#tilde-module) | Выполняет деинициализацию текущего экземпляра `Module` класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                      | Описание:
------------------------- | ---------------------------------------------------
[Модуль:: module](#module) | Инициализирует новый экземпляр класса `Module`.

### <a name="public-methods"></a>Открытые методы

name                                                    | Описание:
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Модуль:: Create](#create)                               | Создает экземпляр модуля.
[Модуль::D Екрементобжекткаунт](#decrementobjectcount)   | Уменьшает количество объектов, отслеживаний модулем.
[Модуль:: GetActivationFactory](#getactivationfactory)   | Получает фабрику активации для модуля.
[Модуль:: Жетклассобжект](#getclassobject)               | Извлекает кэш фабрик класса.
[Модуль:: module](#getmodule)                         | Создает экземпляр модуля.
[Модуль:: Жетобжекткаунт](#getobjectcount)               | Извлекает количество объектов, управляемых этим модулем.
[Модуль:: IncrementObjectCount](#incrementobjectcount)   | Увеличивает число объектов, обрабатываемых модулем.
[Модуль:: Регистеркомобжект](#registercomobject)         | Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.
[Модуль:: Регистеробжектс](#registerobjects)             | Регистрирует объекты COM или среда выполнения Windows, чтобы другие приложения могли подключаться к ним.
[Модуль:: Регистервинртобжект](#registerwinrtobject)     | Регистрирует один или несколько объектов среда выполнения Windows, чтобы другие приложения могли подключаться к ним.
[Модуль:: Terminate](#terminate)                         | Приводит к завершению работы всех экземпляров фабрик, созданных модулем.
[Модуль:: UnregisterCOMObject](#unregistercomobject)     | Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.
[Модуль:: Унрегистеробжектс](#unregisterobjects)         | Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.
[Модуль:: Унрегистервинртобжект](#unregisterwinrtobject) | Отменяет регистрацию одного или нескольких объектов среда выполнения Windows, чтобы другие приложения не могли подключаться к ним.

### <a name="protected-methods"></a>Защищенные методы

Имя                      | Описание:
------------------------- | --------------------------------
[Модуль:: Create](#create) | Создает экземпляр модуля.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                         | Описание:
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Модуль:: objectCount_](#objectcount)         | Отслеживает количество классов, созданных с помощью функции [make](make-function.md) .
[Модуль:: releaseNotifier_](#releasenotifier) | Содержит указатель на `ReleaseNotifier` объект.

### <a name="macros"></a>Макросы

Имя                                                                   | Описание:
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос задает параметры фабрики и идентификатора группы по умолчанию.
[ActivatableClassWithFactory](activatableclass-macros.md)   | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос позволяет указать конкретный параметр фабрики.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос позволяет указать определенные параметры фабрики и идентификатора группы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>Модуль:: ~ module

Выполняет деинициализацию текущего экземпляра `Module` класса.

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>Модуль:: Create

Создает экземпляр модуля.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип модуля.

*обратный вызов*<br/>
Вызывается при освобождении объекта последнего экземпляра модуля.

*object*<br/>
Параметры *объекта* и *метода* используются в сочетании. Указывает на последний объект экземпляра, когда освобождается последний объект экземпляра в модуле.

*Method*<br/>
Параметры *объекта* и *метода* используются в сочетании. Указывает на метод объекта последнего экземпляра, когда освобождается последний объект экземпляра в модуле.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>Модуль::D Екрементобжекткаунт

Уменьшает количество объектов, отслеживаний модулем.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число до операции декремента.

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>Модуль:: GetActivationFactory

Получает фабрику активации для модуля.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*пактиватиблеклассид*<br/>
Представляет IID класса среды выполнения.

*ппифактори*<br/>
Представляет интерфейс IActivationFactory указанного класса среды выполнения.

*Имя*<br/>
Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в макросе [активатаблеклассвисфакторекс](activatableclass-macros.md) , или укажите, **`nullptr`** чтобы получить имя сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>Модуль:: Жетклассобжект

Извлекает кэш фабрик классов.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*этому*<br/>
Идентификатор класса.

*riid*<br/>
Запрошенный идентификатор интерфейса.

*ппв*<br/>
Указатель на возвращаемый объект.

*Имя*<br/>
Имя сервера, указанное в `ActivatableClassWithFactory` `ActivatableClassWithFactoryEx` макросе, или, `ActivatableClass` или **`nullptr`** для получения имени сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Этот метод следует использовать только для COM, а не для среда выполнения Windows. Этот метод предоставляет только `IClassFactory` методы.

## <a name="modulegetmodule"></a><a name="getmodule"></a>Модуль:: module

Создает экземпляр модуля.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>Модуль:: Жетобжекткаунт

Извлекает количество объектов, управляемых этим модулем.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество объектов, управляемых этим модулем.

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>Модуль:: IncrementObjectCount

Увеличивает число объектов, обрабатываемых модулем.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число до операции приращения.

## <a name="modulemodule"></a><a name="module"></a>Модуль:: module

Инициализирует новый экземпляр класса `Module`.

```cpp
Module();
```

### <a name="remarks"></a>Примечания

Этот конструктор защищен и не может быть вызван с помощью **`new`** ключевого слова. Вместо этого вызовите либо [Module:: имя_модуля](#getmodule) , либо [модуль:: Create](#create).

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>Модуль:: objectCount_

Отслеживает количество классов, созданных с помощью функции [make](make-function.md) .

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>Модуль:: Регистеркомобжект

Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>Параметры

*Имя*<br/>
Полное имя сервера.

*CLSID*<br/>
Массив регистрируемых идентификаторов CLSID.

*factories*<br/>
Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.

*сеанс*<br/>
После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.

*count*<br/>
Количество идентификаторов CLSID, которые необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

### <a name="remarks"></a>Примечания

COM-объекты зарегистрированы с помощью перечислителя CLSCTX_LOCAL_SERVER перечисления CLSCTX.

Тип соединения с зарегистрированными объектами задается сочетанием текущего параметра шаблона *комфлаг* и перечислителя REGCLS_SUSPENDED перечисления регклс.

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>Модуль:: Регистеробжектс

Регистрирует объекты COM или среда выполнения Windows, чтобы другие приложения могли подключаться к ним.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*модуль*<br/>
Массив объектов COM или среда выполнения Windows.

*Имя*<br/>
Имя сервера, который создал объекты.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>Модуль:: Регистервинртобжект

Регистрирует один или несколько объектов среда выполнения Windows, чтобы другие приложения могли подключаться к ним.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Параметры

*Имя*<br/>
Имя, которое определяет подмножество объектов, затронутых этой операцией.

*активатаблеклассидс*<br/>
Массив активируемых идентификаторов CLSID для регистрации.

*"*<br/>
Значение, которое идентифицирует зарегистрированные объекты класса. Это значение в дальнейшем используется для отмены регистрации.

*count*<br/>
Количество объектов, которое необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>Модуль:: releaseNotifier_

Содержит указатель на `ReleaseNotifier` объект.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>Модуль:: Terminate

Приводит к завершению работы всех экземпляров фабрик, созданных модулем.

```cpp
void Terminate();
```

### <a name="remarks"></a>Примечания

Освобождает фабрики в кэше.

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>Модуль:: UnregisterCOMObject

Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Параметры

*Имя*<br/>
(Не используется)

*сеанс*<br/>
Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан методом [регистеркомобжект](#registercomobject) .

*count*<br/>
Количество классов для отмены регистрации.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>Модуль:: Унрегистеробжектс

Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*модуль*<br/>
Указатель на модуль.

*Имя*<br/>
Представляет имя, которое определяет подмножество объектов, затронутых этой операцией.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>Модуль:: Унрегистервинртобжект

Отменяет регистрацию одного или нескольких объектов среда выполнения Windows, чтобы другие приложения не могли подключаться к ним.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Параметры

*"*<br/>
Указатель на значение, определяющее объект класса, регистрация которого должна быть отменена.
