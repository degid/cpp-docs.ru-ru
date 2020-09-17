---
title: Класс CComObjectRootEx
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: b4dbc42cb0c6fe2c9c6692e0db37267ce3fff361
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833651"
---
# <a name="ccomobjectrootex-class"></a>Класс CComObjectRootEx

Этот класс предоставляет методы для обработки управления счетчиком ссылок на объекты как для неагрегированных, так и для агрегированных объектов.

## <a name="syntax"></a>Синтаксис

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Параметры

*среадмодел*<br/>
Класс, методы которого реализуют требуемую потоковую модель. Можно явно выбрать модель потоков, установив для *среадмодел* значение [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md), [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md)или [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md). Можно принять модель потока по умолчанию сервера, установив для *среадмодел* значение [ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel) или [ккомглобалссреадмодел](atl-typedefs.md#ccomglobalsthreadmodel).

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|Конструктор.|
|[InternalAddRef](#internaladdref)|Увеличивает значение счетчика ссылок для неагрегированного объекта.|
|[InternalRelease](#internalrelease)|Уменьшает значение счетчика ссылок для неагрегированного объекта.|
|[Блокировка](#lock)|Если модель потока является многопоточной, получает владение объектом критической секции.|
|[Блокирован](#unlock)|Если модель потока является многопоточной, освобождает владение объектом критической секции.|

### <a name="ccomobjectrootbase-methods"></a>Методы Ккомобжектрутбасе

|Функция|Описание|
|-|-|
|[финалконструкт](#finalconstruct)|Переопределите в своем классе, чтобы выполнить инициализацию, необходимую для объекта.|
|[финалрелеасе](#finalrelease)|Переопределите в классе, чтобы выполнить очистку, требуемую для объекта.|
|[аутераддреф](#outeraddref)|Увеличивает значение счетчика ссылок для агрегированного объекта.|
|[аутеркуеринтерфаце](#outerqueryinterface)|Делегирует внешнему `IUnknown` объекту агрегированного объекта.|
|[аутеррелеасе](#outerrelease)|Уменьшает значение счетчика ссылок для агрегированного объекта.|

### <a name="static-functions"></a>Статические функции

|Функция|Описание|
|-|-|
|[интерналкуеринтерфаце](#internalqueryinterface)|Делегирует к `IUnknown` объекту неагрегированного объекта.|
|[обжектмаин](#objectmain)|Вызывается во время инициализации и завершения модуля для производных классов, перечисленных в сопоставлении объектов.|

### <a name="data-members"></a>Элементы данных

|Элемент данных|Описание|
|-|-|
|[m_dwRef](#m_dwref)|Вместе с `m_pOuterUnknown` , часть объединения. Используется, если объект не является агрегированным для хранения счетчика ссылок `AddRef` и `Release` .|
|[m_pOuterUnknown](#m_pouterunknown)|Вместе с `m_dwRef` , часть объединения. Используется при статистической обработке объекта для хранения указателя на внешнюю неизвестную.|

## <a name="remarks"></a>Примечания

`CComObjectRootEx` обрабатывает управление счетчиком ссылок на объекты для неагрегированных и агрегированных объектов. Он содержит счетчик ссылок на объекты, если объект не выполняет статистическую обработку, и содержит указатель на внешнюю неизвестную функцию, если выполняется статистическая обработка объекта. Для агрегированных объектов `CComObjectRootEx` методы можно использовать для обработки сбоя внутреннего объекта, а также для защиты внешнего объекта от удаления при освобождении внутренних интерфейсов или при удалении внутреннего объекта.

Класс, реализующий COM-сервер, должен наследовать от `CComObjectRootEx` или [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).

Если в определении класса указан макрос [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) , ATL создает экземпляр `CComPolyObject<CYourClass>` при `IClassFactory::CreateInstance` вызове метода. Во время создания проверяется значение внешней неизвестной. Если он равен NULL, `IUnknown` реализуется для неагрегированного объекта. Если внешнее неизвестное значение не равно NULL, `IUnknown` реализуется для агрегированного объекта.

Если в классе не указан макрос DECLARE_POLY_AGGREGATABLE, ATL создает экземпляр `CAggComObject<CYourClass>` для агрегированных объектов или экземпляр `CComObject<CYourClass>` для неагрегированных объектов.

Преимущество использования заключается в том `CComPolyObject` , что не следует одновременно использовать `CComAggObject` и `CComObject` в модуле для обработки агрегированных и неагрегированных вариантов. В `CComPolyObject` обоих случаях обрабатывается один объект. Поэтому в модуле существует только одна копия таблицы vtable и одна копия функций. Если таблица vtable велика, это может значительно снизить размер модуля. Однако если таблица vtable невелика, использование `CComPolyObject` может привести к тому, что размер модуля будет немного больше, поскольку он не оптимизирован для агрегированного или неагрегированного объекта, как `CComAggObject` и `CComObject` .

Если объект является агрегированным, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) реализуется с помощью `CComAggObject` или `CComPolyObject` . Эти классы делегируют `QueryInterface` , `AddRef` и `Release` вызывают метод `CComObjectRootEx` `OuterQueryInterface` , `OuterAddRef` и `OuterRelease` для пересылки внешней неизвестной. Как правило, в классе переопределяется `CComObjectRootEx::FinalConstruct` для создания статистических объектов и переопределяется `CComObjectRootEx::FinalRelease` для высвобождения всех агрегированных объектов.

Если объект не является агрегированным, `IUnknown` реализуется с помощью `CComObject` или `CComPolyObject` . В этом случае вызовы `QueryInterface` , `AddRef` и `Release` делегируются для `CComObjectRootEx` `InternalQueryInterface` , `InternalAddRef` и `InternalRelease` для выполнения фактических операций.

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a> CComObjectRootEx:: CComObjectRootEx

Конструктор инициализирует счетчик ссылок равным 0.

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a> CComObjectRootEx:: Финалконструкт

Этот метод можно переопределить в производном классе, чтобы выполнить инициализацию, необходимую для объекта.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK об успешном или одном из стандартных значений HRESULT ошибок.

### <a name="remarks"></a>Примечания

По умолчанию `CComObjectRootEx::FinalConstruct` просто возвращает S_OK.

Существует ряд преимуществ для выполнения инициализации в `FinalConstruct` , а не конструкторе класса:

- Нельзя вернуть код состояния из конструктора, но можно вернуть HRESULT с помощью `FinalConstruct` возвращаемого значения. При создании объектов класса с помощью стандартной фабрики класса, предоставляемой библиотекой ATL, это возвращаемое значение передается обратно клиенту COM, что позволяет предоставить им подробные сведения об ошибке.

- Виртуальные функции нельзя вызывать с помощью механизма виртуальных функций из конструктора класса. Вызов виртуальной функции из конструктора класса приводит к статическому разрешаемому вызову функции, как определено в этой точке иерархии наследования. Вызовы чистых виртуальных функций приводят к ошибкам компоновщика.

   Класс не является самым производным классом в иерархии наследования — он полагается на производный класс, предоставляемый библиотекой ATL, для предоставления некоторых функциональных возможностей. Существует хороший шанс, что инициализация должна будет использовать функции, предоставляемые этим классом (это безусловно важно, когда объектам класса требуется агрегирование других объектов), но конструктор в классе не имеет способа получить доступ к этим функциям. Код построения для класса выполняется до того, как будет полностью создан самый производный класс.

   Однако `FinalConstruct` вызывается сразу после того, как будет полностью создан самый производный класс, позволяющий вызывать виртуальные функции и использовать реализацию расчета ссылок, предоставляемую библиотекой ATL.

### <a name="example"></a>Пример

Как правило, Переопределите этот метод в классе, производном от, `CComObjectRootEx` чтобы создать статистические объекты. Пример:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

В случае сбоя построения можно вернуть ошибку. Можно также использовать макрос [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) для защиты внешнего объекта от удаления, если во время создания внутренний агрегированный объект увеличивает число ссылок, а затем уменьшает значение на 0.

Ниже приведен типичный способ создания статистического выражения.

- Добавьте `IUnknown` указатель на объект класса и инициализируйте его значением NULL в конструкторе.

- Переопределите `FinalConstruct` , чтобы создать статистическое выражение.

- Используйте `IUnknown` указатель, определенный в качестве параметра, к макросу [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) .

- Переопределите `FinalRelease` , чтобы освободить `IUnknown` указатель.

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a> CComObjectRootEx:: Финалрелеасе

Этот метод можно переопределить в производном классе для выполнения любой очистки, необходимой для объекта.

```cpp
void FinalRelease();
```

### <a name="remarks"></a>Примечания

По умолчанию `CComObjectRootEx::FinalRelease` не выполняет никаких действий.

Выполнение очистки в `FinalRelease` предпочтительно для добавления кода в деструктор класса, так как объект все еще полностью создан в точке, где `FinalRelease` вызывается. Это позволяет безопасно обращаться к методам, предоставляемым самым производным классом. Это особенно важно для освобождения всех агрегированных объектов перед их удалением.

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a> CComObjectRootEx:: InternalAddRef

Увеличивает число ссылок неагрегированного объекта на 1.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

### <a name="remarks"></a>Примечания

Если модель потока является многопоточной, `InterlockedIncrement` используется для предотвращения одновременного изменения счетчика ссылок несколькими потоками.

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a> CComObjectRootEx:: Интерналкуеринтерфаце

Извлекает указатель на запрошенный интерфейс.

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*псис*<br/>
окне Указатель на объект, содержащий карту COM интерфейсов, доступных для `QueryInterface` .

*пентриес*<br/>
окне Указатель на `_ATL_INTMAP_ENTRY` структуру, которая обращается к карте доступных интерфейсов.

*IID*<br/>
окне Идентификатор GUID запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, указанный в *IID*, или значение null, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является агрегатным, `InternalQueryInterface` не выполняет делегирование внешнему неизвестному объекту. Вы можете вводить интерфейсы в таблицу-сопоставлении COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из вариантов.

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a> CComObjectRootEx:: InternalRelease

Уменьшает значение счетчика ссылок для неагрегированного объекта на 1.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках, не относящихся к отладке и отладке, эта функция возвращает значение, которое может быть полезно для диагностики или тестирования. Точное возвращаемое значение зависит от многих факторов, например от используемой операционной системы, а также от того, могут ли они быть счетчиком ссылок.

### <a name="remarks"></a>Примечания

Если модель потока является многопоточной, `InterlockedDecrement` используется для предотвращения одновременного изменения счетчика ссылок несколькими потоками.

## <a name="ccomobjectrootexlock"></a><a name="lock"></a> CComObjectRootEx:: Lock

Если модель потока является многопоточной, этот метод вызывает функцию Win32 API [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection), которая ожидает, пока поток не сможет стать владельцем объекта критического раздела, полученного с помощью закрытого члена данных.

```cpp
void Lock();
```

### <a name="remarks"></a>Примечания

После завершения выполнения защищенного кода поток должен вызвать, `Unlock` чтобы освободить владение критической секцией.

Если модель потока является однопотоковой, этот метод ничего не делает.

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a> CComObjectRootEx:: m_dwRef

Часть объединения, которая обращается к четырем байтам памяти.

```
long m_dwRef;
```

### <a name="remarks"></a>Примечания

В `m_pOuterUnknown` составе объединения:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Если объект не является агрегированным, счетчик ссылок, к которому обращается `AddRef` и, `Release` сохраняется в `m_dwRef` . Если объект является агрегатным, указатель на внешнюю неизвестную функцию хранится в [m_pOuterUnknown](#m_pouterunknown).

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a> CComObjectRootEx:: m_pOuterUnknown

Часть объединения, которая обращается к четырем байтам памяти.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Примечания

В `m_dwRef` составе объединения:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Если объект является агрегатным, то указатель на внешнюю неизвестную функцию хранится в `m_pOuterUnknown` . Если объект не является агрегированным, счетчик ссылок, к которому обращается `AddRef` и, `Release` хранится в [m_dwRef](#m_dwref).

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a> CComObjectRootEx:: Обжектмаин

Для каждого класса, указанного в сопоставлении объектов, эта функция вызывается один раз при инициализации модуля и снова после завершения.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Параметры

*бстартинг*<br/>
заполняет Значение равно TRUE, если инициализируется класс. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Значение параметра *бстартинг* указывает, выполняется ли инициализация или завершение модуля. Реализация по умолчанию `ObjectMain` не выполняет никаких действий, но эту функцию можно переопределить в своем классе, чтобы инициализировать или очистить ресурсы, которые необходимо выделить для класса. Обратите внимание, что `ObjectMain` вызывается до запроса всех экземпляров класса.

`ObjectMain` вызывается из точки входа библиотеки DLL, поэтому тип операции, которую может выполнять функция точки входа, ограничен. Дополнительные сведения об этих ограничениях см. в разделе [DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) и [DllMain](/windows/win32/Dlls/dllmain).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a> CComObjectRootEx:: Аутераддреф

Увеличивает значение счетчика ссылок внешней неизвестной агрегатной функции.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a> CComObjectRootEx:: Аутеркуеринтерфаце

Извлекает косвенный указатель на запрошенный интерфейс.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, указанный в *IID*, или значение null, если агрегат не поддерживает интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a> CComObjectRootEx:: Аутеррелеасе

Уменьшает значение счетчика ссылок внешней неизвестной агрегатной функции.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках, не относящихся к отладке, всегда возвращает 0. В отладочных сборках возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a> CComObjectRootEx:: Unlock

Если модель потока является многопоточной, этот метод вызывает функцию Win32 API [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection), которая освобождает владение объектом критической секции, полученным с помощью закрытого члена данных.

```cpp
void Unlock();
```

### <a name="remarks"></a>Примечания

Чтобы получить владение, поток должен вызвать `Lock` . Каждый вызов метода `Lock` требует соответствующего вызова, `Unlock` чтобы освободить владение критическим разделом.

Если модель потока является однопотоковой, этот метод ничего не делает.

## <a name="see-also"></a>См. также раздел

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
