---
title: Класс Ккомсафеделетекритикалсектион
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: 115cbd466f51db271f4be65ce708fe54c7f2b2ce
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833638"
---
# <a name="ccomsafedeletecriticalsection-class"></a>Класс Ккомсафеделетекритикалсектион

Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ккомсафеделетекритикалсектион:: Ккомсафеделетекритикалсектион](#ccomsafedeletecriticalsection)|Конструктор.|
|[Ккомсафеделетекритикалсектион:: ~ Ккомсафеделетекритикалсектион](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккомсафеделетекритикалсектион:: init](#init)|Создает и инициализирует объект критической секции.|
|[Ккомсафеделетекритикалсектион:: Lock](#lock)|Получает владение объектом критической секции.|
|[Ккомсафеделетекритикалсектион:: Term](#term)|Освобождает системные ресурсы, используемые объектом критического раздела.|

### <a name="data-members"></a>Элементы данных

|Элемент данных|Описание|
|-|-|
|[m_bInitialized](#m_binitialized)|Помечает, инициализирован ли внутренний `CRITICAL_SECTION` объект.|

## <a name="remarks"></a>Примечания

`CComSafeDeleteCriticalSection` является производным от класса [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md). Однако `CComSafeDeleteCriticalSection` предоставляет дополнительные механизмы безопасности по сравнению с [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md).

Когда экземпляр выходит из `CComSafeDeleteCriticalSection` области действия или явно удаляется из памяти, объект критической критический раздел автоматически очищается, если он по-прежнему является допустимым. Кроме того, метод [ккомсафеделетекритикалсектион:: Term](#term) будет закрыт, если базовый объект критического раздела еще не был выделен или уже освобожден из памяти.

Дополнительные сведения о вспомогательных классах критической секции см. в разделе [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре.h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a> Ккомсафеделетекритикалсектион:: Ккомсафеделетекритикалсектион

Конструктор.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Примечания

Задает для элемента данных [m_bInitialized](#m_binitialized) значение false.

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a> Ккомсафеделетекритикалсектион:: ~ Ккомсафеделетекритикалсектион

Деструктор

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Освобождает внутренний `CRITICAL_SECTION` объект из памяти, если элемент данных [m_bInitialized](#m_binitialized) имеет значение true.

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a> Ккомсафеделетекритикалсектион:: init

Вызывает реализацию метода [init](/visualstudio/debugger/init) для базового класса и задает для [m_bInitialized](#m_binitialized) значение true в случае успеха.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: init](../../atl/reference/ccomcriticalsection-class.md#init).

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a> Ккомсафеделетекритикалсектион:: Lock

Вызывает реализацию [блокировки](ccomcriticalsection-class.md#lock)базового класса.

```
HRESULT Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

### <a name="remarks"></a>Примечания

Этот метод предполагает, что при записи для элемента данных [m_bInitialized](#m_binitialized) ЗАДАНО значение true. Утверждение создается в отладочных сборках, если это условие не выполнено.

Дополнительные сведения о поведении функции см. в разделе [ккомкритикалсектион:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a> Ккомсафеделетекритикалсектион:: m_bInitialized

Помечает, инициализирован ли внутренний `CRITICAL_SECTION` объект.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Примечания

`m_bInitialized`Элемент данных используется для контроля допустимости базового `CRITICAL_SECTION` объекта, связанного с классом [ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md) . Базовый `CRITICAL_SECTION` объект не будет пытаться освободить из памяти, если этот флаг не установлен в значение true.

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a> Ккомсафеделетекритикалсектион:: Term

Вызывает реализацию базового класса [ккомкритикалсектион:: Term](../../atl/reference/ccomcriticalsection-class.md#term) , если внутренний `CRITICAL_SECTION` объект является допустимым.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: Term](../../atl/reference/ccomcriticalsection-class.md#term)или S_OK, если для [m_bInitialized](#m_binitialized) было задано значение false при входе.

### <a name="remarks"></a>Примечания

Вызывать этот метод можно, даже если внутренний `CRITICAL_SECTION` объект является недопустимым. Деструктор этого класса вызывает этот метод, если элемент данных [m_bInitialized](#m_binitialized) имеет значение true.

## <a name="see-also"></a>См. также раздел

[Класс Ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
