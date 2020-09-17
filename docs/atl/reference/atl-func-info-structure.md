---
title: Структура _ATL_FUNC_INFO
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: b1c740cf1a1ed344dbceb028bd1f39a87fc09363
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168596"
---
# <a name="_atl_func_info-structure"></a>Структура _ATL_FUNC_INFO

Содержит сведения о типе, используемые для описания метода или свойства в DISP-интерфейсе.

## <a name="syntax"></a>Синтаксис

```cpp
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Участники

`cc`<br/>
Соглашение о вызовах. При использовании этой структуры с классом [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) этот элемент должен быть CC_STDCALL. `CC_CDECL`— единственный вариант, поддерживаемый в Windows CE для `CALLCONV` поля `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается, поэтому его поведение не определено.

`vtReturn`<br/>
Тип варианта возвращаемого значения функции.

`nParams`<br/>
Число параметров функции.

`pVarTypes`<br/>
Массив вариативных типов параметров функции.

## <a name="remarks"></a>Примечания

Внутри библиотека ATL использует эту структуру для хранения информации, полученной из библиотеки типов. Вам может потребоваться манипулировать этой структурой напрямую, если указать сведения о типе для обработчика событий, используемого с классом [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) и [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) макросе.

## <a name="example"></a>Пример

При наличии метода disp-интерфейса, определенного в IDL:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

необходимо определить `_ATL_FUNC_INFO` структуру:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Требования

Заголовок: atlcom.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)<br/>
[Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
