---
title: Макросы объектов оснастки
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: 7e006a17ad480ea79f6aeec224278815c8c3f164
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835198"
---
# <a name="snap-in-object-macros"></a>Макросы объектов оснастки

Эти макросы обеспечивают поддержку расширений оснастки.

|Имя|Описание|
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Помечает начало схемы класса данных расширения оснастки для объекта оснастки.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Помечает начало отображения панели инструментов для объекта оснастки.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Помечает конец схемы класса данных расширения оснастки для объекта оснастки.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Помечает конец отображения панели инструментов для объекта оснастки.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Создает элемент данных для класса данных расширения оснастки.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Вводит класс данных расширения оснастки в карту классов данных расширения оснастки объекта оснастки.|
|[снапинменуид](#snapinmenuid)|Объявляет идентификатор контекстного меню, используемого объектом оснастки.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Вводит панель инструментов в карту панели инструментов объекта оснастки.|

## <a name="requirements"></a>Требования

**Заголовок:** атлснап.h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a> BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Помечает начало схемы класса данных расширения оснастки.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Параметры

*classname*<br/>
окне Имя класса данных расширения оснастки.

### <a name="remarks"></a>Примечания

Запустите карту расширений оснастки с помощью макроса BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP, добавьте записи для каждого типа данных расширения оснастки с помощью макроса [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) и завершите карту с помощью макроса [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a> BEGIN_SNAPINTOOLBARID_MAP

Объявляет начало отображения идентификатора панели инструментов для объекта оснастки.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Параметры

*_class*<br/>
окне Указывает класс объекта оснастки.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a> END_EXTENSION_SNAPIN_NODEINFO_MAP

Помечает конец схемы класса данных расширения оснастки.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Примечания

Запустите карту расширений оснастки с помощью макроса [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) , добавьте записи для каждого из типов данных оснастки расширения с помощью макроса [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) и завершите карту с помощью макроса END_EXTENSION_SNAPIN_NODEINFO_MAP.

### <a name="example"></a>Пример

См. пример для [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a> END_SNAPINTOOLBARID_MAP

Объявляет конец отображения идентификатора панели инструментов для объекта оснастки.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Параметры

*_class*<br/>
окне Указывает класс объекта оснастки.

### <a name="example"></a>Пример

См. пример для [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a> EXTENSION_SNAPIN_DATACLASS

Добавляет элемент данных в класс данных расширения оснастки для класса, производного от **иснапинитемимпл**.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Параметры

*dataClass*<br/>
окне Класс данных расширения оснастки.

### <a name="remarks"></a>Примечания

Этот класс также следует указывать в сопоставлении классов данных расширений оснастки. Запустите карту классов данных расширений оснастки с помощью макроса [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) , добавьте записи для каждого типа данных расширения оснастки с помощью макроса [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) и завершите карту с помощью макроса [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a> EXTENSION_SNAPIN_NODEINFO_ENTRY

Добавляет класс данных расширения оснастки к сопоставлению классов данных расширений оснастки.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Параметры

*dataClass*<br/>
окне Класс данных расширения оснастки.

### <a name="remarks"></a>Примечания

Запустите карту классов данных расширений оснастки с помощью макроса [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) , добавьте записи для каждого типа данных расширения оснастки с помощью макроса EXTENSION_SNAPIN_NODEINFO_ENTRY и завершите карту с помощью макроса [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) .

### <a name="example"></a>Пример

См. пример для [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a> снапинменуид

Этот макрос используется для объявления ресурса контекстного меню объекта оснастки.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Определяет контекстное меню объекта оснастки.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a> SNAPINTOOLBARID_ENTRY

Используйте этот макрос для ввода идентификатора панели инструментов в сопоставлении идентификатора панели инструментов объекта оснастки.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Определяет элемент управления ToolBar.

### <a name="remarks"></a>Примечания

Макрос [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) отмечает начало отображения идентификатора панели инструментов. конец знака отмечается [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) макросом.

### <a name="example"></a>Пример

См. пример для [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
