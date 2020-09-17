---
title: Класс Катлаутосреадмодуле
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: f4bd1071380bf3e31c69c593c5db81112fdf21de
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168310"
---
# <a name="catlautothreadmodule-class"></a>Класс Катлаутосреадмодуле

Этот класс реализует COM-сервер модели подразделения в пуле потоков.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Примечания

`CAtlAutoThreadModule`является производным от [катлаутосреадмодулет](../../atl/reference/catlautothreadmodulet-class.md) и реализует COM-сервер модели подразделения в пуле потоков. `CAtlAutoThreadModule`использует [ккомапартмент](../../atl/reference/ccomapartment-class.md) для управления апартаментом для каждого потока в модуле.

Для указания [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) в качестве фабрики класса необходимо использовать макрос [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) в определении класса объекта. Затем следует добавить один экземпляр класса, производного от `CAtlAutoThreadModuleT` , например. `CAtlAutoThreadModule` Пример:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Этот класс заменяет устаревший класс [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlAutoThreadModule`

[катлаутосреадмодулет](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Класс Катлаутосреадмодулет](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[Класс Иатлаутосреадмодуле](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
