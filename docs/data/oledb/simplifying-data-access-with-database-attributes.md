---
title: Упрощение доступа к данным с помощью атрибутов базы данных
ms.date: 10/19/2018
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
ms.openlocfilehash: d22f8a25bc7bb58f72346a15edb51f062c44e1b4
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79546179"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Упрощение доступа к данным с помощью атрибутов базы данных

В этом разделе показано использование атрибутов базы данных для упрощения операций с базой данных.

Основным способом доступа к информации из базы данных является создание класса команды (или таблицы) и класса записи пользователя для конкретной таблицы в базе данных. Атрибуты базы данных упрощают некоторые из объявлений шаблонов, которые ранее приходилось делать.

Чтобы продемонстрировать использование атрибутов базы данных, в следующих разделах показаны две эквивалентные таблицы и объявления классов записей пользователей: в первом используются атрибуты, а во втором используются шаблоны OLE DB. Такой код объявления обычно размещается в файле заголовка с именем для таблицы или объекта команды, например Authors.h.

Сравнивая два файла, вы можете увидеть, насколько проще использовать атрибуты. Существуют следующие различия.

- С помощью атрибутов необходимо объявить только один класс: `CAuthors`, тогда как с шаблонами необходимо объявить два: `CAuthorsNoAttrAccessor` и `CAuthorsNoAttr`.

- Вызов `db_source` в версии с атрибутом эквивалентен `OpenDataSource()` вызову в объявлении шаблона.

- Вызов `db_table` в версии с атрибутом эквивалентен следующему объявлению шаблона:

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- `db_column` вызовы в версии с атрибутами эквивалентны сопоставлению столбцов (см. `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) в объявлении шаблона.

Атрибуты вставляют объявление класса записи пользователя. Класс записей пользователя равен `CAuthorsNoAttrAccessor` в объявлении шаблона. Если класс таблицы `CAuthors`, добавленный класс записи пользователя называется `CAuthorsAccessor`, и можно только просмотреть его объявление в подставляемом коде. Дополнительные сведения см. в разделе «добавленные атрибутами классы записей пользователей» в [записях пользователей](../../data/oledb/user-records.md).

В атрибутах и шаблонном коде необходимо задать свойства набора строк с помощью `CDBPropSet::AddProperty`.

Сведения об атрибутах, описываемых в этом разделе, см. в разделе [OLE DB атрибуты потребителя](../../windows/ole-db-consumer-attributes.md).

> [!NOTE]
> Для компиляции примеров ниже необходимы следующие `include` операторы:

> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>Объявление таблицы и метода доступа с помощью атрибутов

Следующий код вызывает `db_source` и `db_table` для класса Table. `db_source` указывает используемый источник данных и соединение. `db_table` вставляет соответствующий код шаблона для объявления класса таблицы. `db_column` указать карту столбцов и внедрить объявление метода доступа. OLE DB атрибуты потребителя можно использовать в любом проекте, поддерживающем ATL.

Ниже приведена таблица и объявление метода доступа с помощью атрибутов.

```cpp
//////////////////////////////////////////////////////////////////////
// Table and accessor declaration using attributes
// authors.h
//////////////////////////////////////////////////////////////////////

// Table class declaration
// (Note that you must provide your own connection string for db_source.)
[
   db_source(L"your connection string"),
   db_table("Authors")
]
class CAuthors
{
public:
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>Объявление таблицы и метода доступа с помощью шаблонов

Ниже приведена таблица и объявление метода доступа с помощью шаблонов.

```cpp
//////////////////////////////////////////////////////////////////////
// Table and user record class declaration using templates
// authors.h
//////////////////////////////////////////////////////////////////////

// User record class declaration
class CAuthorsNoAttrAccessor
{
public:
   DWORD m_dwAuIDStatus;
   DWORD m_dwAuthorStatus;
   DWORD m_dwYearBornStatus;
   DWORD m_dwAuIDLength;
   DWORD m_dwAuthorLength;
   DWORD m_dwYearBornLength;
   LONG m_AuID;
   TCHAR m_Author[51];
   SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
   HRESULT OpenDataSource()
   {
      CDataSource _db;

HRESULT hr;
      hr = _db.OpenFromInitializationString(L"your connection string");
      if (FAILED(hr))
      {
#ifdef _DEBUG
         AtlTraceErrorRecords(hr);
#endif
         return hr;
      }
      return m_session.Open(_db);
   }
   void CloseDataSource()
   {
      m_session.Close();
   }
   operator const CSession&()
   {
      return m_session;
   }
   CSession m_session;
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)
   END_COLUMN_MAP()
};
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
{
public:
   HRESULT OpenAll()
   {
HRESULT hr;
      hr = OpenDataSource();
      if (FAILED(hr))
         return hr;
      __if_exists(GetRowsetProperties)
      {
         CDBPropSet propset(DBPROPSET_ROWSET);
         __if_exists(HasBookmark)
         {
            propset.AddProperty(DBPROP_IRowsetLocate, true);
         }
         GetRowsetProperties(&propset);
         return OpenRowset(&propset);
      }
      __if_not_exists(GetRowsetProperties)
      {
         __if_exists(HasBookmark)
         {
            CDBPropSet propset(DBPROPSET_ROWSET);
            propset.AddProperty(DBPROP_IRowsetLocate, true);
            return OpenRowset(&propset);
         }
      }
      return OpenRowset();
   }
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
   {
HRESULT hr = Open(m_session, "Authors", pPropSet);
#ifdef _DEBUG
      if(FAILED(hr))
         AtlTraceErrorRecords(hr);
#endif
      return hr;
   }
   void CloseAll()
   {
      Close();
      CloseDataSource();
   }
};
```

## <a name="see-also"></a>См. также:

[Атрибуты объекта-получателя OLE DB](../../windows/ole-db-consumer-attributes.md)
