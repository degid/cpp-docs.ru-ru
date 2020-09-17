---
title: Класс Кдатарековерихандлер
ms.date: 03/27/2019
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: 4bb4d4ddf291cb1efc01b887c54a6573c52df8dc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842927"
---
# <a name="cdatarecoveryhandler-class"></a>Класс Кдатарековерихандлер

`CDataRecoveryHandler`Автоматически сохраняет документы и восстанавливает их при неожиданном завершении работы приложения.

## <a name="syntax"></a>Синтаксис

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[Кдатарековерихандлер:: Кдатарековерихандлер](#cdatarecoveryhandler)|Формирует объект `CDataRecoveryHandler`.|

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[Кдатарековерихандлер:: Аутосавеаллдокументинфо](#autosavealldocumentinfo)|Автоматически сохраняет каждый файл, зарегистрированный в `CDataRecoveryHandler` классе.|
|[Кдатарековерихандлер:: Аутосаведокументинфо](#autosavedocumentinfo)|Автоматически сохраняет указанный документ.|
|[Кдатарековерихандлер:: Креатедокументинфо](#createdocumentinfo)|Добавляет документ в список открытых документов.|
|[Кдатарековерихандлер::D Елетеаллаутосаведфилес](#deleteallautosavedfiles)|Удаляет все текущие автоматически сохраненные файлы.|
|[Кдатарековерихандлер::D Елетеаутосаведфиле](#deleteautosavedfile)|Удаляет указанный автоматически сохраненный файл.|
|[Кдатарековерихандлер:: Женератеаутосавефиленаме](#generateautosavefilename)|Создает имя для файла автосохранения, связанного с заданным именем файла документа.|
|[Кдатарековерихандлер:: Жетаутосавеинтервал](#getautosaveinterval)|Возвращает интервал между попытками автосохранения.|
|[Кдатарековерихандлер:: Жетаутосавепас](#getautosavepath)|Возвращает путь к автоматически сохраненным файлам.|
|[Кдатарековерихандлер:: Жетдокументлистнаме](#getdocumentlistname)|Извлекает имя документа из `CDocument` объекта.|
|[Кдатарековерихандлер:: Жетнормалдокументтитле](#getnormaldocumenttitle)|Возвращает стандартный заголовок для указанного документа.|
|[Кдатарековерихандлер:: Жетрековереддокументтитле](#getrecovereddocumenttitle)|Создает и возвращает заголовок для восстановленного документа.|
|[Кдатарековерихандлер:: Жетрестартидентифиер](#getrestartidentifier)|Возвращает уникальный идентификатор перезапуска для приложения.|
|[Кдатарековерихандлер:: Жетсаведокументинфунидле](#getsavedocumentinfoonidle)|Указывает, выполняет ли функция `CDataRecoveryHandler` автосохранения в текущем цикле бездействия.|
|[Кдатарековерихандлер:: Жетшутдовнбирестартманажер](#getshutdownbyrestartmanager)|Указывает, привело ли диспетчеру перезапуска приложение к завершению работы.|
|[Кдатарековерихандлер:: Initialize](#initialize)|Инициализирует объект `CDataRecoveryHandler`.|
|[Кдатарековерихандлер:: Куерирестореаутосаведдокументс](#queryrestoreautosaveddocuments)|Отображает диалоговое окно для каждого документа, `CDataRecoveryHandler` автоматически сохраненного пользователем. Диалоговое окно определяет, хочет ли пользователь восстановить автоматически сохраненный документ.|
|[Кдатарековерихандлер:: Реадопендокументлист](#readopendocumentlist)|Загружает открытый список документов из реестра.|
|[Кдатарековерихандлер:: Ремоведокументинфо](#removedocumentinfo)|Удаляет указанный документ из списка открытых документов.|
|[Кдатарековерихандлер:: Реопенпревиаусдокументс](#reopenpreviousdocuments)|Открывает ранее открытые документы.|
|[Кдатарековерихандлер:: Рестореаутосаведдокументс](#restoreautosaveddocuments)|Восстанавливает автоматически сохраненные документы на основе введенных пользователем данных.|
|[Кдатарековерихандлер:: Савеопендокументлист](#saveopendocumentlist)|Сохраняет текущий список открытых документов в реестре Windows.|
|[Кдатарековерихандлер:: Сетаутосавеинтервал](#setautosaveinterval)|Задает время между циклами автосохранения в миллисекундах.|
|[Кдатарековерихандлер:: Сетаутосавепас](#setautosavepath)|Задает каталог, в котором хранятся автоматически сохраняемые файлы.|
|[Кдатарековерихандлер:: Сетрестартидентифиер](#setrestartidentifier)|Задает уникальный идентификатор перезапуска для данного экземпляра `CDataRecoveryHandler` .|
|[Кдатарековерихандлер:: Сетсаведокументинфунидле](#setsavedocumentinfoonidle)|Указывает, сохраняет ли объект `CDataRecoveryHandler` сведения о открытом документе в реестре Windows во время текущего цикла бездействия.|
|[Кдатарековерихандлер:: Сетшутдовнбирестартманажер](#setshutdownbyrestartmanager)|Указывает, была ли Предыдущая выходная часть приложения вызвана диспетчером перезапуска.|
|[Кдатарековерихандлер:: Упдатедокументинфо](#updatedocumentinfo)|Обновляет сведения для документа, так как пользователь сохранил его.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|m_bRestoringPreviousOpenDocs|Указывает, будет ли обработчик восстановления данных открывать ранее открытые документы.|
|m_bSaveDocumentInfoOnIdle|Указывает, будет ли обработчик восстановления данных автоматически сохранять документы в следующем цикле бездействия.|
|m_bShutdownByRestartManager|Указывает, приводит ли диспетчер перезапуска к завершению работы приложения.|
|m_dwRestartManagerSupportFlags|Флаги, указывающие, какую поддержку предоставляет диспетчер перезапуска для приложения.|
|m_lstAutosavesToDelete|Список автоматически сохраненных файлов, которые не были удалены при закрытии исходных документов. При выходе из приложения Диспетчер перезапуска повторяет попытку удаления файлов.|
|m_mapDocNameToAutosaveName|Соответствие имен документов именам автоматически сохраненных файлов.|
|m_mapDocNameToDocumentPtr|Таблица имен документов для указателей [CDocument](../../mfc/reference/cdocument-class.md) .|
|m_mapDocNameToRestoreBool|Сопоставляет имена документов с логическим параметром, указывающим, следует ли восстанавливать автоматически сохраненный документ.|
|m_mapDocumentPtrToDocName|Таблица `CDocument` указателей на имена документов.|
|m_mapDocumentPtrToDocTitle|Таблица `CDocument` указателей на заголовки документов. Эти заголовки используются для сохранения файлов.|
|m_nAutosaveInterval|Время в миллисекундах между автосохранением.|
|m_nTimerID|Идентификатор таймера автосохранения.|
|m_strAutosavePath|Расположение, в котором хранятся автоматически сохраняемые документы.|
|m_strRestartIdentifier|Строковое представление идентификатора GUID диспетчера перезапуска.|

## <a name="remarks"></a>Примечания

Диспетчер перезапуска использует `CDataRecoveryHandler` класс для наблюдения за всеми открытыми документами и для их автосохранения при необходимости. Чтобы включить Автосохранение, используйте метод [кдатарековерихандлер:: сетсаведокументинфунидле](#setsavedocumentinfoonidle) . Этот метод направляет `CDataRecoveryHandler` для выполнения автосохранения в следующем цикле бездействия. Диспетчер перезапуска вызывает `SetSaveDocumentInfoOnIdle` , когда `CDataRecoveryHandler` должен выполнить Автосохранение.

Все методы `CDataRecoveryHandler` класса являются виртуальными. Переопределите методы в этом классе, чтобы создать пользовательский обработчик восстановления данных. Если не создать собственный обработчик восстановления данных или диспетчер перезапуска, не создавайте экземпляр Кдатарековерихандлер. [Класс CWinApp](../../mfc/reference/cwinapp-class.md) создает `CDataRecoveryHandler` объект по мере необходимости.

Прежде чем можно будет использовать `CDataRecoveryHandler` объект, необходимо вызвать метод [кдатарековерихандлер:: Initialize](#initialize).

Поскольку `CDataRecoveryHandler` класс тесно подключен к диспетчеру перезапуска, `CDataRecoveryHandler` он зависит от глобального параметра `m_dwRestartManagerSupportFlags` . Этот параметр определяет разрешения, которые диспетчер перезапуска имеет и как он взаимодействует с приложением. Чтобы включить диспетчер перезапуска в существующее приложение, необходимо назначить `m_dwRestartManagerSupportFlags` соответствующее значение в конструкторе основного приложения. Дополнительные сведения об использовании диспетчера перезапуска см. [в разделе руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).

## <a name="requirements"></a>Требования

**Заголовок:** афксдатарековери.h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a> Кдатарековерихандлер:: Аутосавеаллдокументинфо

Автоматически сохраняет каждый файл, зарегистрированный в `CDataRecoveryHandler` классе.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если `CDataRecoveryHandler` сохранены все документы; Значение FALSE, если какой либо документ не был сохранен.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если нет документов, которые необходимо сохранить. Он также возвращает значение TRUE без сохранения документов, если при извлечении `CWinApp` или `CDocManager` для приложения возникает ошибка.

Чтобы использовать этот метод, необходимо задать либо AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, либо AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL в `m_dwRestartManagerSupportFlags` . Дополнительные сведения см. [в разделе руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a> Кдатарековерихандлер:: Аутосаведокументинфо

Автоматически сохраняет указанный документ.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на `CDocument` Сохраняемый объект.

*бресетмодифиедфлаг*\
окне Значение TRUE указывает, что параметр `CDataRecoveryHandler` учитывает *пдокумент* для изменения; Значение FALSE указывает, что платформа считает *пдокумент* неизменной. Дополнительные сведения о последствиях этого флага см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если установлены соответствующие флаги и *пдокумент* является допустимым `CDocument` объектом.

### <a name="remarks"></a>Примечания

Каждый `CDocument` объект имеет флаг, указывающий, изменился ли он с момента последнего сохранения. Чтобы определить состояние этого флага, используйте параметр [CDocument:: Modified](../../mfc/reference/cdocument-class.md#ismodified) . Если с `CDocument` момента последнего сохранения объект не изменился, `AutosaveDocumentInfo` удаляет все автоматически сохраненные файлы для этого документа. Если документ был изменен с момента последнего сохранения, то при его закрытии пользователю предлагается сохранить документ перед закрытием.

> [!NOTE]
> Использование *бресетмодифиедфлаг* для изменения состояния документа на неизмененное может привести к потере несохраненных данных пользователем. Если платформа считает документ неизмененным, при закрытии он не предлагает пользователю сохранить.

Этот метод создает исключение с помощью макроса [Assert](diagnostic-services.md#assert) , если *пдокумент* не является допустимым `CDocument` объектом.

Чтобы использовать этот метод, необходимо задать либо AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, либо AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags*.

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a> Кдатарековерихандлер:: Кдатарековерихандлер

Формирует объект `CDataRecoveryHandler`.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>Параметры

*дврестартманажерсуппортфлагс*\
окне Указывает, какие параметры диспетчера перезапуска поддерживаются.

*наутосавеинтервал*\
окне Время между автосохранением. Этот параметр задается в миллисекундах.

### <a name="remarks"></a>Примечания

Платформа MFC автоматически создает `CDataRecoveryHandler` объект для приложения при использовании мастера **создания проекта** . Если вы не настраиваете поведение восстановления данных или диспетчер перезапуска, не следует создавать `CDataRecoveryHandler` объект.

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a> Кдатарековерихандлер:: Креатедокументинфо

Добавляет документ в список открытых документов.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на объект `CDocument` . Этот метод создает сведения о документе для этого `CDocument` .

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод проверяет, существует ли уже *пдокумент* в списке документов перед добавлением документа. Если *пдокумент* уже есть в списке, этот метод удаляет автоматически сохраненный файл, связанный с *пдокумент*.

Чтобы использовать этот метод, необходимо задать либо AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, либо AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags*.

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a> Кдатарековерихандлер::D Елетеаллаутосаведфилес

Удаляет все текущие автоматически сохраненные файлы.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает значение TRUE.

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a> Кдатарековерихандлер::D Елетеаутосаведфиле

Удаляет указанный автоматически сохраненный файл.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Параметры

*страутосаведфиле*\
окне Строка, содержащая имя автоматически сохраненного файла.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Если этот метод не может удалить автоматически сохраненный файл, он сохраняет имя файла в списке. Деструктор для `CDataRecoveryHandler` пытается удалить каждый автоматически сохраненный файл, указанный в этом списке.

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a> Кдатарековерихандлер:: Женератеаутосавефиленаме

Создает имя для файла автосохранения, связанного с заданным именем файла документа.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Параметры

*стрдокументнаме*<br/>
окне Строка, содержащая имя документа. `GenerateAutosaveFileName` использует это имя документа для создания соответствующего имени файла автосохранения.

### <a name="return-value"></a>Возвращаемое значение

Имя файла автосохранения, созданное из *стрдокументнаме*.

### <a name="remarks"></a>Примечания

Каждое имя документа имеет сопоставление "один к одному" с именем файла автосохранения.

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a> Кдатарековерихандлер:: Жетаутосавеинтервал

Возвращает интервал между попытками автосохранения.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число миллисекунд между попытками автосохранения.

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a> Кдатарековерихандлер:: Жетаутосавепас

Возвращает путь к автоматически сохраненным файлам.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расположение, в котором хранятся автоматически сохраняемые документы.

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a> Кдатарековерихандлер:: Жетдокументлистнаме

Извлекает имя документа из `CDocument` объекта.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на объект `CDocument` . `GetDocumentListName` Извлекает имя документа из этого `CDocument` .

### <a name="return-value"></a>Возвращаемое значение

Имя документа из *пдокумент*.

### <a name="remarks"></a>Примечания

`CDataRecoveryHandler`Использует имя документа в качестве ключа в *m_mapDocNameToAutosaveName*, *m_mapDocNameToDocumentPtr*и *m_mapDocNameToRestoreBool*. Этот параметр позволяет `CDataRecoveryHandler` отслеживать `CDocument` объекты, имя файла автосохранения и параметры автосохранения.

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a> Кдатарековерихандлер:: Жетнормалдокументтитле

Возвращает стандартный заголовок для указанного документа.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на объект `CDocument` .

### <a name="return-value"></a>Возвращаемое значение

Стандартный заголовок для указанного документа.

### <a name="remarks"></a>Примечания

Обычный заголовок документа обычно представляет собой имя файла документа без пути. Это заголовок в поле **имя файла** диалогового окна **Сохранить как** .

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a> Кдатарековерихандлер:: Жетрековереддокументтитле

Создает и возвращает заголовок для восстановленного документа.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Параметры

*стрдокументтитле*<br/>
окне Обычная подпись для документа.

### <a name="return-value"></a>Возвращаемое значение

Название восстановленного документа.

### <a name="remarks"></a>Примечания

По умолчанию восстановленный заголовок документа является обычным названием с добавленным к нему **[восстановленным]** . При `CDataRecoveryHandler` запросе пользователя на восстановление автоматически сохраненных документов отображается имя пользователя.

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a> Кдатарековерихандлер:: Жетрестартидентифиер

Возвращает уникальный идентификатор перезапуска для приложения.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор перезапуска.

### <a name="remarks"></a>Примечания

Идентификатор перезапуска уникален для каждого выполнения приложения.

В `CDataRecoveryHandler` реестре хранятся сведения о документах, открытых в настоящий момент. Когда диспетчер перезапуска завершает работу приложения и перезапускает его, он передает идентификатор перезапуска `CDataRecoveryHandler` . `CDataRecoveryHandler`Использует идентификатор перезапуска для получения списка ранее открытых документов. Это позволяет `CDataRecoveryHandler` пытаться найти и восстановить автоматически сохраненные файлы.

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a> Кдатарековерихандлер:: Жетсаведокументинфунидле

Указывает, выполняет ли функция `CDataRecoveryHandler` автосохранения в текущем цикле бездействия.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает на `CDataRecoveryHandler` Автосохранение в текущем цикле бездействия; Значение FALSE указывает, что это не так.

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a> Кдатарековерихандлер:: Жетшутдовнбирестартманажер

Указывает, привело ли диспетчеру перезапуска приложение к завершению работы.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска привел к завершению работы приложения; Значение FALSE указывает, что это не так.

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a> Кдатарековерихандлер:: Initialize

Инициализирует объект `CDataRecoveryHandler`.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация выполнена успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Процесс инициализации загружает путь для хранения файлов автосохранения из реестра. Если `Initialize` метод не может найти этот каталог или если путь РАВЕН null, `Initialize` завершается с ошибкой и возвращается значение `FALSE` .

Используйте [кдатарековерихандлер:: сетаутосавепас](#setautosavepath) , чтобы изменить путь автосохранения после того, как приложение инициализирует `CDataRecoveryHandler` .

Этот `Initialize` метод также запускает таймер, который отслеживает, когда происходит следующее сохранение. Используйте [кдатарековерихандлер:: сетаутосавеинтервал](#setautosaveinterval) для изменения интервала автосохранения после того, как приложение инициализирует `CDataRecoveryHandler` .

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a> Кдатарековерихандлер:: Куерирестореаутосаведдокументс

Отображает диалоговое окно для каждого документа, `CDataRecoveryHandler` автоматически сохраненного пользователем. Диалоговое окно определяет, хочет ли пользователь восстановить автоматически сохраненный документ.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Примечания

Если приложение имеет кодировку Unicode, этот метод отображает [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для пользователя. В противном случае платформа использует [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) для запроса пользователя.

После `QueryRestoreAutosavedDocuments` сбора всех ответов от пользователя данные сохраняются в переменной члена *m_mapDocNameToRestoreBool*. Этот метод не восстанавливает автоматически сохраненные документы.

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a> Кдатарековерихандлер:: Реадопендокументлист

Загружает открытый список документов из реестра.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что `ReadOpenDocumentList` загружены сведения по крайней мере для одного документа из реестра. Значение FALSE указывает, что сведения о документе не загружены.

### <a name="remarks"></a>Примечания

Эта функция загружает сведения о открытом документе из реестра и сохраняет их в переменной члена *m_mapDocNameToAutosaveName*.

После `ReadOpenDocumentList` загрузки всех данных он удаляет из реестра сведения о документе.

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a> Кдатарековерихандлер:: Ремоведокументинфо

Удаляет указанный документ из списка открытых документов.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на документ, который необходимо удалить.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *пдокумент* был удален из списка. Значение FALSE, если произошла ошибка.

### <a name="remarks"></a>Примечания

Когда пользователь закрывает документ, платформа использует этот метод, чтобы удалить его из списка открытых документов.

Если `RemoveDocumentInfo` не удается найти *пдокумент* в списке открытых документов, он не выполняет никаких действий и возвращает значение true.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES необходимо задать в *m_dwRestartManagerSupportFlags*.

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a> Кдатарековерихандлер:: Реопенпревиаусдокументс

Открывает ранее открытые документы.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если был открыт хотя бы один документ; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод открывает Последнее сохранение ранее открытых документов. Если документ не был сохранен или автосохранен, `ReopenPreviousDocuments` открывает пустой документ на основе шаблона для этого типа файлов.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES необходимо задать в *m_dwRestartManagerSupportFlags*. Если этот параметр не задан, функция `ReopenPreviousDocuments` не выполняет никаких действий и возвращает значение false.

Если в списке ранее открытых документов нет документов, `ReopenPreviousDocuments` не выполняет никаких действий и возвращает значение false.

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a> Кдатарековерихандлер:: Рестореаутосаведдокументс

Восстанавливает автоматически сохраненные документы на основе введенных пользователем данных.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно восстанавливает документы.

### <a name="remarks"></a>Примечания

Этот метод вызывает [кдатарековерихандлер:: куерирестореаутосаведдокументс](#queryrestoreautosaveddocuments) для определения документов, которые пользователь хочет восстановить. Если пользователь решает не восстанавливать автоматически сохраненный документ, `RestoreAutosavedDocuments` удаляется файл автосохранения. В противном случае `RestoreAutosavedDocuments` заменяет открытый документ на автоматически сохраненную версию.

Чтобы использовать этот метод, необходимо задать либо AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES, либо AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES в `m_dwRestartManagerSupportFlags` .

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a> Кдатарековерихандлер:: Савеопендокументлист

Сохраняет текущий список открытых документов в реестре Windows.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если нет открытых документов для сохранения или если они были успешно сохранены. Значение FALSE, если имеются документы для сохранения в реестре, но они не были сохранены из-за ошибки.

### <a name="remarks"></a>Примечания

Диспетчер перезапуска вызывает, `SaveOpenDocumentList` когда приложение неожиданно завершает работу или закрывается для обновления. При перезапуске приложения для получения списка открытых документов используется [кдатарековерихандлер:: реадопендокументлист](#readopendocumentlist) .

Этот метод сохраняет только список открытых документов. Метод [кдатарековерихандлер:: аутосаведокументинфо](#autosavedocumentinfo) отвечает за сохранение самих документов.

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a> Кдатарековерихандлер:: Сетаутосавеинтервал

Задает время между циклами автосохранения в миллисекундах.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Параметры

*наутосавеинтервал*<br/>
окне Новый интервал автосохранения в миллисекундах.

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a> Кдатарековерихандлер:: Сетаутосавепас

Задает каталог, в котором хранятся автоматически сохраняемые файлы.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Параметры

*страутосавепас*\
окне Путь, по которому хранятся файлы автосохранения.

### <a name="remarks"></a>Примечания

Изменение каталога автосохранения не приводит к перемещению автоматически сохраненных файлов.

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a> Кдатарековерихандлер:: Сетрестартидентифиер

Задает уникальный идентификатор перезапуска для данного экземпляра `CDataRecoveryHandler` .

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Параметры

*стррестартидентифиер*\
окне Уникальный идентификатор диспетчера перезапуска.

### <a name="remarks"></a>Примечания

Диспетчер перезапуска записывает сведения об открытых документах в реестре. Эта информация хранится с уникальным идентификатором перезапуска в качестве ключа. Поскольку идентификатор перезапуска уникален для каждого экземпляра приложения, несколько экземпляров приложения могут неожиданно завершить работу, и диспетчер перезапуска может восстановить каждый из них.

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a> Кдатарековерихандлер:: Сетсаведокументинфунидле

Указывает, сохраняет ли объект `CDataRecoveryHandler` сведения о открытом документе в реестре Windows во время текущего цикла бездействия.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Параметры

*бсавеонидле*\
окне Значение TRUE, чтобы сохранять сведения о документе во время текущего цикла бездействия; Значение FALSE, чтобы не выполнять сохранение.

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a> Кдатарековерихандлер:: Сетшутдовнбирестартманажер

Указывает, была ли Предыдущая выходная часть приложения вызвана диспетчером перезапуска.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Параметры

*бшутдовнбирестартманажер*\
окне Значение TRUE указывает, что диспетчер перезапуска привел к завершению работы приложения; Значение FALSE, чтобы указать, что приложение завершилось по другой причине.

### <a name="remarks"></a>Примечания

Платформа ведет себя по-разному в зависимости от того, была ли Предыдущая выход непредвиденной или была инициирована диспетчером перезапуска.

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a> Кдатарековерихандлер:: Упдатедокументинфо

Обновляет сведения для документа, так как пользователь сохранил его.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

*пдокумент*\
окне Указатель на сохраненный документ.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод удалил автоматически сохраненный документ и обновил сведения о документе. Значение FALSE, если произошла ошибка.

### <a name="remarks"></a>Примечания

Когда пользователь сохраняет документ, приложение удаляет автоматически сохраненный файл, так как он больше не нужен. `UpdateDocumentInfo` удаляет автоматически сохраненный файл путем вызова [кдатарековерихандлер:: ремоведокументинфо](#removedocumentinfo). `UpdateDocumentInfo` затем добавляет сведения из *пдокумент* в список открытых документов `RemoveDocumentInfo` , поскольку удаляет эти сведения, но сохраненный документ остается открытым.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES необходимо задать в *m_dwRestartManagerSupportFlags*.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Как добавить поддержку диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)
