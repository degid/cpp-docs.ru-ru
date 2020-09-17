---
title: Класс CComCoClass
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: 11e724a982f3a2f404473dbdd34d848842cc8e14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320819"
---
# <a name="ccomcoclass-class"></a>Класс CComCoClass

Этот класс предоставляет методы для создания экземпляров класса и получения его свойств.

## <a name="syntax"></a>Синтаксис

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `CComCoClass`.

*пклид*<br/>
Указатель на CLSID объекта.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCoClass::СозданиеInstance](#createinstance)|(Статик) Создает экземпляр класса и запросы для интерфейса.|
|[CComCoClass::Ошибка](#error)|(Статик) Возвращает клиенту богатую информацию об ошибках.|
|[CComCoClass:GetObjectCLSID](#getobjectclsid)|(Статик) Возвращает идентификатор класса объекта.|
|[CComCoClass::GetObjectОписание](#getobjectdescription)|(Статик) Переопределение, чтобы вернуть описание объекта.|

## <a name="remarks"></a>Примечания

`CComCoClass`предоставляет методы для извлечения CLSID объекта, настройки информации об ошибках и создания экземпляров класса. Любой класс, зарегистрированный на карте `CComCoClass`объектов, должен быть выведен из.

`CComCoClass`также определяет фабрику класса по умолчанию и модель агрегации для объекта. `CComCoClass`использует следующие два макроса:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) Объявляет фабрику класса [CComClassFactory.](../../atl/reference/ccomclassfactory-class.md)

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) Заявляет, что ваш объект может быть агрегирован.

Вы можете переопределить любой из этих по умолчанию, указав другой макрос в определении класса. Например, использовать [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) `CComClassFactory`вместо , указать [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макрос:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomcoclasscreateinstance"></a><a name="createinstance"></a>CComCoClass::СозданиеInstance

Используйте `CreateInstance` эти функции для создания экземпляра объекта COM и получения указателя интерфейса без использования COM API.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
Интерфейс COM, который должен быть возвращен через *pp*.

*панкУтер*<br/>
(в) Внешний неизвестный или контролирующий неизвестный агрегат.

*Pp*<br/>
(ваут) Адрес переменной указателя, которая получает запрашиваемый указатель интерфейса, если создание успешно.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. См [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) в SDK Windows для описания возможных значений возврата.

### <a name="remarks"></a>Примечания

Используйте первую перегрузку этой функции для создания типичных объектов; использовать вторую перегрузку, когда вам нужно агрегировать создаваемый объект.

Класс ATL, реализующий необходимый объект COM (т.е. класс, используемый в качестве первого параметра шаблона [для CComCoClass),](../../atl/reference/ccomcoclass-class.md)должен находиться в том же проекте, что и код вызова. Создание объекта COM осуществляется фабрикой класса, зарегистрированной для этого класса ATL.

Эти функции полезны для создания объектов, которые вы не допустили от внешнего создания с помощью [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) макроса. Они также полезны в ситуациях, когда вы хотите избежать COM API по причинам эффективности.

Обратите внимание, что интерфейс *должен* иметь IID, связанный с ним, который может быть извлечен с помощью [оператора __uuidof.](../../cpp/uuidof-operator.md)

### <a name="example"></a>Пример

В следующем примере `CDocument` — это класс ATL, `CComCoClass` созданный `IDocument` мастером, полученный из реализации интерфейса. Класс зарегистрирован на карте объектов с OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO макроса, поэтому клиенты не могут создавать экземпляры документа с помощью [CoCreateInstance.](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) `CApplication`— это CoClass, предоставляющий метод на одном из своих интерфейсов COM для создания экземпляров класса документов. Приведенный ниже код показывает, насколько легко создавать экземпляры класса документов с помощью `CreateInstance` элемента, унаследованного от базового `CComCoClass` класса.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

## <a name="ccomcoclasserror"></a><a name="error"></a>CComCoClass::Ошибка

Эта статическая функция `IErrorInfo` настраивает интерфейс для предоставления клиенту информации об ошибках.

```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>Параметры

*lpszDesc*<br/>
(в) Строка, описывающая ошибку. Версия Unicode `Error` указывает, что *lpszDesc* имеет тип LPCOLESTR; версия ANSI определяет тип LPCSTR.

*Iid*<br/>
(в) IID интерфейса, определяющий ошибку или GUID_NULL (значение по умолчанию), если ошибка определена операционной системой.

*hRes*<br/>
(в) HRESULT вы хотите вернуться к вызывающему абоненту. Значение по умолчанию — 0. Для получения более подробной информации о *hRes,* см.

*nID*<br/>
(в) Идентификатор ресурса, в котором хранится строка описания ошибок. Это значение должно лежать между 0x0200 и 0xFFFF, включительно. В отладке сборки, **ASSERT** приведет, если *nID* не индексирует действительную строку. В сборках релизов строка описания ошибок будет установлена на "Неизвестная ошибка".

*dwHelpID*<br/>
(в) Идентификатор контекста справки для ошибки.

*lpszHelpFile*<br/>
(в) Путь и имя файла справки, описывающие ошибку.

*hInst*<br/>
(в) Ручка к ресурсу. По умолчанию этот `_AtlModule::GetResourceInstance`параметр находится где `_AtlModule` находится глобальный экземпляр [CAtlModule](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Для `Error`вызова объект должен `ISupportErrorInfo Interface` реализовать интерфейс.

Если параметр *hRes* незеро, то `Error` возвращает значение *hRes.* Если *hRes* равен нулю, `Error` то первые четыре версии возврата DISP_E_EXCEPTION. Последние две версии возвращают результат **макро-MAKE_HRESULT (1, FACILITY_ITF,** *nID).* **)**

## <a name="ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>CComCoClass:GetObjectCLSID

Обеспечивает последовательный способ извлечения CLSID объекта.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор класса объекта.

## <a name="ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>CComCoClass::GetObjectОписание

Эта статическая функция получает текстовое описание для объекта класса.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Возвращаемое значение

Описание объекта класса.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает NULL. Этот метод можно переопределить с помощью [макроса DECLARE_OBJECT_DESCRIPTION.](object-map-macros.md#declare_object_description) Пример:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription`называется `IComponentRegistrar::GetComponents`. `IComponentRegistrar`— это интерфейс автоматизации, позволяющий регистрировать и отменять отдельные компоненты в DLL. При создании объекта регистратора компонентов с помощью AtL Project Wizard `IComponentRegistrar` мастер автоматически реализует интерфейс. `IComponentRegistrar`обычно используется сервером транзакций Майкрософт.

Для получения дополнительной информации о ATL [Creating an ATL Project](../../atl/reference/creating-an-atl-project.md)проект Мастера, см.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
