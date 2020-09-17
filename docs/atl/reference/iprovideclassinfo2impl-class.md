---
title: IProvideClassInfo2Impl класс
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: 0d1ee9acc1cfabc71ecf33fcb5919d826899c671
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329568"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl класс

Этот класс обеспечивает реализацию по умолчанию методов [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) и [IProvideClassInfo2.](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2)

## <a name="syntax"></a>Синтаксис

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Параметры

*пкоксид*<br/>
Указатель на идентификатор кокласса.

*psrcid*<br/>
Указатель на идентификатор для исходящего дистипа кокласса по умолчанию.

*плибид*<br/>
Указатель на LIBID библиотеки типов, содержащей информацию об интерфейсе. По умолчанию библиотека типа сервера передается.

*wMajor*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*wMinor*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*<br/>
Класс используется для управления информацией типа coclass. Значение по умолчанию — `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Извлекает `ITypeInfo` указатель на информацию типа coclass.|
|[IProvideClassinfo2Impl::GetGUID](#getguid)|Извлекает GUID для исходящего дисинтерфейса объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Управляет информацией типа для coclass.|

## <a name="remarks"></a>Примечания

Интерфейс [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) расширяет [IProvideClassInfo,](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) `GetGUID` добавляя метод. Этот метод позволяет клиенту получить исходящий IID интерфейса объекта для набора событий по умолчанию. Класс `IProvideClassInfo2Impl` обеспечивает реализацию `IProvideClassInfo` и `IProvideClassInfo2` методы по умолчанию.

`IProvideClassInfo2Impl`содержит статический член `CComTypeInfoHolder` типа, который управляет информацией типа для coclass.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo

Извлекает `ITypeInfo` указатель на информацию типа coclass.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

Смотрите [IProvideClassInfo::GetClassInfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) в Windows SDK.

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a>IProvideClassinfo2Impl::GetGUID

Извлекает GUID для исходящего дисинтерфейса объекта.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Примечания

Смотрите [IProvideClassInfo2::GetGUID](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) в Windows SDK.

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl

Конструктор.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Примечания

Вызывает `AddRef` [_tih](#_tih) члена. Деструктор вызывает `Release`.

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a>IProvideClassInfo2Impl::_tih

Этот элемент статического данных является экземпляром параметра шаблона класса, *tihclass*, который по умолчанию является `CComTypeInfoHolder`.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Примечания

`_tih`управляет информацией типа для coclass.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
