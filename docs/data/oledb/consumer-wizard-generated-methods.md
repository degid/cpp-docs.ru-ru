---
title: Методы, создаваемые мастером объекта-получателя
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, wizard-generated classes and methods
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: ce2442909fd318187a1508300a75ff4f634b3410
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211514"
---
# <a name="consumer-wizard-generated-methods"></a>Методы, создаваемые мастером объекта-получателя

::: moniker range="vs-2019"

Мастер объекта-получателя ATL OLE DB недоступен в Visual Studio 2019 и более поздних версиях. Эту функцию все еще можно добавить вручную.

::: moniker-end

::: moniker range="<=vs-2017"

**Мастер потребителя ATLE OLE DB** и **Мастер приложений MFC** имеют определенные функции, о которых необходимо знать. Некоторые методы по-разному выполняются в проектах с атрибутами, поэтому существует несколько предостережений. Каждый случай рассматривается ниже. Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` открывает источник данных и наборы строк, а также включает закладки, если они доступны.

- `CloseAll` закрывает все открытые наборы строк и прекращает выполнение всех команд.

- `OpenRowset` вызывается `OpenAll` для открытия наборов строк объекта-получателя.

- `GetRowsetProperties` возвращает указатель на набор свойств набора строк, с помощью которого можно задать свойства.

- `OpenDataSource` открывает источник данных, используя строку инициализации, указанную в диалоговом окне **Свойства канала передачи данных**.

- `CloseDataSource` закрывает источник данных в соответствующем порядке.

## <a name="openall-and-closeall"></a>OpenAll и CloseAll

```cpp
HRESULT OpenAll();

void CloseAll();
```

В следующем примере показано, как можно вызывать `OpenAll` и `CloseAll` при повторном выполнении одной и той же команды. Сравните пример кода в [CCommand::Close](../../data/oledb/ccommand-close.md), который отображает вариант, вызывающий `Close` и `ReleaseCommand` вместо `CloseAll`.

```cpp
int main(int argc, char* argv[])
{
   HRESULT hr;

   hr = CoInitialize(NULL);

   CCustOrdersDetail rs;      // Your CCommand-derived class
   rs.m_OrderID = 10248;      // Open order 10248
   hr = rs.OpenAll();         // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the first command execution
   rs.Close();

   rs.m_OrderID = 10249;      // Open order 10249 (a new order)
   hr = rs.Open();            // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the second command execution;
   // Instead of rs.CloseAll() you could call
   // rs.Close() and rs.ReleaseCommand():
   rs.CloseAll();

   CoUninitialize();
   return 0;
}
```

### <a name="remarks"></a>Примечания

Если определен метод `HasBookmark`, код `OpenAll` задает свойство `DBPROP_IRowsetLocate`. Перед его использованием необходимо убедиться, что провайдер поддерживает это свойство.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` вызывает этот метод, чтобы открыть один или несколько наборов строк в объекте-получателе. Как правило, не нужно вызывать `OpenRowset`, если нет необходимости работать с несколькими источниками данных / сессиями / наборами строк. `OpenRowset` объявлен в файле заголовка класса команды или таблицы.

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
{
   HRESULT hr = Open(m_session, NULL, pPropSet);
   #ifdef _DEBUG
   if(FAILED(hr))
      AtlTraceErrorRecords(hr);
   #endif
   return hr;
}
```

Атрибуты реализуют этот метод по-разному. Эта версия требует объект сеанса и командную строку, которая по умолчанию является командной строкой, указанной в db_command, хотя вы можете установить другую. Если определен метод `HasBookmark`, код `OpenRowset` задает свойство `DBPROP_IRowsetLocate`. Перед его использованием необходимо убедиться, что провайдер поддерживает это свойство.

```cpp
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)
{

   DBPROPSET *pPropSet = NULL;
   CDBPropSet propset(DBPROPSET_ROWSET);
   __if_exists(HasBookmark)

   {
      propset.AddProperty(DBPROP_IRowsetLocate, true);
      pPropSet= &propset;
      }
...
}
```

## <a name="getrowsetproperties"></a>GetRowsetProperties

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet);
```

Этот метод возвращает указатель на набор свойств набора строк. Можно использовать этот указатель для установки таких свойств, как `DBPROP_IRowsetChange`. `GetRowsetProperties` используется в классе записей пользователя следующим образом. Можно изменить этот код, чтобы установить дополнительные свойства набора строк.

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="remarks"></a>Примечания

Не стоит определять глобальный метод `GetRowsetProperties`, потому что он может конфликтовать с методом, определенным мастером. Это — сгенерированный мастером метод, который вы получаете с проектами на основе шаблонов и атрибутов. Атрибуты не внедряют этот код.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource и CloseDataSource

```cpp
HRESULT OpenDataSource();

void CloseDataSource();
```

### <a name="remarks"></a>Примечания

Мастер определяет методы `OpenDataSource` и `CloseDataSource`. `OpenDataSource` вызывает [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).

::: moniker-end

## <a name="see-also"></a>См. также раздел

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
