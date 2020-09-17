---
title: Класс Ккомаутокритикалсектион
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 26b43fa4adc40993a44318c67be990c781b5cdf6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226637"
---
# <a name="ccomautocriticalsection-class"></a>Класс Ккомаутокритикалсектион

`CComAutoCriticalSection`предоставляет методы для получения и освобождения владельца объекта критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ккомаутокритикалсектион:: Ккомаутокритикалсектион](#ccomautocriticalsection)|Конструктор.|
|[Ккомаутокритикалсектион:: ~ Ккомаутокритикалсектион](#dtor)|Деструктор|

## <a name="remarks"></a>Примечания

`CComAutoCriticalSection`аналогичен классу [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md), за исключением `CComAutoCriticalSection` автоматической инициализации объекта критической секции в конструкторе.

Обычно используется `CComAutoCriticalSection` **`typedef`** имя [аутокритикалсектион](ccommultithreadmodel-class.md#autocriticalsection). Это имя указывает, `CComAutoCriticalSection` когда используется [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) .

`Init`Методы и `Term` из [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) недоступны при использовании этого класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре.h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>Ккомаутокритикалсектион:: Ккомаутокритикалсектион

Конструктор.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Примечания

Вызывает функцию Win32 [инитиализекритикалсектион](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), которая инициализирует объект критической секции.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>Ккомаутокритикалсектион:: ~ Ккомаутокритикалсектион

Деструктор

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [делетекритикалсектион](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection), который освобождает все системные ресурсы, используемые объектом критического раздела.

## <a name="see-also"></a>См. также статью

[Класс Ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс Ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)
