---
title: Класс CDataPathProperty
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 479f5d47d9cff72d36dbd25e434182af1ba01ef4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754652"
---
# <a name="cdatapathproperty-class"></a>Класс CDataPathProperty

Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

## <a name="syntax"></a>Синтаксис

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Формирует объект `CDataPathProperty`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDataPathProperty::GetControl](#getcontrol)|Извлекает асинхронный элемент управления `CDataPathProperty` OLE, связанный с объектом.|
|[CDataPathProperty::GetPath](#getpath)|Извлекает имя пути свойства.|
|[CDataPathProperty::Открыто](#open)|Инициирует загрузку асинхронного свойства для управления ActiveX (OLE).|
|[CDataPathProperty::ResetData](#resetdata)|Звонки, `CAsyncMonikerFile::OnDataAvailable` чтобы уведомить контейнер об изменении свойств управления.|
|[CDataPathProperty::SetControl](#setcontrol)|Устанавливает асинхронный элемент управления ActiveX (OLE), связанный с свойством.|
|[CDataPathProperty::SetPath](#setpath)|Устанавливает имя пути свойства.|

## <a name="remarks"></a>Примечания

Асинхронные свойства загружаются после синхронного начала.

Класс `CDataPathProperty` происходит от `CAysncMonikerFile`. Для реализации асинхронных свойств в элементах управления OLE, получить класс из, `CDataPathProperty`и переопределить [OnDataAvailable.](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)

Для получения дополнительной информации о том, как использовать асинхронные кликеры и элементы управления ActiveX в интернет-приложениях, см.

- [Первые шаги в Интернете: Управление ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Первые шаги Интернета: Асинхронные Моники](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty

Формирует объект `CDataPathProperty`.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на объект управления OLE, связанный с этим `CDataPathProperty` объектом.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного прозвища, которое ссылается на фактическое абсолютное местоположение свойства. `CDataPathProperty`использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, `file://` подготовьтесь к пути.

### <a name="remarks"></a>Примечания

Объект, `COleControl` на который указывает *pControl,* используется `Open` и извлекается полученными классами. Если *pControl* null, то `Open` элемент управления, `SetControl`используемый с, должен быть установлен с . Если *lpszPath* является NULL, вы можете `Open` пройти по `SetPath`пути через или установить его с .

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a>CDataPathProperty::GetControl

Вызов этой функции участника `COleControl` для извлечения объекта, связанного с объектом. `CDataPathProperty`

```
COleControl* GetControl();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на элемент управления `CDataPathProperty` OLE, связанный с объектом. NULL, если не контроль связан.

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a>CDataPathProperty::GetPath

Вызов ислините эту функцию участника `CDataPathProperty` для получения пути, `Open`установленного, когда объект был `SetPath` построен или указан в, или указаны в предыдущем вызове функции участника.

```
CString GetPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя пути в сам уведомую собственность. Может быть пустым, если не указан путь.

## <a name="cdatapathpropertyopen"></a><a name="open"></a>CDataPathProperty::Открыто

Вызовите эту функцию участника, чтобы инициировать загрузку асинхронного свойства для связанного элемента управления.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на объект управления OLE, связанный с этим `CDataPathProperty` объектом.

*pОшибка*<br/>
Указатель на исключение файла. В случае ошибки, будет установлен на причину.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного прозвища, которое ссылается на фактическое абсолютное местоположение свойства. `CDataPathProperty`использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, `file://` подготовьтесь к пути.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Функция пытается получить `IBindHost` интерфейс от управления.

Прежде `Open` чем звонить без пути, значение для пути свойства должно быть установлено. Это может быть сделано, когда объект построен, `SetPath` или повызовуфункции функции члена.

Перед `Open` вызовом без контроля с объектом может быть связан элемент управления ActiveX (ранее известный как элемент управления OLE). Это может быть сделано, когда объект построен, или по звонку. `SetControl`

Все перегрузки [CAsyncMonikerFile::Открыть](../../mfc/reference/casyncmonikerfile-class.md#open) также `CDataPathProperty`доступны из .

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a>CDataPathProperty::ResetData

Вызов используйте эту `CAsyncMonikerFile::OnDataAvailable` функцию, чтобы уведомить контейнер о том, что свойства управления изменились, и вся информация, загруженная асинхронно, больше не полезна.

```
virtual void ResetData();
```

### <a name="remarks"></a>Примечания

Открытие должно быть перезапущено. Выведенные классы могут переопределить эту функцию для различных по умолчанию.

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a>CDataPathProperty::SetControl

Вызовите эту функцию участника, чтобы связать `CDataPathProperty` асинхронный элемент управления OLE с объектом.

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на асинхронный элемент управления OLE, связанный с свойством.

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a>CDataPathProperty::SetPath

Вызовите эту функцию участника, чтобы установить имя пути свойства.

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, к свойству, загружаемому асинхронно. `CDataPathProperty`использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, `file://` подготовьтесь к пути.

## <a name="see-also"></a>См. также раздел

[MFC Образец Изображения](../../overview/visual-cpp-samples.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
