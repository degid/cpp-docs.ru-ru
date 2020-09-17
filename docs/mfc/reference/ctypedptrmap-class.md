---
title: Класс CTypedPtrMap
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 410f0101fd0f8cda271fe0f2353b06b9e8d773b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754361"
---
# <a name="ctypedptrmap-class"></a>Класс CTypedPtrMap

Предоставляет типобезопасную "программу-оболочку" для объектов классов карты указателей `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`и `CMapStringToPtr`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс типа набранной указатель карты; должен быть класс карты `CMapPtrToPtr`указателя (, `CMapPtrToWord`, `CMapWordToPtr`или `CMapStringToPtr`).

*Ключ*<br/>
Класс объекта, используемого в качестве ключа к карте.

*Значение*<br/>
Класс объекта, хранящегося на карте.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|
|[CTypedPtrMap::Поиск](#lookup)|Возвращает `KEY` на основе `VALUE`.|
|[CTypedPtrMap::RemoveKey](#removekey)|Удаляет элемент, указанный ключом.|
|[CTypedPtrMap::SetAt](#setat)|Вставляет элемент на карту; заменяет существующий элемент при обнаружении соответствующего ключа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrMap::оператор \[\]](#operator_at)|Вставляет элемент в карту.|

## <a name="remarks"></a>Примечания

При использовании, `CTypedPtrMap`средство проверки типа СЗ помогает устранить ошибки, вызванные несовместимыми типами указателей.

Поскольку `CTypedPtrMap` все функции являются внеочередными, использование этого шаблона не оказывает существенного влияния на размер или скорость кода.

Для получения дополнительной `CTypedPtrMap`информации об [Template-Based Classes](../../mfc/template-based-classes.md)использовании , [см.](../../mfc/collections.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc

Извлекает элемент карты `rNextPosition`на, `rNextPosition` затем обновляется для обозначения следующего элемента на карте.

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Упоняет ссылку на значение POSITION, возвращенное предыдущим `GetNextAssoc` `BASE_CLASS` **или:GetStartPosition.**

*Ключ*<br/>
Параметры шаблона, определяющие тип ключей карты.

*rKey*<br/>
Определяет возвращенный ключ извлеченного элемента.

*Значение*<br/>
Параметры шаблона, определяющие тип значений карты.

*Rvalue*<br/>
Определяет возвращенное значение извлеченного элемента.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для итерации всех элементов на карте. Обратите внимание, что последовательность положения не обязательно совпадает с последовательностью значения ключа.

Если извлеченный элемент является последним на карте, то `rNextPosition` новое значение устанавливается на NULL.

Эта влиневая функция вызывает `BASE_CLASS` **::GetNextAssoc**.

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::Поиск

`Lookup`использует алгоритм хэширования, чтобы быстро найти элемент карты с ключом, который точно соответствует.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Параметры шаблона, определяющие базовый класс класса этой карты.

*key*<br/>
Ключ элемента, который будет смотреть вверх.

*Значение*<br/>
Параметры шаблона, определяющие тип значений, хранящихся на этой карте.

*Rvalue*<br/>
Определяет возвращенное значение извлеченного элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта влиневая функция вызывает `BASE_CLASS` **::Lookup**.

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrMap::оператор

Этот оператор может быть использован только на левой стороне оператора назначения (l-значение).

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Параметры шаблона, определяющие тип значений, хранящихся на этой карте.

*BASE_CLASS*<br/>
Параметры шаблона, определяющие базовый класс класса этой карты.

*key*<br/>
Ключ элемента, который будет рассмотрен или создан на карте.

### <a name="remarks"></a>Примечания

Если нет элемента карты с указанным ключом, создается новый элемент. Нет "правой стороны" (r-value) эквивалентного этому оператору, поскольку существует вероятность того, что ключ может не быть найден на карте. Используйте `Lookup` функцию члена для поиска элементов.

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::RemoveKey

Эта функция `BASE_CLASS`участника **вызывает::RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Параметры шаблона, определяющие тип ключей карты.

*key*<br/>
Ключ для удаления элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись была найдена и успешно удалена; в противном случае 0.

### <a name="remarks"></a>Примечания

Для более подробных замечаний, см [Cmapstringtoob::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

## <a name="ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt

Эта функция `BASE_CLASS`участника **вызывает ::SetAt**.

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Параметры шаблона, определяющие тип ключей карты.

*key*<br/>
Определяет ключевую стоимость нового value.

*newValue*<br/>
Определяет указатель объекта, который является значением нового элемента.

### <a name="remarks"></a>Примечания

Для более подробных замечаний, см [Cmapstringtoob::Setat](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Класс CmapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)
