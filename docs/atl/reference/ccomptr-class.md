---
title: Класс CComPtr
description: Справочное руководство по библиотеке активных шаблонов (ATL) класса CComPtr.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 855466225db2672755658dcbbc9a266d09e0e7be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327527"
---
# <a name="ccomptr-class"></a>Класс CComPtr

Интеллектуальный класс указателей для управления указатели интерфейса COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>Параметры

*T*<br/>
Интерфейс COM с указанием типа указателя для хранения.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComPtr::CComPtr](#ccomptr)|Конструктор.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComPtr::оператор](#operator_eq)|Назначает указатель указателю на указатель участника.|

## <a name="remarks"></a>Примечания

ATL `CComPtr` использует и [CCom-IPtr](../../atl/reference/ccomqiptr-class.md) для управления указателями интерфейсов COM. Оба являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md), и оба делают автоматический подсчет ссылок.

Классы `CComPtr` [CCom-IPtr](../../atl/reference/ccomqiptr-class.md) могут помочь устранить утечки памяти, выполняя автоматический подсчет ссылок.  Следующие функции делают одни и те же логические операции. Однако вторая версия может быть менее подверженной ошибкам, `CComPtr` поскольку она использует класс:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

В сборках Debug ссылка atlsd.lib для отслеживания кода.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Ccomptrbase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomptrccomptr"></a><a name="ccomptr"></a>CComPtr::CComPtr

Конструктор.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Параметры

*Lp*<br/>
Используется для инициализации указателя интерфейса.

*T*<br/>
Интерфейс COM.

### <a name="remarks"></a>Примечания

Конструкторы, которые принимают аргумент `AddRef` вызова на *lp,* если это не нулевой указатель. Объект, не являемый ненулевой, получает `Release` вызов на уничтожение объекта CComPtr или если новый объект приписан объекту CComPtr.

## <a name="ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::оператор

Оператор присвоения.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CComPtr` обновленный объект

### <a name="remarks"></a>Примечания

Эта операция addRefs новый объект и выпускает существующий объект, если один существует.

## <a name="see-also"></a>См. также раздел

[CComPtr::CComPtr](#ccomptr)<br/>
[CCom'IPtr:CComqIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
