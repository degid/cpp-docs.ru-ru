---
title: Класс CComGITPtr
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: 230eeb1577189d2057e530e1df8ef99c611fb32b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327838"
---
# <a name="ccomgitptr-class"></a>Класс CComGITPtr

Этот класс предоставляет методы работы с указателями интерфейсов и глобальной таблицей интерфейсов (GIT).

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя интерфейса, который будет храниться в GIT.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Конструктор.|
|[CComGITPtr:::CComGITPtr](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr:Attach](#attach)|Вызовите этот метод для регистрации указателя интерфейса в глобальной таблице интерфейсов (GIT).|
|[CComGITPtr:CopyTo](#copyto)|Вызовите этот метод, чтобы скопировать интерфейс от глобальной таблицы интерфейса (GIT) к пройденому указателю.|
|[CComGITPtr: :Detach](#detach)|Вызовите этот метод, чтобы `CComGITPtr` отделить интерфейс от объекта.|
|[CComGITPtr:GetCookie](#getcookie)|Вызовите этот метод, `CComGITPtr` чтобы вернуть файл cookie с объекта.|
|[CComGITPtr::Revoke](#revoke)|Вызовите этот метод, чтобы удалить интерфейс из глобальной таблицы интерфейса (GIT).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr::оператор DWORD](#operator_dword)|Возвращает файл cookie `CComGITPtr` с объекта.|
|[CComGITPtr::оператор](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Файл Cookie.|

## <a name="remarks"></a>Примечания

Объекты, которые агрегируют свободный поток маршала и должны использовать указатели интерфейса, полученные от других объектов, должны предпринять дополнительные шаги для обеспечения правильного маршала интерфейсов. Обычно это включает в себя хранение указателей интерфейса в GIT и получение указателя от GIT каждый раз, когда он используется. Класс `CComGITPtr` предоставляется, чтобы помочь вам использовать указатели интерфейса, хранящиеся в GIT.

> [!NOTE]
> Глобальная таблица интерфейса доступна только на Windows 95 с DCOM версии 1.1 и позже, Windows 98, Windows NT 4.0 с пакетом услуг 3 и позже, и Windows 2000.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomgitptrattach"></a><a name="attach"></a>CComGITPtr:Attach

Вызовите этот метод для регистрации указателя интерфейса в глобальной таблице интерфейсов (GIT).

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель интерфейса, который будет добавлен в GIT.

*dwCookie*<br/>
Файлы cookie, используемые для определения указателя интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

В отладке сборки возникает ошибка утверждения, если GIT недействителен, или если файл cookie равен NULL.

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a>CComGITPtr::CComGITPtr

Конструктор.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель интерфейса, который будет храниться в глобальной таблице интерфейса (GIT).

*Git*<br/>
(в) Ссылка на `CComGITPtr` существующий объект.

*dwCookie*<br/>
(в) Файлы cookie, используемые для идентификации указателя интерфейса.

*Rv*<br/>
(в) Объект `CComGITPtr` источника для перемещения данных с.

### <a name="remarks"></a>Примечания

Создает новый `CComGITPtr` объект, дополнительно `CComGITPtr` используя существующий объект.

Конструктор, используя *rv* является двигаться конструктор. Данные перемещаются из источника, *rv*, а затем *rv* очищается.

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a>CComGITPtr:::CComGITPtr

Деструктор

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Примечания

Удаляет интерфейс из глобальной таблицы интерфейса (GIT), используя [CComGITPtr::Revoke](#revoke).

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a>CComGITPtr:CopyTo

Вызовите этот метод, чтобы скопировать интерфейс от глобальной таблицы интерфейса (GIT) к пройденому указателю.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Параметры

*Pp*<br/>
Указатель, который должен получить интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Интерфейс из GIT скопирован в пройденый указатель. Указатель должен быть выпущен абонентом, когда он больше не требуется.

## <a name="ccomgitptrdetach"></a><a name="detach"></a>CComGITPtr: :Detach

Вызовите этот метод, чтобы `CComGITPtr` отделить интерфейс от объекта.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie `CComGITPtr` с объекта.

### <a name="remarks"></a>Примечания

Это до вызывающего абонента, чтобы удалить интерфейс из GIT, используя [CComGITPtr::Отмена](#revoke).

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a>CComGITPtr:GetCookie

Вызовите этот метод, `CComGITPtr` чтобы вернуть файл cookie с объекта.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает печенье.

### <a name="remarks"></a>Примечания

Файлы cookie — это переменная, используемая для определения интерфейса и его местоположения.

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a>CComGITPtr::m_dwCookie

Файл Cookie.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Примечания

Файлы cookie — это переменная, используемая для определения интерфейса и его местоположения.

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a>CComGITPtr::оператор

Оператор назначения.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на интерфейс.

*Git*<br/>
[in] Ссылка на объект `CComGITPtr`.

*dwCookie*<br/>
(в) Файлы cookie, используемые для идентификации указателя интерфейса.

*Rv*<br/>
(в) Перемещение `CComGITPtr` данных с.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComGITPtr` объект.

### <a name="remarks"></a>Примечания

Присваивает объекту `CComGITPtr` новое значение либо из существующего объекта, либо из ссылки на глобальную таблицу интерфейсов.

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a>CComGITPtr::оператор DWORD

Возвращает файлcookieо-файловое, связанное с объектом. `CComGITPtr`

```
operator DWORD() const;
```

### <a name="remarks"></a>Примечания

Файлы cookie — это переменная, используемая для определения интерфейса и его местоположения.

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a>CComGITPtr::Revoke

Вызовите этот метод, чтобы удалить текущий интерфейс из глобальной таблицы интерфейса (GIT).

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Удаляет интерфейс из GIT.

## <a name="see-also"></a>См. также раздел

[Бесплатный Резьбовый Маршал](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Доступ к интерфейсам по квартирам](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Когда использовать таблицу глобального интерфейса](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
