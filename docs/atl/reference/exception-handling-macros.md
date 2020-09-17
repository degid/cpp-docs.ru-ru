---
title: Макросы обработки исключений
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 7fcd8221ba5f121749cf366a93cc8a6d8d00ed7c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833443"
---
# <a name="exception-handling-macros"></a>Макросы обработки исключений

Эти макросы обеспечивают поддержку обработки исключений.

|Имя|Описание|
|-|-|
|[_ATLCATCH](#_atlcatch)|Инструкции для управления ошибками, происходящими в связанном `_ATLTRY` .|
|[_ATLCATCHALL](#_atlcatchall)|Инструкции для управления ошибками, происходящими в связанном `_ATLTRY` .|
|[_ATLTRY](#_atltry)|Помечает раздел защищенного кода, в котором может возникнуть ошибка.|

## <a name="requirements"></a>Требования

**Заголовок:** атлдеф.h

## <a name="_atlcatch"></a><a name="_atlcatch"></a> _ATLCATCH

Инструкции для управления ошибками, происходящими в связанном `_ATLTRY` .

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Параметры

*e*<br/>
Исключение для перехвата.

### <a name="remarks"></a>Примечания

Используется в сочетании со свойством `_ATLTRY`. Разрешается в C++ [catch (катлексцептион e)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки определенного типа исключений c++.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

Инструкции для управления ошибками, происходящими в связанном `_ATLTRY` .

```
_ATLCATCHALL
```

### <a name="remarks"></a>Примечания

Используется в сочетании со свойством `_ATLTRY`. Разрешается в C++ [catch (...)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки всех типов исключений c++.

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

Помечает раздел защищенного кода, в котором может возникнуть ошибка.

```
_ATLTRY
```

### <a name="remarks"></a>Примечания

Используется в сочетании с [_ATLCATCH](#_atlcatch) или [_ATLCATCHALL](#_atlcatchall). Разрешается в символ C++ [try](../../cpp/try-throw-and-catch-statements-cpp.md).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
