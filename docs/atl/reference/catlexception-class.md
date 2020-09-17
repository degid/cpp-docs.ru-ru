---
title: Класс Катлексцептион
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: f09d9b2f46233cf356f5ade8a5b90e08a213d276
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168206"
---
# <a name="catlexception-class"></a>Класс Катлексцептион

Этот класс определяет исключение ATL.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлексцептион:: Катлексцептион](#catlexception)|Конструктор.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Катлексцептион::operator HRESULT](#operator_hresult)|Приводит текущий объект к значению HRESULT.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Катлексцептион:: m_hr](#m_hr)|Переменная типа HRESULT, созданная объектом и используемая для хранения условия ошибки.|

## <a name="remarks"></a>Примечания

`CAtlException` Объект представляет условие исключения, связанное с операцией ATL. `CAtlException` Класс включает открытый элемент данных, в котором хранится код состояния, указывающий причину исключения, и оператор приведения, позволяющий обрабатывать исключение так, как если бы это был HRESULT.

В целом, вместо создания `AtlThrow` `CAtlException` объекта напрямую будет вызываться.

## <a name="requirements"></a>Требования

**Заголовок:** атлексцепт.h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>Катлексцептион:: Катлексцептион

Конструктор.

```cpp
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Параметры

*hr*<br/>
Код ошибки HRESULT.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>Катлексцептион::operator HRESULT

Приводит текущий объект к значению HRESULT.

```cpp
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>Катлексцептион:: m_hr

Элемент данных HRESULT.

```cpp
HRESULT m_hr;
```

### <a name="remarks"></a>Примечания

Элемент данных, в котором хранится условие ошибки. Значение HRESULT задается конструктором [катлексцептион:: катлексцептион](#catlexception).

## <a name="see-also"></a>См. также

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
