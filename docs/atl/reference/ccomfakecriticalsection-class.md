---
title: Класс Ккомфакекритикалсектион
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 5ada0fbed705af34391709653dbd3638fed32bf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226585"
---
# <a name="ccomfakecriticalsection-class"></a>Класс Ккомфакекритикалсектион

Этот класс предоставляет те же методы, что и [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критическую секцию.

## <a name="syntax"></a>Синтаксис

```
class CComFakeCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккомфакекритикалсектион:: init](#init)|Не выполняет никаких действий, так как нет критического раздела.|
|[Ккомфакекритикалсектион:: Lock](#lock)|Не выполняет никаких действий, так как нет критического раздела.|
|[Ккомфакекритикалсектион:: Term](#term)|Не выполняет никаких действий, так как нет критического раздела.|
|[Ккомфакекритикалсектион:: Unlock](#unlock)|Не выполняет никаких действий, так как нет критического раздела.|

## <a name="remarks"></a>Примечания

`CComFakeCriticalSection`отражает методы, найденные в [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md). Однако не `CComFakeCriticalSection` предоставляет критическую секцию, поэтому его методы не выполняют никаких действий.

Обычно используется `CComFakeCriticalSection` **`typedef`** имя, либо `AutoCriticalSection` `CriticalSection` . При использовании [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) или [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md)оба эти **`typedef`** имени ссылаются `CComFakeCriticalSection` . При использовании [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md)они ссылаются на [ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection` соответственно.

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре.h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>Ккомфакекритикалсектион:: init

Не выполняет никаких действий, так как нет критического раздела.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>Ккомфакекритикалсектион:: Lock

Не выполняет никаких действий, так как нет критического раздела.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>Ккомфакекритикалсектион:: Term

Не выполняет никаких действий, так как нет критического раздела.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>Ккомфакекритикалсектион:: Unlock

Не выполняет никаких действий, так как нет критического раздела.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="see-also"></a>См. также статью

[Общие сведения о классах](../../atl/atl-class-overview.md)
