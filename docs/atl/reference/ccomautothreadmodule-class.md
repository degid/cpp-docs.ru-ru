---
title: Класс Ккомаутосреадмодуле
ms.date: 11/04/2016
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 405b05548cda2b2d379b849d9278293b8d747d2e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833794"
---
# <a name="ccomautothreadmodule-class"></a>Класс Ккомаутосреадмодуле

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Параметры

*среадаллокатор*<br/>
окне Класс, управляющий выбором потока. Значение по умолчанию — [ккомсимплесреадаллокатор](../../atl/reference/ccomsimplethreadallocator-class.md).

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[CreateInstance](#createinstance)|Выбирает поток, а затем создает объект в связанном апартаменте.|
|[жетдефаултсреадс](#getdefaultthreads)|Статически Динамически вычисляет количество потоков для модуля в зависимости от числа процессоров.|
|[Init](#init)|Создает потоки модуля.|
|[Блокировка](#lock)|Увеличивает счетчик блокировок для модуля и текущего потока.|
|[Блокирован](#unlock)|Уменьшает счетчик блокировок для модуля и в текущем потоке.|

### <a name="data-members"></a>Элементы данных

|Элемент данных|Описание|
|-|-|
|[двсреадид](#dwthreadid)|Содержит идентификатор текущего потока.|
|[m_Allocator](#m_allocator)|Управляет выбором потока.|
|[m_nThreads](#m_nthreads)|Содержит число потоков в модуле.|
|[m_pApartments](#m_papartments)|Управляет апартаментами модуля.|

## <a name="remarks"></a>Примечания

> [!NOTE]
> Этот класс устарел, он был заменен производными классами [катлаутосреадмодуле](../../atl/reference/catlautothreadmodule-class.md) и [катлмодуле](../../atl/reference/catlmodule-class.md) . Приведенная ниже информация предназначена для использования с более старыми выпусками ATL.

`CComAutoThreadModule` является производным от [CComModule](../../atl/reference/ccommodule-class.md) для реализации com-сервера с контейнерами в пуле потоков для exe и служб Windows. `CComAutoThreadModule` использует [ккомапартмент](../../atl/reference/ccomapartment-class.md) для управления апартаментом для каждого потока в модуле.

Производные модули от `CComAutoThreadModule` , если требуется создавать объекты в нескольких подразделениях. Необходимо также включить макрос [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) в определение класса объекта, чтобы указать [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) в качестве фабрики класса.

По умолчанию библиотека ATL COM помощью мастера (мастер проектов ATL в Visual Studio .NET) будет наследовать модуль от `CComModule` . Чтобы использовать `CComAutoThreadModule` , измените определение класса. Пример:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[катлмодуле](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[катлмодулет](../../atl/reference/catlmodulet-class.md)

[катлаутосреадмодулет](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a> Ккомаутосреадмодуле:: CreateInstance

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Параметры

*пфнкреатеинстанце*<br/>
окне Указатель на функцию Creator.

*riid*<br/>
окне IID запрашиваемого интерфейса.

*ппвобж*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ппвобж* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Выбирает поток, а затем создает объект в связанном апартаменте.

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a> Ккомаутосреадмодуле::d Всреадид

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Примечания

Содержит идентификатор текущего потока.

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a> Ккомаутосреадмодуле:: Жетдефаултсреадс

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Число потоков, создаваемых в модуле EXE.

### <a name="remarks"></a>Примечания

Эта статическая функция динамически вычисляет максимальное число потоков для модуля EXE в зависимости от числа процессоров. По умолчанию это возвращаемое значение передается методу [init](#init) для создания потоков.

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a> Ккомаутосреадмодуле:: init

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Параметры

*ш*<br/>
окне Указатель на массив записей сопоставлений объектов.

*h*<br/>
окне Значение HINSTANCE, передаваемое в `DLLMain` или `WinMain` .

*плибид*<br/>
окне Указатель на идентификатор LIBID библиотеки типов, связанной с проектом.

*нсреадс*<br/>
окне Число создаваемых потоков. По умолчанию *нсреадс* — значение, возвращаемое [жетдефаултсреадс](#getdefaultthreads).

### <a name="remarks"></a>Примечания

Инициализирует элементы данных и создает количество потоков, заданных параметром *нсреадс*.

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a> Ккомаутосреадмодуле:: Lock

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Выполняет атомарное приращение для счетчика блокировок для модуля и для текущего потока. `CComAutoThreadModule` использует счетчик блокировок модулей, чтобы определить, есть ли у клиентов доступ к модулю. Счетчик блокировок текущего потока используется для статистических целей.

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a> Ккомаутосреадмодуле:: m_Allocator

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Примечания

Объект, управляющий выбором потока. По умолчанию `ThreadAllocator` параметр шаблона класса — [ккомсимплесреадаллокатор](../../atl/reference/ccomsimplethreadallocator-class.md).

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a> Ккомаутосреадмодуле:: m_nThreads

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
int m_nThreads;
```

### <a name="remarks"></a>Примечания

Содержит число потоков в модуле EXE. При вызове [init](#init) `m_nThreads` задается значение параметра *нсреадс* . Контейнер, связанный с каждым потоком, управляется объектом [ккомапартмент](../../atl/reference/ccomapartment-class.md) .

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a> Ккомаутосреадмодуле:: m_pApartments

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Примечания

Указывает на массив объектов [ккомапартмент](../../atl/reference/ccomapartment-class.md) , каждый из которых управляет подразделением в модуле. Число элементов в массиве основано на элементе [m_nThreads](#m_nthreads) .

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a> Ккомаутосреадмодуле:: Unlock

Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Выполняет Атомарное уменьшение числа блокировок для модуля и для текущего потока. `CComAutoThreadModule` использует счетчик блокировок модулей, чтобы определить, есть ли у клиентов доступ к модулю. Счетчик блокировок текущего потока используется для статистических целей.

Если счетчик блокировок модуля достигает нуля, модуль можно выгрузить.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
