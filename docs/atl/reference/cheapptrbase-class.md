---
title: Класс CHeapPtrBase
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: e247b4f488411ffdcde5d1d9016436c9c36fe793
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747680"
---
# <a name="cheapptrbase-class"></a>Класс CHeapPtrBase

Этот класс составляет основу для нескольких умных классов указателей кучи.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, который будет храниться на куче.

*Распределителя*<br/>
Класс распределения памяти для использования. По умолчанию режимы CRT используются для выделения и свободной памяти.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase:: »CHeapPtrBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Вызовите этот метод для выделения памяти.|
|[CHeapPtrBase::Attach](#attach)|Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.|
|[CHeapPtrBase::Detach](#detach)|Вызовите этот метод, чтобы освободить право собственности на указатель.|
|[CHeapPtrBase::Бесплатно](#free)|Вызовите этот метод, чтобы `CHeapPtrBase`удалить объект, на который указывает .|
|[CHeapPtrBase:ReallocateBytes](#reallocatebytes)|Вызовите этот метод для перераспределения памяти.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase:Оператор ТЗ](#operator_t_star)|Оператор актерского состава.|
|[CHeapPtrBase::оператор &](#operator_amp)|Оператора &.|
|[CHeapPtrBase:Оператор ->](#operator_ptr)|Оператор указателя на участника.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|Переменная данных указателя.|

## <a name="remarks"></a>Примечания

Этот класс составляет основу для нескольких умных классов указателей кучи. Полученные классы, например, [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CComHeapPtr,](../../atl/reference/ccomheapptr-class.md)добавляют свои собственные конструкторы и операторов. Ознакомьтесь с этими классами для примеров реализации.

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes

Вызовите этот метод для выделения памяти.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Количество байтов памяти для выделения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если память успешно выделена, ложнов в противном случае.

### <a name="remarks"></a>Примечания

В отладочных сборках произойдет сбой утверждения, если переменная [CHeapPtrBase::m_pData](#m_pdata) в настоящее время указывает на существующее значение; то есть, он не равен NULL.

## <a name="cheapptrbaseattach"></a><a name="attach"></a>CHeapPtrBase::Attach

Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Параметры

*Pdata*<br/>
Объект `CHeapPtrBase` будет владеть этим указателем.

### <a name="remarks"></a>Примечания

Когда `CHeapPtrBase` объект становится владельцем указателя, он автоматически удаляет указатель и любые выделенные данные, когда он выходит за рамки.

В отладочных сборках произойдет сбой утверждения, если переменная [CHeapPtrBase::m_pData](#m_pdata) в настоящее время указывает на существующее значение; то есть, он не равен NULL.

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a>CHeapPtrBase:: »CHeapPtrBase

Деструктор

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="cheapptrbasedetach"></a><a name="detach"></a>CHeapPtrBase::Detach

Вызовите этот метод, чтобы освободить право собственности на указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Выпускает право собственности на указатель, устанавливает [CHeapPtrBase::m_pData](#m_pdata) переменной члена null и возвращает копию указателя.

## <a name="cheapptrbasefree"></a><a name="free"></a>CHeapPtrBase::Бесплатно

Вызовите этот метод, чтобы `CHeapPtrBase`удалить объект, на который указывает .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Примечания

Объект, на который `CHeapPtrBase` указывает сяроб, освобождается, и переменная [CHeapPtrBase::m_pData](#m_pdata) переменная члена установлена null.

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a>CHeapPtrBase::m_pData

Переменная данных указателя.

```
T* m_pData;
```

### <a name="remarks"></a>Примечания

Эта переменная члена содержит информацию указателя.

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a>CHeapPtrBase::оператор&amp;

Оператора &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес объекта, на который `CHeapPtrBase` указывает объект.

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a>CHeapPtrBase:оператор -&gt;

Оператор указателя на участника.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение переменной [CHeapPtrBase::m_pData](#m_pdata) переменной.

### <a name="remarks"></a>Примечания

Используйте этот оператор для вызова метода `CHeapPtrBase` в классе, на который указывает объект. В сборках отладки произойдет `CHeapPtrBase` сбой утверждения, если точки NULL.

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a>CHeapPtrBase:Оператор ТЗ

Оператор актерского состава.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает [CHeapPtrBase::m_pData](#m_pdata).

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a>CHeapPtrBase:ReallocateBytes

Вызовите этот метод для перераспределения памяти.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Новый объем памяти, чтобы выделить, в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если память успешно выделена, ложнов в противном случае.

## <a name="see-also"></a>См. также раздел

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
