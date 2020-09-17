---
title: Класс invoke_result
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: e3e1a28310660ad1fbdae4dd58973de378ddf364
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233136"
---
# <a name="invoke_result-class"></a>Класс invoke_result

Определяет тип возвращаемого значения вызываемого типа, который принимает указанные типы аргументов во время компиляции. Добавлено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Параметры

*Предназначен*\
Вызываемый тип для запроса.

*Args*\
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Используйте этот шаблон для определения типа результата *вызываемого*(*args*...) во время компиляции, где *вызываемый* объект и все типы в аргументах *args* являются полным типом, массивом неизвестной привязки или, возможно, с указанием ОПС **`void`** . `type`Член шаблона класса называет тип возвращаемого значения, *вызываемого* при вызове, используя *Args*аргументы arguments.... `type`Элемент определен только в том случае, если *вызываемый* метод можно вызвать при помощи аргументов *args*... в невычисленном контексте. В противном случае шаблон класса не имеет члена `type` , что позволяет SFINAE тесты для определенного набора типов аргументов во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также статью

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
