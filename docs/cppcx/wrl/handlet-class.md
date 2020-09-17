---
title: HandleT - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: 661d3cb92b20fc929a9bae3cad7bb55740e5e096
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213012"
---
# <a name="handlet-class"></a>HandleT - класс

Представляет дескриптор объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Параметры

*Метод HandleTraits*<br/>
Экземпляр структуры [метод HandleTraits](handletraits-structure.md) , определяющей общие характеристики маркера.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя     | Описание
-------- | -----------------------------
`Traits` | Синоним для `HandleTraits`.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | --------------------------------------------------
[Handleing:: Handle](#handlet)        | Инициализирует новый экземпляр класса `HandleT`.
[Handleing:: ~ Handle](#tilde-handlet) | Выполняет деинициализацию экземпляра `HandleT` класса.

### <a name="public-methods"></a>Открытые методы

name                         | Описание
---------------------------- | ----------------------------------------------------------------------
[Handle:: Attach](#attach)   | Связывает указанный маркер с текущим `HandleT` объектом.
[Handle:: Close](#close)     | Закрывает текущий объект `HandleT`.
[Handle::D етач](#detach)   | Отменяет связь текущего `HandleT` объекта с его базовым маркером.
[Handle:: Get](#get)         | Возвращает значение базового маркера.
[Handle:: IsValid](#isvalid) | Указывает, представляет ли текущий `HandleT` объект маркер.

### <a name="protected-methods"></a>Защищенные методы

Имя                                     | Описание
---------------------------------------- | ------------------------------------
[Handle:: InternalClose](#internalclose) | Закрывает текущий объект `HandleT`.

### <a name="public-operators"></a>Открытые операторы

Имя                                   | Описание
-------------------------------------- | ----------------------------------------------------------------------------------
[Handle::operator=](#operator-assign) | Перемещает значение указанного `HandleT` объекта в текущий `HandleT` объект.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Описание
--------------------------- | ----------------------------------------------------------------
[Handle:: handle_](#handle) | Содержит маркер, представленный `HandleT` объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="handlethandlet"></a><a name="tilde-handlet"></a>Handleing:: ~ Handle

Выполняет деинициализацию экземпляра `HandleT` класса.

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a>Handle:: Attach

Связывает указанный маркер с текущим `HandleT` объектом.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор.

## <a name="handletclose"></a><a name="close"></a>Handle:: Close

Закрывает текущий объект `HandleT`.

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Маркер, лежащий в данный момент, `HandleT` закрыт, а `HandleT` для задается недопустимое состояние.

Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.

## <a name="handletdetach"></a><a name="detach"></a>Handle::D етач

Отменяет связь текущего `HandleT` объекта с его базовым маркером.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Базовый маркер.

### <a name="remarks"></a>Примечания

По завершении этой операции текущим `HandleT` задается недопустимое состояние.

## <a name="handletget"></a><a name="get"></a>Handle:: Get

Возвращает значение базового маркера.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор.

## <a name="handlethandle_"></a><a name="handle"></a>Handle:: handle_

Содержит маркер, представленный `HandleT` объектом.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a>Handleing:: Handle

Инициализирует новый экземпляр класса `HandleT`.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует `HandleT` объект, который не является допустимым маркером объекта. Второй конструктор создает новый `HandleT` объект на основе параметра *h*.

## <a name="handletinternalclose"></a><a name="internalclose"></a>Handle:: InternalClose

Закрывает текущий объект `HandleT`.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`HandleT`значение, если текущий закрытый успешно завершен; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

`InternalClose()`имеет **`protected`** .

## <a name="handletisvalid"></a><a name="isvalid"></a>Handle:: IsValid

Указывает, представляет ли текущий `HandleT` объект маркер.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект `HandleT` представляет обработчик; в противном случае — **`false`** .

## <a name="handletoperator"></a><a name="operator-assign"></a>Handle::operator=

Перемещает значение указанного `HandleT` объекта в текущий `HandleT` объект.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на Handle.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий `HandleT` объект.

### <a name="remarks"></a>Примечания

Эта операция делает недействительным `HandleT` объект, указанный параметром *h*.
