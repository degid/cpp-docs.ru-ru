---
title: Класс value_compare (&lt;map&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: 1f872edce6f0114be7c90a8108ba248fd793a989
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447582"
---
# <a name="value_compare-class-ltmapgt"></a>Класс value_compare (&lt;map&gt;)

Предоставляет объект функции, который может сравнить элементы объекта map, сравнивая значения их ключей, чтобы определить их относительный порядок в объекте map.

## <a name="syntax"></a>Синтаксис

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>Примечания

Критерий сравнения, предоставляемый `value_compare` между `value_types` целых элементов, содержащихся в сопоставлении, вызывается путем сравнения ключей соответствующих элементов с помощью вспомогательной конструкции класса. Оператор функции-члена использует объект `comp` типа `key_compare`, хранящегося в объекте функции, предоставляемом `value_compare`, для сравнения компонентов с ключевыми порядками сортировки двух элементов.

Для наборов и множественных наборов, которые представляют собой простые контейнеры, в которых значения ключей идентичны значениям элементов, `value_compare` эквивалентно `key_compare`; для сопоставлений и объектов multimap, это не так, так как элементы типа `pair` не эквивалентны значению ключа элемента.

## <a name="example"></a>Пример

См. пример объявления и использования [ в примере для ](../standard-library/map-class.md#value_comp)value_comp`value_compare`.

## <a name="requirements"></a>Требования

**Заголовок:** \<Map >

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[Структура binary_function](../standard-library/binary-function-struct.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
