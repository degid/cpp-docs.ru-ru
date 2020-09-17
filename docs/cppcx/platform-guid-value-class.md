---
title: Класс значения Platform::Guid
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 7c3b89ff238b1cb5ee9fbb71e83d20f571e656a3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031541"
---
# <a name="platformguid-value-class"></a>Класс значения Platform::Guid

Представляет тип «GUID» (/окна/win32/api/guiddef/ns-guid-guid) в системе типа Windows Runtime.

## <a name="syntax"></a>Синтаксис

```cpp
public value struct Guid
```

### <a name="members"></a>Участники

`Platform::Guid`имеет `Equals()`, `GetHashCode()`и `ToString()` методы, полученные из [платформы::Объект класса](../cppcx/platform-object-class.md), и `GetTypeCode()` метод, полученный из [платформы::Тип класса](../cppcx/platform-type-class.md). `Platform::Guid`также имеет следующих членов.

|Участник|Описание|
|------------|-----------------|
|[Guid](#ctor)|Инициализирует новый экземпляр `Platform::Guid`.|
|[оператора](#operator-equality)|Оператор «равно».|
|[оператора!](#operator-inequality)|Оператор «не равно».|
|[Оператор&lt;](#operator-less)|Оператор «меньше».|
|[оператор()](#operator-call)|Преобразует `Platform::Guid` в `GUID`.|

### <a name="remarks"></a>Примечания

Для создания `Platform::Guid`нового, используйте [Windows::Основа::GuidHelper::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) статический метод.

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a>Guid::Guid конструкторы

Инициализирует новый экземпляр `Platform::Guid`.

### <a name="syntax"></a>Синтаксис

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>Параметры

*a*<br/>
Первые 4 байта `GUID`.

*B*<br/>
Следующие 2 байта `GUID`.

*C*<br/>
Следующие 2 байта `GUID`.

*D*<br/>
Следующий байт структуры `GUID`.

*E*<br/>
Следующий байт структуры `GUID`.

*F*<br/>
Следующий байт структуры `GUID`.

*Г*<br/>
Следующий байт структуры `GUID`.

*H*<br/>
Следующий байт структуры `GUID`.

*Я*<br/>
Следующий байт структуры `GUID`.

*J*<br/>
Следующий байт структуры `GUID`.

*K*<br/>
Следующий байт структуры `GUID`.

*М*<br/>
А `GUID` в виде [структуры GUID.](/windows/win32/api/guiddef/ns-guiddef-guid)

*n*<br/>
Остальные 8 байтов `GUID`.

## <a name="guidoperator-operator"></a><a name="operator-equality"></a>Guid::Оператор - Оператор

Сравнивает два экземпляра `Platform::Guid` на предмет их равенства.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*guid1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*guid2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Правда, если `Platform::Guid` эти две инстанции равны.

### <a name="remarks"></a>Примечания

Предпочитаю использовать `==` оператора вместо [Windows:::Foundation:::GuidHelper::Equals](/uwp/api/windows.foundation.guidhelper.equals) static method.

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a>Гид::Оператор!

Сравнивает два экземпляра `Platform::Guid` на неравенство.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*guid1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*guid2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Правда, если `Platform::Guid` эти два экземпляра не равны.

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a>Guid::Оператор&lt;

Сравнивает `Platform::Guid` два экземпляра для заказа.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*guid1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*guid2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Правда, если *guid1* упорядочен до *guid2*. Заказ является лексикографическим после `Platform::Guid` обработки каждого, как будто это массив из четырех 32-битных неподписанных значений. Это не заказ, используемый сервером S'L или рамочным .NET, и не является таким же, как лексикографический заказ по репрезентации строк.

Этот оператор предоставляется `Guid` таким образом, чтобы объекты могли легче потребляться стандартной библиотекой СЗ.

## <a name="guidoperator-operator"></a><a name="operator-call"></a>Guid::Оператор() Оператор

Неявно преобразует `Platform::Guid` [структуру GUID.](/windows/win32/api/guiddef/ns-guiddef-guid)

### <a name="syntax"></a>Синтаксис

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Возвращаемое значение

[Структура GUID](/windows/win32/api/guiddef/ns-guiddef-guid).

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
