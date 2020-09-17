---
title: Глобальные функции схемы COM
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: adf4e06eb46aed74d08071dccce1db549ca31226
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833599"
---
# <a name="com-map-global-functions"></a>Глобальные функции схемы COM

Эти функции обеспечивают поддержку для `IUnknown` реализаций карт com.

|Функция|Описание|
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Делегирует к `IUnknown` объекту неагрегированного объекта.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Создает эффективный код для сравнения интерфейсов `IUnknown` .|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a> атлинтерналкуеринтерфаце

Извлекает указатель на запрошенный интерфейс.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*псис*<br/>
окне Указатель на объект, содержащий карту COM интерфейсов, доступных для `QueryInterface` .

*пентриес*<br/>
окне Массив `_ATL_INTMAP_ENTRY` структур, обращающихся к карте доступных интерфейсов.

*IID*<br/>
окне Идентификатор GUID запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, указанный в *IID*, или значение null, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`AtlInternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является агрегатным, `AtlInternalQueryInterface` не выполняет делегирование внешнему неизвестному объекту. Вы можете вводить интерфейсы в таблицу-сопоставлении COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из вариантов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a> инлинеисекуалиункновн

Вызовите эту функцию для особого случая тестирования для `IUnknown` .

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Параметры

*rguid1*<br/>
окне Идентификатор GUID для сравнения `IID_IUnknown` .

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы схемы COM](../../atl/reference/com-map-macros.md)
