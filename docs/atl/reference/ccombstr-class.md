---
title: Класс CComBSTR
ms.date: 11/04/2016
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: c1448a5638b263a87403edf0baca170f0f952e26
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748134"
---
# <a name="ccombstr-class"></a>Класс CComBSTR

Этот класс является оберткой для [BSTR](/previous-versions/windows/desktop/automat/bstr)s.

## <a name="syntax"></a>Синтаксис

```
class CComBSTR
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|Конструктор.|
|[CComBSTR:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::Приложение](#append)|Приложения строки `m_str`к .|
|[CComBSTR::AppendBSTR](#appendbstr)|Приложения BSTR к `m_str`.|
|[CComBSTR::AppendBytes](#appendbytes)|Приложения определенное количество байтов к `m_str`.|
|[CComBSTR::ArraytoBSTR](#arraytobstr)|Создает BSTR из первого символа каждого элемента в safearray и прикрепляет его к объекту. `CComBSTR`|
|[CComBSTR::Назначить](#assignbstr)|Назначает BSTR . `m_str`|
|[CComBSTR:Attach](#attach)|Прикрепляет BSTR `CComBSTR` к объекту.|
|[CComBSTR:BSTRTOArray](#bstrtoarray)|Создает одномерный безопасный элемент с нулевым уровнем, где `CComBSTR` каждый элемент массива является символом объекта.|
|[CComBSTR:ByteLength](#bytelength)|Возвращает длину `m_str` байтов.|
|[CComBSTR:Copy](#copy)|Возвращает копию `m_str`.|
|[CComBSTR:Copyto](#copyto)|Возвращает копию `m_str` через параметр **«из»**|
|[CComBSTR: :Detach](#detach)|Отаяние `m_str` от `CComBSTR` объекта.|
|[CComBSTR::Пустой](#empty)|Бесплатно `m_str`.|
|[CComBSTR:Длина](#length)|Возвращает длину `m_str`.|
|[CComBSTR::LoadString](#loadstring)|Загружает ресурс строки.|
|[CComBSTR::ReadFromStream](#readfromstream)|Загружает объект BSTR из потока.|
|[CComBSTR:Tolower](#tolower)|Преобразует строку в нижний регистр.|
|[CComBSTR::Toupper](#toupper)|Преобразует строку в верхний регистр.|
|[CComBSTR::WriteTostream](#writetostream)|Сохраняет `m_str` поток.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::оператор BSTR](#operator_bstr)|Отбрасывает `CComBSTR` объект в BSTR.|
|[CComBSTR:Оператор !](#operator_not)|Возвращает TRUE или FALSE, `m_str`в зависимости от того, является ли NULL.|
|[CComBSTR::оператор !](#operator_neq)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR::оператор &](#operator_amp)|Возвращает адрес `m_str`.|
|[CComBSTR:оператор](#operator_add_eq)|Придатки `CComBSTR` к объекту.|
|[CComBSTR::оператор <](#operator_lt)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR:оператор](#operator_eq)|Присваивает `m_str`значение.|
|[CComBSTR:оператор](#operator_eq_eq)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR::оператор >](#operator_gt)|Сравнивает `CComBSTR` со строкой.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|Содержит BSTR, связанный с объектом. `CComBSTR`|

## <a name="remarks"></a>Примечания

Класс `CComBSTR` представляет собой обертку для BST, которые являются длинн-фиксированными строками. Длина хранится в виде целых в месте памяти, предшествующем данным в строке.

[BSTR](/previous-versions/windows/desktop/automat/bstr) непрекращается после последнего подсчитанного символа, но может также содержать нулевые символы, встроенные в строку. Длина строки определяется количеством символов, а не первым нулевым персонажем.

> [!NOTE]
> Класс `CComBSTR` предоставляет ряд членов (конструкторов, операторов назначения и операторов сравнения), которые берут в качестве аргументов строки ANSI или Unicode. Версии anSI этих функций менее эффективны, чем их аналоги Unicode, поскольку временные строки Unicode часто создаются внутри компании. Для повышения эффективности, используйте версии Unicode, где это возможно.

> [!NOTE]
> Из-за улучшения поведения поиска, реализованного в Visual `bstr = L"String2" + bstr;`Studio .NET, код, который, возможно, `bstr = CStringW(L"String2") + bstr`был составлен в предыдущих выпусках, должен быть реализован как .

Для списка предостережений при использовании, `CComBSTR`см [Программирование с CComBSTR](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccombstrappend"></a><a name="append"></a>CComBSTR::Приложение

Приложения либо *lpsz* или BSTR член *bstrSrc* [m_str](#m_str).

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
(в) Объект `CComBSTR` для придатка.

*Ch*<br/>
(в) Символ для придатка.

*lpsz*<br/>
(в) Строка символов с нулевым завершением. Вы можете передать строку Unicode через перегрузку LPCOLESTR или строку ANSI через версию LPCSTR.

*nЛен*<br/>
(в) Количество символов от *lpsz* до приложения.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

### <a name="remarks"></a>Примечания

Строка ANSI будет преобразована в Unicode перед приложением.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

## <a name="ccombstrappendbstr"></a><a name="appendbstr"></a>CComBSTR::AppendBSTR

Приложения указанного BSTR к [m_str](#m_str).

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) BSTR к придатку.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

### <a name="remarks"></a>Примечания

Не передайте этому методу обычную широкохарактерную строку. Компилятор не может поймать ошибку и ошибки времени выполнения будут происходить.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

## <a name="ccombstrappendbytes"></a><a name="appendbytes"></a>CComBSTR::AppendBytes

Приложения указанного количества байтов для [m_str](#m_str) без преобразования.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
(в) Указатель на массив байтов для придатка.

*P*<br/>
(в) Количество байтов для придатка.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

## <a name="ccombstrarraytobstr"></a><a name="arraytobstr"></a>CComBSTR::ArraytoBSTR

Освобождает любую существующую строку, удерживаемую в `CComBSTR` объекте, затем создает BSTR из первого `CComBSTR` символа каждого элемента в safearray и прикрепляет его к объекту.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Параметры

*Psrc*<br/>
(в) Безопасный, содержащий элементы, используемые для создания строки.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

## <a name="ccombstrassignbstr"></a><a name="assignbstr"></a>CComBSTR::Назначить

Назначает BSTR для [m_str](#m_str).

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
(в) BSTR для присвоения `CComBSTR` текущему объекту.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

## <a name="ccombstrattach"></a><a name="attach"></a>CComBSTR:Attach

Прикрепляет BSTR `CComBSTR` к объекту, установив [m_str](#m_str) членом *в src.*

```cpp
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) BSTR прикрепить к объекту.

