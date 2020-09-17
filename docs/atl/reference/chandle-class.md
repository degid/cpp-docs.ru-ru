---
title: Класс CHandle
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 4b883bdf3159c40f8d74866f04f655ae73d82a8a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747692"
---
# <a name="chandle-class"></a>Класс CHandle

Этот класс предоставляет методы для создания и использования объекта рукоятки.

## <a name="syntax"></a>Синтаксис

```
class CHandle
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|Конструктор.|
|[CHandle:::»CHandle](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHandle::Attach](#attach)|Вызовите этот `CHandle` метод, чтобы прикрепить объект к существующей ручке.|
|[CHandle::Закрыть](#close)|Вызовите этот `CHandle` метод, чтобы закрыть объект.|
|[CHandle::Detach](#detach)|Вызовите этот метод, чтобы `CHandle` отделить ручку от объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CHandle::оператор HANDLE](#operator_handle)|Возвращает значение сохраненной ручки.|
|[CHandle::оператор](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CHandle::m_h](#m_h)|Переменная участника, которая хранит ручку.|

## <a name="remarks"></a>Примечания

Объект `CHandle` может использоваться всякий раз, когда требуется `CHandle` ручка: основное отличие состоит в том, что объект будет автоматически удален.

> [!NOTE]
> Некоторые функции API будут использовать NULL как пустую или недействительную ручку, в то время как другие — INVALID_HANDLE_VALUE. `CHandle`использует только NULL и будет рассматривать INVALID_HANDLE_VALUE как реальную ручку. Если вы вызываете API, который может вернуть INVALID_HANDLE_VALUE, вы должны проверить это значение, прежде чем звонить [CHandle::Attach](#attach) или передать его `CHandle` конструктору, и вместо этого передать NULL.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="chandleattach"></a><a name="attach"></a>CHandle::Attach

Вызовите этот `CHandle` метод, чтобы прикрепить объект к существующей ручке.

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>Параметры

*H*<br/>
`CHandle`возьмет на себя ответственность за ручку *h*.

### <a name="remarks"></a>Примечания

Присваивает `CHandle` объект ручке *h,* а затем вызывает **h.Detach ()**. В сборках отладок, ATLASSERT будет поднят, если *ч* является NULL. Никакой другой проверки достоверности ручки не производится.

## <a name="chandlechandle"></a><a name="chandle"></a>CHandle::CHandle

Конструктор.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>Параметры

*H*<br/>
Существующая ручка или `CHandle`.

### <a name="remarks"></a>Примечания

Создает новый `CHandle` объект, по желанию `CHandle` используя существующую ручку или объект.

## <a name="chandlechandle"></a><a name="dtor"></a>CHandle:::»CHandle

Деструктор

```
~CHandle() throw();
```

### <a name="remarks"></a>Примечания

Освобождает `CHandle` объект, позвонив [CHandle::Закрыть](#close).

## <a name="chandleclose"></a><a name="close"></a>CHandle::Закрыть

Вызовите этот `CHandle` метод, чтобы закрыть объект.

```cpp
void Close() throw();
```

### <a name="remarks"></a>Примечания

Закрывает открытую ручку объекта. Если ручка NULL, что будет `Close` в случае, если уже вызвано, ATLASSERT будет поднят в отладке сборки.

## <a name="chandledetach"></a><a name="detach"></a>CHandle::Detach

Вызовите этот метод, чтобы `CHandle` отделить ручку от объекта.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает отсоединиваемую ручку.

### <a name="remarks"></a>Примечания

Выпускает право собственности на рукоятку.

## <a name="chandlem_h"></a><a name="m_h"></a>CHandle::m_h

Переменная участника, которая хранит ручку.

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a>CHandle::оператор

Оператор назначения.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>Параметры

*H*<br/>
`CHandle`возьмет на себя ответственность за ручку *h*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CHandle` новый объект.

### <a name="remarks"></a>Примечания

Если `CHandle` объект в настоящее время содержит ручку, он будет закрыт. Объект, `CHandle` передаваемый в будет иметь свою ручку ссылки на NULL. Это гарантирует, `CHandle` что два объекта никогда не будут содержать одну и ту же активную ручку.

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a>CHandle::оператор HANDLE

Возвращает значение сохраненной ручки.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение, хранящееся в [CHandle::m_h](#m_h).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
