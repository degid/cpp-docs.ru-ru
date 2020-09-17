---
title: Класс CSettingsStoreSP
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 9e22184a4081762a3d505645752e514315146981
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318457"
---
# <a name="csettingsstoresp-class"></a>Класс CSettingsStoreSP

Класс `CSettingsStoreSP` — это класс помощников, который можно использовать для создания экземпляров [класса CSettingsStore.](../../mfc/reference/csettingsstore-class.md)

## <a name="syntax"></a>Синтаксис

```
class CSettingsStoreSP
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Формирует объект `CSettingsStoreSP`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStoreSP::Создание](#create)|Создает экземпляр класса, который является `CSettingsStore`производным от .|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Устанавливает класс времени выполнения. Метод `Create` использует класс времени выполнения для определения того, какой класс объектов создать.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|`m_dwUserData`|Пользовательские пользовательские данные, хранящиеся в объекте. `CSettingsStoreSP` Эти данные предоставляются в `CSettingsStoreSP` конструктор объекта.|
|`m_pRegistry`|Объект, `CSettingsStore`полученный методом, `Create` создается.|

## <a name="remarks"></a>Примечания

Вы можете `CSettingsStoreSP` использовать класс для перенаправления всех операций реестра MFC в другие места, такие как файл XML или база данных. Для этого выполните следующие действия.

1. Создайте класс `CMyStore`(например), и `CSettingsStore`получите его из .

1. Используйте [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) `CSettingsStore` макросы с пользовательским классом, чтобы обеспечить динамическое создание.

1. Переопределить виртуальные функции `Read` `Write` и реализовать и функции в вашем пользовательском классе. Реализуйте любую другую функциональность для чтения и записи данных в нужное место.

1. В приложении `CSettingsStoreSP::SetRuntimeClass` звоните и передайте указатель [на структуру CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) полученную от вашего класса.

Всякий раз, когда фреймворк обычно получает доступ к реестру, он будет динамически мгновенно использовать ваш пользовательский класс и использовать его для чтения или записи данных.

`CSettingsStoreSP::SetRuntimeClass`использует глобальную статическую переменную. Таким образом, одновременно доступен только один пользовательский магазин.

## <a name="requirements"></a>Требования

**Заголовок:** afxsettingsstore.h

## <a name="csettingsstorespcreate"></a><a name="create"></a>CSettingsStoreSP::Создание

Создает новый экземпляр объекта, полученного из [класса CSettingsStore.](../../mfc/reference/csettingsstore-class.md)

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Параметры

*bAdmin*<br/>
(в) Параметр Boolean, определяющий, `CSettingsStore` создается ли объект в режиме администратора.

*bReadOnly*<br/>
(в) Параметр Boolean, определяющий, `CSettingsStore` создается ли объект для доступа только для чтения.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на вновь созданный `CSettingsStore` объект.

### <a name="remarks"></a>Примечания

Вы можете использовать метод [CSettingsStoreSP::SetRuntimeClass,](#setruntimeclass) чтобы `CSettingsStoreSP::Create` определить, какой тип объекта будет создавать. По умолчанию этот `CSettingsStore` метод создает объект.

При создании `CSettingsStore` объекта в режиме администратора место по умолчанию для всего доступа к реестру HKEY_LOCAL_MACHINE. В противном случае место по умолчанию для всего доступа к реестру HKEY_CURRENT_USER.

Если *bAdmin* является правдой, приложение должно иметь права на администрирование. В противном случае, он не сможет, когда он пытается получить доступ к реестру.

### <a name="example"></a>Пример

В следующем примере показано, `Create` как `CSettingsStoreSP` использовать метод класса.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP

Строит объект [класса CSettingsStoreSP.](../../mfc/reference/csettingsstoresp-class.md)

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*dwUserData*<br/>
(в) Данные, определяемые пользователем, `CSettingsStoreSP` которые хранит объект.

### <a name="remarks"></a>Примечания

Объект `CSettingsStoreSP` хранит данные *dwUserData* в защищенной переменной `m_dwUserData`участника.

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass

Устанавливает класс времени выполнения. Метод [CSettingsStoreSP::Создание](#create) использует класс времени выполнения, чтобы определить, какой тип объекта создать.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Параметры

*pRTI*<br/>
(в) Указатель на информацию о классе времени выполнения для класса, полученного из [класса CSettingsStore.](../../mfc/reference/csettingsstore-class.md)

### <a name="return-value"></a>Возвращаемое значение

TRUE в случае успеха; FALSE, если класс, идентифицированный *pRTI,* не является производным от `CSettingsStore`.

### <a name="remarks"></a>Примечания

Вы можете использовать [класс CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) `CSettingsStore`для получения классов из. Используйте `SetRuntimeClass` метод, если вы хотите создать объекты пользовательского класса, который получен из. `CSettingsStore`

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)
