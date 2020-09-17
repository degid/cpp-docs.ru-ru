---
title: Пространство имен Microsoft::WRL::Details
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: 50208242d77d7b54951bcb44608f1a20b5147efc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223477"
---
# <a name="microsoftwrldetails-namespace"></a>Пространство имен Microsoft::WRL::Details

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс ComPtrRef](comptrref-class.md)|Представляет ссылку на объект типа ComPtr \<T> .|
|[Класс оператор comptrrefbase](comptrrefbase-class.md)|Представляет базовый класс для класса [ComPtrRef](comptrref-class.md) .|
|[Класс DontUseNewUseMake](dontusenewusemake-class.md)|Предотвращает использование оператора `new` в `RuntimeClass` . Следовательно, вместо этого следует использовать [функцию make](make-function.md) .|
|[Класс EventTargetArray](eventtargetarray-class.md)|Представляет массив обработчиков событий.|
|[Класс MakeAllocator](makeallocator-class.md)|Выделяет память для класса активируемого с поддержкой слабых ссылок или без нее.|
|[Класс ModuleBase](modulebase-class.md)|Представляет базовый класс для классов [модулей](module-class.md) .|
|[Класс RemoveIUnknown](removeiunknown-class.md)|Делает тип, эквивалентный `IUnknown` типу на основе, но имеющий невиртуальные `QueryInterface` `AddRef` методы, и `Release` .|
|[Класс WeakReference](weakreference-class.md)|Представляет *слабую ссылку* , которую можно использовать с среда выполнения Windows или классическим com. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

### <a name="structures"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[ArgTraits - структура](argtraits-structure.md)|Объявляет указанный интерфейс делегата и анонимную функцию-член с заданным числом параметров.|
|[ArgTraitsHelper - структура](argtraitshelper-structure.md)|Помогает определить общие характеристики аргументов делегата.|
|[BoolStruct - структура](boolstruct-structure.md)|Определяет, `ComPtr` управляет ли объект временем существования объекта в интерфейсе. `BoolStruct`используется внутри оператором [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) .|
|[CreatorMap - структура](creatormap-structure.md)|Содержит сведения о том, как выполнять инициализацию, регистрацию и отмену регистрации объектов.|
|[DerefHelper - структура](derefhelper-structure.md)|Представляет разыменованный указатель на параметр шаблона `T*`.|
|[EnableIf - структура](enableif-structure.md)|Определяет элемент данных типа, указанного вторым параметром шаблона, если первый параметр шаблона имеет значение **`true`** .|
|[FactoryCache - структура](factorycache-structure.md)|Содержит расположение фабрики класса и значение, идентифицирующее зарегистрированный среда выполнения Windows или объект класса COM.|
|[ImplementsBase - структура](implementsbase-structure.md)|Используется для проверки типов параметров шаблона в [структуре Implements](implements-structure.md).|
|[ImplementsHelper - структура](implementshelper-structure.md)|Помогает реализовать структуру [Implements](implements-structure.md) .|
|[InterfaceList - структура](interfacelist-structure.md)|Используется для создания рекурсивного списка интерфейсов.|
|[InterfaceListHelper - структура](interfacelisthelper-structure.md)|Создает `InterfaceList` тип, рекурсивно применяя заданные аргументы параметра шаблона.|
|[InterfaceTraits - структура](interfacetraits-structure.md)|Реализует общие характеристики интерфейса.|
|[InvokeHelper - структура](invokehelper-structure.md)|Предоставляет реализацию `Invoke()` метода на основе указанного числа и типа аргументов.|
|[IsBaseOfStrict - структура](isbaseofstrict-structure.md)|Проверяет, является ли один тип базовым для другого.|
|[IsSame - структура](issame-structure.md)|Определяет, совпадают ли указанные типы друг с другом.|
|[Структура Nil](nil-structure.md)|Используется для указания неуказанного необязательного параметра шаблона.|
|[RemoveReference - структура](removereference-structure.md)|Отделяет ссылку или признак rvalue-reference от указанного параметра шаблона класса.|
|[Структура RuntimeClassBase](runtimeclassbase-structure.md)|Используется для обнаружения `RuntimeClass` функции [make](make-function.md) .|
|[Структура RuntimeClassBaseT](runtimeclassbaset-structure.md)|Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.|
|[VerifyInheritanceHelper - структура](verifyinheritancehelper-structure.md)|Проверяет, является ли один интерфейс производным от другого интерфейса.|
|[VerifyInterfaceHelper - структура](verifyinterfacehelper-structure.md)|Проверяет, соответствует ли интерфейс, указанный параметром шаблона, определенным требованиям.|

### <a name="enumerations"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[AsyncStatusInternal - перечисление](asyncstatusinternal-enumeration.md)|Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[Функция Активатионфакторикаллбакк](activationfactorycallback-function.md)|Возвращает фабрику активации для указанного идентификатора активации.|
|[Move, функция](move-function.md)|Перемещает указанный аргумент из одного расположения в другое.|
|[Функция RaiseException](raiseexception-function.md)|Вызывает исключение в вызывающем потоке.|
|[Функция swap (WRL)](swap-function-wrl.md)|Меняет местами значения двух указанных аргументов.|
|[Функция Терминатемап](terminatemap-function.md)|Завершает работу фабрик классов в указанном модуле.|

## <a name="requirements"></a>Требования

**Заголовок:** Async.h, Client.h, кореврапперс.h, Event.h, FTM.h, реализует.h, internal.h, Module.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также статью

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)<br/>
[Пространство имен Microsoft:: WRL:: оберток](microsoft-wrl-wrappers-namespace.md)
