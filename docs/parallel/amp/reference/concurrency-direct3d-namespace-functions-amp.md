---
title: Функции пространства имен Concurrency::direct3d (AMP)
ms.date: 08/31/2018
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::get_device
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
ms.openlocfilehash: bf98249001c2b8227581fbbbcceeebd085e5d820
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831116"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Функции пространства имен concurrency::direct3d (AMP)

:::row:::
   :::column span="":::
      [просто](#abs)\
      [фиксаци](#clamp)\
      [каунтбитс](#countbits)\
      [create_accelerator_view](#create_accelerator_view)\
      [d3d_access_lock](#d3d_access_lock)\
      [d3d_access_try_lock](#d3d_access_try_lock)\
      [d3d_access_unlock](#d3d_access_unlock)
   :::column-end:::
   :::column span="":::
      [фирстбисигх](#firstbithigh)\
      [фирстбитлов](#firstbitlow)\
      [get_buffer](#get_buffer)\
      [get_device](#get_device)\
      [имакс](#imax)\
      [имин](#imin)\
      [is_timeout_disabled](#is_timeout_disabled)
   :::column-end:::
   :::column span="":::
      [отслеживания](#mad)\
      [make_array](#make_array)\
      [учитываем](#noise)\
      [радианах](#radians)\
      [rcp](#rcp)\
      [реверсебитс](#reversebits)
   :::column-end:::
   :::column span="":::
      [насытить](#saturate)\
      [писать](#sign)\
      [смусстеп](#smoothstep)\
      [первом](#step)\
      [Компания](#umax)\
      [умин](#umin)
   :::column-end:::
:::row-end:::

## <a name="requirements"></a>Требования

**Заголовок:** **пространство имен** amp.h: Concurrency

## <a name="abs"></a><a name="abs"></a> просто

Возвращает абсолютное значение аргумента

```cpp
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента.

## <a name="clamp"></a><a name="clamp"></a> фиксаци

Выполняет вычисление значения первого указанного аргумента, который задается в диапазоне, определяемом вторым и третьим указанными аргументами.

```cpp
inline float clamp(
    float _X,
    float _Min,
    float _Max) restrict(amp);

inline int clamp(
    int _X,
    int _Min,
    int _Max) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение для фиксации

*_Min*<br/>
Нижняя граница диапазона срезов.

*_Max*<br/>
Верхняя граница диапазона срезов.

### <a name="return-value"></a>Возвращаемое значение

Значение `_X` .

## <a name="countbits"></a><a name="countbits"></a> каунтбитс

Подсчитывает количество битов набора в _X

```cpp
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение без знака

### <a name="return-value"></a>Возвращаемое значение

Возвращает число бит набора в _X

## <a name="create_accelerator_view"></a><a name="create_accelerator_view"></a> create_accelerator_view

Создает объект [accelerator_view](accelerator-view-class.md) из указателя на интерфейс устройства Direct3D.

## <a name="syntax"></a>Синтаксис

```cpp
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Параметры

*_Accelerator*<br/>
Ускоритель, в котором создается новый accelerator_view.

*_D3D_device*<br/>
Указатель на интерфейс устройства Direct3D.

*_Disable_timeout*<br/>
Логический параметр, указывающий, следует ли отключать время ожидания для только что созданного accelerator_view. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D и используется, чтобы указать, должна ли операционная система разрешать выполнение рабочих нагрузок, выполняющих более 2 секунд, без сброса устройства в соответствии с механизмом обнаружения и восстановления по времени ожидания Windows. Этот флаг рекомендуется использовать, если необходимо выполнять длительные задачи на accelerator_view.

*_Qmode*<br/>
[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) , используемый для вновь созданной accelerator_view. Этот параметр имеет значение по умолчанию `queuing_mode_automatic` .

## <a name="return-value"></a>Возвращаемое значение

`accelerator_view`Объект, созданный из переданного интерфейса устройства Direct3D.

## <a name="remarks"></a>Примечания

Эта функция создает новый `accelerator_view` объект на основе существующего указателя на интерфейс устройства Direct3D. Если вызов функции завершился с ошибкой, счетчик ссылок параметра увеличивается на единицу с помощью `AddRef` вызова интерфейса. Вы можете безопасно освободить объект, если он больше не требуется в коде DirectX. При сбое вызова метода выдается [runtime_exception](runtime-exception-class.md) .

`accelerator_view`Объект, создаваемый с помощью этой функции, является потокобезопасным. Необходимо синхронизировать одновременное использование `accelerator_view` объекта. Несинхронизированное одновременное использование `accelerator_view` объекта и необработанного интерфейса ID3D11Device приводит к неопределенному поведению.

C++ AMP среда выполнения предоставляет подробные сведения об ошибке в режиме отладки с помощью слоя отладки D3D, если используется `D3D11_CREATE_DEVICE_DEBUG` флаг.

## <a name="d3d_access_lock"></a><a name="d3d_access_lock"></a> d3d_access_lock

Получите блокировку на accelerator_view для безопасного выполнения операций D3D с ресурсами, которые совместно используются accelerator_view. Accelerator_view и все C++ AMP ресурсы, связанные с этим accelerator_view внутренне используют эту блокировку при выполнении операций и блокируются, пока другой поток удерживает блокировку на доступ к D3D. Эта блокировка не является рекурсивной: это не определено поведение для вызова этой функции из потока, который уже владеет блокировкой. Это поведение не определено для выполнения операций с accelerator_view или любым контейнером данных, связанным с accelerator_view из потока, в котором находится блокировка доступа D3D. См. также scoped_d3d_access_lock, класс в стиле RAII для блокировки доступа D3D на основе области.

```cpp
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view для блокировки.

## <a name="d3d_access_try_lock"></a><a name="d3d_access_try_lock"></a> d3d_access_try_lock

Попытка получить блокировку доступа D3D на accelerator_view без блокировки.

```cpp
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view для блокировки.

### <a name="return-value"></a>Возвращаемое значение

значение true, если блокировка была получена, или false, если она в данный момент удерживается другим потоком.

## <a name="d3d_access_unlock"></a><a name="d3d_access_unlock"></a> d3d_access_unlock

Освобождение блокировки доступа D3D на заданном accelerator_view. Если вызывающий поток не удерживает блокировку accelerator_view результаты не определены.

```cpp
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view, для которого снимается блокировка.

## <a name="firstbithigh"></a><a name="firstbithigh"></a> фирстбисигх

Возвращает расположение первого набора бит в _X, начиная с бита с наивысшим порядковым номером и Переходя к биту наименьшего порядка.

```cpp
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Расположение первого набора бит

## <a name="firstbitlow"></a><a name="firstbitlow"></a> фирстбитлов

Возвращает расположение первого набора бит в _X, начиная с младшего бита и заканчивая битом наивысшего порядка.

```cpp
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает расположение первого набора бит

## <a name="get_buffer"></a><a name="get_buffer"></a> get_buffer

Получение интерфейса буфера Direct3D, лежащего в основе указанного массива.

```cpp
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов в массиве.

*_Rank*<br/>
Ранг массива.

*_Array*<br/>
Массив на accelerator_view Direct3D, для которого возвращается базовый интерфейс буфера Direct3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий буферу Direct3D, который является базовым для массива.

## <a name="a-nameget_device-get_device"></a><a name="get_device"> get_device

Получение интерфейса устройства D3D, лежащего в основе accelerator_view.

```cpp
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Параметры

*АВ*<br/>
D3D-accelerator_view, для которого возвращается базовый интерфейс устройства D3D.

### <a name="return-value"></a>Возвращаемое значение

`IUnknown`Указатель интерфейса устройства D3D, лежащего в основе accelerator_view.

## <a name="imax"></a><a name="imax"></a> имакс

Определение максимального числового значения аргументов

```cpp
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат максимального числового значения аргументов

## <a name="imin"></a><a name="imin"></a> имин

Определение минимального числового значения аргументов

```cpp
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат минимального числового значения аргументов

## <a name="is_timeout_disabled"></a><a name="is_timeout_disabled"></a> is_timeout_disabled

Возвращает логический флаг, указывающий, отключено ли время ожидания для указанного accelerator_view. Соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D.

```cpp
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>Параметры

*_Accelerator_view*<br/>
Accelerator_view, для которого запрашиваются параметры с отключенным временем ожидания.

### <a name="return-value"></a>Возвращаемое значение

Логический флаг, указывающий, отключено ли время ожидания для указанного accelerator_view.

## <a name="mad"></a><a name="mad"></a> отслеживания

Выполняет вычисление произведения первого и второго указанных аргументов, а затем добавляет третий указанный аргумент.

```cpp
inline float mad(
    float _X,
    float _Y,
    float _Z) restrict(amp);

inline double mad(
    double _X,
    double _Y,
    double _Z) restrict(amp);

inline int mad(
    int _X,
    int _Y,
    int _Z) restrict(amp);

inline unsigned int mad(
    unsigned int _X,
    unsigned int _Y,
    unsigned int _Z) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Первый указанный аргумент.

*_Y*<br/>
Второй указанный аргумент.

*_Z*<br/>
Третий указанный аргумент.

### <a name="return-value"></a>Возвращаемое значение

Результат `_X` \* `_Y`  +  `_Z` .

## <a name="make_array"></a><a name="make_array"></a> make_array

Создание массива из указателя интерфейса буфера Direct3D.

```cpp
template<
    typename value_type,
    int _Rank
>
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,
    const Concurrency::accelerator_view& _Rv,
    IUnknown* _D3D_buffer)  ;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элемента создаваемого массива.

*_Rank*<br/>
Ранг создаваемого массива.

*_Extent*<br/>
Экстент, описывающий форму статистического выражения массива.

*_Rv*<br/>
Представление D3D Accelerator, на котором создается массив.

*_D3D_buffer*<br/>
Указатель интерфейса IUnknown буфера D3D, из которого создается массив.

### <a name="return-value"></a>Возвращаемое значение

Массив, созданный с помощью предоставленного буфера Direct3D.

## <a name="noise"></a><a name="noise"></a> учитываем

Создает случайное значение с помощью алгоритма шума Perl

```cpp
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, из которого формируется шум Perl

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение шума Perl в диапазоне от-1 до 1

## <a name="radians"></a><a name="radians"></a> радианах

Преобразует _X из градусов в радианы

```cpp
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X, преобразованное из градусов в радианы

## <a name="rcp"></a><a name="rcp"></a> rcp

Выполняет вычисление обратной величины указанного аргумента с помощью быстрой аппроксимации.

```cpp
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение, для которого требуется вычислить обратную величину.

### <a name="return-value"></a>Возвращаемое значение

Обратная часть указанного аргумента.

## <a name="reversebits"></a><a name="reversebits"></a> реверсебитс

Изменяет порядок битов в _X

```cpp
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение без знака

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение с битовым порядком, обратным в _X

## <a name="saturate"></a><a name="saturate"></a> насытить

Фиксации _X в диапазоне от 0 до 1

```cpp
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X с фиксацией в диапазоне от 0 до 1

## <a name="sign"></a><a name="sign"></a> писать

Определяет знак указанного аргумента.

```cpp
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Знак аргумента.

## <a name="smoothstep"></a><a name="smoothstep"></a> смусстеп

Возвращает гладкую Хермите интерполяцию между 0 и 1, если _X находится в диапазоне [_Min, _Max].

```cpp
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Min*<br/>
Значение с плавающей запятой

*_Max*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если _X меньше _Min; 1, если _X больше _Max; в противном случае значение от 0 до 1, если _X находится в диапазоне [_Min, _Max]

## <a name="step"></a><a name="step"></a> первом

Сравнивает два значения, возвращая 0 или 1 в зависимости от того, какое значение больше

```cpp
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение 1, если _X больше или равно _Y; в противном случае 0

## <a name="umax"></a><a name="umax"></a> Компания

Определение максимального числового значения аргументов

```cpp
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат максимального числового значения аргументов

## <a name="umin"></a><a name="umin"></a> умин

Определение минимального числового значения аргументов

```cpp
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат минимального числового значения аргументов

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency::direct3d](concurrency-direct3d-namespace.md)
