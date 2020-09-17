---
title: Структура _ATL_MODULE70
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: 8d39cdd281e09cdfe09546627aa630a11d12464e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168570"
---
# <a name="_atl_module70-structure"></a>Структура _ATL_MODULE70

Содержит данные, используемые каждым модулем ATL.

## <a name="syntax"></a>Синтаксис

```cpp
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Участники

`cbSize`<br/>
Размер структуры, используемый для управления версиями.

`m_nLockCnt`<br/>
Число ссылок, чтобы определить, как долго модуль должен оставаться активным.

`m_pTermFuncs`<br/>
Отслеживает функции, которые были зарегистрированы для вызова при завершении работы ATL.

`m_csStaticDataInitAndTypeInfo`<br/>
Используется для координации доступа к внутренним данным в многопоточных ситуациях.

## <a name="remarks"></a>Примечания

[_ATL_MODULE](atl-typedefs.md#_atl_module) определяется как typedef для `_ATL_MODULE70`.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
