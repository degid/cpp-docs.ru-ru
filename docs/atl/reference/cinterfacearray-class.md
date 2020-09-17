---
title: Класс CInterfaceArray
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: e6efe31989b06f0977ecff156a8f64053dc64ad1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326801"
---
# <a name="cinterfacearray-class"></a>Класс CInterfaceArray

Этот класс предоставляет полезные методы при построении массива указателей интерфейса COM.

## <a name="syntax"></a>Синтаксис

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Параметры

*Я*<br/>
Интерфейс COM с указанием типа указателя для хранения.

*пиид*<br/>
Указатель на IID *I*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Конструктор для массива интерфейса.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и производные методы для создания массива указателей интерфейса COM. Используйте [CInterfaceList,](../../atl/reference/cinterfacelist-class.md) когда требуется список.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray

Конструктор.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует интеллектуальный массив указателей.

## <a name="see-also"></a>См. также раздел

[Класс CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Класс CCom-IPtr](../../atl/reference/ccomqiptr-class.md)<br/>
[Класс CCom-IPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
