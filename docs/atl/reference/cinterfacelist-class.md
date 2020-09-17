---
title: Класс CInterfaceList
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 0a7fd781c63e4ea084cf078e49fc9efb9cfa2d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326779"
---
# <a name="cinterfacelist-class"></a>Класс CInterfaceList

Этот класс предоставляет полезные методы при построении списка указателей интерфейса COM.

## <a name="syntax"></a>Синтаксис

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Конструктор для списка интерфейсов.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и выведенные методы для создания списка указателей интерфейса COM. Используйте [CInterfaceArray,](../../atl/reference/cinterfacearray-class.md) когда требуется массив.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Catllist](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a>CInterfaceList::CInterfaceList

Конструктор для списка интерфейсов.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока, с значением по умолчанию 10.

### <a name="remarks"></a>Примечания

Размер блока — это мера объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов.

## <a name="see-also"></a>См. также раздел

[Класс CAtlList](../../atl/reference/catllist-class.md)<br/>
[Класс CCom-IPtr](../../atl/reference/ccomqiptr-class.md)<br/>
[Класс CCom-IPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
