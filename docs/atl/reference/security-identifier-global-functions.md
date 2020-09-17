---
title: Глобальные функции идентификатора безопасности
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: e040cbb76e851bd323360f4f5ae602f9c73651d1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834483"
---
# <a name="security-identifier-global-functions"></a>Глобальные функции идентификатора безопасности

Эти функции возвращают распространенные хорошо известные объекты SID.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[Sids::AccountOps](#accountops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.|
|[Sids::Admins](#admins)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.|
|[Sids::AnonymousLogon](#anonymouslogon)|Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.|
|[Sids::AuthenticatedUser](#authenticateduser)|Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.|
|[Sids::BackupOps](#backupops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.|
|[Sids::Batch](#batch)|Возвращает идентификатор безопасности SECURITY_BATCH_RID.|
|[Sids::CreatorGroup](#creatorgroup)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.|
|[Sids::CreatorOwner](#creatorowner)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.|
|[Sids::Dialup](#dialup)|Возвращает идентификатор безопасности SECURITY_DIALUP_RID.|
|[Sids::Guests](#guests)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.|
|[Sids::Interactive](#interactive)|Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.|
|[Sids::Local](#local)|Возвращает идентификатор безопасности SECURITY_LOCAL_RID.|
|[Sids::Network](#network)|Возвращает идентификатор безопасности SECURITY_NETWORK_RID.|
|[Sids::NetworkService](#networkservice)|Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.|
|[Sids::Null](#null)|Возвращает идентификатор безопасности SECURITY_NULL_RID.|
|[Sids::PreW2KAccess](#prew2kaccess)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.|
|[Sids::PowerUsers](#powerusers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.|
|[Sids::PrintOps](#printops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.|
|[Sids::Proxy](#proxy)|Возвращает идентификатор безопасности SECURITY_PROXY_RID.|
|[Sids::RasServers](#rasservers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.|
|[Sids::Replicator](#replicator)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.|
|[Sids::RestrictedCode](#restrictedcode)|Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.|
|[Sids::Self](#self)|Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.|
|[Sids::ServerLogon](#serverlogon)|Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.|
|[Sids::Service](#service)|Возвращает идентификатор безопасности SECURITY_SERVICE_RID.|
|[Sids::System](#system)|Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.|
|[Sids::SystemOps](#systemops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.|
|[Sids::TerminalServer](#terminalserver)|Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.|
|[Sids::Users](#users)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.|
|[SID:: World](#world)|Возвращает идентификатор безопасности SECURITY_WORLD_RID.|

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="sidsaccountops"></a><a name="accountops"></a> SID:: Аккаунтопс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a> SID:: Администраторы

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a> SID:: Анонимауслогон

Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a> SID:: Аусентикатедусер

Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a> SID:: Баккупопс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a> SID:: Batch

Возвращает идентификатор безопасности SECURITY_BATCH_RID.

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a> SID:: Креаторграуп

Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a> SID:: Креаторграупсервер

Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a> SID:: Креаторовнер

Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a> SID:: Креаторовнерсервер

Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a> SID::D иалуп

Возвращает идентификатор безопасности SECURITY_DIALUP_RID.

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a> SID:: Гости

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a> SID:: Interactive

Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a> SID:: local

Возвращает идентификатор безопасности SECURITY_LOCAL_RID.

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a> SID:: сеть

Возвращает идентификатор безопасности SECURITY_NETWORK_RID.

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a> SID:: NetworkService

Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Примечания

Используйте сетевую учетную запись, чтобы разрешить пользователю NT AUTHORITY\NetworkService чтение объекта безопасности Кперфмон. NetworkService добавляет SecurityAttribute в код Атлсервер, который позволяет библиотеке DLL входить в систему под учетной записью NetworkService в Windows XP Home Edition, Windows XP Professional, Windows Server 2003 и более поздних операционных системах.

При создании пользовательских счетчиков журнала с помощью класса Атлсервер Кперфмон в MMC PerfMon счетчики могут не отображаться при просмотре файла журнала, хотя они будут правильно отображаться в режиме реального времени. Пользовательские счетчики производительности Кперфмон не имеют необходимых разрешений для работы в службе "журналы и оповещения производительности" (smlogsvc.exe) в операционных системах Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (или более поздней версии). Эта служба работает под учетной записью NT AUTHORITY\NetworkService.

## <a name="sidsnull"></a><a name="null"></a> SID:: NULL

Возвращает идентификатор безопасности SECURITY_NULL_RID.

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a> SID::P reW2KAccess

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a> SID::P Оверусерс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a> SID::P Ринтопс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a> SID::P Рокси

Возвращает идентификатор безопасности SECURITY_PROXY_RID.

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a> SID:: Рассерверс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a> ИД безопасности:: репликатор

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a> SID:: Рестриктедкоде

Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a> SID:: Self

Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a> SID:: Серверлогон

Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a> SID:: Service

Возвращает идентификатор безопасности SECURITY_SERVICE_RID.

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a> SID:: System

Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a> SID:: Системопс

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a> SID:: Терминалсервер

Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a> SID:: пользователи

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a> SID:: World

Возвращает идентификатор безопасности SECURITY_WORLD_RID.

```
CSid World() throw(...);
```

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
