---
title: Макросы схемы свойств
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 5e14c3cb82b9b7527ed8af42e181581097218360
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834659"
---
# <a name="property-map-macros"></a>Макросы схемы свойств

Эти макросы определяют сопоставления и записи свойств.

|Имя|Описание|
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|Помечает начало схемы свойства ATL.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Указывает экстент или размеры элемента управления ActiveX.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Вводит в карту свойства Описание свойства, идентификатор DISPID и страницу свойств.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Вводит описание свойства, DISPID свойства, CLSID страницы свойств и `IDispatch` IID в карту свойств.|
|[PROP_PAGE](#prop_page)|Вводит CLSID страницы свойств в карту свойств.|
|[END_PROP_MAP](#end_prop_map)|Помечает конец схемы свойств ATL.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a> BEGIN_PROP_MAP

Помечает начало схемы свойства объекта.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
окне Указывает класс, содержащий карту свойств.

### <a name="remarks"></a>Примечания

В сопоставлении свойств хранятся описания свойств, идентификаторы DISPID свойств, идентификаторы CLSID страницы свойств и `IDispatch` идентификаторов IID. Классы [иперпропертибровсингимпл](../../atl/reference/iperpropertybrowsingimpl-class.md), [иперсистпропертибагимпл](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)и [испеЦифипропертипажесимпл](../../atl/reference/ispecifypropertypagesimpl-class.md) используют карту свойств для извлечения и задания этих сведений.

При создании объекта с помощью мастера проектов ATL мастер создаст пустую карту свойств, указав BEGIN_PROP_MAP, за которой следует [END_PROP_MAP](#end_prop_map).

BEGIN_PROP_MAP не сохраняет экстент (то есть измерения) карты свойств, так как объект, использующий карту свойств, не может иметь пользовательский интерфейс, поэтому он не будет иметь экстента. Если объект является элементом управления ActiveX с пользовательским интерфейсом, он имеет экстент. В этом случае для предоставления экстента необходимо указать [PROP_DATA_ENTRY](#prop_data_entry) в сопоставлении свойств.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a> PROP_DATA_ENTRY

Указывает экстент или размеры элемента управления ActiveX.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Параметры

*сздеск*<br/>
окне Описание свойства.

*участниками*<br/>
окне Элемент данных, содержащий экстент; Например, `m_sizeExtent` .

*vt*<br/>
окне Указывает тип VARIANT для свойства.

### <a name="remarks"></a>Примечания

Этот макрос вызывает сохранение указанного элемента данных.

При создании элемента управления ActiveX мастер вставляет этот макрос после [BEGIN_PROP_MAP](#begin_prop_map) макроса Map, а затем перед [END_PROP_MAPом](#end_prop_map)макроса схемы свойства.

### <a name="example"></a>Пример

В следующем примере сохраняется экстент объекта ( `m_sizeExtent` ).

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a> PROP_ENTRY_TYPE

Используйте этот макрос для ввода описания свойства, идентификатора DISPID свойства и идентификатора CLSID страницы свойств в карту свойств объекта.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Параметры

*сздеск*<br/>
окне Описание свойства.

*DISPID*<br/>
окне Идентификатор DISPID свойства.

*этому*<br/>
окне Идентификатор CLSID связанной страницы свойств. Используйте специальное значение CLSID_NULL для свойства, не имеющего связанной страницы свойств.

*vt*<br/>
окне Тип свойства.

### <a name="remarks"></a>Примечания

Макрос PROP_ENTRY был небезопасен и не рекомендуется к использованию. Он был заменен PROP_ENTRY_TYPE.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало схемы свойства. конец знака отмечается [END_PROP_MAP](#end_prop_map) макросом.

### <a name="example"></a>Пример

См. пример для [BEGIN_PROP_MAP](#begin_prop_map).

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a> PROP_ENTRY_TYPE_EX

Аналогично [PROP_ENTRY_TYPE](#prop_entry_type), но позволяет указать конкретный IID, если объект поддерживает несколько сдвоенных интерфейсов.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Параметры

*сздеск*<br/>
окне Описание свойства.

*DISPID*<br/>
окне Идентификатор DISPID свойства.

*этому*<br/>
окне Идентификатор CLSID связанной страницы свойств. Используйте специальное значение CLSID_NULL для свойства, не имеющего связанной страницы свойств.

*ииддиспатч*<br/>
окне Идентификатор IID сдвоенного интерфейса, определяющего свойство.

*vt*<br/>
окне Тип свойства.

### <a name="remarks"></a>Примечания

Макрос PROP_ENTRY_EX был небезопасен и не рекомендуется к использованию. Он был заменен PROP_ENTRY_TYPE_EX.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало схемы свойства. конец знака отмечается [END_PROP_MAP](#end_prop_map) макросом.

### <a name="example"></a>Пример

В следующем примере группируются записи `IMyDual1` , за которыми следует запись `IMyDual2` . Группировка по сдвоенному интерфейсу повысит производительность.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a> PROP_PAGE

Этот макрос используется для ввода идентификатора CLSID страницы свойств в карту свойств объекта.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Параметры

*этому*<br/>
окне Идентификатор CLSID страницы свойств.

### <a name="remarks"></a>Примечания

PROP_PAGE похож на [PROP_ENTRY_TYPE](#prop_entry_type), но не требует описания свойства или DISPID.

> [!NOTE]
> Если вы уже указали CLSID с PROP_ENTRY_TYPE или [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), вам не нужно создавать дополнительную запись с PROP_PAGE.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало схемы свойства. конец знака отмечается [END_PROP_MAP](#end_prop_map) макросом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a> END_PROP_MAP

Помечает конец схемы свойств объекта.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Примечания

При создании объекта с помощью мастера проектов ATL мастер создаст пустую карту свойств, указав [BEGIN_PROP_MAP](#begin_prop_map) , за которой следует END_PROP_MAP.

### <a name="example"></a>Пример

См. пример для [BEGIN_PROP_MAP](#begin_prop_map).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
