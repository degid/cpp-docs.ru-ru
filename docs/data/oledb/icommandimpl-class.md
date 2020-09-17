---
title: Класс ICommandImpl
ms.date: 11/04/2016
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
ms.openlocfilehash: c88554d717888719ad6d805a2871489ce4b0df32
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845592"
---
# <a name="icommandimpl-class"></a>Класс ICommandImpl

Предоставляет реализацию интерфейса [ICommand](/previous-versions/windows/desktop/ms709737(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `ICommandImpl` .

*коммандбасе*<br/>
Интерфейс команды. Значение по умолчанию — `ICommand`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Отмена](#cancel)|Отменяет текущее выполнение команды.|
|[канцелексекутион](#cancelexecution)|Отменяет текущее выполнение команды.|
|[CreateRowset](#createrowset)|Создает объект набора строк.|
|[Execute](#execute)|Выполняет команду.|
|[жетдбсессион](#getdbsession)|Возвращает указатель интерфейса на сеанс, создавший команду.|
|[ICommandImpl](#icommandimpl)|Конструктор.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_bCancel](#bcancel)|Указывает, должна ли команда быть отменена.|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|Указывает, должна ли команда быть отменена при выполнении.|
|[m_bIsExecuting](#bisexecuting)|Указывает, выполняется ли в данный момент команда.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс для объекта Command.

## <a name="icommandimplcancel"></a><a name="cancel"></a> ICommandImpl:: Cancel

Отменяет текущее выполнение команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>Примечания

См. раздел [ICommand:: Cancel](/previous-versions/windows/desktop/ms714402(v=vs.85)) в *справочнике по OLE DB программиста*.

## <a name="icommandimplcancelexecution"></a><a name="cancelexecution"></a> ICommandImpl:: Канцелексекутион

Отменяет текущее выполнение команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CancelExecution();
```

## <a name="icommandimplcreaterowset"></a><a name="createrowset"></a> ICommandImpl:: CreateRowset

Вызывается инструкцией [EXECUTE](../../data/oledb/icommandimpl-execute.md) для создания одного набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>Параметры

*RowsetClass*<br/>
Член класса шаблона, представляющий класс набора строк пользователя. Обычно создается мастером.

*пункаутер*<br/>
окне Указатель на управляющий `IUnknown` интерфейс, если набор строк создается как часть статистического выражения; в противном случае — значение null.

*riid*<br/>
окне Соответствует *riid* в `ICommand::Execute` .

*ппарамс*<br/>
[вход/выход] Соответствует *ппарамс* в `ICommand::Execute` .

*пкровсаффектед*<br/>
Соответствует *пкровсаффектед* в `ICommand::Execute` .

*ppRowset*<br/>
[вход/выход] Соответствует *ппровсет* в `ICommand::Execute` .

*провсетобж*<br/>
заполняет Указатель на объект набора строк. Обычно этот параметр не используется, но его можно использовать, если необходимо выполнить больше работы над набором строк перед передачей его в COM-объект. Время существования *провсетобж* привязывается *ппровсет*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. `ICommand::Execute`Список типичных значений см. в разделе.

### <a name="remarks"></a>Примечания

Чтобы создать более одного набора строк или предоставить собственные условия для создания различных наборов строк, разместите разные вызовы `CreateRowset` из в `Execute` .

См. раздел [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) в *справочнике по OLE DB программиста.*

## <a name="icommandimplexecute"></a><a name="execute"></a> ICommandImpl:: Execute

Выполняет команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Execute(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) в *справочнике по OLE DB программиста*.

### <a name="remarks"></a>Примечания

Запрошенный исходящий интерфейс будет интерфейсом, полученным из объекта набора строк, создаваемого этой функцией.

`Execute` вызывает [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Переопределите реализацию по умолчанию, чтобы создать более одного набора строк или предоставить собственные условия для создания различных наборов строк.

## <a name="icommandimplgetdbsession"></a><a name="getdbsession"></a> ICommandImpl:: Жетдбсессион

Возвращает указатель интерфейса на сеанс, создавший команду.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>Параметры

См. раздел [ICommand:: жетдбсессион](/previous-versions/windows/desktop/ms719622(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Полезно для получения свойств из сеанса.

## <a name="icommandimplicommandimpl"></a><a name="icommandimpl"></a> ICommandImpl:: ICommandImpl

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
ICommandImpl();
```

## <a name="icommandimplm_bcancel"></a><a name="bcancel"></a> ICommandImpl:: m_bCancel

Указывает, отменена ли команда.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>Примечания

Эту переменную можно получить в `Execute` методе класса Command и при необходимости отменить.

## <a name="icommandimplm_bcancelwhenexecuting"></a><a name="bcancelwhenexecuting"></a> ICommandImpl:: m_bCancelWhenExecuting

Указывает, может ли команда быть отменена при выполнении.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>Примечания

Значение по умолчанию — **`true`** (может быть отменено).

## <a name="icommandimplm_bisexecuting"></a><a name="bisexecuting"></a> ICommandImpl:: m_bIsExecuting

Указывает, выполняется ли в данный момент команда.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>Примечания

`Execute`Метод класса Command может присвоить этой переменной значение **`true`** .

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
