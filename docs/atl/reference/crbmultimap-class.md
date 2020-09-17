---
title: Класс CRBMultiMap
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 1e36bc267b3a539d2d1d4bf370b9cdc33828c760
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331419"
---
# <a name="crbmultimap-class"></a>Класс CRBMultiMap

Этот класс представляет собой структуру отображения, которая позволяет каждому ключу быть связанс с более чем одним значением, используя красно-черное двоичное дерево.

## <a name="syntax"></a>Синтаксис

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Конструктор.|
|[CRBMultiMap:::CRBMultiMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRBmultimap:FindFirstWithKey](#findfirstwithkey)|Вызовите этот метод, чтобы найти положение первого элемента с заданным ключом.|
|[CRBmultimap:GetNextValueWithKey](#getnextvaluewithkey)|Вызовите этот метод, чтобы получить значение, связанное с данным ключом, и обновите значение позиции.|
|[CRBmultimap:GetNextWithKey](#getnextwithkey)|Вызовите этот метод, чтобы получить элемент, связанный с данным ключом, и обновите значение позиции.|
|[CRBMultiMap:Вставьте](#insert)|Вызовите этот метод, чтобы вставить пару элементов в карту.|
|[CRBMultiMap::RemoveKey](#removekey)|Вызовите этот метод, чтобы удалить все элементы ключа/значения для данного ключа.|

## <a name="remarks"></a>Примечания

`CRBMultiMap`обеспечивает поддержку массива отображения любого данного типа, управляя упорядоченным набором ключевых элементов и значений. В отличие от класса [CRBMap,](../../atl/reference/crbmap-class.md) каждый ключ может быть связан с более чем одним значением.

Элементы (состоящие из ключа и значения) хранятся в бинарной структуре дерева, используя метод [CRBMultiMap::Insert.](#insert) Элементы могут быть удалены с помощью метода [CRBMultiMap::RemoveKey,](#removekey) который удаляет все элементы, которые соответствуют данному ключу.

Обход дерева становится возможным с помощью таких методов, как [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Доступ к потенциально множественным значениям на ключ возможен с помощью методов [CRBMultiMap::FindFirstWithKey,](#findfirstwithkey) [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)и [CRBMultiMap::GetNextWithKey.](#getnextwithkey) Иллюстрацию к этому на практике можно посмотреть пример [CRBMultiMap::CRBMultiMap.](#crbmultimap)

Параметры *KTraits* и *VTraits* являются типами признаков, которые содержат любой дополнительный код, необходимый для копирования или перемещения элементов.

`CRBMultiMap`происходит от [CRBTree](../../atl/reference/crbtree-class.md), который реализует двоичное дерево с помощью красно-черного алгоритма. Альтернатива `CRBMultiMap` и `CRBMap` предлагается классом [CAtlMap.](../../atl/reference/catlmap-class.md) Если необходимо сохранить лишь небольшое количество элементов, подумайте об использовании класса [CSimpleMap.](../../atl/reference/csimplemap-class.md)

Для более полного обсуждения различных классов коллекции и их особенностей и характеристик производительности, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap

Конструктор.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

Параметр *nBlockSize* является мерой объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов. По умолчанию будет выделяться место для 10 элементов одновременно.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a>CRBMultiMap:::CRBMultiMap

Деструктор

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a>CRBmultimap:FindFirstWithKey

Вызовите этот метод, чтобы найти положение первого элемента с заданным ключом.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Определяет ключ, идентифицирует найденный элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает POSITION первого элемента ключа/значения, если ключ найден, NULL в противном случае.

### <a name="remarks"></a>Примечания

Ключ в `CRBMultiMap` банку имеет одно или несколько связанных значений. Этот метод обеспечит значение позиции первого значения (которое может, по сути, быть единственным значением), связанным с этим конкретным ключом. Возвращается значение позиции, чтобы получить значение и обновить позицию с [помощью CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) или [CRBMultiMap::GetNextWithKey.](#getnextwithkey)

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

Смотрите пример [CRBMultiMap:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a>CRBmultimap:GetNextValueWithKey

Вызовите этот метод, чтобы получить значение, связанное с данным ключом, и обновите значение позиции.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение позиции, полученное либо с вызовом в [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey), или предыдущий `GetNextValueWithKey`звонок.

*Ключ*<br/>
Определяет ключ, идентифицирует найденный элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает пару элементов, связанную с данным ключом.

### <a name="remarks"></a>Примечания

Значение позиции обновляется, чтобы указать на следующее значение, связанное с ключом. Если больше не существует значений, значение позиции устанавливается в NULL.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

Смотрите пример [CRBMultiMap:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a>CRBmultimap:GetNextWithKey

Вызовите этот метод, чтобы получить элемент, связанный с данным ключом, и обновите значение позиции.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение позиции, полученное либо с вызовом в [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), или предыдущий `GetNextWithKey`звонок.

*Ключ*<br/>
Определяет ключ, идентифицирует найденный элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает следующий элемент [CRBTree::CPair Class,](crbtree-class.md#cpair_class) связанный с данным ключом.

### <a name="remarks"></a>Примечания

Значение позиции обновляется, чтобы указать на следующее значение, связанное с ключом. Если больше не существует значений, значение позиции устанавливается в NULL.

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

## <a name="crbmultimapinsert"></a><a name="insert"></a>CRBMultiMap:Вставьте

Вызовите этот метод, чтобы вставить пару элементов в карту.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключевое значение для `CRBMultiMap` добавления к объекту.

*value*<br/>
Значение для добавления к объекту, связанное `CRBMultiMap` с *ключом.*

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение пары элементов ключа/значения `CRBMultiMap` в объекте.

### <a name="remarks"></a>Примечания

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

Смотрите пример [CRBMultiMap:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapremovekey"></a><a name="removekey"></a>CRBMultiMap::RemoveKey

Вызовите этот метод, чтобы удалить все элементы ключа/значения для данного ключа.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Упогоняет ключ, который определяет элемент (ы) для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество значений, связанных с данным ключом.

### <a name="remarks"></a>Примечания

`RemoveKey`удаляет все элементы ключа/значения, которые имеют ключ, который соответствует *ключу.*

Ознакомиться с документацией базового класса [CRBTree](../../atl/reference/crbtree-class.md) можно получить информацию о других доступных методах.

### <a name="example"></a>Пример

Смотрите пример [CRBMultiMap:CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>См. также раздел

[Класс CRBTree](../../atl/reference/crbtree-class.md)<br/>
[Класс CAtlMap](../../atl/reference/catlmap-class.md)<br/>
[Класс CRBMap](../../atl/reference/crbmap-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
