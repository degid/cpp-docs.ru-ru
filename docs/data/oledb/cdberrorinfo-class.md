---
title: Класс CDBErrorInfo
ms.date: 11/04/2016
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- CDBErrorInfo::GetErrorRecords
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
ms.openlocfilehash: 5c26a3f1e8b5589afebd72c7b722ab9ed9e4229d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838312"
---
# <a name="cdberrorinfo-class"></a>Класс CDBErrorInfo

Обеспечивает поддержку OLE DB обработки ошибок с помощью интерфейса OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[жеталлерроринфо](#getallerrorinfo)|Возвращает все сведения об ошибке, содержащиеся в записи об ошибке.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Вызывает [IErrorRecords:: жетбасицерроринфо](/previous-versions/windows/desktop/ms723907(v=vs.85)) , чтобы получить основные сведения об указанной ошибке.|
|[GetCustomErrorObject](#getcustomerrorobject)|Вызывает [IErrorRecords:: жеткустомерроробжект](/previous-versions/windows/desktop/ms725417(v=vs.85)) , чтобы вернуть указатель на интерфейс для пользовательского объекта ошибки.|
|[GetErrorInfo](#geterrorinfo)|Вызывает [IErrorRecords:: жетерроринфо](/previous-versions/windows/desktop/ms711230(v=vs.85)) для возвращения `IErrorInfo` указателя интерфейса на указанную запись.|
|[GetErrorParameters](#geterrorparameters)|Вызывает [IErrorRecords:: жетеррорпараметерс](/previous-versions/windows/desktop/ms715793(v=vs.85)) для возврата параметров ошибки.|
|[жетерроррекордс](#geterrorrecords)|Возвращает записи об ошибках для указанного объекта.|

## <a name="remarks"></a>Примечания

Этот интерфейс возвращает пользователю одну или несколько записей об ошибках. Сначала вызовите метод [CDBErrorInfo:: жетерроррекордс](../../data/oledb/cdberrorinfo-geterrorrecords.md) , чтобы получить количество записей об ошибках. Затем вызовите одну из функций доступа, например [CDBErrorInfo:: жеталлерроринфо](../../data/oledb/cdberrorinfo-getallerrorinfo.md), чтобы получить сведения об ошибке для каждой записи.

## <a name="cdberrorinfogetallerrorinfo"></a><a name="getallerrorinfo"></a> CDBErrorInfo:: Жеталлерроринфо

Возвращает все типы сведений об ошибках, содержащиеся в записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,
   LCID lcid,  BSTR* pbstrDescription,
   BSTR* pbstrSource = NULL,
   GUID* pguid = NULL,
   DWORD* pdwHelpContext = NULL,
   BSTR* pbstrHelpFile = NULL) const throw();
```

#### <a name="parameters"></a>Параметры

*улрекорднум*<br/>
окне Отсчитываемый от нуля номер записи, для которой возвращаются сведения об ошибке.

*lcid*<br/>
окне КОД локали для возвращаемой информации об ошибке.

*пбстрдескриптион*<br/>
заполняет Указатель на текстовое описание ошибки или значение NULL, если языковой стандарт не поддерживается. См. заметки.

*пбстрсаурце*<br/>
заполняет Указатель на строку, содержащую имя компонента, вызвавшего ошибку.

*пгуид*<br/>
заполняет Указатель на идентификатор GUID интерфейса, который определил ошибку.

*пдвхелпконтекст*<br/>
заполняет Указатель на идентификатор контекста справки для ошибки.

*пбстрхелпфиле*<br/>
заполняет Указатель на строку, содержащую путь к файлу справки, описывающему ошибку.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно. Другие возвращаемые значения см. в разделе [IErrorRecords:: жетерроринфо](/previous-versions/windows/desktop/ms711230(v=vs.85)) в *справочнике программиста OLE DB* .

### <a name="remarks"></a>Примечания

Выходное значение *пбстрдескриптион* получается внутренне путем вызова метода `IErrorInfo::GetDescription` , который задает значение null, если языковой стандарт не поддерживается, или если выполняются оба следующих условия.

1. значение *LCID* — не Английский (США) и

1. значение *LCID* не равно значению, возвращаемому функцией жетусердефаултлЦид.

## <a name="cdberrorinfogetbasicerrorinfo"></a><a name="getbasicerrorinfo"></a> CDBErrorInfo:: Жетбасицерроринфо

Вызывает [IErrorRecords:: жетбасицерроринфо](/previous-versions/windows/desktop/ms723907(v=vs.85)) , чтобы получить основные сведения об ошибке, такие как код возврата и номер ошибки, зависящий от поставщика.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетбасицерроринфо](/previous-versions/windows/desktop/ms723907(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdberrorinfogetcustomerrorobject"></a><a name="getcustomerrorobject"></a> CDBErrorInfo:: Жеткустомерроробжект

Вызывает [IErrorRecords:: жеткустомерроробжект](/previous-versions/windows/desktop/ms725417(v=vs.85)) , чтобы вернуть указатель на интерфейс для пользовательского объекта ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жеткустомерроробжект](/previous-versions/windows/desktop/ms725417(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdberrorinfogeterrorinfo"></a><a name="geterrorinfo"></a> CDBErrorInfo:: Жетерроринфо

Вызывает [IErrorRecords:: жетерроринфо](/previous-versions/windows/desktop/ms711230(v=vs.85)) , чтобы вернуть указатель интерфейса [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) к указанной записи.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетерроринфо](/previous-versions/windows/desktop/ms711230(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdberrorinfogeterrorparameters"></a><a name="geterrorparameters"></a> CDBErrorInfo:: Жетеррорпараметерс

Вызывает [IErrorRecords:: жетеррорпараметерс](/previous-versions/windows/desktop/ms715793(v=vs.85)) для возврата параметров ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетеррорпараметерс](/previous-versions/windows/desktop/ms715793(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdberrorinfogeterrorrecords"></a><a name="geterrorrecords"></a> CDBErrorInfo:: Жетерроррекордс

Возвращает записи об ошибках для указанного объекта.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Интерфейс к объекту, для которого необходимо получить записи об ошибках.

*IID*<br/>
окне Идентификатор IID интерфейса, связанного с ошибкой.

*пкрекордс*<br/>
заполняет Указатель на (с отсчетом от единицы) числа записей об ошибках.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если необходимо проверить интерфейс, из которого нужно получить сведения об ошибке, используйте первую форму функции. В противном случае используйте вторую форму.

## <a name="see-also"></a>См. также раздел

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
