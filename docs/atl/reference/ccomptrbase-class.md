---
title: Класс CComPtrBase
ms.date: 11/04/2016
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 9c62cc912b3fea3ea68390882bdda37cbfb25a7e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747759"
---
# <a name="ccomptrbase-class"></a>Класс CComPtrBase

Этот класс обеспечивает основу для интеллектуальных классов указателей с использованием com-программ памяти.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, на который ссылается смарт-указатель.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase:::CComPtrBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase:Консультация](#advise)|Вызовите этот метод, `CComPtrBase`чтобы создать связь между точкой соединения 's и раковиной клиента.|
|[CComPtrBase:Attach](#attach)|Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Вызовите этот метод, чтобы создать объект класса, связанный с указанным идентификатором класса или идентификатором программы.|
|[CComPtrBase:CopyTo](#copyto)|Вызовите этот `CComPtrBase` метод, чтобы скопировать указатель на другую переменную указателя.|
|[CComPtrBase::Detach](#detach)|Вызовите этот метод, чтобы освободить право собственности на указатель.|
|[CComPtrBase::EqualObject](#isequalobject)|Вызовите этот метод, `IUnknown` чтобы проверить, указывает `CComPtrBase` ли указанный пункт на тот же объект, связанный с объектом.|
|[CComPtrBase:QueryInterface](#queryinterface)|Вызовите этот метод, чтобы вернуть указатель в указанный интерфейс.|
|[CComPtrBase:Release](#release)|Вызовите этот метод, чтобы выпустить интерфейс.|
|[CComPtrBase::Set](#setsite)|Вызовите этот метод, `CComPtrBase` чтобы установить участок объекта на `IUnknown` родительский объект.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase:Оператор ТЗ](#operator_t_star)|Оператор актерского состава.|
|[CComPtrBase:Оператор !](#operator_not)|Оператор НЕ.|
|[CComPtrBase:оператор &](#operator_amp)|Оператора &.|
|[CComPtrBase:оператор](#operator_star)|Оператор \*.|
|[CComPtrBase:оператор <](#ccomptrbase__operator lt)|Меньше, чем оператор.|
|[CComPtrBase:оператор](#operator_eq_eq)|Оператор равенства.|
|[CComPtrBase:оператор ->](#operator_ptr)|Оператор указателя на членов.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase::p](#p)|Переменная данных указателя.|

## <a name="remarks"></a>Примечания

Этот класс обеспечивает основу для других интеллектуальных указателей, которые используют процедуры управления памятью COM, такие как [CCom-IPtr](../../atl/reference/ccomqiptr-class.md) и [CComPtr.](../../atl/reference/ccomptr-class.md) Полученные классы добавляют свои собственные конструкторы и операторов, `CComPtrBase`но полагаются на методы, предоставляемые .

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a>CComPtrBase:Консультация

Вызовите этот метод, `CComPtrBase`чтобы создать связь между точкой соединения 's и раковиной клиента.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
Указатель на клиента `IUnknown`.

*Iid*<br/>
GUID точки соединения. Как правило, это то же самое, что исходящий интерфейс, управляемый точкой соединения.

*Pdw*<br/>
Указатель на файл cookie, который однозначно идентифицирует соединение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Дополнительную информацию можно узнать в [AtlAdvise.](connection-point-global-functions.md#atladvise)

## <a name="ccomptrbaseattach"></a><a name="attach"></a>CComPtrBase:Attach

Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Параметры

*p2*<br/>
Объект `CComPtrBase` будет владеть этим указателем.

### <a name="remarks"></a>Примечания

`Attach`вызывает [CComPtrBase::Освобождение](#release) на существующей переменной [CComPtrBase::p](#p) член, а затем назначает *p2* . `CComPtrBase::p` Когда `CComPtrBase` объект берет на себя право собственности `Release` на указатель, он автоматически вызывает указатель, который удалит указатель и любые выделенные данные, если подсчет ссылок на объект идет до 0.

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a>CComPtrBase:::CComPtrBase

Деструктор

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Примечания

Выпускает интерфейс, на `CComPtrBase`который указывает .

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a>CComPtrBase::CoCreateInstance

Вызовите этот метод, чтобы создать объект класса, связанный с указанным идентификатором класса или идентификатором программы.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>Параметры

*szProgID*<br/>
Указатель на ProgID, используемый для восстановления CLSID.

*pUnkOuter*<br/>
Если NULL указывает, что объект не создается как часть агрегата. Если не- NULL, является указателем на `IUnknown` интерфейс агрегатного `IUnknown`объекта (управление).

*dwClsКонтекст*<br/>
Контекст, в котором будет работать код, управляющий вновь созданным объектом.

*rclsid*<br/>
CLSID, связанный с данными и кодом, которые будут использоваться для создания объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING или E_NOINTERFACE на неудачу. Ознакомьтесь с описанием этих ошибок [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) и [CLSIDFromProgID.](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid)

### <a name="remarks"></a>Примечания

Если первая форма метода называется, [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) используется для восстановления CLSID. Обе формы затем вызова [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

В отладке сборки произойдет ошибка утверждения, если [CComPtrBase: :p](#p) не равна NULL.

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a>CComPtrBase:CopyTo

Вызовите этот `CComPtrBase` метод, чтобы скопировать указатель на другую переменную указателя.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Параметры

*Ppt*<br/>
Адрес переменной, которая `CComPtrBase` получит указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, E_POINTER на неудачу.

### <a name="remarks"></a>Примечания

Копирует `CComPtrBase` указатель на *ppT*. Количество ссылок на [cComPtrBase::p](#p) переменной участника приращено.

Ошибка HRESULT будет возвращена, если *ppT* равен NULL. В отладке сборки возникает ошибка утверждения, если *ppT* равен NULL.

## <a name="ccomptrbasedetach"></a><a name="detach"></a>CComPtrBase::Detach

Вызовите этот метод, чтобы освободить право собственности на указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Выпускает право собственности на указатель, устанавливает переменную [cComPtrBase::p](#p) данных в NULL и возвращает копию указателя.

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a>CComPtrBase::EqualObject

Вызовите этот метод, `IUnknown` чтобы проверить, указывает `CComPtrBase` ли указанный пункт на тот же объект, связанный с объектом.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Параметры

*pДругие*<br/>
Объект `IUnknown *` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если объекты идентичны, ложные в противном случае.

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a>CComPtrBase:Оператор !

Оператор НЕ.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, `CComHeapPtr` если указатель равен NULL, ложные в противном случае.

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a>CComPtrBase::оператор&amp;

Оператора &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес объекта, на который `CComPtrBase` указывает объект.

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a>CComPtrBase::оператор\*

Оператор \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [CComPtrBase::p](#p); то есть указатель на объект, на `CComPtrBase` который ссылается объект.

Если отладка сборки, ошибка утверждения будет происходить, если [CComPtrBase: :p](#p) не равна NULL.

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a>CComPtrBase:оператор

Оператор равенства.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если `CComPtrBase` и *pT* указывают на тот же объект, ложное в противном случае.

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a>CComPtrBase:оператор -&gt;

Оператор указателя на участника.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение переменной [CComPtrBase::p](#p) данных.

### <a name="remarks"></a>Примечания

Используйте этот оператор для вызова метода `CComPtrBase` в классе, на который указывает объект. В сборках отладок произойдет сбой утверждения, если участник `CComPtrBase` данных указывает на NULL.

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a>CComPtrBase::оператор&lt;

Меньше, чем оператор.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращается верно, если указатель, управляемый текущим объектом, меньше указателя, с которым он сравнивается.

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a>CComPtrBase:оператор T\*

Оператор актерского состава.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает указатель на тип данных объекта, определенный в шаблоне класса.

## <a name="ccomptrbasep"></a><a name="p"></a>CComPtrBase::p

Переменная данных указателя.

```
T* p;
```

### <a name="remarks"></a>Примечания

Эта переменная члена содержит информацию указателя.

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a>CComPtrBase:QueryInterface

Вызовите этот метод, чтобы вернуть указатель в указанный интерфейс.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Параметры

*Q*<br/>
Тип объекта, указатель интерфейса которого необходим.

*Pp*<br/>
Адрес выходных переменных, который получает запрашиваемый указатель интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или E_NOINTERFACE на неудачу.

### <a name="remarks"></a>Примечания

Этот метод вызывает [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)).

В отладке сборки будет происходить ошибка утверждения, если *pp* не равна NULL.

## <a name="ccomptrbaserelease"></a><a name="release"></a>CComPtrBase:Release

Вызовите этот метод, чтобы выпустить интерфейс.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Примечания

Интерфейс выпущен, и [CComPtrBase::p](#p) установлен на NULL.

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a>CComPtrBase::Set

Вызовите этот метод, `CComPtrBase` чтобы установить участок объекта на `IUnknown` родительский объект.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Параметры

*панкРодитель*<br/>
Указатель на `IUnknown` интерфейс родительского интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Этот метод называется [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
