---
title: Класс ICommandTextImpl
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: 8d435cd8c5c8723d008be98482631f081c967058
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845124"
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl

Предоставляет реализацию для интерфейса [ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс команды, производный от `ICommandTextImpl` .

## <a name="requirements"></a>Требования

**Заголовок:** алтдб.h

## <a name="members"></a>Элементы

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[жеткоммандтекст](#getcommandtext)|Возвращает текстовую команду, заданную последним вызовом метода [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|
|[SetCommandText](#setcommandtext)|Задает текст команды, заменяя существующий текст команды.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_strCommandText](#strcommandtext)|Сохраняет текст команды.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс для команд.

## <a name="icommandtextimplgetcommandtext"></a><a name="getcommandtext"></a> ICommandTextImpl:: Жеткоммандтекст

Возвращает текстовую команду, заданную последним вызовом метода [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommandText:: жеткоммандтекст](/previous-versions/windows/desktop/ms709825(v=vs.85)) в *справочнике программиста OLE DB*. По умолчанию параметр *пгуиддиалект* игнорируется.

## <a name="icommandtextimplsetcommandtext"></a><a name="setcommandtext"></a> ICommandTextImpl:: SetCommandText

Задает текст команды, заменяя существующий текст команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="icommandtextimplm_strcommandtext"></a><a name="strcommandtext"></a> ICommandTextImpl:: m_strCommandText

Сохраняет текстовую строку команды.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
