---
title: Макросы входа COM-интерфейса
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: 1358a51f6bcb65f9c54c2006a6a467cf96593b5f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834704"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY макросов

Эти макросы вводят интерфейсы объекта в карту COM, чтобы к ним можно было получить доступ `QueryInterface` . Порядок записей в схеме COM — это интерфейсы заказов, которые будут проверяться на соответствие идентификатору IID во время `QueryInterface` .

|Макрос|Описание|
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Вводит интерфейсы в карту COM-интерфейса.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Используйте этот макрос для устранения неоднозначности двух ветвей наследования.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Используйте этот макрос, чтобы ввести интерфейс в карту COM и указать его идентификатор IID.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|То же, что и [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, что можно указать другой идентификатор IID.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Когда запрашивается интерфейс, определяемый *IID* , `COM_INTERFACE_ENTRY_AGGREGATE` перенаправляется в `punk` .|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|То же, что и [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос идентификатора IID приводит к пересылке запроса в *Punk*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|То же, что и [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением случаев, когда *Punk* имеет значение null, он автоматически создает статистическое выражение, описываемое *идентификатором CLSID*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|То же, что и [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос для любого IID приводит к пересылке запроса в *Punk*, и если *Punk* имеет значение null, автоматически создает статистическое выражение, описываемое *идентификатором CLSID*.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Заставляет программу вызывать [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) , когда запрашивается указанный интерфейс.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Сохраняет данные, относящиеся к интерфейсу, для каждого экземпляра.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Предоставляет интерфейсы разрыва.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Обрабатывает карту COM базового класса, когда обработка достигает этой записи в сопоставлении COM.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Общий механизм для подключения к `QueryInterface` логике ATL.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|То же, что и [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос идентификатора IID приводит к вызову функции *Func*.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Возвращает E_NOINTERFACE и завершает обработку карты COM, когда запрашивается указанный интерфейс.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

Вводит интерфейсы в карту COM-интерфейса.

### <a name="syntax"></a>Синтаксис

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя интерфейса, от которого объект класса наследуется напрямую.

### <a name="remarks"></a>Примечания

Как правило, это наиболее часто используемый тип записи.

### <a name="example"></a>Пример

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a> COM_INTERFACE_ENTRY2

Используйте этот макрос для устранения неоднозначности двух ветвей наследования.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя интерфейса, который необходимо предоставить из объекта.

*штук*<br/>
окне Имя ветви наследования, из которой предоставляется *x* .

### <a name="remarks"></a>Примечания

Например, если объект класса является производным от двух сдвоенных интерфейсов, вы предоставляете `IDispatch` использование COM_INTERFACE_ENTRY2, поскольку `IDispatch` может быть получен из одного из интерфейсов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a> COM_INTERFACE_ENTRY_IID

Используйте этот макрос, чтобы ввести интерфейс в карту COM и указать его идентификатор IID.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID предоставленного интерфейса.

*x*<br/>
окне Имя класса, таблица vtable которого будет предоставляться как интерфейс, определяемый *IID*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a> COM_INTERFACE_ENTRY2_IID

То же, что и [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, что можно указать другой идентификатор IID.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID, указываемый для интерфейса.

*x*<br/>
окне Имя интерфейса, от которого объект класса наследуется напрямую.

*штук*<br/>
окне Имя второго интерфейса, от которого объект класса наследуется напрямую.

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a> COM_INTERFACE_ENTRY_AGGREGATE

Когда запрашивается интерфейс, идентифицируемый *IID* , COM_INTERFACE_ENTRY_AGGREGATE пересылается в *Punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID интерфейса, запрашиваемого для.

*Punk*<br/>
окне Имя `IUnknown` указателя.

### <a name="remarks"></a>Примечания

Предполагается, что параметр *Punk* указывает на внутреннюю неизвестную статистическую функцию или на null, в этом случае запись пропускается. Как правило, `CoCreate` статистическое выражение выполняется в `FinalConstruct` .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a> COM_INTERFACE_ENTRY_AGGREGATE_BLIND

То же, что и [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос идентификатора IID приводит к пересылке запроса в *Punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Параметры

*Punk*<br/>
окне Имя `IUnknown` указателя.

### <a name="remarks"></a>Примечания

Если запрос интерфейса завершается неудачей, обработка карты COM продолжится.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE

То же, что и [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением случаев, когда *Punk* имеет значение null, он автоматически создает статистическое выражение, описываемое *идентификатором CLSID*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID интерфейса, запрашиваемого для.

*Punk*<br/>
окне Имя `IUnknown` указателя. Должен быть членом класса, содержащего карту COM.

*этому*<br/>
окне Идентификатор агрегата, который будет создан, если *Punk* имеет значение null.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

То же, что и [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос для любого IID приводит к пересылке запроса в *Punk*, и если *Punk* имеет значение null, автоматически создает статистическое выражение, описываемое *идентификатором CLSID*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Параметры

*Punk*<br/>
окне Имя `IUnknown` указателя. Должен быть членом класса, содержащего карту COM.

*этому*<br/>
окне Идентификатор агрегата, который будет создан, если *Punk* имеет значение null.

### <a name="remarks"></a>Примечания

Если запрос интерфейса завершается неудачей, обработка карты COM продолжится.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a> COM_INTERFACE_ENTRY_BREAK

Заставляет программу вызывать [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) , когда запрашивается указанный интерфейс.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Текст, используемый для создания идентификатора интерфейса.

### <a name="remarks"></a>Примечания

IID интерфейса будет создан путем добавления *x* к `IID_` . Например, если *x* имеет значение `IPersistStorage` , то IID будет иметь значение `IID_IPersistStorage` .

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a> COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Сохраняет данные, относящиеся к интерфейсу, для каждого экземпляра.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID для интерфейса разрыва.

*x*<br/>
окне Имя класса, реализующего интерфейс.

*Punk*<br/>
окне Имя `IUnknown` указателя. Должен быть членом класса, содержащего карту COM. Должно быть инициализировано значением NULL в конструкторе объекта класса.

### <a name="remarks"></a>Примечания

Если интерфейс не используется, он уменьшает общий размер экземпляра объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a> COM_INTERFACE_ENTRY_TEAR_OFF

Предоставляет интерфейсы разрыва.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID для интерфейса разрыва.

*x*<br/>
окне Имя класса, реализующего интерфейс.

### <a name="remarks"></a>Примечания

Интерфейс разрыва реализуется как отдельный объект, который создается каждый раз, когда запрашивается интерфейс, который он представляет. Как правило, интерфейс создается как отрывный, если интерфейс редко используется, поскольку он сохраняет указатель vtable в каждом экземпляре основного объекта. Разрыв удаляется, когда счетчик ссылок становится равным нулю. Класс, реализующий отрыв, должен быть производным от класса `CComTearOffObjectBase` и иметь собственную карту com.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a> COM_INTERFACE_ENTRY_CHAIN

Обрабатывает карту COM базового класса, когда обработка достигает этой записи в сопоставлении COM.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Параметры

*classname*<br/>
окне Базовый класс текущего объекта.

### <a name="remarks"></a>Примечания

Например, в следующем коде:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

Обратите внимание, что первая запись в сопоставлении COM должна быть интерфейсом для объекта, содержащего карту COM. Поэтому невозможно запустить записи схемы com с COM_INTERFACE_ENTRY_CHAIN, что приводит к тому, что поиск в схеме COM другого объекта будет вестись в точке, где **COM_INTERFACE_ENTRY_CHAIN (** `COtherObject` **)** отображается в сопоставлении COM объекта. Если необходимо сначала выполнить поиск по схеме COM другого объекта, добавьте запись интерфейса для `IUnknown` в схему com, а затем сопоставьте карту COM другого объекта. Пример:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a> COM_INTERFACE_ENTRY_FUNC

Общий механизм для подключения к `QueryInterface` логике ATL.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID предоставленного интерфейса.

*dw*<br/>
окне Параметр, передаваемый в *Func*.

*func*<br/>
окне Указатель функции, который будет возвращать *IID*.

### <a name="remarks"></a>Примечания

Если *IID* соответствует идентификатору IID интерфейса, запрашиваемого, то вызывается функция, указанная функцией *Func* . Объявление функции должно быть следующим:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

При вызове функции `pv` указывает на объект класса. Параметр *riid* ссылается на интерфейс, для которого выполняется запрос, `ppv` является указателем на расположение, в котором функция должна сохранять указатель на интерфейс, а *DW* — это параметр, указанный в записи. Функция должна иметь значение \* `ppv` null и возвращать E_NOINTERFACE или S_FALSE, если он не возвращает интерфейс. При использовании E_NOINTERFACE обработка карт COM завершается. При использовании S_FALSE обработка карт COM продолжится, несмотря на то, что не был возвращен указатель интерфейса. Если функция возвращает указатель интерфейса, она должна возвращать S_OK.

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a> COM_INTERFACE_ENTRY_FUNC_BLIND

То же, что и [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос идентификатора IID приводит к вызову функции *Func*.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Параметры

*dw*<br/>
окне Параметр, передаваемый в *Func*.

*func*<br/>
окне Функция, которая вызывается при обработке этой записи в сопоставлении COM.

### <a name="remarks"></a>Примечания

Любой сбой приведет к тому, что обработка будет продолжена на карте COM. Если функция возвращает указатель интерфейса, она должна возвращать S_OK.

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a> COM_INTERFACE_ENTRY_NOINTERFACE

Возвращает E_NOINTERFACE и завершает обработку карты COM, когда запрашивается указанный интерфейс.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Текст, используемый для создания идентификатора интерфейса.

### <a name="remarks"></a>Примечания

Этот макрос можно использовать для предотвращения использования интерфейса в конкретном случае. Например, этот макрос можно вставить в карту COM прямо перед COM_INTERFACE_ENTRY_AGGREGATE_BLIND, чтобы предотвратить перенаправление запроса для интерфейса в внутреннюю неизвестную функцию.

IID интерфейса будет создан путем добавления *x* к `IID_` . Например, если *x* имеет значение `IPersistStorage` , то IID будет иметь значение `IID_IPersistStorage` .
