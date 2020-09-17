---
title: db_column (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: 98f546a243016fa85f6d71159ab2fc0a7963bae3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833119"
---
# <a name="db_column"></a>db_column

Привязывает указанный столбец к переменной в наборе строк.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Параметры

*ordinal*<br/>
Порядковый номер столбца (по `DBCOLUMNINFO` порядковому номеру) или имя столбца (строка ANSI или Юникод), соответствующие полю в наборе строк, к которому необходимо привязать данные. При использовании чисел можно пропустить последовательные порядковые номера (например: 1, 2, 3, 5). Имя может содержать пробелы, если используемый поставщик OLE DB поддерживает его. Например, можно использовать любой из следующих форматов:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*типом*<br/>
Используемых [Индикатор типа](/previous-versions/windows/desktop/ms711251(v=vs.85)) OLE DB для записи столбца.

*precision*<br/>
Используемых Точность, используемая для записи столбца. Дополнительные сведения см. в описании `bPrecision` элемента [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) .

*масштаб*<br/>
Используемых Масштаб, используемый для записи столбца. Дополнительные сведения см. в описании `bScale` элемента [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) .

*status*<br/>
Используемых Переменная-член, используемая для хранения состояния этого столбца. Состояние указывает, является ли значение столбца значением типа данных или другим значением, таким как NULL. Возможные значения см. в разделе [состояние](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB*.

*length*<br/>
Используемых Переменная-член, используемая для хранения размера столбца в байтах.

## <a name="remarks"></a>Примечания

**db_column** привязывает указанный столбец таблицы к переменной в наборе строк. Он разделяет данные элементов, которые могут участвовать в `IAccessor` привязке на основе OLE DB. Этот атрибут настраивает карту столбцов, обычно определенную с помощью OLE DB пользовательских макросов [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../../data/oledb/end-column-map.md)и [COLUMN_ENTRY](../../data/oledb/column-entry.md). Они управляют [структурой OLE DB DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) для привязки указанного столбца. Каждый элемент, помеченный атрибутом **db_column** , будет занимать одну запись в сопоставлении столбцов в форме записи столбца. Таким образом, этот атрибут вызывается в том случае, если необходимо разместить карту столбцов, то есть в классе Command или Table.

Используйте **db_column** в сочетании с атрибутами [db_table](db-table.md) или [db_command](db-command.md) .

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

Пример использования этого атрибута в приложении см. в разделе [Read](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Пример

Этот пример привязывает столбец таблицы к **`long`** элементу данных и задает поля состояния и длины.

```cpp
// db_column_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   DBSTATUS m_dwProductIDStatus;
   DBLENGTH m_dwProductIDLength;

   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;
};
```

## <a name="example"></a>Пример

Этот пример привязывает четыре столбца к **`long`** , символьную строку, метку времени и `DB_NUMERIC` целое число в указанном порядке.

```cpp
// db_column_2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   [db_column("1")] LONG m_OrderID;
   [db_column("2")] TCHAR m_CustomerID[6];
   [db_column("4")] DB_NUMERIC m_OrderDate;
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **`struct`** , член, метод|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[OLE DB атрибуты потребителя](ole-db-consumer-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
