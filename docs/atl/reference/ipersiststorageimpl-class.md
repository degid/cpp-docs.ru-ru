---
title: IPersistStorageImpl Класс
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: b235b190f237293932705e4d290ac963088722f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326468"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl Класс

Этот класс реализует интерфейс [IPersistStorage.](/windows/win32/api/objidl/nn-objidl-ipersiststorage)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPersistStorageImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPersistStorageImpl::GetClassID](#getclassid)|Извлекает CLSID объекта.|
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Поручает объекту освободить все объекты хранения и войти в режим HandsOff. Реализация ATL возвращает S_OK.|
|[IPersistStorageImpl::InitNew](#initnew)|Инициализирует новое хранилище.|
|[IPersistStorageImpl::IsDirty](#isdirty)|Проверяет, изменились ли данные объекта с момента его последнего сохранения.|
|[IPersistStorageImpl::Load](#load)|Загружает свойства объекта из указанного хранилища.|
|[IPersistStorageImpl::Сохранить](#save)|Сохраняет свойства объекта в указанном хранилище.|
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Уведомляет объект о том, что он может вернуться в обычный режим для записи на объект хранения. Реализация ATL возвращает S_OK.|

## <a name="remarks"></a>Примечания

`IPersistStorageImpl`реализует интерфейс [IPersistStorage,](/windows/win32/api/objidl/nn-objidl-ipersiststorage) который позволяет клиенту запросить загрузку объекта и сохранить его постоянные данные с помощью хранилища.

Реализация этого класса требует `T` класса, чтобы `IPersistStreamInit` сделать `QueryInterface`реализацию интерфейса доступной через . Обычно это означает, что `T` класс должен происходить от [IPersistStreamInitImpl,](../../atl/reference/ipersiststreaminitimpl-class.md)обеспечивать запись на `IPersistStreamInit` карте [COM](com-map-macros.md)и использовать карту [свойств](property-map-macros.md) для описания постоянных данных класса.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a>IPersistStorageImpl::GetClassID

Извлекает CLSID объекта.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Примечания

Смотрите [IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage

Поручает объекту освободить все объекты хранения и войти в режим HandsOff.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IPersistStorage::HandsOffStorage](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) в Windows SDK.

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistStorageImpl::InitNew

Инициализирует новое хранилище.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>Примечания

Реализация ATL делегирует интерфейс [IPersistStreamInit.](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)

Смотрите [IPersistStorage:InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) в Windows SDK.

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistStorageImpl::IsDirty

Проверяет, изменились ли данные объекта с момента его последнего сохранения.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>Примечания

Реализация ATL делегирует интерфейс [IPersistStreamInit.](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)

Смотрите [IPersistStorage:IsDirty](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) в Windows SDK.

## <a name="ipersiststorageimplload"></a><a name="load"></a>IPersistStorageImpl::Load

Загружает свойства объекта из указанного хранилища.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>Примечания

Реализация ATL делегирует интерфейс [IPersistStreamInit.](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) `Load`использует поток под названием "Содержимое" для извлечения данных объекта. Метод [Сохранения](#save) изначально создает этот поток.

Смотрите [IPersistStorage: Загрузите](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) в Windows SDK.

## <a name="ipersiststorageimplsave"></a><a name="save"></a>IPersistStorageImpl::Сохранить

Сохраняет свойства объекта в указанном хранилище.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>Примечания

Реализация ATL делегирует интерфейс [IPersistStreamInit.](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) Когда `Save` он впервые вызывается, он создает поток под названием "Содержимое" на указанном хранилище. Этот поток затем используется в `Save` последующих вызовах и в вызовах [к Загрузке.](#load)

Смотрите [IPersistStorage:Сохранить](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) в Windows SDK.

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted

Уведомляет объект о том, что он может вернуться в обычный режим для записи на объект хранения.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IPersistStorage:СохранитьЗавершено](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Хранилища и потоки](/windows/win32/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl класс](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl Класс](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
