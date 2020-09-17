---
title: Класс CCachedDataPathProperty
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: ebab34433f23b119e3444b3eaa8b0ad6313555af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352368"
---
# <a name="ccacheddatapathproperty-class"></a>Класс CCachedDataPathProperty

Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.

## <a name="syntax"></a>Синтаксис

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Формирует объект `CCachedDataPathProperty`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`объект, в котором кэшировать данные.|

## <a name="remarks"></a>Примечания

Файл памяти хранится в оперативной памяти, а не на диске и полезен для быстрых временных переводов.

Наряду `CAysncMonikerFile` `CDataPathProperty`с `CCachedDataPathProperty` и , обеспечивает функциональность для использования асинхронных кликторов в управления OLE. С `CCachedDataPathProperty` помощью объектов вы можете передавать данные асинхронно из URL или `m_Cache` источника файлов и хранить их в файле памяти через общедоступную переменную. Все данные хранятся в файле памяти, и нет необходимости переопределять [OnDataAvailable,](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) если вы не хотите смотреть уведомления и отвечать. Например, при передаче большого . GIF файл и хотите уведомить ваш контроль, что больше данных `OnDataAvailable` прибыли, и он должен перерисовать себя, переопределить, чтобы сделать уведомление.

Класс `CCachedDataPathProperty` происходит от `CDataPathProperty`.

Для получения дополнительной информации о том, как использовать асинхронные кликеры и элементы управления ActiveX в интернет-приложениях, смотрите следующие темы:

- [Первые шаги в Интернете: Управление ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Первые шаги Интернета: Асинхронные Моники](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty

Формирует объект `CCachedDataPathProperty`.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на объект управления ActiveX, связанный с этим `CCachedDataPathProperty` объектом.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного прозвища, которое ссылается на фактическое абсолютное местоположение свойства. `CCachedDataPathProperty`использует URL-адреса, а не имена файлов. Если требуется `CCachedDataPathProperty` объект для файла, подготовите file:// к пути.

### <a name="remarks"></a>Примечания

Объект, `COleControl` на который указывает *pControl,* используется [Open](../../mfc/reference/cdatapathproperty-class.md#open) и извлекается полученными классами. Если *pControl* является NULL, `Open` элемент управления, используемого с должны быть установлены с [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Если *lpszPath* является NULL, вы можете `Open` пройти по пути через или установить его с [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a>CCachedDataPathProperty::m_Cache

Содержит название класса файла памяти, в который кэшируется данные.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Примечания

Файл памяти хранится в оперативной памяти, а не на диске.

## <a name="see-also"></a>См. также раздел

[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
