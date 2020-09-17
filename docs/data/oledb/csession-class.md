---
title: класс CSession
ms.date: 11/04/2016
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
ms.openlocfilehash: 6858c26df5f5ee364717d089704117e650282278
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841107"
---
# <a name="csession-class"></a>класс CSession

Представляет отдельный сеанс доступа к базе данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CSession
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Рвал](#abort)|Отменяет (завершает) транзакцию.|
|[Закрыть](#close)|Закрывает сеанс.|
|[Фиксация](#commit)|Завершает транзакцию.|
|[жеттрансактионинфо](#gettransactioninfo)|Возвращает сведения о транзакции.|
|[Открыть](#open)|Открывает новый сеанс для объекта источника данных.|
|[StartTransaction](#starttransaction)|Начинает новую транзакцию для этого сеанса.|

## <a name="remarks"></a>Примечания

Один или несколько сеансов могут быть связаны с каждым соединением с поставщиком (источником данных), представленным объектом [CDataSource](../../data/oledb/cdatasource-class.md) . Чтобы создать новый объект `CSession` для `CDataSource` , вызовите [CSession:: Open](../../data/oledb/csession-open.md). Для начала транзакции базы данных `CSession` предоставляет `StartTransaction` метод. После запуска транзакции ее можно зафиксировать с помощью `Commit` метода или отменить с помощью `Abort` метода.

## <a name="csessionabort"></a><a name="abort"></a> CSession:: Abort

Завершает транзакцию.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Abort(BOID* pboidReason = NULL,
   BOOL bRetaining = FALSE,
   BOOL bAsync = FALSE) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85)) в *справочнике по OLE DB программиста*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="csessionclose"></a><a name="close"></a> CSession:: Close

Закрывает сеанс, Открытый с помощью [CSession:: Open](../../data/oledb/csession-open.md).

### <a name="syntax"></a>Синтаксис

```cpp
void Close() throw();
```

### <a name="remarks"></a>Примечания

Освобождает `m_spOpenRowset` указатель.

## <a name="csessioncommit"></a><a name="commit"></a> CSession:: Commit

Завершает транзакцию.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Commit(BOOL bRetaining = FALSE,
   DWORD grfTC = XACTTC_SYNC,
   DWORD grfRM = 0) const throw();
```

#### <a name="parameters"></a>Параметры

См. статью [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85)) в *справочнике по OLE DB программиста*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85)).

## <a name="csessiongettransactioninfo"></a><a name="gettransactioninfo"></a> CSession:: Жеттрансактионинфо

Возвращает сведения о транзакции.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [ITransaction:: жеттрансактионинфо](/previous-versions/windows/desktop/ms714975(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ITransaction:: жеттрансактионинфо](/previous-versions/windows/desktop/ms714975(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="csessionopen"></a><a name="open"></a> CSession:: Open

Открывает новый сеанс для объекта источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CDataSource& ds,
   DBPROPSET *pPropSet = NULL,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Параметры

*DS*<br/>
окне Источник данных, для которого должен быть открыт сеанс.

*pPropSet*<br/>
окне Указатель на массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , содержащий свойства и значения, которые необходимо задать. См. раздел [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK.

*улпропсетс*<br/>
окне Число структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , переданных в аргументе *ппропсет* .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Необходимо открыть объект источника данных с помощью [CDataSource:: Open](../../data/oledb/cdatasource-open.md) перед его передачей в `CSession::Open` .

## <a name="csessionstarttransaction"></a><a name="starttransaction"></a> CSession:: StartTransaction

Начинает новую транзакцию для этого сеанса.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,
   ULONG isoFlags = 0,
   ITransactionOptions* pOtherOptions = NULL,
   ULONG* pulTransactionLevel = NULL) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [ITransactionLocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ITransactionLocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также раздел

[CatDB](../../overview/visual-cpp-samples.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
