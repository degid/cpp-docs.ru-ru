---
title: Пространство имен Microsoft::WRL
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
ms.openlocfilehash: c92251dacbfa17e8f1ac0cbdc41aa9b06118ac91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213776"
---
# <a name="microsoftwrl-namespace"></a>Пространство имен Microsoft::WRL

Определяет фундаментальные типы, составляющие библиотеку шаблонов среда выполнения Windows C++ .

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL;
```

## <a name="members"></a>Члены

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt | InhibitWeakReference>`|

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс ActivationFactory](activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|
|[Класс AsyncBase](asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|
|[Класс ClassFactory](classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|
|[Класс ComPtr](comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|
|[Класс DeferrableEventArgs](deferrableeventargs-class.md)|Класс шаблона, используемый для типов аргументов событий для задержек.|
|[EventSource](eventsource-class.md)|Представляет событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий.|
|[Класс FtmBase](ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|
|[Класс Module](module-class.md)|Представляет коллекцию связанных объектов.|
|[Класс RuntimeClass](runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|
|[Класс SimpleActivationFactory](simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|
|[Класс SimpleClassFactory](simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|
|[Класс WeakRef](weakref-class.md)|Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

### <a name="structures"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[Структура ChainInterfaces](chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|
|[Структура CloakedIid](cloakediid-structure.md)|Указывает на шаблоны `RuntimeClass`, `Implements` и `ChainInterfaces`, которые указанный интерфейс недоступен в списке IID.|
|[Структура Implements](implements-structure.md)|Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.|
|[Структура MixIn](mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|
|[Структура RuntimeClassFlags](runtimeclassflags-structure.md)|Содержит тип для экземпляра [RuntimeClass](runtimeclass-class.md).|

### <a name="enumerations"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление AsyncResultType](asyncresulttype-enumeration.md)|Задает тип результата, возвращаемого методом `GetResults()`.|
|[Перечисление ModuleType](moduletype-enumeration.md)|Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.|
|[Перечисление RuntimeClassType](runtimeclasstype-enumeration.md)|Указывает поддерживаемый тип экземпляра [RuntimeClass](runtimeclass-class.md) .|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[Функция AsWeak](asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|
|[Функция Callback (WRL)](callback-function-wrl.md)|Создает объект, функция-член которого является методом обратного вызова.|
|[Функция CreateActivationFactory](createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|
|[Функция CreateClassFactory](createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|
|[Функция Make](make-function.md)|Инициализирует указанный класс среда выполнения Windows.|

## <a name="requirements"></a>Требования

**Заголовок:** Async.h, Client.h, кореврапперс.h, Event.h, FTM.h, реализует.h, internal.h, Module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)
