---
title: Класс CHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: a512aa974cb57072915f887f0c2a20ed1263ffa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326920"
---
# <a name="cheapptr-class"></a>Класс CHeapPtr

Интеллектуальный класс указателей для управления кучей указателей.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, который будет храниться на куче.

*Распределителя*<br/>
Класс распределения памяти для использования.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtr::Выделение](#allocate)|Вызов иметод для выделения памяти на куче для хранения объектов.|
|[CHeapPtr::Перераспределить](#reallocate)|Вызовите этот метод, чтобы перераспределить память на куче.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtr::оператор](#operator_eq)|Оператор назначения.|

## <a name="remarks"></a>Примечания

`CHeapPtr`происходит от [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) и по умолчанию использует режимы CRT (в [CCRTAllocator)](../../atl/reference/ccrtallocator-class.md)для выделения и свободной памяти. Класс [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) может быть использован для построения списка указателей кучи. Смотрите также [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), который использует процедуры распределения памяти COM.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="cheapptrallocate"></a><a name="allocate"></a>CHeapPtr::Выделение

Вызов иметод для выделения памяти на куче для хранения объектов.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Параметры

*nЭлементы*<br/>
Количество элементов, используемых для расчета количества памяти для выделения. Значение по умолчанию — 1.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если память была успешно распределена, ложно йода на сбой.

### <a name="remarks"></a>Примечания

Процедуры разлестьиспользуются для резервирования достаточного количества памяти на куче для хранения объектов *nElement* типа, определенного в конструкторе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a>CHeapPtr::CHeapPtr

Конструктор.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Существующий указатель кучи или `CHeapPtr`.

### <a name="remarks"></a>Примечания

Указатель кучи может быть дополнительно создан с помощью `CHeapPtr` существующего указателя или объекта. Если это так, новый `CHeapPtr` объект берет на себя ответственность за управление новым указателем и ресурсами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a>CHeapPtr::оператор

Оператор присвоения.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Существующий объект `CHeapPtr`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CHeapPtr`обновленную .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a>CHeapPtr::Перераспределить

Вызовите этот метод, чтобы перераспределить память на куче.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Параметры

*nЭлементы*<br/>
Новое количество элементов, используемых для расчета количества памяти для выделения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если память была успешно распределена, ложно йода на сбой.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
