---
title: IPersistStreamInitImpl класс
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: 0d6ac4639ac0cfb97416ca80b7a2ec3903d7b8e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326463"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl класс

Этот класс `IUnknown` реализует и обеспечивает реализацию интерфейса [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) по умолчанию.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPersistStreamInitImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Извлекает CLSID объекта.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Извлекает размер потока, необходимый для сохранения данных объекта. Реализация ATL возвращает E_NOTIMPL.|
|[IPersistStreamInitImpl::InitNew](#initnew)|Инициализирует вновь созданный объект.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Проверяет, изменились ли данные объекта с момента его последнего сохранения.|
|[IPersistStreamInitImpl::Load](#load)|Загружает свойства объекта из указанного потока.|
|[IPersistStreamInitImpl::Сохранить](#save)|Сохраняет свойства объекта в указанном потоке.|

## <a name="remarks"></a>Примечания

Интерфейс [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) позволяет клиенту запрашивать, чтобы ваш объект загружал и сохраняет свои постоянные данные в одном потоке. Класс `IPersistStreamInitImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a>IPersistStreamInitImpl::GetClassID

Извлекает CLSID объекта.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Примечания

Смотрите [IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a>IPersistStreamInitImpl::GetSizeMax

Извлекает размер потока, необходимый для сохранения данных объекта.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPersistStreamInit::GetSizeMax](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) в Windows SDK.

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a>IPersistStreamInitImpl::InitNew

Инициализирует вновь созданный объект.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Примечания

Смотрите [IPersistStreamInit::InitNew](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) в Windows SDK.

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a>IPersistStreamInitImpl::IsDirty

Проверяет, изменились ли данные объекта с момента его последнего сохранения.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Примечания

Смотрите [IPersistStreamInit::Грязный](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) в Windows SDK.

## <a name="ipersiststreaminitimplload"></a><a name="load"></a>IPersistStreamInitImpl::Load

Загружает свойства объекта из указанного потока.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для получения этой информации.

Смотрите [IPersistStreamInit::Загрузка](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) в Windows SDK.

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a>IPersistStreamInitImpl::Сохранить

Сохраняет свойства объекта в указанном потоке.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для хранения этой информации.

Смотрите [IPersistStreamInit::Сохранить](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Хранилища и потоки](/windows/win32/Stg/storages-and-streams)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
