---
title: Класс CCommand
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: beabe73ff4ce0e6be8aaccfcdc636adc1ba04d5c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838442"
---
# <a name="ccommand-class"></a>Класс CCommand

Предоставляет методы для задания и выполнения команды.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Тип класса метода доступа (например,, `CDynamicParameterAccessor` `CDynamicStringAccessor` или `CEnumeratorAccessor` ), который должна использовать команда. Значение по умолчанию — `CNoAccessor` , которое указывает, что класс не поддерживает параметры или выходные столбцы.

*тровсет*<br/>
Тип класса набора строк (например, `CArrayRowset` или `CNoRowset` ), который должна использовать команда. Значение по умолчанию — `CRowset`.

*тмултипле*<br/>
Чтобы использовать команду OLE DB, которая может возвращать несколько результатов, укажите [CMultipleResults](../../data/oledb/cmultipleresults-class.md). В противном случае используйте [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Дополнительные сведения см. в разделе [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85)).

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Закрыть](#close)|Закрывает текущую команду.|
|[жетнекстресулт](#getnextresult)|Извлекает следующий результат при использовании нескольких результирующих наборов.|
|[Открыть](#open)|Выполняет и при необходимости привязывает команду.|

### <a name="inherited-methods"></a>Наследуемые методы

| Имя | Описание |
|-|-|
|[Создание](#create)|Создает новую команду для указанного сеанса, а затем задает текст команды.|
|[CreateCommand](#createcommand)|Создает новую команду.|
|[GetParameterInfo](#getparameterinfo)|Возвращает список параметров команды, их имена и типы.|
|[Обеспечьте](#prepare)|Проверяет и оптимизирует текущую команду.|
|[релеасекомманд](#releasecommand)|При необходимости освобождает метод доступа к параметру, а затем освобождает команду.|
|[SetParameterInfo](#setparameterinfo)|Задает собственный тип для каждого параметра команды.|
|[Unprepare](#unprepare)|Отменяет текущий план выполнения команды.|

## <a name="remarks"></a>Примечания

Используйте этот класс, если необходимо выполнить операцию на основе параметров или выполнить команду. Если нужно просто открыть простой набор строк, используйте вместо него [CTable](../../data/oledb/ctable-class.md) .

Класс метода доступа, который вы используете, определяет метод привязки параметров и данных.

Обратите внимание, что нельзя использовать хранимые процедуры с поставщиком OLE DB для Jet, так как этот поставщик не поддерживает хранимые процедуры (в строках запросов разрешены только константы).

## <a name="ccommandclose"></a><a name="close"></a> CCommand:: Close

Освобождает набор строк метода доступа, связанный с командой.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Команда использует набор строк, метод доступа set Result и (необязательно) метод доступа к параметру (в отличие от таблиц, которые не поддерживают параметры и не требуют метода доступа к параметрам).

При выполнении команды необходимо вызвать обе функции `Close` и [релеасекомманд](../../data/oledb/ccommand-releasecommand.md) после команды.

Если необходимо повторно выполнить одну и ту же команду, следует освободить метод доступа к результирующему набору, вызвав `Close` перед вызовом метода `Execute` . В конце серии необходимо освободить метод доступа к параметру, вызвав `ReleaseCommand` . Другой распространенный сценарий — вызов хранимой процедуры, которая имеет выходные параметры. Во многих поставщиках (например, поставщик OLE DB для SQL Server) значения выходных параметров будут недоступны до закрытия метода доступа к результирующему набору. Вызовите, `Close` чтобы закрыть возвращаемый набор строк и метод доступа к результирующему набору, но не метод доступа к параметру, что позволяет получить значения выходных параметров.

### <a name="example"></a>Пример

В следующем примере показано, как можно вызывать `Close` и `ReleaseCommand` при повторном выполнении одной и той же команды.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a> CCommand:: Жетнекстресулт

Выбирает следующий результирующий набор, если он доступен.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Параметры

*пулровсаффектед*<br/>
[вход/выход] Указатель на память, в которой возвращается число строк, затронутых командой.

*ббинд*<br/>
окне Указывает, следует ли выполнять автоматическую привязку команды после ее выполнения. Значение по умолчанию — **`true`** , что приводит к автоматическому связыванию команды. Установка параметра *ббинд* для **`false`** предотвращения автоматической привязки команды, чтобы можно было выполнить привязку вручную. (Ручная привязка особенно интересна для пользователей OLAP.)

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если результирующий набор был ранее выбран, эта функция освобождает предыдущий результирующий набор и отменяет привязку столбцов. Если *ббинд* имеет значение **`true`** , то он привязывает новые столбцы.

Эту функцию следует вызывать только в том случае, если вы указали несколько результатов, задав `CCommand` параметр шаблона *тмултипле* = `CMultipleResults` .

## <a name="ccommandopen"></a><a name="open"></a> CCommand:: Open

Выполняет и при необходимости привязывает команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
окне Сеанс, в котором выполняется команда.

*всзкомманд*<br/>
окне Выполняемая команда, передаваемая как строка в Юникоде. Может иметь значение NULL при использовании `CAccessor` , в этом случае команда будет получена из значения, переданного в макрос [DEFINE_COMMAND](../../data/oledb/define-command.md) . Дополнительные сведения см. в разделе [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) в *OLE DB справочнике программиста* .

*сзкомманд*<br/>
окне То же, что и *всзкомманд* , за исключением того, что этот параметр принимает строку команды ANSI. Четвертая форма этого метода может принимать значение NULL. Дополнительные сведения см. в разделе "Примечания" Далее в этом разделе.

*pPropSet*<br/>
окне Указатель на массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , содержащий свойства и значения, которые необходимо задать. См. раздел [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK.

*провсаффектед*<br/>
[вход/выход] Указатель на память, в которой возвращается число строк, затронутых командой. Если * \* провсаффектед* имеет значение null, число строк не возвращается. В противном случае `Open` устанавливает * \* провсаффектед* в соответствии со следующими условиями:

|If|Следующее действие|
|--------|----------|
|`cParamSets`Элемент `pParams` больше 1|* \* провсаффектед* представляет общее количество строк, затронутых всеми наборами параметров, указанными при выполнении.|
|Количество затронутых строк недоступно|* \* провсаффектед* имеет значение-1.|
|Команда не обновляет, не удаляет или не вставляет строки|* \* провсаффектед* не определен.|

*гуидкомманд*<br/>
окне Идентификатор GUID, указывающий синтаксис и общие правила для поставщика, используемого при анализе текста команды. Дополнительные сведения см. в разделе [ICommandText:: жеткоммандтекст](/previous-versions/windows/desktop/ms709825(v=vs.85)) and [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) в *справочнике программиста OLE DB* .

*ббинд*<br/>
окне Указывает, следует ли выполнять автоматическую привязку команды после ее выполнения. Значение по умолчанию — **`true`** , что приводит к автоматическому связыванию команды. Установка параметра *ббинд* для **`false`** предотвращения автоматической привязки команды, чтобы можно было выполнить привязку вручную. (Ручная привязка особенно интересна для пользователей OLAP.)

*улпропсетс*<br/>
окне Число структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , переданных в аргументе *ппропсет* .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Первые три формы `Open` принимают сеанс, создают команду и выполняют команду, привязывая все необходимые параметры.

Первая форма `Open` принимает строку команды в Юникоде и не имеет значения по умолчанию.

Вторая форма `Open` принимает строку команды ANSI и не имеет значения по умолчанию (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).

Третья форма `Open` позволяет строке команды иметь значение null, так как тип **`int`** со значением по умолчанию NULL. Он предоставляется для вызова `Open(session, NULL);` или, `Open(session);` поскольку null имеет тип **`int`** . Эта версия требует и утверждает, что **`int`** параметр имеет значение null.

Используйте четвертую форму, `Open` Если вы уже создали команду и хотите выполнить одну [подготовку](../../data/oledb/ccommand-prepare.md) и несколько выполнений.

> [!NOTE]
> `Open` вызовы `Execute` , которые, в свою очередь, вызывают `GetNextResult` .

## <a name="ccommandcreate"></a><a name="create"></a> CCommand:: Create

Вызывает метод [CCommand:: CreateCommand](../../data/oledb/ccommand-createcommand.md) , чтобы создать команду для указанного сеанса, а затем вызывает [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) , чтобы указать текст команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
окне Сеанс, в котором создается команда.

*всзкомманд*<br/>
окне Указатель на текст в Юникоде строки команды.

*сзкомманд*<br/>
окне Указатель на текст строки команды в формате ANSI.

*гуидкомманд*<br/>
окне Идентификатор GUID, указывающий синтаксис и общие правила для поставщика, используемого при анализе текста команды. Описание диалектов см. в разделе [ICommandText:: жеткоммандтекст](/previous-versions/windows/desktop/ms709825(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Первая форма `Create` принимает строку команды в Юникоде. Вторая форма `Create` принимает строку команды ANSI (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a> CCommand:: CreateCommand

Создает новую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
окне `CSession` Объект, связываемый с новой командой.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает команду, используя указанный объект сеанса.

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a> CCommand:: GetParameterInfo

Возвращает список параметров команды, их имена и типы.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommandWithParameters:: GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccommandprepare"></a><a name="prepare"></a> CCommand::P готовка

Проверяет и оптимизирует текущую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Параметры

*цекспектедрунс*<br/>
окне Количество ситуаций, в которых должна выполняться команда.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода OLE DB [ICommandPrepare::P готовка](/previous-versions/windows/desktop/ms718370(v=vs.85)).

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a> CCommand:: Релеасекомманд

Освобождает метод доступа к параметру, а затем освобождает саму команду.

### <a name="syntax"></a>Синтаксис

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Примечания

`ReleaseCommand` используется в сочетании с `Close` . Сведения об использовании см. в разделе " [Закрыть](../../data/oledb/ccommand-close.md) ".

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a> CCommand:: SetParameterInfo

Задает собственный тип для каждого параметра команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommandWithParameters:: SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccommandunprepare"></a><a name="unprepare"></a> CCommand:: unprepare

Отменяет текущий план выполнения команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода OLE DB [ICommandPrepare:: unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85)).

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
