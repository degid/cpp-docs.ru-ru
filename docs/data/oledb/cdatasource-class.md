---
title: Класс CDataSource
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: 2ce5090d7e1c74607a82ddbb79afebe185a1dca7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838351"
---
# <a name="cdatasource-class"></a>Класс CDataSource

Соответствует объекту источника данных OLE DB, который представляет подключение через поставщик к источнику данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CDataSource
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Закрыть](#close)|Закрывает подключение.|
|[жетинитиализатионстринг](#getinitializationstring)|Извлекает строку инициализации открытого в данный момент источника данных.|
|[GetProperties](#getproperties)|Возвращает значения свойств, заданных в данный момент для подключенного источника данных.|
|[GetProperty](#getproperty)|Возвращает значение одного свойства, установленного в данный момент для подключенного источника данных.|
|[Открыть](#open)|Создает соединение с поставщиком (источником данных) с помощью `CLSID` , `ProgID` или `CEnumerator` моникера, предоставленного вызывающим объектом.|
|[опенфромфиленаме](#openfromfilename)|Открывает источник данных из файла, указанного пользователем по имени.|
|[опенфроминитиализатионстринг](#openfrominitializationstring)|Открывает источник данных, указанный в строке инициализации.|
|[опенвиспромптфиленаме](#openwithpromptfilename)|Позволяет пользователю выбрать ранее созданный файл канала передачи данных, чтобы открыть соответствующий источник данных.|
|[опенвиссервицекомпонентс](#openwithservicecomponents)|Открывает объект источника данных с помощью диалогового окна «связь данных».|

## <a name="remarks"></a>Примечания

Для одного подключения можно создать один или несколько сеансов базы данных. Эти сеансы представлены `CSession` . Чтобы открыть соединение перед созданием сеанса с, необходимо вызвать метод [CDataSource:: Open](../../data/oledb/cdatasource-open.md) `CSession::Open` .

Пример использования см `CDataSource` . в примере [catdb](../../overview/visual-cpp-samples.md) .

## <a name="cdatasourceclose"></a><a name="close"></a> CDataSource:: Close

Закрывает соединение, освобождая `m_spInit` указатель.

### <a name="syntax"></a>Синтаксис

```cpp
void Close() throw();
```

## <a name="cdatasourcegetinitializationstring"></a><a name="getinitializationstring"></a> CDataSource:: Жетинитиализатионстринг

Извлекает строку инициализации открытого в данный момент источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>Параметры

*пинитиализатионстринг*<br/>
заполняет Указатель на строку инициализации.

*бинклудепассворд*<br/>
[входные] **`true`** Если строка содержит пароль, в противном случае — значение **`false`** .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Полученная строка инициализации может использоваться для повторного открытия этого соединения с источником данных.

## <a name="cdatasourcegetproperties"></a><a name="getproperties"></a> Свойства CDataSource:: Properties

Возвращает сведения о свойствах, запрошенных для объекта подключенного источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [интерфейс IDBProperties:: Properties](/previous-versions/windows/desktop/ms714344(v=vs.85)) в *справочнике программиста OLE DB* в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Чтобы получить одно свойство, используйте [параметр-Property](../../data/oledb/cdatasource-getproperty.md).

## <a name="cdatasourcegetproperty"></a><a name="getproperty"></a> CDataSource:: Property

Возвращает значение указанного свойства для объекта подключенного источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, определяющий набор свойств, для которого возвращается свойство.

*PropID*<br/>
окне Идентификатор свойства для возвращаемого свойства.

*пвариант*<br/>
заполняет Указатель на объект Variant, где `GetProperty` возвращает значение свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Чтобы получить несколько свойств, используйте [Свойства](../../data/oledb/cdatasource-getproperties.md).

## <a name="cdatasourceopen"></a><a name="open"></a> CDataSource:: Open

Открывает соединение с источником данных с помощью `CLSID` `ProgID` `CEnumerator` моникера, или предложит пользователю диалоговое окно с указателем.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,
   LPCTSTR pName,LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>Параметры

*этому*<br/>
окне `CLSID` Поставщик данных.

*pPropSet*<br/>
окне Указатель на массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , содержащий свойства и значения, которые необходимо задать. См. раздел [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK.

*nPropertySets*<br/>
окне Число структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , переданных в аргументе *ппропсет* .

*pName*<br/>
[входные данные] Имя базы данных, к которой необходимо подключиться.

*пусернаме*<br/>
[входные данные] Имя пользователя.

*ппассворд*<br/>
[входные данные] Пароль пользователя.

*нинитмоде*<br/>
[входные данные] Режим инициализации базы данных. Список допустимых режимов инициализации см. в разделе [Свойства инициализации](/previous-versions/windows/desktop/ms723127(v=vs.85))в *справочнике по OLE DB программиста* в Windows SDK. Если *нинитмоде* равен нулю, то режим инициализации не включается в набор свойств, используемый для открытия соединения.

*сзпрогид*<br/>
[входные данные] Идентификатор программы.

*Перечислитель*<br/>
окне Объект [CEnumerator](../../data/oledb/cenumerator-class.md) , используемый для получения моникера для открытия соединения, когда вызывающий объект не указывает `CLSID` .

*hWnd*<br/>
[входные данные] Дескриптор окна, которое является родительским объектом диалогового окна. Использование перегрузки функции, использующей параметр *HWND* , автоматически вызовет компоненты службы; Дополнительные сведения см. в разделе Примечания.

*двпромптоптионс*<br/>
[входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Перегрузка метода, использующая параметр *HWND* , открывает объект источника данных с компонентами службы в oledb32.dll; Эта библиотека DLL содержит реализацию функций компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в справочнике по OLE DB в [руководстве программиста OLE DB](/previous-versions/windows/desktop/ms713643(v=vs.85)).

Перегрузки метода, не использующие параметр *HWND* , открывают объект источника данных без использования компонентов службы в oledb32.dll. Объект [CDataSource](../../data/oledb/cdatasource-class.md) , Открытый с помощью перегрузок этой функции, не сможет использовать какие-либо функции компонентов службы.

### <a name="example"></a>Пример

В следующем коде показано, как открыть источник данных Jet 4.0 с помощью шаблонов OLE DB. Источник данных Jet обрабатывается так же, как источник данных OLE DB. Однако для вызова требуется `Open` два набора свойств: один для DBPROPSET_DBINIT, а другой — для DBPROPSET_JETOLEDB_DBINIT, чтобы можно было задать DBPROP_JETOLEDB_DATABASEPASSWORD.

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="cdatasourceopenfromfilename"></a><a name="openfromfilename"></a> CDataSource:: Опенфромфиленаме

Открывает источник данных из файла, указанного пользователем по имени.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>Параметры

*сзфиленаме*<br/>
[входные данные] Имя файла (обычно это файл подключения к источнику данных (UDL)).

Дополнительные сведения о файлах канала передачи данных (UDL-файлах) см. в разделе [Общие сведения об API канала передачи данных](/previous-versions/windows/desktop/ms718102(v=vs.85)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в справочнике по OLE DB в [руководстве программиста OLE DB](/previous-versions/windows/desktop/ms713643(v=vs.85)).

## <a name="cdatasourceopenfrominitializationstring"></a><a name="openfrominitializationstring"></a> CDataSource:: Опенфроминитиализатионстринг

Открывает источник данных, заданный определяемой пользователем строкой инициализации.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>Параметры

*сзинитиализатионстринг*<br/>
окне Строка инициализации.

*фпромптфоринфо*<br/>
окне Если для этого аргумента задано значение **`true`** , то `OpenFromInitializationString` свойство DBPROP_INIT_PROMPT будет установлено равным DBPROMPT_COMPLETEREQUIRED, что указывает, что пользователю будет выдаваться запрос только в том случае, если требуется дополнительная информация. Это полезно в ситуациях, когда строка инициализации указывает базу данных, для которой требуется пароль, но строка не содержит пароль. Пользователю будет предложено ввести пароль (или любые другие недостающие сведения) при попытке подключения к базе данных.

Значение по умолчанию — **`false`** , которое указывает, что пользователь не должен получать запрос (установка DBPROP_INIT_PROMPT DBPROMPT_NOPROMPT).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д.

## <a name="cdatasourceopenwithpromptfilename"></a><a name="openwithpromptfilename"></a> CDataSource:: Опенвиспромптфиленаме

Этот метод отображает диалоговое окно, а затем открывает источник данных, используя указанный пользователем файл.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>Параметры

*hWnd*<br/>
[входные данные] Дескриптор окна, которое является родительским объектом диалогового окна.

*двпромптоптионс*<br/>
[входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.

*szInitialDirectory*<br/>
[входные данные] Исходный каталог для отображения в диалоговом окне выбора.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в справочнике по OLE DB в [руководстве программиста OLE DB](/previous-versions/windows/desktop/ms713643(v=vs.85)).

## <a name="cdatasourceopenwithservicecomponents"></a><a name="openwithservicecomponents"></a> CDataSource:: Опенвиссервицекомпонентс

Открывает объект источника данных с помощью компонентов службы в oledb32.dll.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>Параметры

*этому*<br/>
окне `CLSID` Поставщик данных.

*сзпрогид*<br/>
[входные данные] Идентификатор программы поставщика данных.

*ппропсет*<br/>
окне Указатель на массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , содержащий свойства и значения, которые необходимо задать. См. раздел [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK. При инициализации объекта источника данных свойства должны принадлежать к группе свойств источника данных. Если одно и то же свойство указано более одного раза в *ппропсет*, то используется значение, зависящее от поставщика. Если *улпропсетс* равен нулю, этот параметр игнорируется.

*улпропсетс*<br/>
окне Число структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , переданных в аргументе *ппропсет* . Если это значение равно нулю, поставщик игнорирует *ппропсет*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в справочнике по OLE DB в [руководстве программиста OLE DB](/previous-versions/windows/desktop/ms713643(v=vs.85)).

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
