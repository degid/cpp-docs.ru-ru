---
title: Класс CEnumerator
ms.date: 11/04/2016
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
ms.openlocfilehash: f3e3a61028768144cbef17912952622f19ad0242
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838156"
---
# <a name="cenumerator-class"></a>Класс CEnumerator

Использует объект перечислителя OLE DB, который предоставляет интерфейс [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) для возврата набора строк, описывающего все источники данных и перечислители.

## <a name="syntax"></a>Синтаксис

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Поиск](#find)|Выполняет поиск по доступным поставщикам (источникам данных), ищут один из них с указанным именем.|
|[Моникер](#getmoniker)|Извлекает `IMoniker` интерфейс для текущей записи.|
|[Открыть](#open)|Открывает перечислитель.|

## <a name="remarks"></a>Примечания

Данные можно извлекать `ISourcesRowset` косвенно из этого класса.

## <a name="cenumeratorfind"></a><a name="find"></a> CEnumerator:: Find

Ищет указанное имя между доступными поставщиками.

### <a name="syntax"></a>Синтаксис

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>Параметры

*сзсеарчнаме*<br/>
окне Искомое имя.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если имя было найдено. В противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Это имя сопоставляется с `SOURCES_NAME` членом интерфейса [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) .

## <a name="cenumeratorgetmoniker"></a><a name="getmoniker"></a> CEnumerator:: моникер

Анализирует отображаемое имя, чтобы извлечь компонент строки, который можно преобразовать в моникер.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker,
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>Параметры

*ппмоникер*<br/>
заполняет Моникер, проанализированный из отображаемого имени ([CEnumeratorAccessor:: m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) текущей строки.

*лпсздисплайнаме*<br/>
окне Отображаемое имя для синтаксического анализа.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cenumeratoropen"></a><a name="open"></a> CEnumerator:: Open

Привязывает моникер для перечислителя, если он указан, а затем получает набор строк для перечислителя путем вызова [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>Параметры

*пмоникер*<br/>
окне Указатель на моникер для перечислителя.

*пклсид*<br/>
окне Указатель на `CLSID` перечислитель.

*Перечислитель*<br/>
окне Ссылка на перечислитель.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