### <a name="remarks"></a>Примечания

Не передайте этому методу обычную широкохарактерную строку. Компилятор не может поймать ошибку и ошибки времени выполнения будут происходить.

> [!NOTE]
> Этот метод будет `m_str` утверждать, если не является NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>CComBSTR:BSTRTOArray

Создает одномерный безопасный элемент с нулевым уровнем, где `CComBSTR` каждый элемент массива является символом объекта.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
(ваут) Указатель на safearray используется для удержания результатов функции.

### <a name="return-value"></a>Возвращаемое значение

S_OK на успех, или любое стандартное значение ошибки HRESULT.

## <a name="ccombstrbytelength"></a><a name="bytelength"></a>CComBSTR:ByteLength

Возвращает количество байтов `m_str`в, за исключением прекращающегося нулевого характера.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина [m_str](#m_str) члена в байтах.

### <a name="remarks"></a>Примечания

Возвращает 0, если `m_str` NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

## <a name="ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR::CComBSTR

Конструктор. Конструктор по умолчанию устанавливает [m_str](#m_str) член null.

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);
CComBSTR(REFGUID  guid);
CComBSTR(int nSize);
CComBSTR(int nSize, LPCOLESTR sz);
CComBSTR(int nSize, LPCSTR sz);
CComBSTR(LPCOLESTR pSrc);
CComBSTR(LPCSTR pSrc);
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
(в) Количество символов для копирования из *Sz* или первоначальный `CComBSTR`размер символов для .

*Sz*<br/>
[входные данные] Строка для копирования. Версия Unicode определяет LPCOLESTR; версия ANSI определяет LPCSTR.

*Psrc*<br/>
[входные данные] Строка для копирования. Версия Unicode определяет LPCOLESTR; версия ANSI определяет LPCSTR.

*src*<br/>
[входные данные] Объект `CComBSTR`.

*guid*<br/>
(в) Ссылка на `GUID` структуру.

### <a name="remarks"></a>Примечания

Конвейер копирования `m_str` устанавливается на копию члена BSTR *src*. Конструктор `REFGUID` преобразует GUID в строку, `StringFromGUID2` используя и хранит результат.

Другие конструкторы присваивают `m_str` копию указанной строки. Если вы передаете значение для *nSize,* то будут скопированы только символы *nSize,* а затем прекращающийся нулевой символ.

`CComBSTR` поддерживает семантику перемещения. Конструктор перемещения (принимающий ссылку rvalue (`&&`)) можно использовать, чтобы создать объект, который использует те же базовые данные, что и старый объект, передаваемый как аргумент, без необходимости копировать объект.

Деструктор освобождает строку, на которую указывает `m_str`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

## <a name="ccombstrccombstr"></a><a name="dtor"></a>CComBSTR:::

Деструктор

```
~CComBSTR();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает строку, на которую указывает `m_str`.

## <a name="ccombstrcopy"></a><a name="copy"></a>CComBSTR:Copy

Выделяет и возвращает копию `m_str`.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Копия члена [m_str.](#m_str) Если `m_str` NULL, возвращает NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

## <a name="ccombstrcopyto"></a><a name="copyto"></a>CComBSTR:Copyto

Выделяет и возвращает копию [m_str](#m_str) через параметр.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Параметры

*pbstr*<br/>
(ваут) Адрес BSTR, в котором можно вернуть строку, выделенную этим методом.

*pvarDest*<br/>
(ваут) Адрес VARIANT, в котором можно вернуть строку, выделенную этим методом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT, указывающее на успех или неудачу копии.

### <a name="remarks"></a>Примечания

После вызова этого метода, VARIANT указал на *pvarDest* будет типа VT_BSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

## <a name="ccombstrdetach"></a><a name="detach"></a>CComBSTR: :Detach

Отделожения [m_str](#m_str) `CComBSTR` от объекта `m_str` и устанавливает на NULL.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

BSTR, связанный `CComBSTR` с объектом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

## <a name="ccombstrempty"></a><a name="empty"></a>CComBSTR::Пустой

Освобождает [m_str](#m_str) члена.

```cpp
void Empty() throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

## <a name="ccombstrlength"></a><a name="length"></a>CComBSTR:Длина

Возвращает количество символов `m_str`в, исключая прекращающийся нулевой характер.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина [члена m_str.](#m_str)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

## <a name="ccombstrloadstring"></a><a name="loadstring"></a>CComBSTR::LoadString

Загружает ресурс строки, указанный *nID,* и хранит его в этом объекте.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Параметры

Смотрите [LoadString](/windows/win32/api/winuser/nf-winuser-loadstringw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если строка успешно загружена; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Примечания

Первая функция загружает ресурс из модуля, идентифицированного вами, через параметр *hInst.* Вторая функция загружает ресурс из ресурсного модуля, связанного с объектом, полученным в этом проекте, полученным [cComModule.](../../atl/reference/ccommodule-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

## <a name="ccombstrm_str"></a><a name="m_str"></a>CComBSTR::m_str

Содержит BSTR, связанный с объектом. `CComBSTR`

```
BSTR m_str;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

## <a name="ccombstroperator-bstr"></a><a name="operator_bstr"></a>CComBSTR::оператор BSTR

Отбрасывает `CComBSTR` объект в BSTR.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Примечания

Позволяет передавать `CComBSTR` объекты функциям, которые имеют параметры **BSTR.**

### <a name="example"></a>Пример

Смотрите пример [CComBSTR::m_str](#m_str).

## <a name="ccombstroperator-"></a><a name="operator_not"></a>CComBSTR:Оператор !

Проверяет, является ли строка BSTR NULL.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если [m_str](#m_str) член NULL; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот оператор проверяет только значение NULL, а не пустую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_neq"></a>CComBSTR::оператор !

Возвращает логическую противоположность [оператора](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[входные данные] Объект `CComBSTR`.

*pszSrc*<br/>
(в) Строка с нулевым завершением.

*nНулл*<br/>
(в) Должно быть, NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CComBSTR` элемент не равен объекту; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Примечания

`CComBSTR`s сравниваются текстово в контексте локального локального по умолчанию пользователя. Окончательный оператор сравнения просто сравнивает содержащуюся строку с NULL.

## <a name="ccombstroperator-amp"></a><a name="operator_amp"></a>CComBSTR:оператор&amp;

Возвращает адрес BSTR, хранящийся в [m_str](#m_str) члене.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Примечания

`CComBstr operator &`имеет специальное утверждение, связанное с ним, чтобы помочь определить утечки памяти. Программа будет утверждать, `m_str` когда участник инициализирован. Это утверждение было создано для определения `& operator` ситуаций, когда `m_str` программист использует для присвоения новому значению участнику без освобождения первого выделения `m_str`. Если `m_str` равняется NULL, программа предполагает, что m_str еще не выделен. В этом случае программа не будет утверждать.

Это утверждение не включено по умолчанию. Определите ATL_CCOMBSTR_ADDRESS_OF_ASSERT, чтобы включить это утверждение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_add_eq"></a>CComBSTR:оператор

Придаток строки `CComBSTR` к объекту.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
(в) Объект `CComBSTR` для придатка.

*pszSrc*<br/>
(в) Строка с нулевым завершением приложения.

### <a name="remarks"></a>Примечания

`CComBSTR`s сравниваются текстово в контексте локального локального по умолчанию пользователя. Сравнение LPCOLESTR осуществляется с использованием `memcmp` необработанных данных в каждой строке. Сравнение LPCSTR осуществляется таким же образом, как только была создана временная копия *PszSrc* Unicode. Окончательный оператор сравнения просто сравнивает содержащуюся строку с NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

## <a name="ccombstroperator-lt"></a><a name="operator_lt"></a>CComBSTR:оператор&lt;

Сравнивает `CComBSTR` со строкой.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CComBSTR` элемент меньше объекта; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Примечания

Сравнение выполняется с помощью локального по умолчанию пользователя.

## <a name="ccombstroperator-"></a><a name="operator_eq"></a>CComBSTR:оператор

Устанавливает [m_str](#m_str) членом копию *pSrc* или копию члена BSTR *src*. Оператор назначения перемещения `src` перемещается, не копируя его.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Примечания

Параметр *pSrc* определяет либо LPCOLESTR для версий Unicode, либо LPCSTR для версий ANSI.

### <a name="example"></a>Пример

Смотрите пример [cComBSTR::Copy](#copy).

## <a name="ccombstroperator-"></a><a name="operator_eq_eq"></a>CComBSTR:оператор

Сравнивает `CComBSTR` со строкой. `CComBSTR`s сравниваются текстово в контексте локального локального по умолчанию пользователя.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[входные данные] Объект `CComBSTR`.

*pszSrc*<br/>
(в) Строка с нулевым завершением.

*nНулл*<br/>
(в) Должно быть, NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CComBSTR` элемент равен объекту; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Примечания

Окончательный оператор сравнения просто сравнивает содержащуюся строку с NULL.

## <a name="ccombstroperator-gt"></a><a name="operator_gt"></a>CComBSTR:оператор&gt;

Сравнивает `CComBSTR` со строкой.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CComBSTR` элемент больше, чем объект; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Примечания

Сравнение выполняется с помощью локального по умолчанию пользователя.

## <a name="ccombstrreadfromstream"></a><a name="readfromstream"></a>CComBSTR::ReadFromStream

Устанавливает [m_str](#m_str) членом BSTR, содержащимся в указанном потоке.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке, содержащем данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream`требует, чтобы содержимое потока в текущем положении было совместимо с форматом данных, записанным по вызову [WriteToStream.](#writetostream)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

## <a name="ccombstrtolower"></a><a name="tolower"></a>CComBSTR:Tolower

Преобразует содержащуюся строку в нижний регистр.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительную информацию о том, как выполняется преобразование, можно `CharLowerBuff` ознакомиться.

## <a name="ccombstrtoupper"></a><a name="toupper"></a>CComBSTR::Toupper

Преобразует содержащуюся строку в верхний регистр.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительную информацию о том, как выполняется преобразование, можно `CharUpperBuff` ознакомиться.

## <a name="ccombstrwritetostream"></a><a name="writetostream"></a>CComBSTR::WriteTostream

Сохраняет [m_str](#m_str) участника потока.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вы можете воссоздать BSTR из содержимого потока с помощью функции [ReadFromStream.](#readfromstream)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[ATL и MFC String Преобразование Макрос](string-conversion-macros.md)
