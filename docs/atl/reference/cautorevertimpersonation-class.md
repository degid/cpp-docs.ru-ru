---
title: Класс CAutoRevertIm
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: ea119436fd36d0814c05f1b48380028ad3f63f0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748244"
---
# <a name="cautorevertimpersonation-class"></a>Класс CAutoRevertIm

Этот класс возвращает объекты [CAccessToken](../../atl/reference/caccesstoken-class.md) в состояние nonimpersonating, когда оно выходит за рамки.

## <a name="syntax"></a>Синтаксис

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoRevertImperson::CAutoRevertImperson](#cautorevertimpersonation)|Строит `CAutoRevertImpersonation` объект|
|[CAutoRevertImperson:: »CAutoRevertImperson](#dtor)|Уничтожает объект и возвращает олицетворение маркера доступа.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAutoRevertImperson::Attach](#attach)|Автоматизирует реверсию олицетворения токена доступа.|
|[CAutoRevertImperson::Detach](#detach)|Отменяет автоматическое повторное олицетворение.|
|[CAutoRevertImperson::GetAccessToken](#getaccesstoken)|Извлекает ток маркера доступа, связанный с этим объектом.|

## <a name="remarks"></a>Примечания

[Токен доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделенный каждому пользователю, зарегистрированным на систему Windows NT или Windows 2000. Эти токены доступа могут быть `CAccessToken` представлены в классе.

Иногда необходимо выдавать себя за токены доступа. Этот класс предоставляется в качестве удобства, но он не выполняет олицетворение токенов доступа; он выполняет только автоматическое реверсия в необезливное состояние. Это связано с тем, что олицетворение доступа токенов может быть выполнено несколькими способами.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a>CAutoRevertImperson::Attach

Автоматизирует реверсию олицетворения токена доступа.

```cpp
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*Пэт*<br/>
Адрес объекта [CAccessToken,](../../atl/reference/caccesstoken-class.md) который будет автоматически возвращен

### <a name="remarks"></a>Примечания

Этот метод следует использовать только в том случае, если объект `CAccessToken` [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) был создан с помощью указателя NULL, или если Ранее назывался [Detach.](#detach) В простых случаях нет необходимости использовать этот метод.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a>CAutoRevertImperson::CAutoRevertImperson

Формирует объект `CAutoRevertImpersonation`.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*Пэт*<br/>
Адрес объекта [CAccessToken,](../../atl/reference/caccesstoken-class.md) который должен быть возвращен автоматически.

### <a name="remarks"></a>Примечания

Фактическое олицетворение токена доступа должно выполняться отдельно от `CAutoRevertImpersonation` и предпочтительно до создания объекта. Это олицетворение будет автоматически возвращено, когда `CAutoRevertImpersonation` объект выходит за рамки.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a>CAutoRevertImperson:: »CAutoRevertImperson

Уничтожает объект и возвращает олицетворение маркера доступа.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Примечания

Возвращает любое олицетворение, дейневшее в настоящее время для объекта [CAccessToken,](../../atl/reference/caccesstoken-class.md) предоставляемого либо при строительстве, либо через метод [Attach.](#attach) Если `CAccessToken` нет, деструктор не имеет эффекта.

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a>CAutoRevertImperson::Detach

Отменяет автоматическое повторное олицетворение.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или NULL, если не существует ассоциации.

### <a name="remarks"></a>Примечания

Вызов **Detach** предотвращает `CAutoRevertImpersonation` возврат объекта к любому олицетворению, действовавшем в настоящее время для объекта [CAccessToken,](../../atl/reference/caccesstoken-class.md) связанного с этим объектом. `CAutoRevertImpersonation`может быть уничтожен без каких-либо последствий `CAccessToken` или воссоединиться с тем же или другим объектом с помощью [Attach.](#attach)

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a>CAutoRevertImperson::GetAccessToken

Извлекает ток маркера доступа, связанный с этим объектом.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или NULL, если не существует ассоциации.

### <a name="remarks"></a>Примечания

Если этот метод называется для целей, которые включают реверсию олицетворения `CAccessToken` объекта, вместо этого следует использовать метод [Detach.](#detach)

## <a name="see-also"></a>См. также раздел

[Образец ATLSecurity](../../overview/visual-cpp-samples.md)<br/>
[Токены доступа](/windows/win32/SecAuthZ/access-tokens)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
