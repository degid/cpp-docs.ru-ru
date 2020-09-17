---
title: Класс CCom-IPtr
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: 2b1d8b92fbc5e95a5061956bafc4922d249a6f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327420"
---
# <a name="ccomqiptr-class"></a>Класс CCom-IPtr

Интеллектуальный класс указателей для управления указатели интерфейса COM.

## <a name="syntax"></a>Синтаксис

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Интерфейс COM с указанием типа указателя для хранения.

*пиид*<br/>
Указатель на IID *T*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCom'IPtr:CComqIPtr](#ccomqiptr)|Конструктор.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CCom-IPtr::оператор](#operator_eq)|Назначает указатель указателю на указатель участника.|

## <a name="remarks"></a>Примечания

ATL `CComQIPtr` использует и [CComPtr](../../atl/reference/ccomptr-class.md) для управления com указатели интерфейса, оба из которых вытекают из [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Оба класса выполняют автоматический `AddRef` подсчет `Release`ссылок через звонки и . Перегруженные операторы обрабатывают операции указателей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Ccomptrbase](../../atl/reference/ccomptrbase-class.md)

[Ccomptr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a>CCom'IPtr:CComqIPtr

Конструктор.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Параметры

*Lp*<br/>
Используется для инициализации указателя интерфейса.

*T*<br/>
Интерфейс COM.

*пиид*<br/>
Указатель на IID *T*.

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a>CCom-IPtr::оператор

Оператор назначения.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Параметры

*Lp*<br/>
Используется для инициализации указателя интерфейса.

*T*<br/>
Интерфейс COM.

*пиид*<br/>
Указатель на IID *T*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CComQIPtr` обновленный объект.

## <a name="see-also"></a>См. также раздел

[CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CCom'IPtr:CComqIPtr](#ccomqiptr)<br/>
[Класс CComPtrBase](../../atl/reference/ccomptrbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CCom-IPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)
