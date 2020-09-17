---
title: Класс scoped_d3d_access_lock
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: b5a2d9dab9cba7b19fa0d0b1627f653f2c7fdc57
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126400"
---
# <a name="scoped_d3d_access_lock-class"></a>Класс scoped_d3d_access_lock

Оболочка RAII для блокировки доступа D3D на объекте accelerator_view.

## <a name="syntax"></a>Синтаксис

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор scoped_d3d_access_lock](#ctor)|Перегружен. Формирует объект `scoped_d3d_access_lock`. Блокировка освобождается, когда объект выходит из области действия.|
|[Деструктор ~ scoped_d3d_access_lock](#dtor)|Освобождает блокировку доступа D3D для связанного объекта `accelerator_view`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Получает владение блокировкой от другого `scoped_d3d_access_lock`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scoped_d3d_access_lock`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт.h

**Пространство имен:** concurrency::direct3d

## <a name="ctor"></a>scoped_d3d_access_lock

Формирует объект `scoped_d3d_access_lock`. Блокировка освобождается, когда объект выходит из области действия.

```cpp
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
`accelerator_view` для принятия блокировки.

*_T*<br/>
Объект `adopt_d3d_access_lock_t`.

*_Other*<br/>
Объект `scoped_d3d_access_lock`, из которого будет перемещена существующая блокировка.

## <a name="construction"></a>Создание экземпляра

[1] конструктор получает блокировку на доступ D3D для заданного объекта [accelerator_view](accelerator-view-class.md) . Создание блоков до тех пор, пока блокировка не будет получена.

[2] конструктор применяет блокировку к D3D из заданного объекта [accelerator_view](accelerator-view-class.md) .

[3] конструктор перемещения принимает существующую блокировку доступа D3D из другого объекта `scoped_d3d_access_lock`. Конструкция не блокируется.

## <a name="dtor"></a>~ scoped_d3d_access_lock

Освобождает блокировку доступа D3D для связанного объекта `accelerator_view`.

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a>Оператор =

Принимает владение блокировкой доступа к D3D из другого объекта `scoped_d3d_access_lock`, освобождая предыдущую блокировку.

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Accelerator_view, из которого будет перемещена блокировка доступа D3D.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `scoped_accelerator_view_lock`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency::direct3d](concurrency-direct3d-namespace.md)
