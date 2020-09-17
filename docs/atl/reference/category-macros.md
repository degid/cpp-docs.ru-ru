---
title: Макросы категорий
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 0db32c9550cd76fbc8e1f6776b8ecf4cceffebd7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833898"
---
# <a name="category-macros"></a>Макросы категорий

Эти макросы определяют карты категорий.

|Макрос|Описание|
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Помечает начало таблицы категорий.|
|[END_CATEGORY_MAP](#end_category_map)|Отмечает конец таблицы категорий.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|Указывает категории, реализуемые COM-объектом.|
|[REQUIRED_CATEGORY](#required_category)|Указывает категории, необходимые для контейнера объектом COM.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="begin_category_map"></a><a name="begin_category_map"></a> BEGIN_CATEGORY_MAP

Помечает начало таблицы категорий.

```cpp
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
окне Имя класса, содержащего карту категорий.

### <a name="remarks"></a>Примечания

Таблица категорий используется для указания категорий компонентов, которые будут реализованы классом COM, и категорий, которые требуются для его контейнера.

Добавьте запись [IMPLEMENTED_CATEGORY](#implemented_category) на карту для каждой категории, реализованной классом com. Добавьте запись [REQUIRED_CATEGORY](#required_category) на карту для каждой категории, которую класс требует реализовать на своих клиентах. Отметьте конец схемы с помощью макроса [END_CATEGORY_MAP](#end_category_map) .

Категории компонентов, перечисленные на карте, будут регистрироваться автоматически при регистрации модуля, если класс имеет связанную [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto).

> [!NOTE]
> ATL использует стандартный диспетчер категорий компонентов для регистрации категорий компонентов. Если диспетчер отсутствует в системе при регистрации модуля, регистрация будет выполнена, но категории компонентов не будут зарегистрированы для этого класса.

Дополнительные сведения о категориях компонентов см. в разделе [что такое категории компонентов и как они работают](/windows/win32/com/component-categories-and-how-they-work) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a> END_CATEGORY_MAP

Отмечает конец таблицы категорий.

```cpp
END_CATEGORY_MAP()
```

### <a name="example"></a>Пример

См. пример для [BEGIN_CATEGORY_MAP](#begin_category_map).

## <a name="implemented_category"></a><a name="implemented_category"></a> IMPLEMENTED_CATEGORY

Добавьте IMPLEMENTED_CATEGORYный макрос к [карте категории](#begin_category_map) компонента, чтобы указать, что он должен быть зарегистрирован в качестве реализации категории, определяемой параметром *CATID* .

```cpp
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Параметры

*catID*<br/>
окне Константа или переменная CATID, содержащая глобальный уникальный идентификатор (GUID) для реализованной категории. Адрес *CATID* будет создан и добавлен на карту. Для выбора категорий запасов см. таблицу ниже.

### <a name="remarks"></a>Примечания

Категории компонентов, перечисленные на карте, будут регистрироваться автоматически при регистрации модуля, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать сведения о категории, зарегистрированные для класса, чтобы определить его возможности и требования, не создавая его экземпляр.

Дополнительные сведения о категориях компонентов см. в разделе [что такое категории компонентов и как они работают](/windows/win32/com/component-categories-and-how-they-work) в Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Выбор категорий запасов

|Описание|Символ|GUID реестра|
|-----------------|------------|-------------------|
|Безопасность в сценариях|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Безопасность для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Включение веб-узла простого фрейма|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Объекты, поддерживающие Интернет|Пример списка см. в разделе [объекты, поддерживающие Интернет](/windows/win32/com/internet-aware-objects) , в Windows SDK.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a> REQUIRED_CATEGORY

Добавьте REQUIRED_CATEGORYный макрос к [карте категории](#begin_category_map) компонента, чтобы указать, что она должна быть зарегистрирована как обязательная Категория, определяемая параметром *CATID* .

```cpp
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Параметры

*catID*<br/>
окне Константа или переменная CATID, содержащая глобальный уникальный идентификатор (GUID) для требуемой категории. Адрес *CATID* будет создан и добавлен на карту. Для выбора категорий запасов см. таблицу ниже.

### <a name="remarks"></a>Примечания

Категории компонентов, перечисленные на карте, будут регистрироваться автоматически при регистрации модуля, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать сведения о категории, зарегистрированные для класса, чтобы определить его возможности и требования, не создавая его экземпляр. Например, элементу управления может потребоваться, чтобы контейнер поддерживал привязку данных. Контейнер может определить, есть ли у него возможности, необходимые для размещения элемента управления, выполнив запрос к диспетчеру категорий для категорий, необходимых для этого элемента управления. Если контейнер не поддерживает требуемую функцию, он может отказаться размещать COM-объект.

Дополнительные сведения о категориях компонентов, включая пример списка, см. в разделе [что такое категории компонентов и как они работают](/windows/win32/com/component-categories-and-how-they-work) в Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Выбор категорий запасов

|Описание|Символ|GUID реестра|
|-----------------|------------|-------------------|
|Безопасность в сценариях|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Безопасность для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Включение веб-узла простого фрейма|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Объекты, поддерживающие Интернет|Пример списка см. в разделе [объекты, поддерживающие Интернет](/windows/win32/com/internet-aware-objects) , в Windows SDK.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
