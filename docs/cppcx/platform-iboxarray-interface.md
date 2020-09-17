---
title: Интерфейс Platform::IBoxArray
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 493770cab092c2bb719d47e5d3a9d6a9f0646489
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444156"
---
# <a name="platformiboxarray-interface"></a>Интерфейс Platform::IBoxArray

`IBoxArray` является оболочкой для массивов типов значений, передаваемых через двоичный интерфейс приложений (ABI) или хранящихся в коллекциях элементов `Platform::Object^` , таких как коллекции в элементах управления XAML.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип упакованного значение в каждом элементе массива.

### <a name="remarks"></a>Примечания

`IBoxArray` — имя C++/cx для `Windows::Foundation::IReferenceArray`.

### <a name="members"></a>Члены

Интерфейс `IBoxArray` наследует от интерфейса `IValueType` . Интерфейс`IBoxArray` также содержит следующие члены:

|Метод|Description|
|------------|-----------------|
|[Value](#value)|Возвращает распакованный массив, который ранее хранился в этом экземпляре `IBoxArray` .|

## <a name="value"></a>Свойство IBoxArray:: value

Возвращает значение, которое было изначально сохранено в этом объекте.

### <a name="syntax"></a>Синтаксис

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Параметры

*T*<br/>
Введите запакованное значение.

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Возвращает значение, которое было изначально сохранено в этом объекте.

### <a name="remarks"></a>Примечания

Пример см. в разделе [Упаковка](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>См. также раздел

[Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
