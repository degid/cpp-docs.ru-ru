---
title: db_param (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_param
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
ms.openlocfilehash: 008a7f1ea07e6c23ad6d812ac4fbf3b30ef1da89
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833079"
---
# <a name="db_param"></a>db_param

Связывает указанную переменную элемента с входным или выходным параметром и разделяет переменную.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_param(ordinal, paramtype="DBPARAMIO_INPUT", dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Параметры

*ordinal*<br/>
Номер столбца (DBCOLUMNINFO порядковый номер), соответствующий полю в наборе строк, к которому требуется привязать данные.

*типу paramtype*<br/>
Используемых Тип, заданный для параметра. Поставщики поддерживают только типы ввода-вывода, поддерживаемые базовым источником данных. Тип является сочетанием одного или нескольких значений ДБПАРАМИОЕНУМ:

- DBPARAMIO_INPUT Входной параметр

- DBPARAMIO_OUTPUT Выходной параметр

- DBPARAMIO_NOTPARAM Метод доступа не имеет параметров. Установка `eParamIO` этого значения в методы доступа к строкам напоминает пользователю, что параметры игнорируются.

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

**db_param** определяет параметры, используемые в командах; Поэтому он используется с `db_command` . Например, можно использовать **db_param** для привязки параметров в запросах SQL или хранимых процедурах. Параметры в хранимой процедуре обозначаются вопросительными знаками (?), и элементы данных следует привязывать в порядке, в котором отображаются параметры.

**db_param** разделяет данные элементов, которые могут участвовать в `ICommandWithParameters` привязке на основе OLE DB. Он задает тип параметра (ввод или вывод), тип OLE DB, точность, масштаб, состояние и длину для указанного параметра. Этот атрибут вставляет OLE DB пользовательские макросы BEGIN_PARAM_MAP... END_PARAM_MAP. Каждый элемент, помеченный атрибутом **db_param** , будет занимать одну запись в карте в виде COLUMN_ENTRY.

**db_param** используется в сочетании с атрибутами [db_table](db-table.md) или [db_command](db-command.md) .

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

## <a name="example"></a>Пример

В следующем примере создается класс Command на основе хранимой процедуры Салесбиеар в базе данных Northwind. Он связывает первый параметр в хранимой процедуре с `m_RETURN_VALUE` переменной и определяет его как выходной параметр. Он связывает два последних (входных) параметра с `m_Beginning_Date` и `m_Ending_Date` .

В следующем примере переменная связывается `nOutput` с выходным параметром.

```cpp
// db_param.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_source(L"my_connection_string"),
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")
]
struct CSalesbyYear {
   DBSTATUS m_dwShippedDateStatus;
   DBSTATUS m_dwOrderIDStatus;
   DBSTATUS m_dwSubtotalStatus;
   DBSTATUS m_dwYearStatus;

   DBLENGTH m_dwShippedDateLength;
   DBLENGTH m_dwOrderIDLength;
   DBLENGTH m_dwSubtotalLength;
   DBLENGTH m_dwYearLength;

   // Bind columns
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];

   // Bind parameters
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **`struct`** , член, метод, локальный|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[OLE DB атрибуты потребителя](ole-db-consumer-attributes.md)
