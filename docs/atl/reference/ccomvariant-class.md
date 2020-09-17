---
title: Класс CComVariant
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: 40315077ceba3d87e12c8ab426560deef4928793
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833612"
---
# <a name="ccomvariant-class"></a>Класс CComVariant

Этот класс служит оболочкой для типа VARIANT, предоставляя член, указывающий тип хранимых данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComVariant:: CComVariant](#ccomvariant)|Конструктор.|
|[CComVariant:: ~ CComVariant](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComVariant:: Attach](#attach)|Присоединяет вариант к `CComVariant` объекту.|
|[CComVariant:: ChangeType](#changetype)|Преобразует `CComVariant` объект в новый тип.|
|[CComVariant:: Clear](#clear)|Очищает `CComVariant` объект.|
|[CComVariant:: Copy](#copy)|Копирует вариант в `CComVariant` объект.|
|[CComVariant:: CopyTo](#copyto)|Копирует содержимое `CComVariant` объекта.|
|[CComVariant::D етач](#detach)|Отсоединяет базовый вариант от `CComVariant` объекта.|
|[CComVariant:: DataSize](#getsize)|Возвращает размер содержимого объекта в байтах `CComVariant` .|
|[CComVariant:: Реадфромстреам](#readfromstream)|Загружает вариант из потока.|
|[CComVariant:: Сетбиреф](#setbyref)|Инициализирует `CComVariant` объект и задает `vt` для элемента значение VT_BYREF.|
|[CComVariant:: Вритетостреам](#writetostream)|Сохраняет базовый вариант в потоке.|

### <a name="public-operators"></a>Открытые операторы

|Оператор|Описание|
|-|-|
|[CComVariant::operator<](#operator_lt)|Указывает, `CComVariant` меньше ли объект, чем указанный вариант.|
|[CComVariant::operator>](#operator_gt)|Указывает, `CComVariant` больше ли объект, чем указанный вариант.|
|[operator!=](#operator_neq)|Указывает, `CComVariant` не равен ли объект указанному варианту.|
|[operator=](#operator_eq)|Присваивает значение `CComVariant` объекту.|
|[operator==](#operator_eq_eq)|Указывает, `CComVariant` равен ли объект заданному варианту.|

## <a name="remarks"></a>Примечания

`CComVariant` заключает в оболочку тип VARIANT и VARIANTARG, состоящий из объединения и члена, указывающего тип данных, хранящихся в объединении. Варианты обычно используются в автоматизации.

`CComVariant` является производным от типа VARIANT, поэтому его можно использовать везде, где можно использовать вариант. Например, можно использовать макрос V_VT для извлечения типа `CComVariant` или получить доступ к `vt` члену напрямую, как это можно сделать с вариантом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="ccomvariantattach"></a><a name="attach"></a> CComVariant:: Attach

Безопасно очищает текущее содержимое `CComVariant` объекта, копирует содержимое *pSrc* в этот объект, а затем задает для типа variant *pSrc* значение VT_EMPTY.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
окне Указывает на [вариант](/windows/win32/api/oaidl/ns-oaidl-variant) , который должен быть присоединен к объекту.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Владение данными, удерживаемыми *pSrc* , передается в `CComVariant` объект.

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a> CComVariant:: CComVariant

Каждый конструктор обрабатывает надежную инициализацию `CComVariant` объекта путем вызова `VariantInit` функции Win32 или установки значения и типа объекта в соответствии с передаваемыми параметрами.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
окне `CComVariant` Вариант или, используемый для инициализации `CComVariant` объекта. Содержимое исходного варианта копируется в место назначения без преобразования.

*лпсзсрк*<br/>
окне Символьная строка, используемая для инициализации `CComVariant` объекта. В ЛПКОЛЕСТР версии конструктора или строки ANSI в версию LPCSTR можно передать строку двухбайтовых символов (Юникод), заканчивающуюся нулем. В любом случае строка преобразуется в Юникод BSTR, выделенный с помощью `SysAllocString` . Тип `CComVariant` объекта будет VT_BSTR.

*бсрк*<br/>
окне **`bool`** Объект, используемый для инициализации `CComVariant` объекта. **`bool`** Перед сохранением аргумент преобразуется в VARIANT_BOOL. Тип `CComVariant` объекта будет VT_BOOL.

*нсрк*<br/>
окне **`int`** **BYTE** **`short`** **`long`** **`unsigned short`** **`unsigned long`** **`unsigned int`** Для инициализации объекта используются, Byte,,, лонглонг, улонглонг,, или `CComVariant` . Тип `CComVariant` объекта будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*втсрк*<br/>
окне Тип варианта. Если первый параметр имеет значение **`int`** , допустимые типы — VT_I4 и VT_INT. Если первый параметр имеет значение **`long`** , допустимые типы — VT_I4 и VT_ERROR. Если первый параметр имеет значение **`double`** , допустимые типы — VT_R8 и VT_DATE. Если первый параметр имеет значение **`unsigned int`** , допустимые типы — VT_UI4 и VT_UINT.

*флтсрк*<br/>
окне **`float`** Объект, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_R4.

*дблсрк*<br/>
окне **`double`** Объект, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_R8.

*цисрк*<br/>
окне `CY` Объект, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_CY.

*pSrc*<br/>
окне `IDispatch` Указатель или, `IUnknown` используемый для инициализации `CComVariant` объекта. `AddRef` будет вызываться для указателя интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN соответственно.

Или указатель САФЕРРАЙ, используемый для инициализации `CComVariant` объекта. Копия массива SAFEARRAY хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет сочетанием исходного типа массива SafeArray и VT_ARRAY.

*ксрк*<br/>
окне **`char`** Объект, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_I1.

*бстрсрк*<br/>
окне Объект BSTR, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_BSTR.

### <a name="remarks"></a>Примечания

Деструктор управляет очисткой, вызывая [CComVariant:: Clear](#clear).

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a> CComVariant:: ~ CComVariant

Деструктор

```
~CComVariant() throw();
```

### <a name="remarks"></a>Примечания

Этот метод управляет очисткой путем вызова [CComVariant:: Clear](#clear).

## <a name="ccomvariantchangetype"></a><a name="changetype"></a> CComVariant:: ChangeType

Преобразует `CComVariant` объект в новый тип.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*втнев*<br/>
окне Новый тип для `CComVariant` объекта.

*pSrc*<br/>
окне Указатель на вариант, значение которого будет преобразовано в новый тип. Значение по умолчанию — NULL, означающее, что `CComVariant` объект будет преобразован на месте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если передать значение для *pSrc*, `ChangeType` будет использовать этот вариант в качестве источника для преобразования. В противном случае `CComVariant` объект будет источником.

## <a name="ccomvariantclear"></a><a name="clear"></a> CComVariant:: Clear

Очищает `CComVariant` объект, вызывая `VariantClear` функцию Win32.

```
HRESULT Clear();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Деструктор автоматически вызывает `Clear` .

## <a name="ccomvariantcopy"></a><a name="copy"></a> CComVariant:: Copy

Освобождает `CComVariant` объект и присваивает ему копию УКАЗАННОГО варианта.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
окне Указатель на копируемый объект [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomvariantcopyto"></a><a name="copyto"></a> CComVariant:: CopyTo

Копирует содержимое `CComVariant` объекта.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Параметры

*пстрдест*<br/>
Указывает на BSTR, который получит копию содержимого `CComVariant` объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`CComVariant`Объект должен иметь тип VT_BSTR.

## <a name="ccomvariantdetach"></a><a name="detach"></a> CComVariant::D етач

Отсоединяет базовый вариант от `CComVariant` объекта и задает для типа объекта значение VT_EMPTY.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
заполняет Возвращает базовое значение типа VARIANT объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Обратите внимание, что содержимое варианта, на которое ссылается *пдест* , будет автоматически очищаться перед присвоением значения и типа вызывающего `CComVariant` объекта.

## <a name="ccomvariantgetsize"></a><a name="getsize"></a> CComVariant:: DataSize

Для типов Variant с простым фиксированным размером этот метод возвращает **`sizeof`** значение для базового типа данных и **sizeof (VarType)**.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер в байтах текущего содержимого `CComVariant` объекта.

### <a name="remarks"></a>Примечания

Если вариант содержит указатель интерфейса, `GetSize` запросы для `IPersistStream` или `IPersistStreamInit` . В случае успеха возвращаемое значение является младшим младшим значением 32, возвращаемым `GetSizeMax` плюс `sizeof(CLSID)` и `sizeof(VARTYPE)` . Если указатель интерфейса имеет значение NULL, `GetSize` возвращает `sizeof(CLSID)` плюс `sizeof(VARTYPE)` . Если общий размер больше, чем ULONG_MAX, `GetSize` возвращает значение, `sizeof(VARTYPE)` которое указывает на ошибку.

Во всех остальных случаях временный вариант типа VT_BSTR приводится к текущему ВАРИАНТу. Длина этой BSTR вычисляется как размер длины строки плюс длина строки, а также размер символа NULL плюс **sizeof (VarType)**. Если вариант не может быть приведен к типу VARIANT типа VT_BSTR, функция `GetSize` возвращает **sizeof (VarType)**.

Размер, возвращенный этим методом, соответствует числу байтов, используемых [CComVariant:: вритетостреам](#writetostream) в условиях успешного выполнения.

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a> CComVariant::operator=

Присваивает объекту значение и соответствующий тип `CComVariant` .

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
окне `CComVariant` [Вариант](/windows/win32/api/oaidl/ns-oaidl-variant) или, который должен быть назначен `CComVariant` объекту. Содержимое исходного варианта копируется в место назначения без преобразования.

*бстрсрк*<br/>
окне Значение BSTR, присваиваемое `CComVariant` объекту. Тип `CComVariant` объекта будет VT_BSTR.

*лпсзсрк*<br/>
окне Символьная строка, назначаемая `CComVariant` объекту. В ЛПКОЛЕСТР версию оператора или строку ANSI можно передать версию LPCSTR в виде расширенной строки символов с нулевым значением (Юникод). В любом случае строка преобразуется в Юникод BSTR, выделенный с помощью `SysAllocString` . Тип `CComVariant` объекта будет VT_BSTR.

*бсрк*<br/>
окне **`bool`** Объект, назначаемый `CComVariant` объекту. **`bool`** Перед сохранением аргумент преобразуется в VARIANT_BOOL. Тип `CComVariant` объекта будет VT_BOOL.

*нсрк*<br/>
окне **`int`** Объект, Byte, **`short`** ,, **`long`** лонглонг, улонглонг, **`unsigned short`** , **`unsigned long`** или, **`unsigned int`** который должен быть назначен `CComVariant` объекту. Тип `CComVariant` объекта будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*флтсрк*<br/>
окне **`float`** Объект, назначаемый `CComVariant` объекту. Тип `CComVariant` объекта будет VT_R4.

*дблсрк*<br/>
окне **`double`** Объект, назначаемый `CComVariant` объекту. Тип `CComVariant` объекта будет VT_R8.

*цисрк*<br/>
окне `CY` Объект, назначаемый `CComVariant` объекту. Тип `CComVariant` объекта будет VT_CY.

*pSrc*<br/>
окне `IDispatch` Указатель или, `IUnknown` который должен быть назначен `CComVariant` объекту. `AddRef` будет вызываться для указателя интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN соответственно.

Или — указатель SAFEARRAY, назначаемый `CComVariant` объекту. Копия массива SAFEARRAY хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет сочетанием исходного типа массива SafeArray и VT_ARRAY.

*ксрк*<br/>
окне Символ, присваиваемый `CComVariant` объекту. Тип `CComVariant` объекта будет VT_I1.

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a> CComVariant::operator==

Указывает, `CComVariant` равен ли объект заданному варианту.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение и тип *варсрк* равны значению и типу, соответственно, `CComVariant` объекта. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значения типов Variant. Он сравнивает строки, целые числа и плавающие точки, но не массивы или записи.

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a> CComVariant::operator!=

Указывает, `CComVariant` не равен ли объект указанному варианту.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение или тип *варсрк* не равны значению или типу объекта, соответственно `CComVariant` . В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значения типов Variant. Он сравнивает строки, целые числа и плавающие точки, но не массивы или записи.

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a> CComVariant::operator &lt;

Указывает, `CComVariant` меньше ли объект, чем указанный вариант.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение `CComVariant` объекта меньше значения параметра *варсрк*. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a> CComVariant::operator &gt;

Указывает, `CComVariant` больше ли объект, чем указанный вариант.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение `CComVariant` объекта больше значения параметра *варсрк*. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a> CComVariant:: Реадфромстреам

Задает базовый вариант для варианта, содержащегося в указанном потоке.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке, содержащем данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream` требуется предыдущий вызов [вритетостреам](#writetostream).

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a> CComVariant:: Сетбиреф

Инициализирует `CComVariant` объект и задает `vt` для элемента значение VT_BYREF.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип VARIANT, например BSTR, **`int`** или **`char`** .

*Лутор*<br/>
Указатель, используемый для инициализации `CComVariant` объекта.

### <a name="remarks"></a>Примечания

`SetByRef` — Это шаблон функции, который инициализирует `CComVariant` объект по указателю *PT* и задает `vt` для элемента значение VT_BYREF. Пример:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a> CComVariant:: Вритетостреам

Сохраняет базовый вариант в потоке.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
