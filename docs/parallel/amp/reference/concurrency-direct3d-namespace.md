---
title: Пространство имен Concurrency::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: e1374acbd7061afaba372100cf6e69d9d717da8a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127037"
---
# <a name="concurrencydirect3d-namespace"></a>Пространство имен concurrency::direct3d

Пространство имен `direct3d` предоставляет функции, поддерживающие возможность взаимодействия с D3D. Она позволяет использовать ресурсы D3D для вычислений в коде AMP. Он также позволяет использовать ресурсы, созданные в AMP в коде D3D, без создания избыточных промежуточных копий. Вы можете постепенно ускорить вычислительные области приложений DirectX с помощью C++ amp и использовать API D3D на основе данных, полученных из вычислений amp.

## <a name="syntax"></a>Синтаксис

```cpp
namespace direct3d;
```

## <a name="members"></a>Члены

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс scoped_d3d_access_lock](scoped-d3d-access-lock-class.md)|Оболочка RAII для блокировки доступа D3D на объекте `accelerator_view`.|

### <a name="structures"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[Структура adopt_d3d_access_lock_t](adopt-d3d-access-lock-t-structure.md)|Тип тега, указывающий, что блокировка доступа D3D должна быть принята, а не получена.|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Возвращает абсолютное значение аргумента|
|[фиксаци](concurrency-direct3d-namespace-functions-amp.md#clamp)|Перегружен. Фиксации _X к указанному _Minу и диапазону _Max|
|[каунтбитс](concurrency-direct3d-namespace-functions-amp.md#countbits)|Подсчитывает количество битов набора в _X|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Создает [класс accelerator_view](accelerator-view-class.md) из указателя на интерфейс устройства Direct3D|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Получает блокировку accelerator_view, чтобы безопасно выполнять операции D3D с ресурсами, совместно используемыми с accelerator_view|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Попытка получить блокировку доступа D3D на accelerator_view без блокировки.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Освобождение блокировки доступа D3D на заданном accelerator_view.|
|[фирстбисигх](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Возвращает расположение первого набора бит в _X, начиная с самого высокого бита и заканчивая работой вниз.|
|[фирстбитлов](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Возвращает расположение первого набора бит в _X, начиная с наименьшего бита порядка и работая над|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Получение интерфейса буфера D3D, лежащего в основе массива.|
|[имакс](concurrency-direct3d-namespace-functions-amp.md#imax)|Сравнивает два значения, возвращая большее значение.|
|[имин](concurrency-direct3d-namespace-functions-amp.md#imin)|Сравнивает два значения, возвращая меньшее значение.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Возвращает логический флаг, указывающий, отключено ли время ожидания для указанного accelerator_view.|
|[отслеживания](concurrency-direct3d-namespace-functions-amp.md#mad)|Перегружен. Выполняет арифметическую операцию умножения или добавления для трех аргументов: _X \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Создание массива из указателя интерфейса буфера D3D.|
|[учитываем](concurrency-direct3d-namespace-functions-amp.md#noise)|Создает случайное значение с помощью алгоритма шума Perl|
|[радианах](concurrency-direct3d-namespace-functions-amp.md#radians)|Преобразует _X из градусов в радианы|
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Вычисляет быстрое и приближенное обратное значение аргумента|
|[реверсебитс](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Изменяет порядок битов в _X|
|[насытить](concurrency-direct3d-namespace-functions-amp.md#saturate)|Фиксации _X в диапазоне от 0 до 1|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Перегружен. Возвращает знак аргумента|
|[смусстеп](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Возвращает гладкую Хермите интерполяцию между 0 и 1, если _X находится в диапазоне [_Min, _Max].|
|[первом](concurrency-direct3d-namespace-functions-amp.md#step)|Сравнивает два значения, возвращая 0 или 1 в зависимости от того, какое значение больше|
|[Компания](concurrency-direct3d-namespace-functions-amp.md#umax)|Сравнивает два значения без знака, возвращая большее значение.|
|[умин](concurrency-direct3d-namespace-functions-amp.md#umin)|Сравнивает два значения без знака, возвращая меньшее значение.|

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
