---
title: CSettingsStore Class
ms.date: 11/04/2016
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
ms.openlocfilehash: b1acf959c371aa23ac55ace7fea9466f0e20813f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318464"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class

Создает программу-оболочку для API-функций Windows, обеспечивая объектно-ориентированный интерфейс, который используется для доступа к реестру.

## <a name="syntax"></a>Синтаксис

```
class CSettingsStore : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStore::CSettingsStore](#csettingsstore)|Формирует объект `CSettingsStore`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStore::Закрыть](#close)|Закрывает открытый ключ реестра.|
|[CSettingsStore::CreateKey](#createkey)|Открывает указанный ключ или создает его, если он не существует.|
|[CSettingsStore::DeleteKey](#deletekey)|Удаляет указанный ключ и всех его детей.|
|[CSettingsStore::DeleteValue](#deletevalue)|Удаляет указанное значение открытого ключа.|
|[CSettingsStore::Открыто](#open)|Открывает указанный ключ.|
|[CSettingsStore::Читать](#read)|Извлекает данные для заданного значения ключа.|
|[CSettingsStore::Запись](#write)|Записывает значение в реестр под открытым ключом.|

## <a name="remarks"></a>Примечания

Член `CreateKey` функции `Open` и очень похожи. Если ключ реестра уже `CreateKey` `Open` существует, и функционирует таким же образом. Однако, если ключ реестра `CreateKey` не существует, `Open` создаст его в то время как вернет значение ошибки.

## <a name="example"></a>Пример

В следующем примере показано, как использовать методы `CSettingsStore` открытости и чтения класса. Этот фрагмент кода является частью [образца демо-кода Tool Tip.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Требования

**Заголовок:** afxsettingsstore.h

## <a name="csettingsstoreclose"></a><a name="close"></a>CSettingsStore::Закрыть

Закрывает открытый ключ реестра.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод вызывается из деструктора [класса CSettingsStore.](../../mfc/reference/csettingsstore-class.md)

## <a name="csettingsstorecreatekey"></a><a name="createkey"></a>CSettingsStore::CreateKey

Открывает ключ реестра или создает его, если он не существует.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
(в) Упогоняет название ключа, который будет создан или открыт.

### <a name="return-value"></a>Возвращаемое значение

0 в случае успеха; в противном случае ненулевое значение.

### <a name="remarks"></a>Примечания

`CreateKey`использует `m_hKey` в качестве корня запросов реестра. Он ищет *pszPath* как подключьку `m_hKey`. Если ключ не существует, `CreateKey` создает его. В противном случае, он открывает ключ. `CreateKey`затем `m_hKey` устанавливается на созданный или открытый ключ.

## <a name="csettingsstorecsettingsstore"></a><a name="csettingsstore"></a>CSettingsStore::CSettingsStore

Создает объект `CSettngsStore`.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Параметры

*bAdmin*<br/>
(в) Параметр Boolean определяет, действует `CSettingsStore` ли объект в режиме администратора.

*bReadOnly*<br/>
(в) Параметр Boolean, который определяет, создается ли `CSettingsStore` объект в режиме только для чтения.

### <a name="remarks"></a>Примечания

Если *bAdmin* установлен на `m_hKey` ИСТИНу, переменная члена установлена на **HKEY_LOCAL_MACHINE**. Если вы *установите bAdmin* на FALSE, `m_hKey` установлен на **HKEY_CURRENT_USER**.

Доступ к безопасности зависит от параметра *bReadOnly.* Если *bReadonly* является FALSE, доступ к безопасности будет установлен **на KEY_ALL_ACCESS**. Если *bReadyOnly* является правдой, доступ к безопасности будет установлен на сочетание **KEY_QUERY_VALUE, KEY_NOTIFY** и **KEY_ENUMERATE_SUB_KEYS**. Для получения дополнительной информации о доступе к безопасности вместе с реестром, [см.](/windows/win32/SysInfo/registry-key-security-and-access-rights)

Деструктор для `CSettingsStore` `m_hKey` автоматическиго выпуска.

## <a name="csettingsstoredeletekey"></a><a name="deletekey"></a>CSettingsStore::DeleteKey

Удаляет ключ и всех его детей из реестра.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
(в) Название ключа для удаления.

*bAdmin*<br/>
(в) Переключатель, который определяет местоположение ключа для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод выйдет `CSettingsStore` из строя, если объект находится в режиме только для чтения.

Если параметр *bAdmin* `DeleteKey` равен нулю, ищет ключ для удаления под **HKEY_CURRENT_USER.** Если *bAdmin* является `DeleteKey` ненулевой, ищет ключ для удаления под **HKEY_LOCAL_MACHINE**.

## <a name="csettingsstoredeletevalue"></a><a name="deletevalue"></a>CSettingsStore::DeleteValue

Удаляет значение из `m_hKey`.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Параметры

*pszValue*<br/>
(в) Определяет поле значения для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="csettingsstoreopen"></a><a name="open"></a>CSettingsStore::Открыто

Открывает ключ реестра.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
(в) Имя ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После того, как этот метод `m_hKey` успешно открывает указанный ключ, он устанавливается на рукоятку этого ключа.

## <a name="csettingsstoreread"></a><a name="read"></a>CSettingsStore::Читать

Читает значение от ключа в реестре.

```
virtual BOOL Read(
    LPCTSTR pszKey,
    int& iVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    DWORD& dwVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CString& sVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Read(
    LPCTSTR pszKey,
    CRect& rect);

virtual BOOL Read(
    LPCTSTR pszKey,
    BYTE** ppData,
    UINT* pBytes);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject*& pObj);
