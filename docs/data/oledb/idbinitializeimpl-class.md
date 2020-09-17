---
title: Класс IDBInitializeImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
ms.openlocfilehash: aff02e812d2806201a08164aeb4a8ef290550725
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845540"
---
# <a name="idbinitializeimpl-class"></a>Класс IDBInitializeImpl

Предоставляет реализацию для интерфейса [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IDBInitializeImpl` .

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[идбинитиализеимпл](#idbinitializeimpl)|Конструктор.|

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[Устанавливает](#initialize)|Запускает поставщик.|
|[Отменить инициализацию](#uninitialize)|Останавливает поставщик.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_dwStatus](#dwstatus)|Флаги источника данных.|
|[m_pCUtlPropInfo](#pcutlpropinfo)|Указатель на реализацию свойств базы данных.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс для объектов источника данных и необязательный интерфейс для перечислителей.

## <a name="idbinitializeimplidbinitializeimpl"></a><a name="idbinitializeimpl"></a> Идбинитиализеимпл:: Идбинитиализеимпл

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>Примечания

Инициализирует все элементы данных.

## <a name="idbinitializeimplinitialize"></a><a name="initialize"></a> Идбинитиализеимпл:: Initialize

Инициализирует объект источника данных, подготавливая поддержку его свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>Примечания

См. раздел [IDBInitialize:: Initialize](/previous-versions/windows/desktop/ms718026(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="idbinitializeimpluninitialize"></a><a name="uninitialize"></a> Идбинитиализеимпл:: Uninitialize

Помещает объект источника данных в неинициализированное состояние путем освобождения внутренних ресурсов, таких как поддержка свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>Примечания

См. раздел [IDBInitialize:: Uninitialize](/previous-versions/windows/desktop/ms719648(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="idbinitializeimplm_dwstatus"></a><a name="dwstatus"></a> Идбинитиализеимпл:: m_dwStatus

Флаги источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD m_dwStatus;
```

### <a name="remarks"></a>Примечания

Эти флаги указывают или указывают состояние различных атрибутов для объекта источника данных. Содержит одно или несколько из следующих **`enum`** значений:

```cpp
enum DATASOURCE_FLAGS {
    DSF_MASK_INIT     = 0xFFFFF00F,
    DSF_PERSIST_DIRTY = 0x00000001,
    DSF_INITIALIZED   = 0x00000010,
};
```

| Значение | Описание |
|-|-|
|`DSF_MASK_INIT`|Маска для включения восстановления неинициализированного состояния.|
|`DSF_PERSIST_DIRTY`|Задайте значение, если для объекта источника данных требуется сохраняемость (т. е., если были внесены изменения).|
|`DSF_INITIALIZED`|Установите, если источник данных был инициализирован.|

## <a name="idbinitializeimplm_pcutlpropinfo"></a><a name="pcutlpropinfo"></a> Идбинитиализеимпл:: m_pCUtlPropInfo

Указатель на объект реализации со сведениями о свойствах базы данных.

### <a name="syntax"></a>Синтаксис

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
