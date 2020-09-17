---
title: Класс CDynamicParameterAccessor
ms.date: 02/14/2018
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
ms.openlocfilehash: de9aafe5b04b949112c44be09ac36bede7e7f660
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838182"
---
# <a name="cdynamicparameteraccessor-class"></a>Класс CDynamicParameterAccessor

Аналогичен классу [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , однако получает сведения о задаваемых параметрах путем вызова интерфейса [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) .

## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Требования

**Заголовок**: Atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Конструктор.|
|[GetParam](#getparam)|Получает данные параметров из буфера.|
|[GetParamCount](#getparamcount)|Получает число параметров в методе доступа.|
|[GetParamIO](#getparamio)|Определяет, является ли указанный параметр входным или выходным.|
|[GetParamLength](#getparamlength)|Получает длину указанного параметра, сохраненного в буфере.|
|[GetParamName](#getparamname)|Получает имя указанного параметра.|
|[GetParamStatus](#getparamstatus)|Получает состояние указанного параметра, сохраненного в буфере.|
|[GetParamString](#getparamstring)|Получает строковые данные указанного параметра, сохраненного в буфере.|
|[GetParamType](#getparamtype)|Получает тип данных указанного параметра.|
|[SetParam](#setparam)|Задает буфер, используя данные параметра.|
|[SetParamLength](#setparamlength)|Задает длину указанного параметра, сохраненного в буфере.|
|[SetParamStatus](#setparamstatus)|Задает состояние указанного параметра, сохраненного в буфере.|
|[SetParamString](#setparamstring)|Задает строковые данные указанного параметра, сохраненного в буфере.|

## <a name="remarks"></a>Примечания

Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.

Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера можно с помощью методов [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) и [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Пример использования этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров см. в примере кода [динамикконсумер](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) в репозитории [Microsoft Вксамплес](https://github.com/Microsoft/VCSamples) на сайте GitHub.

## <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a><a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor:: CDynamicParameterAccessor

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
typedef CDynamicParameterAccessor _ParamClass;
CDynamicParameterAccessor(
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000 )
   : CDynamicAccessor(eBlobHandling, nBlobSize )
```

#### <a name="parameters"></a>Параметры

*еблобхандлинг*<br/>
Указывает способ обработки данных большого двоичного объекта. Значение по умолчанию — DBBLOBHANDLING_DEFAULT. Описание значений ДББЛОБХАНДЛИНЖЕНУМ см. в разделе [CDynamicAccessor:: сетблобхандлинг](../../data/oledb/cdynamicaccessor-setblobhandling.md) .

*нблобсизе*<br/>
Максимальный размер большого двоичного объекта в байтах; данные столбца по этому значению рассматриваются как большой двоичный объект. Значение по умолчанию — 8 000. Дополнительные сведения см. в разделе [CDynamicAccessor:: сетблобсизелимит](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) .

### <a name="remarks"></a>Примечания

Дополнительные сведения об обработке больших двоичных объектов см. в описании конструктора [CDynamicAccessor:: CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) .

## <a name="cdynamicparameteraccessorgetparam"></a><a name="getparam"></a> CDynamicParameterAccessor:: param

Извлекает нестроковые данные для указанного параметра из буфера параметров.

### <a name="syntax"></a>Синтаксис

```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,
   ctype* pData) const throw();

template <class ctype> bool GetParam(TCHAR* pParamName,
   ctype* pData) const throw();

void* GetParam(DBORDINAL nParam) const throw();

void* GetParam(TCHAR* pParamName) const throw();
```

#### <a name="parameters"></a>Параметры

*CType*<br/>
Шаблонный параметр, который является типом данных.

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*ппарамнаме*<br/>
окне Имя параметра.

*pData*<br/>
заполняет Указатель на память, содержащую данные, полученные из буфера.

### <a name="return-value"></a>Возвращаемое значение

Для нешаблонных версий указывает на память, содержащую данные, полученные из буфера. Для шаблонных версий возвращает значение **`true`** On Success или **`false`** On failure.

Используйте `GetParam` для получения нестроковых данных параметров из буфера. Используйте [жетпарамстринг](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) для получения данных строковых параметров из буфера.

## <a name="cdynamicparameteraccessorgetparamcount"></a><a name="getparamcount"></a> CDynamicParameterAccessor:: Жетпарамкаунт

Возвращает количество параметров, хранимых в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число параметров.

## <a name="cdynamicparameteraccessorgetparamio"></a><a name="getparamio"></a> CDynamicParameterAccessor:: Жетпарамио

Определяет, является ли указанный параметр входным или выходным.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*ппарамио*<br/>
Указатель на переменную, содержащую `DBPARAMIO` тип (входной или выходной) указанного параметра. Он определяется следующим образом:

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** On Success или **`false`** On failure.

## <a name="cdynamicparameteraccessorgetparamlength"></a><a name="getparamlength"></a> CDynamicParameterAccessor:: Жетпарамленгс

Получает длину указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*пленгс*<br/>
заполняет Указатель на переменную, содержащую длину указанного параметра в байтах.

### <a name="remarks"></a>Примечания

Первое переопределение возвращает значение **`true`** On Success или **`false`** On failure. Второе переопределение указывает на память, содержащую длину параметра.

## <a name="cdynamicparameteraccessorgetparamname"></a><a name="getparamname"></a> CDynamicParameterAccessor:: Жетпарамнаме

Извлекает имя указанного параметра.

### <a name="syntax"></a>Синтаксис

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

### <a name="return-value"></a>Возвращаемое значение

Имя указанного параметра.

## <a name="cdynamicparameteraccessorgetparamstatus"></a><a name="getparamstatus"></a> CDynamicParameterAccessor:: Жетпарамстатус

Получает состояние указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*пстатус*<br/>
заполняет Указатель на переменную, содержащую состояние ДБСТАТУС указанного параметра. Сведения о значениях ДБСТАТУС см. в разделе [состояние](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB*или выполните поиск дбстатус в OLEDB.h.

### <a name="remarks"></a>Примечания

Первое переопределение возвращает значение **`true`** On Success или **`false`** On failure. Второе переопределение указывает на память, содержащую состояние указанного параметра.

## <a name="cdynamicparameteraccessorgetparamstring"></a><a name="getparamstring"></a> CDynamicParameterAccessor:: Жетпарамстринг

Получает строковые данные указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetParamString(DBORDINAL nParam,
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CSimpleStringW& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CHAR* pBuffer,
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,
   WCHAR* pBuffer,
   size_t* pMaxLen) throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*страутпут*<br/>
заполняет `CSimpleStringA`Строковые данные ANSI () или Unicode ( `CSimpleStringW` ) указанного параметра. Необходимо передать параметр типа `CString` , например:

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
заполняет Указатель на строковое значение ANSI (**char**) или Unicode (**WCHAR**) указанного параметра.

*пмакслен*<br/>
заполняет Указатель на размер буфера, на который указывает *pBuffer* (в символах, включая ЗАВЕРШАЮЩЕЕ значение null).

### <a name="remarks"></a>Примечания

Возвращает значение **`true`** On Success или **`false`** On failure.

Если *pBuffer* имеет значение null, этот метод установит требуемый размер буфера в памяти, на который указывает *пмакслен* , и возвратит **`true`** его без копирования данных.

Этот метод завершится ошибкой, если размер буфера *pBuffer* недостаточно велик, чтобы вместить всю строку.

Используйте `GetParamString` для получения данных строковых параметров из буфера. Используйте [параметр param](../../data/oledb/cdynamicparameteraccessor-getparam.md) для получения нестроковых данных параметров из буфера.

## <a name="cdynamicparameteraccessorgetparamtype"></a><a name="getparamtype"></a> CDynamicParameterAccessor:: Жетпарамтипе

Получает тип данных указанного параметра.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*птипе*<br/>
заполняет Указатель на переменную, содержащую тип данных указанного параметра.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** On Success или **`false`** On failure.

## <a name="cdynamicparameteraccessorsetparam"></a><a name="setparam"></a> CDynamicParameterAccessor:: Сетпарам

Задает буфер параметров с использованием указанных (не строковых) данных.

### <a name="syntax"></a>Синтаксис

```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,
   constctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();

template <class ctype>
bool SetParam(TCHAR* pParamName,
   const ctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Параметры

*CType*<br/>
Шаблонный параметр, который является типом данных.

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример:

[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]

*ппарамнаме*<br/>
окне Имя параметра.

*pData*<br/>
окне Указатель на память, содержащую данные, записываемые в буфер.

*status*<br/>
окне Состояние столбца ДБСТАТУС. Сведения о значениях ДБСТАТУС см. в разделе [состояние](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB*или выполните поиск дбстатус в OLEDB.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** On Success или **`false`** On failure.

Используется `SetParam` для задания нестроковых данных параметров в буфере. Используйте [сетпарамстринг](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) для задания данных строковых параметров в буфере.

## <a name="cdynamicparameteraccessorsetparamlength"></a><a name="setparamlength"></a> CDynamicParameterAccessor:: Сетпарамленгс

Задает длину указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*length*<br/>
окне Длина указанного параметра в байтах.

### <a name="remarks"></a>Примечания

Возвращает значение **`true`** On Success или **`false`** On failure.

## <a name="cdynamicparameteraccessorsetparamstatus"></a><a name="setparamstatus"></a> CDynamicParameterAccessor:: Сетпарамстатус

Задает состояние указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*status*<br/>
окне Состояние ДБСТАТУС указанного параметра. Сведения о значениях ДБСТАТУС см. в разделе [состояние](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB*или выполните поиск дбстатус в OLEDB.h.

### <a name="remarks"></a>Примечания

Возвращает значение **`true`** On Success или **`false`** On failure.

## <a name="cdynamicparameteraccessorsetparamstring"></a><a name="setparamstring"></a> CDynamicParameterAccessor:: Сетпарамстринг

Задает строковые данные указанного параметра, сохраненного в буфере.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetParamString(DBORDINAL nParam,
   constCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,
   constWCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Параметры

*нпарам*<br/>
окне Номер параметра (смещение от 1). Параметр 0 зарезервирован для возвращаемых значений. Номер параметра — это индекс параметра в зависимости от его порядка в SQL или вызове хранимой процедуры. Пример см. в разделе [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*пстринг*<br/>
окне Указатель на строковое значение ANSI (**char**) или Unicode (**WCHAR**) указанного параметра. См. раздел ДБСТАТУС в OLEDB.h.

*status*<br/>
окне Состояние ДБСТАТУС указанного параметра. Сведения о значениях ДБСТАТУС см. в разделе [состояние](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB*или выполните поиск дбстатус в OLEDB.h.

### <a name="remarks"></a>Примечания

Возвращает значение **`true`** On Success или **`false`** On failure.

`SetParamString` завершится ошибкой, если вы попытаетесь задать строку, превышающую максимальный размер, указанный для *пстринг*.

Используется `SetParamString` для задания данных строковых параметров в буфере. Используйте [сетпарам](../../data/oledb/cdynamicparameteraccessor-setparam.md) для задания нестроковых данных параметров в буфере.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс Какцессор](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)
