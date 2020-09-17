---
title: ICollectionOnSTLImpl класса
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: a8ccab08b89da8c1b8ef56c8932e27a6c74e62aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329908"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl класса

Этот класс предоставляет методы, используемые классом коллекции.

## <a name="syntax"></a>Синтаксис

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Интерфейс коллекции COM.

*CollType*<br/>
Класс контейнеров Стандартной библиотеки СЗ.

*Itemtype*<br/>
Тип элемента, выставленного интерфейсом контейнера.

*CopyItem*<br/>
[Класс политики копирования](../../atl/atl-copy-policy-classes.md).

*EnumType*<br/>
[Класс CComEnumOnSTL,](../../atl/reference/ccomenumonstl-class.md)совместимый с перечислением.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Возвращает объект регистратора для коллекции.|
|[ICollectionOnSTLImpl::getcount](#get_count)|Возвращает количество элементов в коллекции.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|Возвращает запрошенный товар из коллекции.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Коллекция.|

## <a name="remarks"></a>Примечания

Этот класс обеспечивает реализацию для трех методов интерфейса сбора: [getcount,](#get_count) [get_Item](#get_item)и [get__NewEnum.](#newenum)

Для использования этого класса:

- Определите (или одолжите) интерфейс сбора, который вы хотите реализовать.

- Выизвуйте свой `ICollectionOnSTLImpl` класс из специализации на основе интерфейса этой коллекции.

- Используйте свой производный класс для реализации любых `ICollectionOnSTLImpl`методов из интерфейса сбора, не обрабатываемых .

> [!NOTE]
> Если интерфейс коллекции является двойным интерфейсом, вывешйте свой класс из [IDispatchImpl,](../../atl/reference/idispatchimpl-class.md)передав `ICollectionOnSTLImpl` `IDispatch` специализацию в качестве первого параметра шаблона, если вы хотите, чтобы ATL обеспечивала реализацию методов.

- Добавьте элементы [в](#m_coll) m_coll для заполнения коллекции.

Для получения дополнительной информации и примеров [см.](../../atl/atl-collections-and-enumerators.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a>ICollectionOnSTLImpl::getcount

Этот метод возвращает количество элементов в коллекции.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Параметры

*pcount*<br/>
(ваут) Количество элементов в коллекции.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a>ICollectionOnSTLImpl::get_Item

Этот метод возвращает указанный элемент из коллекции.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
(в) 1-основанный индекс элемента в коллекции.

*pvar*<br/>
(ваут) Элемент, соответствующий *индексу*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Элемент получен путем копирования данных в указанном положении в [m_coll](#m_coll) используя метод копирования `ICollectionOnSTLImpl` класса [политики копирования,](../../atl/atl-copy-policy-classes.md) переданный в качестве аргумента шаблона в специализации.

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a>ICollectionOnSTLImpl::get__NewEnum

Возвращает объект регистратора для коллекции.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Параметры

*ppUnk*<br/>
(ваут) **Инеизвестный** указатель недавно созданного объекта экумератора.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вновь созданный регистратор поддерживает итератор в оригинальной коллекции `m_coll`(так что копия не производится) и содержит ссылку COM на объект коллекции, чтобы убедиться, что коллекция остается в живых, пока есть выдающиеся регистраторы.

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a>ICollectionOnSTLImpl::m_coll

Этот участник содержит элементы, представленные коллекцией.

```
CollType m_coll;
```

## <a name="see-also"></a>См. также раздел

[Пример ATLCollections](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
