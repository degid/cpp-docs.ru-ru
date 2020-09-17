---
title: Класс Катлфилемаппинг
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 7516349e4ec54d8cb90fa6ff23b0ded954aa043b
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168128"
---
# <a name="catlfilemapping-class"></a>Класс Катлфилемаппинг

Этот класс представляет размещенный в памяти файл, добавляя оператор приведения к методам [катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md).

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, используемых для оператора приведения.

## <a name="members"></a>Участники

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Катлфилемаппинг::operator T *](#operator_t_star)|Разрешает неявное `CAtlFileMapping` преобразование объектов `T*`в.|

## <a name="remarks"></a>Примечания

Этот класс добавляет один оператор приведения, чтобы разрешить неявное `CAtlFileMapping` преобразование `T*`объектов в. Другие члены предоставляются базовым классом [катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Требования

**Заголовок:** атлфиле.h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>Катлфилемаппинг::operator T *

Разрешает неявное `CAtlFileMapping` преобразование объектов `T*`в.

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `T*` указатель на начало размещенного в памяти файла.

### <a name="remarks"></a>Примечания

Вызывает метод [катлфилемаппингбасе:: GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и повторно интерпретирует возвращенный указатель как, `T*` где *T* — это тип, используемый в качестве параметра шаблона этого класса.

## <a name="see-also"></a>См. также

[Класс Катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
