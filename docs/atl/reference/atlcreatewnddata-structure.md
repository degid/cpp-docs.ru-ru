---
title: Структура _AtlCreateWndData
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: a38ddb7e3575e883c11b14a9b01004bb54fcd4a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230017"
---
# <a name="_atlcreatewnddata-structure"></a>Структура _AtlCreateWndData

Эта структура содержит данные экземпляра класса в коде окна в ATL.

## <a name="syntax"></a>Синтаксис

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Участники

`m_pThis`<br/>
**`this`** Указатель, используемый для получения доступа к экземпляру класса в процедурах окна.

`m_dwThreadID`<br/>
Идентификатор потока текущего экземпляра класса.

`m_pNext`<br/>
Указатель на следующий `_AtlCreateWndData` объект.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также раздел

[Классы и структуры](../../atl/reference/atl-classes.md)
