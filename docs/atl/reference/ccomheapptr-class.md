---
title: Класс CComHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 78cadfff9a278cf080393ab919f3891b201c91aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327775"
---
# <a name="ccomheapptr-class"></a>Класс CComHeapPtr

Интеллектуальный класс указателей для управления кучей указателей.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, который будет храниться на куче.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Конструктор.|

## <a name="remarks"></a>Примечания

`CComHeapPtr`вытекает `CHeapPtr`из , но использует [CComAllocator](../../atl/reference/ccomallocator-class.md) для выделения памяти с помощью COM процедур. Ознакомиться с доступными методами можно найти [cHeapPtr](../../atl/reference/cheapptr-class.md) и [CHeapPtrBase.](../../atl/reference/cheapptrbase-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr

Конструктор.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Параметры

*Pdata*<br/>
Существующий объект `CComHeapPtr`.

### <a name="remarks"></a>Примечания

Указатель кучи может быть дополнительно создан `CComHeapPtr` с помощью существующего объекта. Если это так, новый `CComHeapPtr` объект берет на себя ответственность за управление новым указателем и ресурсами.

## <a name="see-also"></a>См. также раздел

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Класс CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
