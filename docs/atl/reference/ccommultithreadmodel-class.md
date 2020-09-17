---
title: Класс Ккоммултисреадмодел
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 38ed43e77492484b7c8d8cb06cad71e695d41c4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224283"
---
# <a name="ccommultithreadmodel-class"></a>Класс Ккоммултисреадмодел

`CComMultiThreadModel`предоставляет потокобезопасные методы для увеличения и уменьшения значения переменной.

## <a name="syntax"></a>Синтаксис

```
class CComMultiThreadModel
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[Ккоммултисреадмодел:: Аутокритикалсектион](#autocriticalsection)|Ссылается на класс [ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md).|
|[Ккоммултисреадмодел:: CriticalSection](#criticalsection)|Ссылается на класс [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md).|
|[Ккоммултисреадмодел:: Среадмоделнокс](#threadmodelnocs)|Ссылается на класс [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккоммултисреадмодел::D екремент](#decrement)|Статически Уменьшает значение указанной переменной в безопасном для потоков режиме.|
|[Ккоммултисреадмодел:: Increment](#increment)|Статически Увеличивает значение указанной переменной в безопасном для потоков режиме.|

## <a name="remarks"></a>Примечания

Обычно используется `CComMultiThreadModel` одно из двух **`typedef`** имен: [ккомобжектсреадмодел] (ATL-typedefs. md # ккомобжектсреадмодел или [ккомглобалссреадмодел] (ATL-typedefs. md # ккомглобалссреадмодел. Класс, на который ссылается каждый, **`typedef`** зависит от используемой потоковой модели, как показано в следующей таблице.

|typedef|Единая Организация|Потоковое подразделение|Свободная организация потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ; M =`CComMultiThreadModel`

`CComMultiThreadModel`сам определяет три **`typedef`** имени. `AutoCriticalSection`и `CriticalSection` ссылочные классы, предоставляющие методы для получения и освобождения владения критическим разделом. `ThreadModelNoCS`REFERENCES Class [Ккоммултисреадмоделнокс (ккоммултисреадмоделнокс-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>Ккоммултисреадмодел:: Аутокритикалсектион

При использовании `CComMultiThreadModel` **`typedef`** имя `AutoCriticalSection` ссылается на класс [ккомаутокритикалсектион](ccomautocriticalsection-class.md), который предоставляет методы для получения и освобождения владения объектом критической секции.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Примечания

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) и [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md) также содержат определения для `AutoCriticalSection` . В следующей таблице показана связь между классом потоковой модели и классом критического раздела, на который ссылается `AutoCriticalSection` :

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Кроме того `AutoCriticalSection` , можно использовать **`typedef`** имя [CriticalSection](#criticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

Следующий код моделируется после [CComObjectRootEx](ccomobjectrootex-class.md)и демонстрирует `AutoCriticalSection` использование в потоковой среде.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

В следующих таблицах показаны результаты `InternalAddRef` `Lock` методов и, в зависимости от `ThreadModel` параметра шаблона и модели потоков, используемой приложением:

### <a name="threadmodel--ccomobjectthreadmodel"></a>Среадмодел = Ккомобжектсреадмодел

|Метод|Единый или Апартаментный поток|Свободная организация потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является потокобезопасным.|Приращение является потокобезопасным.|
|`Lock`|Не выполняет никаких действий; нет критической секции для блокировки.|Критическая секция заблокирована.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>Среадмодел = Ккомобжектсреадмодел:: Среадмоделнокс

|Метод|Единый или Апартаментный поток|Свободная организация потоков|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Приращение не является потокобезопасным.|Приращение является потокобезопасным.|
|`Lock`|Не выполняет никаких действий; нет критической секции для блокировки.|Не выполняет никаких действий; нет критической секции для блокировки.|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>Ккоммултисреадмодел:: CriticalSection

При использовании `CComMultiThreadModel` **`typedef`** имя `CriticalSection` ссылается на класс [ккомкритикалсектион](ccomcriticalsection-class.md), который предоставляет методы для получения и освобождения владения объектом критической секции.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Примечания

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) и [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md) также содержат определения для `CriticalSection` . В следующей таблице показана связь между классом потоковой модели и классом критического раздела, на который ссылается `CriticalSection` :

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Кроме того `CriticalSection` , можно использовать **`typedef`** имя [аутокритикалсектион](#autocriticalsection). Не следует указывать `AutoCriticalSection` в глобальных объектах или членах статических классов, если требуется исключить код запуска CRT.

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](#autocriticalsection).

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a>Ккоммултисреадмодел::D екремент

Эта статическая функция вызывает функцию Win32 [интерлоккеддекремент](/windows/win32/api/winnt/nf-winnt-interlockeddecrement), которая уменьшает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*ш*<br/>
окне Указатель на переменную, которую необходимо уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Если результат декремента равен 0, то `Decrement` возвращает 0. Если результат декремента равен нулю, то возвращаемое значение также является ненулевым, но может не совпадать с результатом декремента.

### <a name="remarks"></a>Примечания

`InterlockedDecrement`предотвращает одновременное использование этой переменной более чем одним потоком.

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a>Ккоммултисреадмодел:: Increment

Эта статическая функция вызывает функцию Win32 [интерлоккединкремент](/windows/win32/api/winnt/nf-winnt-interlockedincrement), которая увеличивает значение переменной, на которую указывает *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Параметры

*ш*<br/>
окне Указатель на переменную, которая должна быть увеличена.

### <a name="return-value"></a>Возвращаемое значение

Если результатом приращения является 0, то `Increment` возвращает 0. Если результат инкремента равен нулю, то возвращаемое значение также будет ненулевым, но может не совпадать с результатом приращения.

### <a name="remarks"></a>Примечания

`InterlockedIncrement`предотвращает одновременное использование этой переменной более чем одним потоком.

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>Ккоммултисреадмодел:: Среадмоделнокс

При использовании `CComMultiThreadModel` **`typedef`** имя `ThreadModelNoCS` ссылается на класс [ккоммултисреадмоделнокс](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Примечания

`CComMultiThreadModelNoCS`предоставляет потокобезопасные методы для увеличения и уменьшения переменной; Однако он не предоставляет критическую секцию.

[Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md) , а `CComMultiThreadModelNoCS` также содержит определения для `ThreadModelNoCS` . В следующей таблице показана связь между классом потоковой модели и классом, на который ссылается `ThreadModelNoCS` :

|Класс, определенный в|Ссылка на класс|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Пример

См. раздел [ккоммултисреадмодел:: аутокритикалсектион](#autocriticalsection).

## <a name="see-also"></a>См. также статью

[Класс Ккомсинглесреадмодел](ccomsinglethreadmodel-class.md)<br/>
[Класс Ккомаутокритикалсектион](ccomautocriticalsection-class.md)<br/>
[Класс Ккомкритикалсектион](ccomcriticalsection-class.md)<br/>
[Общие сведения о классах](../atl-class-overview.md)
