---
title: Класс CRegKey
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: d3bdb2e7c3ab0ef56ef7f6fba5d43f1ba0bb7fc6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746519"
---
# <a name="cregkey-class"></a>Класс CRegKey

Этот класс предоставляет методы для манипулирования записями в системном реестре.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CRegKey
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRegKey::CRegKey](#cregkey)|Конструктор.|
|[CRegKey:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRegKey::Прикрепите](#attach)|Вызов иметод, чтобы прикрепить HKEY к объекту, `CRegKey` установив ручку [m_hKey](#m_hkey) элемента. `hKey`|
|[CRegKey::Закрыть](#close)|Вызовите этот метод, чтобы освободить [ручку m_hKey](#m_hkey) и установите его в NULL.|
|[CRegKey::Создание](#create)|Вызовите этот метод, чтобы создать указанный ключ, `hKeyParent`если он не существует в качестве подключаемого ключа.|
|[CRegKey::DeleteSubKey](#deletesubkey)|Вызовите этот метод, чтобы удалить указанный ключ из реестра.|
|[CRegKey::DeleteValue](#deletevalue)|Вызовите этот метод, чтобы удалить поле значения из [m_hKey.](#m_hkey)|
|[CRegKey::Detach](#detach)|Вызовите этот метод, чтобы отделить `CRegKey` ручку `m_hKey` [m_hKey](#m_hkey) от объекта и установить на NULL.|
|[CRegKey::EnumKey](#enumkey)|Вызовите этот метод, чтобы перечислить подключи ключа открытого реестра.|
|[CRegKey::Флеш](#flush)|Вызовите этот метод, чтобы записать все атрибуты ключа открытого реестра в реестр.|
|[CRegKey:GetKeySecurity](#getkeysecurity)|Вызовите этот метод, чтобы получить копию дескриптора безопасности, защищающего открытый ключ реестра.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Этот метод уведомляет вызываемого о изменениях атрибутов или содержимого ключа открытого реестра.|
|[CRegKey::Открыто](#open)|Вызовите этот метод, чтобы открыть указанный ключ и установить [m_hKey](#m_hkey) к ручке этого ключа.|
|[CRegKey::КвимирБинарнаяСтоимость](#querybinaryvalue)|Вызовите этот метод для получения двоичных данных для указанного имени значения.|
|[CRegKey::КвиДИДВАЛВал](#querydwordvalue)|Вызовите этот метод для получения данных DWORD для указанного имени значения.|
|[CRegKey::КвиГИДОдвал](#queryguidvalue)|Вызовите этот метод для получения данных GUID для определенного имени значения.|
|[CRegKey::Кви-РимМультиТрингвал](#querymultistringvalue)|Вызовите этот метод для извлечения многострунных данных для определенного имени значения.|
|[CRegKey::Квири-WORDValue](#queryqwordvalue)|Вызовите этот метод, чтобы получить данные word для определенного имени значения.|
|[CRegKey::КвистрингВент](#querystringvalue)|Вызовите этот метод для извлечения данных строки для определенного имени значения.|
|[CRegKey::Квивале](#queryvalue)|Вызов используйте этот метод для получения данных для заданного поля значения [m_hKey.](#m_hkey) Более ранние версии этого метода больше не поддерживаются и помечены как ATL_DEPRECATED.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Вызовите этот метод, чтобы удалить указанный ключ из реестра и явно удалить любые подключи.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Вызовите этот метод, чтобы установить двоичное значение ключа реестра.|
|[CRegKey:SetDWORDValue](#setdwordvalue)|Вызовите этот метод, чтобы установить значение DWORD ключа реестра.|
|[CRegKey::SetGUIDvalue](#setguidvalue)|Вызовите этот метод, чтобы установить значение GUID ключа реестра.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|Вызовите этот метод, чтобы установить безопасность ключа реестра.|
|[CRegKey::SetKeyValue](#setkeyvalue)|Вызовите этот метод для хранения данных в определенном поле значений указанного ключа.|
|[CRegKey:SetMultiStringValue](#setmultistringvalue)|Вызовите этот метод, чтобы установить многострятое значение ключа реестра.|
|[CRegKey::Set-WORDValue](#setqwordvalue)|Вызовите этот метод, чтобы установить значение ключа реестра.|
|[CRegKey::SetStringValue](#setstringvalue)|Вызовите этот метод, чтобы установить значение строки ключа реестра.|
|[CRegKey::SetValue](#setvalue)|Вызовите этот метод для хранения данных в указанном поле значения [m_hKey.](#m_hkey) Более ранние версии этого метода больше не поддерживаются и помечены как ATL_DEPRECATED.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CRegKey:оператор HKEY](#operator_hkey)|Преобразует `CRegKey` объект в HKEY.|
|[CRegKey::оператор](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|Содержит ручку ключа реестра, `CRegKey` связанную с объектом.|
|[CRegKey::m_pTM](#m_ptm)|Указатель `CAtlTransactionManager` на объект|

## <a name="remarks"></a>Примечания

`CRegKey`предоставляет методы создания и удаляния ключей и значений в системном реестре. Реестр содержит набор определений для компонентов системы, таких как номера версий программного обеспечения, логические к физическим отображениям установленного оборудования и объекты COM.

`CRegKey`обеспечивает интерфейс программирования в системный реестр для данной машины. Например, чтобы открыть определенный `CRegKey::Open`ключ реестра, позвоните . Для получения или изменения значения `CRegKey::QueryValue` данных, вызова или `CRegKey::SetValue`соответственно. Чтобы закрыть ключ, `CRegKey::Close`позвоните .

При закрытии ключа его данные реестра записываются (сливаются) на жесткий диск. Этот процесс может занять несколько секунд. Если приложение должно явно записывать данные реестра на жесткий диск, можно вызвать функцию [RegFlushKey](/windows/win32/api/winreg/nf-winreg-regflushkey) Win32. Тем `RegFlushKey` не менее, использует много системных ресурсов и должны быть вызваны только тогда, когда это абсолютно необходимо.

> [!IMPORTANT]
> Любые методы, позволяющие вызывающему указать местоположение реестра, могут считывать данные, которым нельзя доверять. Методы, применяющие [Reg'svalueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) должны учитывать, что эта функция явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="cregkeyattach"></a><a name="attach"></a>CRegKey::Прикрепите

Вызовите этот метод, чтобы `CRegKey` прикрепить HKEY к объекту, установив ручку [m_hKey](#m_hkey) члена *hKey.*

```cpp
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка ключа реестра.

### <a name="remarks"></a>Примечания

`Attach`будет утверждать, если `m_hKey` не является NULL.

## <a name="cregkeyclose"></a><a name="close"></a>CRegKey::Закрыть

Вызовите этот метод, чтобы освободить [ручку m_hKey](#m_hkey) и установите его в NULL.

```
LONG Close() throw();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае возвращает значение ошибки.

## <a name="cregkeycreate"></a><a name="create"></a>CRegKey::Создание

Вызовите этот метод, чтобы создать указанный ключ, если он не существует в качестве подключаемого ключа *hKeyParent.*

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>Параметры

*hKeyParent*<br/>
Ручка открытого ключа.

*lpszKeyName*<br/>
Упогоняет название ключа, который будет создан или открыт. Это имя должно быть подключкой *hKeyParent*.

*lpszClass*<br/>
Определяет класс ключа, который будет создан или открыт. Значение по умолчанию REG_NONE.

*dwOptions*<br/>
Варианты ключа. Значение по умолчанию является REG_OPTION_NON_VOLATILE. Список возможных значений и описаний можно узнать в SDK СДК с [приведенной](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) в ссылке.

*samDesired*<br/>
Доступ к безопасности для ключа. Значение по умолчанию KEY_READ &#124; KEY_WRITE. Список возможных значений и описаний см. `RegCreateKeyEx`

*lpSecAttr*<br/>
Указатель на [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) структуру, которая указывает, может ли ручка ключа быть унаследована в результате детского процесса. По умолчанию этот параметр является NULL (т.е. ручка не может быть унаследована).

*lpdwDisposition*<br/>
(ваут) Если не-NULL, получает либо REG_CREATED_NEW_KEY (если ключ не существовал и был создан) или REG_OPENED_EXISTING_KEY (если ключ существовал и был открыт).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращается ERROR_SUCCESS и открывает ключ. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

`Create`устанавливает [m_hKey](#m_hkey) членом к ручке этого ключа.

## <a name="cregkeycregkey"></a><a name="cregkey"></a>CRegKey::CRegKey

Конструктор.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ссылка на объект `CRegKey`.

*hKey*<br/>
Ручка к ключу реестра.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Создает новый объект `CRegKey`. Объект может быть создан `CRegKey` из существующего объекта или от ручки до ключа реестра.

## <a name="cregkeycregkey"></a><a name="dtor"></a>CRegKey:::

Деструктор

```
~CRegKey() throw();
```

### <a name="remarks"></a>Примечания

Деструктор высвобождает `m_hKey`.

## <a name="cregkeydeletesubkey"></a><a name="deletesubkey"></a>CRegKey::DeleteSubKey

Вызовите этот метод, чтобы удалить указанный ключ из реестра.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Параметры

*lpszSubKey*<br/>
Условляет сяочное имя ключа для удаления. Это имя должно быть подключкой [m_hKey.](#m_hkey)

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращается ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

`DeleteSubKey`может только удалить ключ, который не имеет подключ. Если ключ имеет подключи, позвоните [RecurseDeleteKey](#recursedeletekey) вместо этого.

## <a name="cregkeydeletevalue"></a><a name="deletevalue"></a>CRegKey::DeleteValue

Вызовите этот метод, чтобы удалить поле значения из [m_hKey.](#m_hkey)

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Параметры

*lpszValue*<br/>
Определяет поле значения для удаления.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращается ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

## <a name="cregkeydetach"></a><a name="detach"></a>CRegKey::Detach

Вызовите этот метод, чтобы отделить `CRegKey` ручку `m_hKey` [m_hKey](#m_hkey) от объекта и установить на NULL.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

HKEY, связанный `CRegKey` с объектом.

## <a name="cregkeyenumkey"></a><a name="enumkey"></a>CRegKey::EnumKey

Вызовите этот метод, чтобы перечислить подключи ключа открытого реестра.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Индекс подключ. Этот параметр должен быть нулевым для первого вызова, а затем приращен для последующих вызовов

*pszName*<br/>
Указатель на буфер, который получает имя подключаемого ключа, включая термин null. Только имя подключаемых скопировано в буфер, а не в полную ключевую иерархию.

*pnNameДлин*<br/>
Указатель на перемену, которая определяет размер в TCHARs буфера, указанного параметром *pszName.* Этот размер должен включать в себя прекращение нулевого символа. Когда метод возвращается, переменная, указанная *pnNameLength,* содержит количество символов, хранящихся в буфере. Обратный счет не включает термин null.

*pftLastWriteTime*<br/>
Указатель на переменную, которая получает время, в которое был записан в последний раз перечисленный подключ.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Чтобы перечислить субки, `CRegKey::EnumKey` позвоните с нулевым индексом. Приравнь значение индекса и повторяйте до тех пор, пока метод не вернется ERROR_NO_MORE_ITEMS. Для получения дополнительной информации, см [RegEnumKeyEx](/windows/win32/api/winreg/nf-winreg-regenumkeyexw) в Windows SDK.

## <a name="cregkeyflush"></a><a name="flush"></a>CRegKey::Флеш

Вызовите этот метод, чтобы записать все атрибуты ключа открытого реестра в реестр.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Для получения дополнительной [RegEnumFlush](/windows/win32/api/winreg/nf-winreg-regflushkey) информации см.

## <a name="cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>CRegKey:GetKeySecurity

Вызовите этот метод, чтобы получить копию дескриптора безопасности, защищающего открытый ключ реестра.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Параметры

*Si*<br/>
Значение [SECURITY_INFORMATION,](/windows/win32/SecAuthZ/security-information) которое указывает на запрашиваемую информацию о безопасности.

*Psd*<br/>
Указатель на буфер, который получает копию запрошенного дескриптора безопасности.

*pnBytes*<br/>
Размер, в байтах, буфера, на который указывает *psd*.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не удается, значение возврата является кодом ошибки ненулевой определяется в WINERROR. H.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [RegGetKeySecurity](/windows/win32/api/winreg/nf-winreg-reggetkeysecurity).

## <a name="cregkeym_hkey"></a><a name="m_hkey"></a>CRegKey::m_hKey

Содержит ручку ключа реестра, `CRegKey` связанную с объектом.

```
HKEY m_hKey;
```

## <a name="cregkeym_ptm"></a><a name="m_ptm"></a>CRegKey::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

## <a name="cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue

Этот метод уведомляет вызываемого о изменениях атрибутов или содержимого ключа открытого реестра.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*bWatchSubtree*<br/>
Определяет флаг, указывающий, следует ли сообщать об изменениях в указанном ключе и всех его подключаемых ключах или только в указанном ключе. Если этот параметр соответствует действительности, метод сообщает об изменениях в ключе и его подключаемых ключах. Если параметр FALSE, метод сообщает изменения только в ключе.

*dwNotifyFilter*<br/>
Определяет набор флагов, которые контролируют, какие изменения должны быть зарегистрированы. Этот параметр может быть комбинацией следующих значений:

|Значение|Значение|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Сообщите вызывающему, если подключка добавлена или удалена.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Сообщите вызывающему об изменениях атрибутов ключа, таких как информация о дескрипторах безопасности.|
|REG_NOTIFY_CHANGE_LAST_SET|Сообщите вызывающему об изменениях в значении ключа. Это может включать добавление или исключение значения или изменение существующего значения.|
|REG_NOTIFY_CHANGE_SECURITY|Сообщите вызывающему об изменениях в дескрипторе безопасности ключа.|

*hEvent*<br/>
Дескриптор события. Если параметр *bAsync* является правдой, метод немедленно возвращается и изменения сообщаются путем сигнализации этого события. Если *bAsync* FALSE, *hEvent* игнорируется.

*bAsync*<br/>
Определяет флаг, указывающий, как изменяется метод. Если этот параметр соответствует действительности, метод немедленно возвращается и сообщает об изменениях, сигнализируя указанное событие. Когда этот параметр FALSE, метод не возвращается до тех пор, пока не произойдет изменение. Если *hEvent* не указывает допустимое событие, параметр *bAsync* не может быть правдой.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Этот метод не уведомляет вызываемого абонента, если указанный ключ удален.

Для получения более подробной информации и примерпрограммы см. [RegNotifyChangeKeyValue](/windows/win32/api/winreg/nf-winreg-regnotifychangekeyvalue).

## <a name="cregkeyopen"></a><a name="open"></a>CRegKey::Открыто

Вызовите этот метод, чтобы открыть указанный ключ и установить [m_hKey](#m_hkey) к ручке этого ключа.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Параметры

*hKeyParent*<br/>
Ручка открытого ключа.

*lpszKeyName*<br/>
Упогоняет название ключа, который будет создан или открыт. Это имя должно быть подключкой *hKeyParent*.

*samDesired*<br/>
Доступ к безопасности для ключа. Значение по умолчанию является KEY_ALL_ACCESS. Список возможных значений и описаний можно узнать в SDK СДК с [приведенной](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) в ссылке.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае значение ненулевой ошибки, определяемое в WINERROR. H.

### <a name="remarks"></a>Примечания

Если параметр *lpszKeyName* является NULL или `Open` указывает на пустую строку, открывает сятвую ручку ключа, идентифицированную *hKeyParent,* но не закрывает ранее открывшуюся ручку.

В отличие от [CRegKey::Создание](#create), `Open` не будет создавать указанный ключ, если он не существует.

## <a name="cregkeyoperator-hkey"></a><a name="operator_hkey"></a>CRegKey:оператор HKEY

Преобразует `CRegKey` объект в HKEY.

```
operator HKEY() const throw();
```

## <a name="cregkeyoperator-"></a><a name="operator_eq"></a>CRegKey::оператор

Оператор присвоения.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ к копированию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на новый ключ.

### <a name="remarks"></a>Примечания

Этот оператор отсоединяет *ключ* от текущего объекта и `CRegKey` вместо этого назначает его объекту.

## <a name="cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>CRegKey::КвимирБинарнаяСтоимость

Вызовите этот метод для получения двоичных данных для указанного имени значения.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*pValue*<br/>
Указатель на буфер, который получает данные значения.

*pnBytes*<br/>
Указатель на переменную, которая определяет размер, в байтах, буфера, на который указывает параметр *pValue.* Когда метод возвращается, эта переменная содержит размер данных, скопированных в буфер.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если ссылки на данные не являются типами REG_BINARY, ERROR_INVALID_DATA возвращается.

### <a name="remarks"></a>Примечания

Этот метод использует `RegQueryValueEx` и подтверждает, что правильный тип данных возвращается. Более подробную информацию можно узнать [из-за реджиривалекса.](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция [Reg'ruryValueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>CRegKey::КвиДИДВАЛВал

Вызовите этот метод для получения данных DWORD для указанного имени значения.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*dwValue*<br/>
Указатель на буфер, который получает DWORD.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если ссылки на данные не являются типом REG_DWORD, ERROR_INVALID_DATA возвращается.

### <a name="remarks"></a>Примечания

Этот метод использует `RegQueryValueEx` и подтверждает, что правильный тип данных возвращается. Более подробную информацию можно узнать [из-за реджиривалекса.](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция [Reg'ruryValueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>CRegKey::КвиГИДОдвал

Вызовите этот метод для получения данных GUID для определенного имени значения.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*guidValue*<br/>
Указатель на переменную, которая получает GUID.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если ссылки на данные не являются действительными GUID, ERROR_INVALID_DATA возвращается.

### <a name="remarks"></a>Примечания

Этот метод использует `CRegKey::QueryStringValue` и преобразует строку в GUID с помощью [CLSIDFromString.](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять.

## <a name="cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>CRegKey::Кви-РимМультиТрингвал

Вызовите этот метод для извлечения многострунных данных для определенного имени значения.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*pszValue*<br/>
Указатель на буфер, который получает многострые данные. Multistring — это массив нулевых строк, упраздненный двумя нулевыми символами.

*pnChars*<br/>
Размер, в TCHARs, буфера указывается на *pszValue*. Когда метод возвращается, *pnChars* содержит размер, в TCHARs, многостряного извлеченного, включая прекращающийся нулевой символ.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если упомянутые данные не являются типами REG_MULTI_SZ, ERROR_INVALID_DATA возвращается.

### <a name="remarks"></a>Примечания

Этот метод использует `RegQueryValueEx` и подтверждает, что правильный тип данных возвращается. Более подробную информацию можно узнать [из-за реджиривалекса.](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция [Reg'ruryValueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>CRegKey::Квири-WORDValue

Вызовите этот метод, чтобы получить данные word для определенного имени значения.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*qwValue*<br/>
Указатель на буфер, который получает «WORD».

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если ссылки на данные не являются типами REG_QWORD, ERROR_INVALID_DATA возвращается.

### <a name="remarks"></a>Примечания

Этот метод использует `RegQueryValueEx` и подтверждает, что правильный тип данных возвращается. Более подробную информацию можно узнать [из-за реджиривалекса.](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция [Reg'ruryValueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyquerystringvalue"></a><a name="querystringvalue"></a>CRegKey::КвистрингВент

Вызовите этот метод для извлечения данных строки для определенного имени значения.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса.

*pszValue*<br/>
Указатель на буфер, который получает данные строки.

*pnChars*<br/>
Размер, в TCHARs, буфера указывается на *pszValue*. При возврате метода *pnChars* содержит размер в TCHARs извлекаемых строк, включая прекращающийся нулевой символ.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, ERROR_SUCCESS возвращается. Если метод не считывает значение, он возвращает код ошибки без нуля, определенный в WINERROR. H. Если данные, на которые ссылаются, не являются типами REG_SZ, ERROR_INVALID_DATA возвращается. Если метод возвращается ERROR_MORE_DATA, *pnChars* равен нулю, а не требуемому размеру буфера в байтах.

### <a name="remarks"></a>Примечания

Этот метод использует `RegQueryValueEx` и подтверждает, что правильный тип данных возвращается. Более подробную информацию можно узнать [из-за реджиривалекса.](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция [Reg'ruryValueEx,](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyqueryvalue"></a><a name="queryvalue"></a>CRegKey::Квивале

Вызов используйте этот метод для получения данных для заданного поля значения [m_hKey.](#m_hkey) Более ранние версии этого метода больше не поддерживаются и помечены как ATL_DEPRECATED.

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку с нулевым завершением, содержащую имя значения для запроса. Если *pszValueName* является NULL или пустой строкой, метод получает тип и данные для неназванного или значения ключа по умолчанию, если таковые имеются.

*pdwType*<br/>
Указатель на переменную, которая получает код с указанием типа данных, хранящихся в указанном значении. Параметр *pdwType* может быть NULL, если код типа не требуется.

*Pdata*<br/>
Указатель на буфер, который получает данные значения. Этот параметр может быть NULL, если данные не требуются.

*pnBytes*<br/>
Указатель на переменную, которая определяет размер, в байтах, буфера, на который указывает параметр *pData.* Когда метод возвращается, эта переменная содержит размер данных, скопированных на *pData.*

*dwValue*<br/>
Численные данные поля значений.

*lpszValueName*<br/>
Определяет поле значения, подавивще запрос.

*szValue*<br/>
Данные строки поля значения.

*pdwCount*<br/>
Размер данных строки. Его значение первоначально устанавливается размербуфера *szValue.*

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае, код ошибки nonzero определенный в WINERROR. H.

### <a name="remarks"></a>Примечания

Две оригинальные `QueryValue` версии больше не поддерживаются и помечены как ATL_DEPRECATED. Компилятор выдаст предупреждение, если эти формы будут использованы.

Оставшийся метод вызывает Reg'svalueEx.

> [!IMPORTANT]
> Этот метод позволяет вызывающеу указать любое местоположение реестра, потенциально читая данные, которым нельзя доверять. Кроме того, функция Reg'ruryValueEx, используемая этим методом, явно не обрабатывает строки, которые являются NULL прекращенными. Оба условия должны быть проверены по коду вызова.

## <a name="cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey

Вызовите этот метод, чтобы удалить указанный ключ из реестра и явно удалить любые подключи.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Параметры

*lpszKey*<br/>
Условляет сяочное имя ключа для удаления. Это имя должно быть подключкой [m_hKey.](#m_hkey)

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае значение ненулевой ошибки, определяемое в WINERROR. H.

### <a name="remarks"></a>Примечания

Если ключ имеет подключи, необходимо вызвать этот метод, чтобы удалить ключ.

## <a name="cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>CRegKey::SetBinaryValue

Вызовите этот метод, чтобы установить двоичное значение ключа реестра.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*pValue*<br/>
Указатель на буфер, содержащий данные, которые будут храниться с указанным значением имени.

*nБайт*<br/>
Определяет размер, в байтах, информации, указанной на *параметре pValue.*

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) для записи значения в реестр.

## <a name="cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>CRegKey:SetDWORDValue

Вызовите этот метод, чтобы установить значение DWORD ключа реестра.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*dwValue*<br/>
Данные DWORD, которые будут храниться с указанным именем значения.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) для записи значения в реестр.

## <a name="cregkeysetguidvalue"></a><a name="setguidvalue"></a>CRegKey::SetGUIDvalue

Вызовите этот метод, чтобы установить значение GUID ключа реестра.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*guidValue*<br/>
Ссылка на GUID, которая будет храниться с указанным значением имени.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует `CRegKey::SetStringValue` и преобразует GUID в строку с помощью [StringFromGUID2.](/windows/win32/api/combaseapi/nf-combaseapi-stringfromguid2)

## <a name="cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>CRegKey::SetKeyValue

Вызовите этот метод для хранения данных в определенном поле значений указанного ключа.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>Параметры

*lpszKeyName*<br/>
Упогоняет название ключа, который будет создан или открыт. Это имя должно быть подключкой [m_hKey.](#m_hkey)

*lpszValue*<br/>
Определяет данные, которые будут храниться. Этот параметр должен быть не-NULL.

*lpszValueName*<br/>
Определяет поле значения, подносящее к установке. Если поле значений с этим именем еще не существует в ключе, оно добавляется.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае, код ошибки nonzero определенный в WINERROR. H.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы создать или открыть ключ *lpszKeyName* и хранить данные *lpszValue* в поле значения *lpszValueName.*

## <a name="cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>CRegKey::SetKeySecurity

Вызовите этот метод, чтобы установить безопасность ключа реестра.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Параметры

*Si*<br/>
Определяет компоненты дескриптора безопасности для установки. Значение может быть сочетанием следующих значений:

|Значение|Значение|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Устанавливает дискреционный список контроля доступа ключа (DACL). Ключ должен иметь WRITE_DAC доступ, или процесс вызова должен быть владельцем объекта.|
|GROUP_SECURITY_INFORMATION|Устанавливает основной идентификатор безопасности группы ключа (SID). Ключ должен иметь WRITE_OWNER доступ, или процесс вызова должен быть владельцем объекта.|
|OWNER_SECURITY_INFORMATION|Устанавливает владельца ключа SID. Ключ должен иметь WRITE_OWNER доступ, или процесс вызова должен быть владельцем объекта или иметь SE_TAKE_OWNERSHIP_NAME привилегию.|
|SACL_SECURITY_INFORMATION|Устанавливает список системного контроля доступа (SACL). Ключ должен иметь ACCESS_SYSTEM_SECURITY доступ. Правильный способ получить этот доступ — включить SE_SECURITY_NAME [привилегию](/windows/win32/secauthz/privileges) в токцентре доступа вызываемого, открыть ручку для ACCESS_SYSTEM_SECURITY доступа, а затем отключить привилегию.|

*Psd*<br/>
Указатель на [SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) структуру, которая определяет атрибуты безопасности для установки для указанного ключа.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Устанавливает атрибуты безопасности ключа. Более подробную информацию можно узнать в [RegSetKeySecurity.](/windows/win32/api/winreg/nf-winreg-regsetkeysecurity)

## <a name="cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>CRegKey:SetMultiStringValue

Вызовите этот метод, чтобы установить многострятое значение ключа реестра.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*pszValue*<br/>
Указатель на многостронье данные, которые будут храниться с указанным значением имени. Multistring — это массив нулевых строк, упраздненный двумя нулевыми символами.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) для записи значения в реестр.

## <a name="cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>CRegKey::Set-WORDValue

Вызовите этот метод, чтобы установить значение ключа реестра.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*qwValue*<br/>
Данные word, которые будут храниться с указанным именем значения.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) для записи значения в реестр.

## <a name="cregkeysetstringvalue"></a><a name="setstringvalue"></a>CRegKey::SetStringValue

Вызовите этот метод, чтобы установить значение строки ключа реестра.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем уже не присутствует, метод добавляет его к ключу.

*pszValue*<br/>
Указатель на данные строки, которые будут храниться с указанным значением имени.

*dwType*<br/>
Тип строки для записи в реестр: либо REG_SZ (по умолчанию) или REG_EXPAND_SZ (для мультиструй).

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, значение возврата ERROR_SUCCESS. Если метод не работает, значение возврата является кодом ошибки без нуля, определенным в WINERROR. H.

### <a name="remarks"></a>Примечания

Этот метод использует [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) для записи значения в реестр.

## <a name="cregkeysetvalue"></a><a name="setvalue"></a>CRegKey::SetValue

Вызовите этот метод для хранения данных в указанном поле значения [m_hKey.](#m_hkey) Более ранние версии этого метода больше не поддерживаются и помечены как ATL_DEPRECATED.

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>Параметры

*pszValueName*<br/>
Указатель на строку, содержащую имя значения для установки. Если значение с этим именем еще не присутствует в ключе, метод добавляет его в ключ. Если *pszValueName* является NULL или пустой строкой, метод устанавливает тип и данные для неназванного или значения ключа по умолчанию.

*dwType*<br/>
Определяет код, указывающий тип данных, на которые указывает параметр *pValue.*

*pValue*<br/>
Указатель на буфер, содержащий данные, которые будут храниться с указанным значением имени.

*nБайт*<br/>
Определяет размер, в байтах, информации, указанной на *параметре pValue.* Если данные имеют тип REG_SZ, REG_EXPAND_SZ или REG_MULTI_SZ, *nBytes* должны включать размер термина null.

*hKeyParent*<br/>
Ручка открытого ключа.

*lpszKeyName*<br/>
Упогоняет название ключа, который будет создан или открыт. Это имя должно быть подключкой *hKeyParent*.

*lpszValue*<br/>
Определяет данные, которые будут храниться. Этот параметр должен быть не-NULL.

*lpszValueName*<br/>
Определяет поле значения, подносящее к установке. Если поле значений с этим именем еще не существует в ключе, оно добавляется.

*dwValue*<br/>
Определяет данные, которые будут храниться.

*bMulti*<br/>
Если ложно, указывает строка типа REG_SZ. Если это правда, указывает строка является многостряным типом REG_MULTI_SZ.

*nValueLen*<br/>
Если *bMulti истинен,* *nValueLen* — это длина *строки lpszValue* в символах. Если *bMulti* является ложным, значение -1 указывает на то, что метод будет вычислять длину автоматически.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает ERROR_SUCCESS; в противном случае, код ошибки nonzero определенный в WINERROR. H.

### <a name="remarks"></a>Примечания

Две оригинальные `SetValue` версии помечены как ATL_DEPRECATED и больше не должны использоваться. Компилятор выдаст предупреждение, если эти формы будут использованы.

Третий метод вызывает [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw).

## <a name="see-also"></a>См. также раздел

[Образец DCOM](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
