---
title: Класс const_mem_fun1_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 93d0e7a116c7c7ba7a2ed1cb46fd88585a99120d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228327"
---
# <a name="const_mem_fun1_t-class"></a>Класс const_mem_fun1_t

Класс адаптера, который позволяет **`const`** вызывать функцию-член, которая принимает один аргумент, как объект бинарной функции при инициализации с помощью аргумента указателя. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Параметры

*member_ptr*\
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*left*\
**`const`** Объект, для которого вызывается функция-член *member_ptr* .

*right*\
Аргумент, присваиваемый *member_ptr*.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Примечания

Шаблон класса хранит копию *member_ptr*, которая должна быть указателем на функцию-член класса `Type` в закрытом объекте-члене. Он определяет свою функцию члена `operator()` как возвращающую `(left->member_ptr)(right) const` .

## <a name="example"></a>Пример

Конструктор `const_mem_fun1_t` редко используется напрямую. `mem_fn`используется для адаптации функций-членов. Пример использования адаптеров функций элементов см. в разделе [mem_fn](../standard-library/functional-functions.md#mem_fn) .
