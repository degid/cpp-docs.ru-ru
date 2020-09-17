---
title: Класс CRBMap
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 9e367ccc875eedf63e4f47018598662af2dfcf7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331403"
---
# <a name="crbmap-class"></a>Класс CRBMap

Этот класс представляет собой структуру отображения с использованием красно-черного двоичного дерева.

## <a name="syntax"></a>Синтаксис

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключевого элемента.

*V*<br/>
Тип элемента значения.

*KTraits*<br/>
Код, используемый для копирования или перемещения ключевых элементов. Более подробную информацию можно узнать в [классе CElementTraits.](../../atl/reference/celementtraits-class.md)

*VTraits*<br/>
Код, используемый для копирования или перемещения элементов значения.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRBMap:CRBMap](#crbmap)|Конструктор.|
|[CRBMap:::CRBMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRBMap:Lookup](#lookup)|Вызовите этот метод, чтобы найти `CRBMap` ключи или значения в объекте.|
|[CRBMap::RemoveKey](#removekey)|Вызовите этот метод, `CRBMap` чтобы удалить элемент из объекта, учитывая ключ.|
|[CRBMap::SetAt](#setat)|Вызовите этот метод, чтобы вставить пару элементов в карту.|

## <a name="remarks"></a>Примечания

`CRBMap`обеспечивает поддержку массива карт любого данного типа, управление упорядоченным массивом ключевых элементов и связанных с ними значений. Каждый ключ может иметь только одно связанное значение. Элементы (состоящие из ключа и значения) хранятся в бинарной структуре дерева, используя метод [CRBMap::SetAt.](#setat) Элементы могут быть удалены с помощью метода [CRBMap::RemoveKey,](#removekey) который удаляет элемент с заданным значением ключа.

Обход дерева становится возможным с помощью таких методов, как [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).

Параметры *KTraits* и *VTraits* являются типами признаков, которые содержат любой дополнительный код, необходимый для копирования или перемещения элементов.

`CRBMap`происходит от [CRBTree](../../atl/reference/crbtree-class.md), который реализует двоичное дерево с помощью красно-черного алгоритма. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) — это вариация, позволяющая использовать несколько значений для каждого ключа. Он тоже является `CRBTree`производным от `CRBMap`, и поэтому разделяет многие функции с .

Альтернатива обоим `CRBMap` `CRBMultiMap` и предлагается классом [CAtlMap.](../../atl/reference/catlmap-class.md) Если необходимо сохранить лишь небольшое количество элементов, подумайте об использовании класса [CSimpleMap.](../../atl/reference/csimplemap-class.md)

Для более полного обсуждения различных классов коллекции и их особенностей и характеристик производительности, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a>CRBMap:CRBMap

Конструктор.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

Параметр *nBlockSize* является мерой объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов. По умолчанию будет выделяться место для 10 элементов одновременно.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a>CRBMap:::CRBMap

Деструктор

```
~CRBMap() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

## <a name="crbmaplookup"></a><a name="lookup"></a>CRBMap:Lookup

Вызовите этот метод, чтобы найти `CRBMap` ключи или значения в объекте.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Определяет ключ, который определяет элемент, который следует изыскнуть.

*value*<br/>
Переменная, которая получает значение "загнан".

### <a name="return-value"></a>Возвращаемое значение

Первая форма метода возвращается верно, если ключ найден, в противном случае ложно. Вторая и третья формы возвращают указатель [cPair.](crbtree-class.md#cpair_class)

### <a name="remarks"></a>Примечания

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a>CRBMap::RemoveKey

Вызовите этот метод, `CRBMap` чтобы удалить элемент из объекта, учитывая ключ.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, соответствующий паре элементов, который вы хотите удалить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если ключ найден и удален, ложный при сбое.

### <a name="remarks"></a>Примечания

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a>CRBMap::SetAt

Вызовите этот метод, чтобы вставить пару элементов в карту.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключевое значение для `CRBMap` добавления к объекту.

*value*<br/>
Значение для добавления к объекту. `CRBMap`

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение пары элементов ключа/значения `CRBMap` в объекте.

### <a name="remarks"></a>Примечания

`SetAt`заменяет существующий элемент при обнаружении соответствующего ключа. Если ключ не найден, создается новая пара ключей/значений.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CRBTree](../../atl/reference/crbtree-class.md)<br/>
[Класс CAtlMap](../../atl/reference/catlmap-class.md)<br/>
[Класс CRBMultiMap](../../atl/reference/crbmultimap-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
