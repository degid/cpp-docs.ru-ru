---
title: Класс CAtlMap
ms.date: 11/04/2016
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: b79e6cbd796569e6ba11c96158099de6c30b310a
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168063"
---
# <a name="catlmap-class"></a>Класс CAtlMap

Этот класс предоставляет методы для создания объекта Map и управления им.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип элемента Key.

*3,3*<br/>
Тип элемента value.

*ктраитс*<br/>
Код, используемый для копирования или перемещения элементов ключа. Дополнительные сведения см. в разделе [класс целементтраитс](../../atl/reference/celementtraits-class.md) .

*втраитс*<br/>
Код, используемый для копирования или перемещения элементов значений.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAtlMap:: КИНАРГТИПЕ](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента|
|[CAtlMap:: КАУТАРГТИПЕ](#koutargtype)|Тип, используемый при возврате ключа в качестве выходного аргумента.|
|[CAtlMap:: ВИНАРГТИПЕ](#vinargtype)|Тип, используемый при передаче значения в качестве входного аргумента.|
|[CAtlMap:: ВАУТАРГТИПЕ](#voutargtype)|Тип, используемый при передаче значения в качестве выходного аргумента.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс CAtlMap:: Кпаир](#cpair_class)|Класс, содержащий элементы Key и value.|

### <a name="cpair-data-members"></a>Элементы данных Кпаир

|Имя|Описание|
|----------|-----------------|
|[Кпаир:: m_key](#m_key)|Элемент данных, в котором хранится элемент key.|
|[Кпаир:: m_value](#m_value)|Элемент данных, в котором хранится элемент value.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap:: CAtlMap](#catlmap)|Конструктор.|
|[CAtlMap:: ~ CAtlMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap:: AssertValid](#assertvalid)|Вызовите этот метод, чтобы вызвать ASSERT, `CAtlMap` если является недопустимым.|
|[CAtlMap::D Исаблеауторехаш](#disableautorehash)|Вызовите этот метод, чтобы отключить автоматическую перехэширование `CAtlMap` объекта.|
|[CAtlMap:: Енаблеауторехаш](#enableautorehash)|Вызовите этот метод, чтобы включить автоматическую повторное `CAtlMap` хэширование объекта.|
|[CAtlMap:: GetAt](#getat)|Вызовите этот метод, чтобы вернуть элемент в указанной позиции на карте.|
|[CAtlMap:: NOCOUNT](#getcount)|Вызовите этот метод, чтобы получить количество элементов в сопоставлении.|
|[CAtlMap:: Жесаштаблесизе](#gethashtablesize)|Вызовите этот метод, чтобы определить количество ячеек в хэш-таблице на карте.|
|[CAtlMap:: Жеткэйат](#getkeyat)|Вызовите этот метод, чтобы получить ключ, хранящийся в заданной `CAtlMap` позиции в объекте.|
|[CAtlMap:: GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель на следующую пару элементов, хранящуюся `CAtlMap` в объекте.|
|[CAtlMap:: Жетнекстассок](#getnextassoc)|Возвращает следующий элемент для итерации.|
|[CAtlMap:: Жетнексткэй](#getnextkey)|Вызовите этот метод, чтобы получить следующий ключ из `CAtlMap` объекта.|
|[CAtlMap:: Жетнекствалуе](#getnextvalue)|Вызовите этот метод, чтобы получить следующее значение из `CAtlMap` объекта.|
|[CAtlMap:: Жетстартпоситион](#getstartposition)|Вызовите этот метод для запуска итерации на карте.|
|[CAtlMap:: Жетвалуеат](#getvalueat)|Вызовите этот метод, чтобы получить значение, хранящееся в заданной позиции `CAtlMap` в объекте.|
|[CAtlMap:: Инисаштабле](#inithashtable)|Вызовите этот метод, чтобы инициализировать хэш-таблицу.|
|[CAtlMap:: IsEmpty](#isempty)|Вызовите этот метод, чтобы проверить наличие пустого объекта Map.|
|[CAtlMap:: Lookup](#lookup)|Вызывайте этот метод для поиска ключей или значений в `CAtlMap` объекте.|
|[CAtlMap:: rehash](#rehash)|Вызовите этот метод для перехеширования `CAtlMap` объекта.|
|[CAtlMap:: RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы `CAtlMap` из объекта.|
|[CAtlMap:: Ремовеатпос](#removeatpos)|Вызовите этот метод, чтобы удалить элемент в заданной позиции в `CAtlMap` объекте.|
|[CAtlMap:: Ремовекэй](#removekey)|Вызовите этот метод, чтобы удалить элемент из `CAtlMap` объекта по заданному ключу.|
|[CAtlMap:: SetAt](#setat)|Вызовите этот метод, чтобы вставить пару элементов в карту.|
|[CAtlMap:: Сетоптималлоад](#setoptimalload)|Вызовите этот метод, чтобы задать оптимальную загрузку `CAtlMap` объекта.|
|[CAtlMap:: Сетвалуеат](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции `CAtlMap` в объекте.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Заменяет или добавляет новый элемент в `CAtlMap`.|

## <a name="remarks"></a>Примечания

`CAtlMap`обеспечивает поддержку для массива сопоставления любого заданного типа, управляя неупорядоченным массивом ключевых элементов и связанными с ними значениями. Элементы (состоящие из ключа и значения) хранятся с помощью алгоритма хэширования, что позволяет эффективно хранить и извлекать большие объемы данных.

Параметры *ктраитс* и *втраитс* являются признаками классов, которые содержат любой дополнительный код, необходимый для копирования или перемещения элементов.

Альтернатива `CAtlMap` предложению класса [крбмап](../../atl/reference/crbmap-class.md) . `CRBMap`также хранит пары "ключ-значение", но имеет различные характеристики производительности. Время, затраченное на вставку элемента, Поиск ключа или удаление ключа из `CRBMap` объекта, является *журналом порядка (n)*, где *n* — число элементов. Для `CAtlMap`все эти операции обычно принимают постоянное время, хотя наихудшие сценарии могут иметь порядок *n*. Таким образом, в типичном случае `CAtlMap` это быстрее.

Другие различия между `CRBMap` и `CAtlMap` становятся очевидными при переборе хранимых элементов. `CRBMap`В элементы отображаются в отсортированном порядке. `CAtlMap`В элементы не упорядочиваются, и порядок не может быть определен.

Если необходимо сохранить небольшое количество элементов, рекомендуется использовать класс [ксимплемап](../../atl/reference/csimplemap-class.md) .

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлколл.h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap:: AssertValid

Вызовите этот метод, чтобы вызвать ASSERT, `CAtlMap` если объект является недопустимым.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Примечания

В отладочных сборках этот метод вызывает утверждение, если `CAtlMap` объект является недопустимым.

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap:: CAtlMap

Конструктор.

```cpp
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>Параметры

*нбинс*<br/>
Число ячеек, содержащих указатели на хранимые элементы. Описание ячеек см. в подразделе "Примечания" Далее в этой статье.

*фоптималлоад*<br/>
Оптимальное соотношение нагрузки.

*флосрешолд*<br/>
Нижнее пороговое значение для коэффициента загрузки.

*фхисрешолд*<br/>
Верхнее пороговое значение для коэффициента загрузки.

*нблокксизе*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

`CAtlMap`ссылается на все свои хранимые элементы путем создания индекса с помощью алгоритма хэширования для ключа. Этот индекс ссылается на "bin", содержащий указатель на хранимые элементы. Если ячейка уже используется, для доступа к последующим элементам создается связанный список. Обход списка выполняется медленнее, чем прямой доступ к правильному элементу, поэтому структуре Map необходимо сбалансировать требования к хранилищу по производительности. В большинстве случаев для предоставления оптимальных результатов выбраны параметры по умолчанию.

Коэффициент нагрузки — это отношение количества ячеек к количеству элементов, хранящихся в объекте Map. При повторном вычислении структуры Map значение параметра *фоптималлоад* будет использоваться для вычисления необходимого количества ячеек. Это значение можно изменить с помощью метода [CAtlMap:: сетоптималлоад](#setoptimalload) .

Параметр *флосрешолд* — это наименьшее значение, которое может достичь коэффициента загрузки `CAtlMap` , прежде чем будет повторно вычислить оптимальный размер Map.

Параметр *фхисрешолд* — это верхнее значение, которое может быть достигнуто коэффициентом `CAtlMap` загрузки, прежде чем объект будет повторно вычислить оптимальный размер Map.

Этот процесс повторного вычисления (называемый повторным хэшированием) включен по умолчанию. Если вы хотите отключить этот процесс, например при вводе большого количества данных за один раз, вызовите метод [CAtlMap::D исаблеауторехаш](#disableautorehash) . Повторно активируйте его с помощью метода [CAtlMap:: енаблеауторехаш](#enableautorehash) .

Параметр *нблокксизе* — это мера объема памяти, выделенной, когда требуется новый элемент. Большие размеры блоков сокращают число вызовов подпрограмм выделения памяти, но используют больше ресурсов.

Прежде чем можно будет сохранить данные, необходимо инициализировать хэш-таблицу с помощью вызова [CAtlMap:: инисаштабле](#inithashtable).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>CAtlMap:: ~ CAtlMap

Деструктор

```cpp
~CAtlMap() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>Класс CAtlMap:: Кпаир

Класс, содержащий элементы Key и value.

```cpp
class CPair : public __POSITION
```

### <a name="remarks"></a>Примечания

Этот класс используется методами [CAtlMap::](#getnext) GetNext и [CAtlMap:: Lookup](#lookup) для доступа к элементам Key и value, хранящимся в структуре сопоставления.

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap::D Исаблеауторехаш

Вызовите этот метод, чтобы отключить автоматическую перехэширование `CAtlMap` объекта.

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Примечания

Если включена автоматическая повторная хеширование (которая по умолчанию), число ячеек в хэш-таблице будет автоматически пересчитано, если значение загрузки (отношение количества ячеек к количеству элементов, хранящихся в массиве) превышает максимальное или минимальное значения, указанные во время создания схемы.

`DisableAutoRehash`наиболее полезен при одновременном добавлении большого числа элементов на карту. Вместо запуска процесса повторной хэширования каждый раз, когда превышены ограничения, более эффективно вызывать `DisableAutoRehash`, добавлять элементы и, наконец, вызывать [CAtlMap:: енаблеауторехаш](#enableautorehash).

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap:: Енаблеауторехаш

Вызовите этот метод, чтобы включить автоматическую повторное `CAtlMap` хэширование объекта.

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Примечания

Если включена автоматическая повторная хеширование (которая по умолчанию), число ячеек в хэш-таблице будет автоматически пересчитано, если значение загрузки (отношение количества ячеек к количеству элементов, хранящихся в массиве) превышает максимальное или минимальное значения, указанные во время создания схемы.

`EnableAutoRefresh`чаще всего используется после вызова [CAtlMap::D исаблеауторехаш](#disableautorehash).

## <a name="catlmapgetat"></a><a name="getat"></a>CAtlMap:: GetAt

Вызовите этот метод, чтобы вернуть элемент в указанной позиции на карте.

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

*key*<br/>
Параметр шаблона, указывающий тип ключа на карте.

*value*<br/>
Параметр шаблона, указывающий тип значения схемы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на текущую пару пар "ключ-значение", хранимую на карте.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если значение *POS* равно null.

## <a name="catlmapgetcount"></a><a name="getcount"></a>CAtlMap:: NOCOUNT

Вызовите этот метод, чтобы получить количество элементов в сопоставлении.

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в объекте Map. Единственный элемент — это пара "ключ-значение".

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap:: Жесаштаблесизе

Вызовите этот метод, чтобы определить количество ячеек в хэш-таблице на карте.

```cpp
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число ячеек в хэш-таблице. Описание см. в разделе [CAtlMap:: CAtlMap](#catlmap) .

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap:: Жеткэйат

Вызовите этот метод, чтобы получить ключ, хранящийся в заданной `CAtlMap` позиции в объекте.

```cpp
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на ключ, хранящийся в заданной позиции в `CAtlMap` объекте.

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapgetnext"></a><a name="getnext"></a>CAtlMap:: GetNext

Вызовите этот метод, чтобы получить указатель на следующую пару элементов, хранящуюся `CAtlMap` в объекте.

```cpp
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующую пару элементов "ключ-значение", хранимых на карте. Счетчик "положение *POS* " обновляется после каждого вызова. Если извлеченный элемент является последним в сопоставлении, для *POS* устанавливается значение null.

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap:: Жетнекстассок

Возвращает следующий элемент для итерации.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

*key*<br/>
Параметр шаблона, указывающий тип ключа на карте.

*value*<br/>
Параметр шаблона, указывающий тип значения схемы.

### <a name="remarks"></a>Примечания

Счетчик "положение *POS* " обновляется после каждого вызова. Если извлеченный элемент является последним в сопоставлении, для *POS* устанавливается значение null.

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap:: Жетнексткэй

Вызовите этот метод, чтобы получить следующий ключ из `CAtlMap` объекта.

```cpp
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ в сопоставлении.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиций, *POS*. Если на карте больше нет записей, счетчику позиции присваивается значение NULL.

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap:: Жетнекствалуе

Вызовите этот метод, чтобы получить следующее значение из `CAtlMap` объекта.

```cpp
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение в сопоставлении.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиций, *POS*. Если на карте больше нет записей, счетчику позиции присваивается значение NULL.

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap:: Жетстартпоситион

Вызовите этот метод для запуска итерации на карте.

```cpp
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает начальную точку, или значение NULL возвращается, если значение Map пустое.

### <a name="remarks"></a>Примечания

Вызовите этот метод для запуска итерации Map, возвращая значение значения value, которое может быть `GetNextAssoc` передано в метод.

> [!NOTE]
> Последовательность итераций не является прогнозируемой

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap:: Жетвалуеат

Вызовите этот метод, чтобы получить значение, хранящееся в заданной позиции `CAtlMap` в объекте.

```cpp
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в заданной позиции в `CAtlMap` объекте.

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap:: Инисаштабле

Вызовите этот метод, чтобы инициализировать хэш-таблицу.

```cpp
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Параметры

*нбинс*<br/>
Число ячеек, используемых хэш-таблицей. Описание см. в разделе [CAtlMap:: CAtlMap](#catlmap) .

*баллокнов*<br/>
Флаг, который указывает, когда должна быть выделена память.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE при успешной инициализации, значение FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`InitHashTable`должен вызываться до того, как все элементы будут сохранены в хэш-таблице.  Если этот метод не вызывается явным образом, он будет вызываться автоматически при первом добавлении элемента с помощью счетчика bin, указанного `CAtlMap` конструктором.  В противном случае Map будет инициализирован с использованием нового счетчика ячеек, указанного параметром *нбинс* .

Если параметр *баллокнов* имеет значение false, то память, требуемая для хэш-таблицы, не будет выделена до первой необходимости. Это может быть полезно, если не уверены в том, что будет использоваться схема.

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapisempty"></a><a name="isempty"></a>CAtlMap:: IsEmpty

Вызовите этот метод, чтобы проверить наличие пустого объекта Map.

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если значение Map пусто, и FALSE в противном случае.

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap:: КИНАРГТИПЕ

Тип, используемый при передаче ключа в качестве входного аргумента.

```cpp
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap:: КАУТАРГТИПЕ

Тип, используемый при возврате ключа в качестве выходного аргумента.

```cpp
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>CAtlMap:: Lookup

Вызывайте этот метод для поиска ключей или значений в `CAtlMap` объекте.

```cpp
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает ключ, определяющий элемент для поиска.

*value*<br/>
Переменная, принимающая искомое значение.

### <a name="return-value"></a>Возвращаемое значение

Первая форма метода возвращает значение true, если ключ найден; в противном случае — значение false. Вторая и третья формы возвращают указатель на [кпаир](#cpair_class) , который можно использовать в качестве позиции для вызовов [CAtlMap:: GetNext](#getnext) и т. д.

### <a name="remarks"></a>Примечания

`Lookup`использует алгоритм хэширования для быстрого поиска элемента Map, содержащего ключ, который точно соответствует заданному ключевому параметру.

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap::operator\[\]

Заменяет или добавляет новый элемент в `CAtlMap`.

```cpp
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ добавляемого или заменяемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, связанное с заданным ключом.

### <a name="example"></a>Пример

Если ключ уже существует, элемент заменяется. Если ключ не существует, добавляется новый элемент. См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmaprehash"></a><a name="rehash"></a>CAtlMap:: rehash

Вызовите этот метод для перехеширования `CAtlMap` объекта.

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Параметры

*нбинс*<br/>
Новое число ячеек для использования в хэш-таблице. Описание см. в разделе [CAtlMap:: CAtlMap](#catlmap) .

### <a name="remarks"></a>Примечания

Если *нбинс* равен 0, `CAtlMap` вычисляет разумное число на основе числа элементов на карте и оптимального параметра загрузки. Обычно процесс повторной хеширования выполняется автоматически, но если был вызван [CAtlMap::D исаблеауторехаш](#disableautorehash) , этот метод выполнит необходимое изменение размера.

## <a name="catlmapremoveall"></a><a name="removeall"></a>CAtlMap:: RemoveAll

Вызовите этот метод, чтобы удалить все элементы `CAtlMap` из объекта.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Примечания

Очищает `CAtlMap` объект, освобождая память, используемую для хранения элементов.

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap:: Ремовеатпос

Вызовите этот метод, чтобы удалить элемент в заданной позиции в `CAtlMap` объекте.

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

### <a name="remarks"></a>Примечания

Удаляет пару "ключ-значение", хранящуюся в указанной позиции. Память, используемая для хранения элемента, освобождается. ПОЗИЦИЯ, на которую ссылается *POS* , становится недопустимой, а позиция любых других элементов в сопоставлении остается допустимой, но не обязательно сохраняет одинаковый порядок.

## <a name="catlmapremovekey"></a><a name="removekey"></a>CAtlMap:: Ремовекэй

Вызовите этот метод, чтобы удалить элемент из `CAtlMap` объекта по заданному ключу.

```cpp
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, соответствующий паре элементов, которое необходимо удалить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если ключ найден и удален, и FALSE при сбое.

### <a name="example"></a>Пример

См. пример для [CAtlMap:: CAtlMap](#catlmap).

## <a name="catlmapsetat"></a><a name="setat"></a>CAtlMap:: SetAt

Вызовите этот метод, чтобы вставить пару элементов в карту.

```cpp
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа, добавляемое в `CAtlMap` объект.

*value*<br/>
Значение, добавляемое в `CAtlMap` объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает расположение пары элементов "ключ-значение" в `CAtlMap` объекте.

### <a name="remarks"></a>Примечания

`SetAt`заменяет существующий элемент, если найден соответствующий ключ. Если ключ не найден, создается новая пара "ключ-значение".

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap:: Сетоптималлоад

Вызовите этот метод, чтобы задать оптимальную загрузку `CAtlMap` объекта.

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Параметры

*фоптималлоад*<br/>
Оптимальное соотношение нагрузки.

*флосрешолд*<br/>
Нижнее пороговое значение для коэффициента загрузки.

*фхисрешолд*<br/>
Верхнее пороговое значение для коэффициента загрузки.

*брехашнов*<br/>
Флаг, указывающий, следует ли повторно вычислить хэш-таблицу.

### <a name="remarks"></a>Примечания

Этот метод переопределяет оптимальное значение загрузки для `CAtlMap` объекта. Описание различных параметров см. в разделе [CAtlMap:: CAtlMap](#catlmap) . Если *брехашнов* имеет значение true, а количество элементов находится за пределами минимального и максимального значений, хэш-таблица пересчитывается.

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap:: Сетвалуеат

Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции `CAtlMap` в объекте.

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом [CAtlMap:: жетнекстассок](#getnextassoc) или [CAtlMap:: жетстартпоситион](#getstartposition).

*value*<br/>
Значение, добавляемое в `CAtlMap` объект.

### <a name="remarks"></a>Примечания

Изменяет элемент value, хранящийся в заданной позиции в `CAtlMap` объекте.

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap:: ВИНАРГТИПЕ

Тип, используемый при передаче значения в качестве входного аргумента.

```cpp
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap:: ВАУТАРГТИПЕ

Тип, используемый при передаче значения в качестве выходного аргумента.

```cpp
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>CAtlMap:: Кпаир:: m_key

Элемент данных, в котором хранится элемент key.

```cpp
const K m_key;
```

### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип элемента Key.

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>CAtlMap:: Кпаир:: m_value

Элемент данных, в котором хранится элемент value.

```cpp
V  m_value;
```

### <a name="parameters"></a>Параметры

*3,3*<br/>
Тип элемента value.

## <a name="see-also"></a>См. также

[Образец бегущей строки](../../overview/visual-cpp-samples.md)<br/>
[Образец UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
