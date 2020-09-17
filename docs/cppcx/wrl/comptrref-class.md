---
title: ComPtrRef - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
ms.openlocfilehash: f92a3e14018cf8c02dec40b664b72a0956f6220e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220539"
---
# <a name="comptrref-class"></a>ComPtrRef - класс

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип [ComPtr \<T> ](comptr-class.md) или производный от него тип, а не просто интерфейс, представленный `ComPtr` .

## <a name="remarks"></a>Примечания

Представляет ссылку на объект типа `ComPtr<T>` .

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef:: ComPtrRef](#comptrref) | Инициализирует новый экземпляр `ComPtrRef` класса из указанного указателя на другой `ComPtrRef` объект.

### <a name="public-methods"></a>Открытые методы

name                                                         | Описание
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:: GetAddressOf](#getaddressof)                     | Извлекает адрес указателя на интерфейс, представленный текущим `ComPtrRef` объектом.
[ComPtrRef:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | Удаляет текущий `ComPtrRef` объект и возвращает указатель на указатель на интерфейс, представленный `ComPtrRef` объектом.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                     | Описание
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::operator InterfaceType * *](#operator-interfacetype-star-star) | Удаляет текущий `ComPtrRef` объект и возвращает указатель на указатель на интерфейс, представленный `ComPtrRef` объектом.
[ComPtrRef::operator T *](#operator-t-star)                               | Возвращает значение элемента данных [ptr_](comptrrefbase-class.md#ptr) текущего объекта ComPtrRef.
[ComPtrRef::operator void * *](#operator-void-star-star)                   | Удаляет текущий `ComPtrRef` объект, приводит указатель к интерфейсу, представленному объектом, в `ComPtrRef` качестве указателя на указатель **`void`** , а затем возвращает указатель приведения.
[ComPtrRef::operator*](#operator-star)                                   | Получает указатель на интерфейс, представленный текущим `ComPtrRef` объектом.
[ComPtrRef::operator==](#operator-equality)                              | Определение равенства двух объектов `ComPtrRef`.
[ComPtrRef::operator!=](#operator-inequality)                            | Определяет неравенство двух объектов `ComPtrRef`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>ComPtrRef:: ComPtrRef

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Базовое значение другого `ComPtrRef` объекта.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр `ComPtrRef` класса из указанного указателя на другой `ComPtrRef` объект.

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>ComPtrRef:: GetAddressOf

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес указателя на интерфейс, представленный текущим `ComPtrRef` объектом.

### <a name="remarks"></a>Примечания

Извлекает адрес указателя на интерфейс, представленный текущим `ComPtrRef` объектом.

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>ComPtrRef::operator==

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*конкретного*<br/>
Ссылка на объект `ComPtrRef`.

*&*<br/>
Ссылка на другой `ComPtrRef` объект или указатель на анонимный тип ( **`void*`** ).

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает значение **`true`** , если объект *a* равен объекту *b*; в противном случае — значение **`false`** .

Второй и третий операторы дают значение **`true`** , если объект *a* равен **`nullptr`** ; в противном случае — значение **`false`** .

Четвертый и пятый операторы выдают **`true`** , если объект *a* равен объекту *b*; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Определение равенства двух объектов `ComPtrRef`.

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>ComPtrRef::operator!=

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*конкретного*<br/>
Ссылка на объект `ComPtrRef`.

*&*<br/>
Ссылка на другой `ComPtrRef` объект или указатель на анонимный объект ( **`void*`** ).

### <a name="return-value"></a>Возвращаемое значение

Первый оператор дает значение **`true`** , если объект *a* не равен объекту *b*; в противном случае — значение **`false`** .

Второй и третий операторы возвращают **`true`** , если объект *a* не равен **`nullptr`** ; в противном случае — **`false`** .

Четвертый и пятый операторы выдают **`true`** , если объект *a* не равен объекту *b*; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Определяет неравенство двух объектов `ComPtrRef`.

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>ComPtrRef::operator InterfaceType\*\*

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` объект и возвращает указатель на указатель на интерфейс, представленный `ComPtrRef` объектом.

## <a name="comptrrefoperator"></a><a name="operator-star"></a>ComPtrRef::operator*

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный текущим `ComPtrRef` объектом.

### <a name="remarks"></a>Примечания

Получает указатель на интерфейс, представленный текущим `ComPtrRef` объектом.

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>ComPtrRef::operator T *

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
operator T*();
```

### <a name="remarks"></a>Примечания

Возвращает значение элемента данных [ptr_](comptrrefbase-class.md#ptr) текущего `ComPtrRef` объекта.

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>ComPtrRef::operator void\*\*

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` объект, приводит указатель к интерфейсу, представленному объектом, в `ComPtrRef` качестве указателя на указатель **`void`** , а затем возвращает указатель приведения.

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtrRef:: ReleaseAndGetAddressOf

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный удаленным `ComPtrRef` объектом.

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` объект и возвращает указатель на указатель на интерфейс, представленный `ComPtrRef` объектом.
