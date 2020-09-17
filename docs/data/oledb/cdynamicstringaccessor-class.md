---
title: Класс CDynamicStringAccessor
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
ms.openlocfilehash: 927ea5ceef9ac74ae3cc1e06a47969b537209002
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838169"
---
# <a name="cdynamicstringaccessor-class"></a>Класс CDynamicStringAccessor

Позволяет получить доступ к источнику данных, если нет сведений о схеме базы данных (базовой структуре базы данных).

## <a name="syntax"></a>Синтаксис

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>Требования

**Заголовок**: Atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[GetString](#getstring)|Извлекает указанные данные столбца в виде строки.|
|[SetString](#setstring)|Задает указанные данные столбца в виде строки.|

## <a name="remarks"></a>Примечания

Хотя [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) запрашивает данные в собственном формате, сообщаемом поставщиком, `CDynamicStringAccessor` запрашивает получение поставщиком всех данных, доступ к которым осуществляется из хранилища данных, в виде строковых данных. Это особенно полезно для простых задач, которые не нуждаются в вычислении значений в хранилище данных, например при отображении или печати содержимого хранилища данных.

Собственный тип данных столбца в хранилище данных не имеет значения; пока поставщик может поддерживать преобразование данных, он предоставит данные в строковом формате. Если поставщик не поддерживает преобразование из собственного типа данных в строку (которая не является распространенной), запрашивающий вызов возвратит значение успеха DB_S_ERRORSOCCURED, а состояние соответствующего столбца будет указывать на проблему преобразования в DBSTATUS_E_CANTCONVERTVALUE.

Используйте `CDynamicStringAccessor` методы для получения сведений о столбцах. Эти сведения о столбцах используются для динамического создания метода доступа во время выполнения.

Сведения о столбцах хранятся в буфере, созданном и управляемом этим классом. Получение данных из буфера с помощью [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)или сохранение их в буфер с помощью [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

Обсуждение и примеры использования динамических классов методов доступа см. в разделе [Использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).

## <a name="cdynamicstringaccessorgetstring"></a><a name="getstring"></a> CDynamicStringAccessor:: GetString

Извлекает указанные данные столбца в виде строки.

### <a name="syntax"></a>Синтаксис

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*пколумннаме*<br/>
окне Указатель на символьную строку, содержащую имя столбца.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строковое значение, полученное из указанного столбца. Значение имеет тип `BaseType` , который будет **char** или **WCHAR** в зависимости от того, определено _UNICODE или нет. Возвращает значение NULL, если указанный столбец не найден.

### <a name="remarks"></a>Примечания

Вторая форма переопределения принимает имя столбца в виде строки ANSI. Третья форма переопределения принимает имя столбца в виде строки в Юникоде.

## <a name="cdynamicstringaccessorsetstring"></a><a name="setstring"></a> CDynamicStringAccessor:: SetString

Задает указанные данные столбца в виде строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Особое значение 0 относится к столбцу Bookmark, если он есть.

*пколумннаме*<br/>
окне Указатель на символьную строку, содержащую имя столбца.

*data*<br/>
окне Указатель на строковые данные, записываемые в указанный столбец.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строковое значение, в которое задается указанный столбец. Значение имеет тип `BaseType` , который будет **char** или **WCHAR** в зависимости от того, определено _UNICODE или нет.

### <a name="remarks"></a>Примечания

Вторая форма переопределения принимает имя столбца в виде строки ANSI, а третья форма переопределения принимает имя столбца в виде строки в Юникоде.

Если _SECURE_ATL имеет ненулевое значение, ошибка утверждения среды выполнения будет сформирована, если длина строки входных *данных* превышает максимально допустимую длину столбца данных, на который указывает ссылка. В противном случае входная строка будет обрезана, если длина превышает максимально допустимую длину.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс Какцессор](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)
