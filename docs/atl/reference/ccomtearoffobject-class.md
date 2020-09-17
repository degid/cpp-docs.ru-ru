---
title: Класс Ккомтеароффобжект
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: 3eee1d33d5eded75d8805584a24e6b6f396a8369
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833625"
---
# <a name="ccomtearoffobject-class"></a>Класс Ккомтеароффобжект

Этот класс реализует интерфейс разрыва.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Класс отрыва, производный от, `CComTearOffObjectBase` и интерфейсы, которые должен поддерживать ваш объект отрыва.

ATL реализует интерфейсы разрыва в два этапа — `CComTearOffObjectBase` методы обработают счетчик ссылок и, в своюмся `QueryInterface` , `CComTearOffObject` реализуют [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ккомтеароффобжект:: Ккомтеароффобжект](#ccomtearoffobject)|Конструктор.|
|[Ккомтеароффобжект:: ~ Ккомтеароффобжект](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккомтеароффобжект:: AddRef](#addref)|Увеличивает значение счетчика ссылок для `CComTearOffObject` объекта.|
|[Ккомтеароффобжект:: QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс либо в классе отрыва, либо в классе Owner.|
|[Ккомтеароффобжект:: Release](#release)|Уменьшает значение счетчика ссылок для `CComTearOffObject` объекта и уничтожает его.|

### <a name="ccomtearoffobjectbase-methods"></a>Методы Ккомтеароффобжектбасе

|Функция|Описание|
|-|-|
|[ккомтеароффобжектбасе](#ccomtearoffobjectbase)|Конструктор.|

### <a name="ccomtearoffobjectbase-data-members"></a>Элементы данных Ккомтеароффобжектбасе

|Элемент данных|Описание|
|-|-|
|[m_pOwner](#m_powner)|Указатель на `CComObject` производный от класса Owner.|

## <a name="remarks"></a>Примечания

`CComTearOffObject` реализует интерфейс разрыва как отдельный объект, который создается только при запросе к этому интерфейсу. Разрыв удаляется, когда счетчик ссылок становится равным нулю. Как правило, создается интерфейс разрыва для интерфейса, который редко используется, поскольку при использовании разрыва сохраняется указатель vtable во всех экземплярах основного объекта.

Класс, реализующий отрыв, должен быть производным от `CComTearOffObjectBase` любого интерфейса, который должен поддерживать ваш объект отрыва. `CComTearOffObjectBase` преобразованный в классе owner и потоковой модели. Класс owner — это класс объекта, для которого реализуется отрыв. Если не указать модель потоков, используется модель потоков по умолчанию.

Необходимо создать карту COM для класса отрыва. Когда библиотека ATL создает экземпляр, он создает `CComTearOffObject<CYourTearOffClass>` или `CComCachedTearOffObject<CYourTearOffClass>` .

Например, в образце BEEPER класс является классом `CBeeper2` отрыва, а `CBeeper` класс является классом-владельцем:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a> Ккомтеароффобжект:: AddRef

Увеличивает значение счетчика ссылок `CComTearOffObject` объекта на единицу.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a> Ккомтеароффобжект:: Ккомтеароффобжект

Конструктор.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
окне Указатель, который будет преобразован в указатель на `CComObject<Owner>` объект.

### <a name="remarks"></a>Примечания

Увеличивает счетчик ссылок владельца на единицу.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a> Ккомтеароффобжект:: ~ Ккомтеароффобжект

Деструктор

```
~CComTearOffObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает Финалрелеасе и уменьшает число блокировок модуля.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a> Ккомтеароффобжект:: Ккомтеароффобжектбасе

Конструктор.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Примечания

Инициализирует член [m_pOwner](#m_powner) значением NULL.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a> Ккомтеароффобжект:: m_pOwner

Указатель на объект [CComObject](../../atl/reference/ccomobject-class.md) , производный от *owner*.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Параметры

*Владелец*<br/>
окне Класс, для которого реализуется отрыв.

### <a name="remarks"></a>Примечания

Во время создания указатель инициализируется значением NULL.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a> Ккомтеароффобжект:: QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне IID запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*, или значение null, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Сначала запросы для интерфейсов в классе отрыва. Если интерфейс отсутствует, запрашивает интерфейс для объекта-владельца. Если запрошенный интерфейс имеет значение `IUnknown` , возвращает объект `IUnknown` владельца.

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a> Ккомтеароффобжект:: Release

Уменьшает значение счетчика ссылок на единицу и, если счетчик ссылок равен нулю, удаляет `CComTearOffObject` .

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках, не относящихся к отладке, всегда возвращает ноль. В отладочных сборках возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="see-also"></a>См. также раздел

[Класс Ккомкачедтеароффобжект](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