```

### <a name="parameters"></a>Параметры

*pszKey*<br/>
(в) Указатель на строку с нулевым завершением, содержащую название значения для чтения из реестра.

*iVal*<br/>
(ваут) Ссылка на неоценимую переменную, которая получает значение, считываемый из ключа реестра.

*dwVal*<br/>
(ваут) Ссылка на 32-битную двойную переменную слова, которая получает значение, считываемый из ключа реестра.

*sVal*<br/>
(ваут) Ссылка на переменную строки, которая получает значение, считываемый из ключа реестра.

*scStringList*<br/>
(ваут) Ссылка на переменную списка строк, которая получает значение, считываемый из ключа реестра.

*scArray*<br/>
(ваут) Ссылка на переменную массива строки, которая получает значение, считываемый из ключа реестра.

*dwcArray*<br/>
(ваут) Ссылка на 32-битную двойную переменную массива слов, которая получает значение, считываемый из ключа реестра.

*wcArray*<br/>
(ваут) Ссылка на 16-битную переменную массива слов, которая получает значение, считываемый из ключа реестра.

*bcArray*<br/>
(ваут) Ссылка на переменную массива байт, которая получает значение, считываемый из ключа реестра.

*lpPoint*<br/>
(ваут) Ссылка на указатель `POINT` на структуру, которая получает значение, считываемые из ключа реестра.

*rect*<br/>
(ваут) Ссылка на переменную [CRect,](../../atl-mfc-shared/reference/crect-class.md) которая получает значение, считываемый из ключа реестра.

*ppData*<br/>
(ваут) Указатель на указатель на данные, которые получают значение, считываемые из ключа реестра.

*pBytes*<br/>
(ваут) Указатель на неподписанную переменную integer. Эта переменная получает размер буфера, на который указывает *ppData.*

*list*<br/>
(ваут) Ссылка на переменную [CObList,](../../mfc/reference/coblist-class.md) которая получает значение, прочитанном из ключа реестра.

*obj*<br/>
(ваут) Ссылка на переменную [CObject,](../../mfc/reference/cobject-class.md) которая получает значение, считываемый из ключа реестра.

*Pobj*<br/>
(ваут) Ссылка на указатель `CObject` на переменную, которая получает значение, считываемый из ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Read`проверки для *pszKey* как `m_hKey`подключька .

## <a name="csettingsstorewrite"></a><a name="write"></a>CSettingsStore::Запись

Записывает значение в реестр под открытым ключом.

```
virtual BOOL Write(
    LPCTSTR pszKey,
    int iVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    DWORD dwVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPCTSTR pszVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Write(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    const CRect& rect);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPBYTE pData,
    UINT nBytes);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject* pObj);
```

### <a name="parameters"></a>Параметры

*pszKey*<br/>
(в) Указатель на строку, содержащую имя значения для установки.

*iVal*<br/>
(в) Ссылка на рядовую переменную, содержащую данные для хранения.

*dwVal*<br/>
(в) Ссылка на 32-битную двойную переменную слова, содержащую данные для хранения.

*pszVal*<br/>
(в) Указатель на нулевую строку переменной, содержащей данные для хранения.

*scStringList*<br/>
(в) Ссылка на переменную [CStringList,](../../mfc/reference/cstringlist-class.md) содержащую данные для хранения.

*bcArray*<br/>
(в) Ссылка на переменную массива байт, содержащую данные для хранения.

*scArray*<br/>
(в) Ссылка на переменную массива строки, содержащую данные для хранения.

*dwcArray*<br/>
(в) Ссылка на 32-битную двойную переменную массива слов, содержащую данные для хранения.

*wcArray*<br/>
(в) Ссылка на 16-битную переменную массива слов, содержащую данные для хранения.

*rect*<br/>
(в) Ссылка на переменную [CRect,](../../atl-mfc-shared/reference/crect-class.md) содержащую данные для хранения.

*lpPoint*<br/>
(в) Ссылка на указатель `POINT` на переменную, содержащую данные для хранения.

*Pdata*<br/>
(в) Указатель на буфер, содержащий данные для хранения.

*nБайт*<br/>
(в) Определяет размер в байтах данных, к которым указывает параметр *pData.*

*list*<br/>
(в) Ссылка на переменную [CObList,](../../mfc/reference/coblist-class.md) содержащую данные для хранения.

*obj*<br/>
(в) Ссылка на переменную [CObject,](../../mfc/reference/cobject-class.md) содержащую данные для хранения.

*Pobj*<br/>
(в) Указатель на указатель `CObject` на переменную, содержащую данные для хранения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Для того, чтобы записать в реестр, при создании объекта [CSettingsStore](../../mfc/reference/csettingsstore-class.md) необходимо установить *bReadТолько* к ненулевому значению. Для получения дополнительной информации см. [CSettingsStore::CSettingsStore](#csettingsstore).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
