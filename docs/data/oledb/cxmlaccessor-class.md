---
title: Класс CXMLAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
ms.openlocfilehash: 36419e85554982d1c3784d0d73663b48cc820b6d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845631"
---
# <a name="cxmlaccessor-class"></a>Класс CXMLAccessor

Позволяет обращаться к источникам данных как к строковым данным, когда нет сведений о схеме хранилища данных (базовой структуре).

## <a name="syntax"></a>Синтаксис

```cpp
class CXMLAccessor : public CDynamicStringAccessorW
```

## <a name="requirements"></a>Требования

**Заголовок**: Atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[жетксмлколумндата](#getxmlcolumndata)|Извлекает сведения о столбце.|
|[жетксмлровдата](#getxmlrowdata)|Извлекает все содержимое таблицы по строкам.|

## <a name="remarks"></a>Примечания

Однако `CXMLAccessor` отличается от `CDynamicStringAccessorW` в том, что он преобразует все данные, доступ к которым осуществлялся из хранилища данных, в формате XML (с тегами). Это особенно удобно для вывода на веб-страницы, поддерживающие XML. Имена XML-тегов будут соответствовать именам столбцов хранилища данных как можно точнее.

Используйте `CDynamicAccessor` методы для получения сведений о столбцах. Эти сведения о столбцах используются для динамического создания метода доступа во время выполнения.

Сведения о столбцах хранятся в буфере, созданном и управляемом этим классом. Получение сведений о столбцах с помощью [жетксмлколумндата](#getxmlcolumndata) или получение данных столбца по строкам с помощью [жетксмлровдата](#getxmlrowdata).

## <a name="example"></a>Пример

[!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]

## <a name="cxmlaccessorgetxmlcolumndata"></a><a name="getxmlcolumndata"></a> CXMLAccessor:: Жетксмлколумндата

Получает сведения о типе столбца таблицы в виде строковых данных в формате XML по столбцам.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();
```

#### <a name="parameters"></a>Параметры

*страутпут*<br/>
заполняет Ссылка на буфер строки, содержащий извлекаемые сведения о типе столбца. Строка форматируется с помощью имен XML-тегов, соответствующих именам столбцов хранилища данных.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Ниже показано, как в XML форматируется информация о типе столбца. `type` Указывает тип данных столбца. Обратите внимание, что типы данных основаны OLE DB типах данных, а не к базе данных, к которой осуществляется доступ.

`<columninfo>`

`<column type = I2/> ColumnName`

`</columninfo>`

## <a name="cxmlaccessorgetxmlrowdata"></a><a name="getxmlrowdata"></a> CXMLAccessor:: Жетксмлровдата

Извлекает все содержимое таблицы в виде строковых данных в формате XML по строкам.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,
   bool bAppend = false) throw();
```

#### <a name="parameters"></a>Параметры

*страутпут*<br/>
заполняет Ссылка на буфер, содержащий данные таблицы для извлечения. Данные форматируются как строковые данные с именами XML-тегов, которые соответствуют именам столбцов хранилища данных.

*баппенд*<br/>
окне Логическое значение, указывающее, следует ли добавлять строку в конец выходных данных.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Ниже показано, как данные строки форматируются в формате XML. `DATA` Ниже представлены данные строки. Используйте методы Move для перехода к нужной строке.

`<row>`

`<column name>DATA</column name>`

`</row>`

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс Какцессор](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)
