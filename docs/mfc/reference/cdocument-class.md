---
title: Класс CDocument
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: d356ba6b6134221c2fc9595fc6d78f91961c5b7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753243"
---
# <a name="cdocument-class"></a>Класс CDocument

Предоставляет базовую функциональность для определяемых пользователем классов документа.

## <a name="syntax"></a>Синтаксис

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDocument::CDocument](#cdocument)|Формирует объект `CDocument`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDocument::AddView](#addview)|Прикрепляет представление к документу.|
|[CDocument::BeginReadChunks](#beginreadchunks)|Инициализирует чтение куска.|
|[CDocument::CanCloseFrame](#cancloseframe)|Расширенный overridable; вызов перед закрытием окна кадра, просматривая этот документ.|
|[CDocument::ClearChunkList](#clearchunklist)|Очищает список кусков.|
|[CDocument::ClearPathName](#clearpathname)|Очищает путь объекта документа.|
|[CDocument::DeleteКонтенты](#deletecontents)|Вызывается для выполнения очистки документа.|
|[CDocument::FindChunk](#findchunk)|Ищет кусок с указанным GUID.|
|[CDocument::GetAdapter](#getadapter)|Возвращает указатель на объектный интерфейс реализации. `IDocument`|
|[CDocument::GetDocTemplate](#getdoctemplate)|Возвращает указатель на шаблон документа, описывающий тип документа.|
|[Документ::GetFile](#getfile)|Возвращает указатель на `CFile` нужный объект.|
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Возвращает позицию первой в списке представлений; используется для начала итерации.|
|[CDocument::GetNextView](#getnextview)|Итерирует список представлений, связанных с документом.|
|[CDocument::GetPathName](#getpathname)|Возвращает путь файла данных документа.|
|[CDocument::GetThumbnail](#getthumbnail)|Вызывается для создания bitmap, которые будут использоваться миниатюры поставщика для отображения эскизов.|
|[CDocument::GetTitle](#gettitle)|Возвращает название документа.|
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Вызывается для инициализации содержимого поиска для обработчика поиска.|
|[CDocument::Ismodified](#ismodified)|Указывается, был ли документ изменен с момента его последнего сохранения.|
|[Документ::IsSearchandорганизуехендлер](#issearchandorganizehandler)|Сообщает, был `CDocument` ли этот экземпляр объекта создан для обработчика & организации поиска.|
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Вызывается для загрузки данных документов из потока.|
|[Документ::НапредсяРихПревьюфонтизменен](#onbeforerichpreviewfontchanged)|Вызывается до того, как шрифт Rich Preview будет изменен.|
|[Документ::Измененныйввввлист](#onchangedviewlist)|Вызывается после добавления представления или удаления из документа.|
|[Документ::OnCloseDocument](#onclosedocument)|Позвонил, чтобы закрыть документ.|
|[Документ::OnCreatePreviewFrame](#oncreatepreviewframe)|Вызывается по системе, когда это необходимо для создания рамки предварительного просмотра для Рич Предварительный просмотр.|
|[Документ::OnDocumentEvent](#ondocumentevent)|Вызывается рамками в ответ на событие документа.|
|[Документ::OndrawThumbnail](#ondrawthumbnail)|Переопределить этот метод в производном классе, чтобы нарисовать содержимое эскиза.|
|[Документ::OnloadDocumentFromstream](#onloaddocumentfromstream)|Вызывается инфраструктурой, когда это необходимо для загрузки данных документа из потока.|
|[Документ::OnNewDocument](#onnewdocument)|Вызывается для создания нового документа.|
|[Документ::OnOpenDocument](#onopendocument)|Вызывается, чтобы открыть существующий документ.|
|[Документ::НаPreviewHandler'sfocus](#onpreviewhandlerqueryfocus)|Направляет обработчик предварительного просмотра, чтобы вернуть HWND от вызова функции GetFocus.|
|[CDocument::OnPreviewHandlerПеревод](#onpreviewhandlertranslateaccelerator)|Направляет обработчик предварительного просмотра для обработки нажатия клавиши, пройденный от насоса сообщения процесса, в котором работает обработчик предварительного просмотра.|
|[Документ::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Вызывается, когда Богатые Предварительный фон цвет изменился.|
|[Документ::OnRichPreviewFont](#onrichpreviewfontchanged)|Вызывается, когда Рич Предварительный шрифт изменился.|
|[Документ::OnRichPreviewSiteИзменен](#onrichpreviewsitechanged)|Вызывается, когда Богатые Предварительный сайт изменился.|
|[Документ::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Вызывается, когда Богатые Предварительный цвет текста изменился.|
|[Документ::OnSaveDocument](#onsavedocument)|Вызывается, чтобы сохранить документ на диске.|
|[Документ::OnunloadHandler](#onunloadhandler)|Вызывается в рамках при выгрузке обработчика предварительного просмотра.|
|[CDocument::PreCloseFrame](#precloseframe)|Вызывается до закрытия окна рамы.|
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Читает следующее значение фрагмента.|
|[Документ::ReleaseFile](#releasefile)|Выпускает файл, чтобы сделать его доступным для использования другими приложениями.|
|[CDocument::RemoveChunk](#removechunk)|Удаляет кусок с указанным GUID.|
|[CDocument::RemoveView](#removeview)|Отсеивает представление из документа.|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Расширенный overridable; вызова, когда операция открытия или сохранения не может быть завершена из-за исключения.|
|[CDocument::СохранениеИзменено](#savemodified)|Расширенный overridable; для того, чтобы спросить пользователя, следует ли сохранять документ.|
|[CDocument::SetChunkValue](#setchunkvalue)|Устанавливает значение куска.|
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Устанавливает флаг, указывающий на то, что вы изменили документ с момента его последнего сохранения.|
|[CDocument::SetPathName](#setpathname)|Устанавливает траекторию файла данных, используемого документом.|
|[CDocument::SetTitle](#settitle)|Устанавливает название документа.|
|[CDocument:UpdateAllViews](#updateallviews)|Уведомляет все представления, которые документ был изменен.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Документ::OnFileSendMail](#onfilesendmail)|Отправляет почтовое сообщение с приложеным документом.|
|[Документ::OnUpdateFileSendMail](#onupdatefilesendmail)|Позволяет командовать отправить почту при наличии почтовой поддержки.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Указывает, что `CDocument` объект был создан dllhost для эскизов. Следует проверить `CView::OnDraw`.|
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Уточняется, что `CDocument` объект был создан prevhost для `Rich Preview`. Следует проверить `CView::OnDraw`.|
|[CDocument::m_bSearchMode](#m_bsearchmode)|Уточняется, что `CDocument` объект был создан индексом или другим поисковым приложением.|
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Определяет цвет фона окна Rich Preview. Этот цвет устанавливается хостом.|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Определяет цвет переднего плана окна Rich Preview. Этот цвет устанавливается хостом.|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Определяет текстовый шрифт для окна Rich Preview. Эта информация о шрифте устанавливается хостом.|

## <a name="remarks"></a>Примечания

Документ представляет единицу данных, которую пользователь обычно открывает с помощью команды File Open и сохраняет с помощью команды Сохранения файлов.

`CDocument`поддерживает стандартные операции, такие как создание документа, его загрузка и сохранение. Фреймов манипулирует `CDocument`документами, используя интерфейс, определяемый .

Приложение может поддерживать более одного типа документа; например, приложение может поддерживать как электронные таблицы, так и текстовые документы. Каждый тип документа имеет связанный шаблон документа; шаблон документа определяет, какие ресурсы (например, таблица меню, значок или таблица ускорителей) используются для этого типа документа. Каждый документ содержит указатель `CDocTemplate` на связанный с ним объект.

Пользователи взаимодействуют с документом через связанный с ним объект [CView(s).](../../mfc/reference/cview-class.md) Представление отображает изображение документа в окне кадра и интерпретирует пользовательский ввод как операции на документе. Документ может иметь несколько представлений, связанных с ним. Когда пользователь открывает окно документа, фреймворк создает представление и прикрепляет его к документу. Шаблон документа определяет, какой тип представления и окна кадра используются для отображения каждого типа документа.

Документы являются частью стандартной командной передачи инфраструктуры и, следовательно, получают команды из стандартных компонентов пользовательского интерфейса (например, элемент меню Сохранение файлов). Документ получает команды, переадресованные активным представлением. Если документ не обрабатывает заданную команду, он перенаправляет команду в шаблон документа, который управляет ею.

При изменении данных документа каждое его мнение должно отражать эти изменения. `CDocument`предоставляет функцию участника [UpdateAllViews](#updateallviews) для того, чтобы вы могли уведомлять представления о таких изменениях, чтобы представления могли перекрасить себя по мере необходимости. Платформа также побуждает пользователя сохранить измененный файл перед его закрытием.

Для реализации документов в типичном приложении необходимо сделать следующее:

- Вывести класс `CDocument` из каждого типа документа.

- Добавление переменных членов для хранения данных каждого документа.

- Реализация функций участника для чтения и изменения данных документа. Мнения документа являются наиболее важными пользователями этих функций-членов.

- Переизобить [cObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функцию элемента в классе документов для записи и чтения данных документа на диск и с диска.

`CDocument`поддерживает отправку документа по почте, если поддержка почты (MAPI) присутствует. Смотрите статьи [MAPI](../../mfc/mapi.md) и [MAPI Поддержки в МФЦ](../../mfc/mapi-support-in-mfc.md).

Для получения `CDocument`дополнительной информации о , см. [Serialization](../../mfc/serialization-in-mfc.md), [Документ / Просмотр Архитектура Темы](../../mfc/document-view-architecture.md), и [документ / просмотр создания](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cdocumentaddview"></a><a name="addview"></a>CDocument::AddView

Вызовите эту функцию, чтобы прикрепить представление к документу.

```cpp
void AddView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Точки добавления представления.

### <a name="remarks"></a>Примечания

Эта функция добавляет указанное представление в список представлений, связанных с документом; функция также устанавливает указатель документа представления на этот документ. Платформа вызывает эту функцию при присоединении вновь созданного объекта представления к документу; это происходит в ответ на команду File New, File Open или New Window или при разделении окна сплиттера.

Вызов ими функции только в том случае, если вы вручную создаете и прикрепляете представление. Обычно необходимо, чтобы фреймворк соединял документы и представления, определив объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для ассоциирования класса документов, класса представления и класса оконного окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

## <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks

Инициализирует чтение куска.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame

Вызывается фреймворком перед тем, как окно кадра, отображающее документ, закрывается.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Указывает на окно рамы, прикрепленное к документу.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если безопасно закрыть окно рамы; в противном случае 0.

### <a name="remarks"></a>Примечания

Проверка реализации по умолчанию, если есть другие окна кадра, отображающие документ. Если указанное окно кадра является последним, отображаемым документом, функция предлагает пользователю сохранить документ, если он был изменен. Переопределить эту функцию, если вы хотите выполнить специальную обработку, когда окно кадра закрыто. Это передовой overridable.

## <a name="cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument

Формирует объект `CDocument`.

```
CDocument();
```

### <a name="remarks"></a>Примечания

Платформа обрабатывает создание документов для вас. Переопределение функции участника [OnNewDocument](#onnewdocument) для выполнения инициализации на основе в основе в основе документов; это особенно важно в приложениях интерфейса единого документа (SDI).

## <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList

Очищает список кусков.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName

Очищает путь объекта документа.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Примечания

Очистка пути `CDocument` от объекта заставляет приложение подсказывать пользователю при следующем сохранении документа. Это делает команду **Сохранить** вести себя как команда **Сохранить как.**

## <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a>CDocument::DeleteКонтенты

Вызывается рамкой для удаления данных документа, не разрушая сам `CDocument` объект.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Примечания

Это называется как раз перед тем, как документ должен быть уничтожен. Он также требует, чтобы убедиться, что документ пуст перед повторного использования. Это особенно важно для приложения SDI, в котором используется только один документ; документ используется повторно всякий раз, когда пользователь создает или открывает другой документ. Вызовите эту функцию для реализации "Edit Clear All" или аналогичной команды, которая удаляет все данные документа. Реализация по умолчанию этой функции не выполняет никаких действий. Переуверьте эту функцию для удаления данных в документе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

## <a name="cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk

Ищет кусок с указанным GUID.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*guid*<br/>
Определяет GUID кусок, чтобы найти.

*Pid*<br/>
Определяет PID кусок, чтобы найти.

### <a name="return-value"></a>Возвращаемое значение

Позиция во внутреннем списке кусков в случае успеха. В противном случае NULL.

### <a name="remarks"></a>Примечания

## <a name="cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter

Возвращает указатель объекту, реализующего `IDocument` интерфейс.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, реализующий `IDocument` интерфейс.

### <a name="remarks"></a>Примечания

## <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate

Вызовите эту функцию, чтобы получить указатель на шаблон документа для этого типа документа.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на шаблон документа для этого типа документа или NULL, если документ не управляется шаблоном документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

## <a name="cdocumentgetfile"></a><a name="getfile"></a>Документ::GetFile

Вызовите эту функцию участника, `CFile` чтобы получить указатель на объект.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, которая является путь к желаемому файлу. Путь может быть относительным или абсолютным.

*pОшибка*<br/>
Указатель на существующий объект исключения файла, указывающий состояние завершения операции.

*nОткрытыефлаги*<br/>
Режим обмена и доступа. Упоняет действие, необходимое при открытии файла. Вы можете комбинировать параметры, перечисленные в конструкторе [CFile::CFile,](../../mfc/reference/cfile-class.md#cfile) используя bitwise OR (&#124;) оператора. Требуется одно разрешение на доступ и один опцион на участие; `modeCreate` режимы `modeNoInherit` и режимы не являются обязательными.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CFile`.

## <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition

Назовите эту функцию, чтобы получить позицию первого представления в списке представлений, связанных с документом.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации с функцией участника [GetNextView.](#getnextview)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView

Назовите эту функцию итерировать через все мнения документа.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение POSITION, возвращенное `GetNextView` предыдущим вызовом на функции участника или [GetFirstViewPosition.](#getfirstviewposition) Это значение не должно быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на представление, идентифицированное *rPosition.*

### <a name="remarks"></a>Примечания

Функция возвращает представление, идентифицированное *rPosition,* а затем устанавливает *rPosition* к значению POSITION следующего представления в списке. Если извлеченное представление является последним в списке, то *rPosition* устанавливается в NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName

Вызовите эту функцию, чтобы получить полностью квалифицированный путь дискового файла документа.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Документ полностью квалифицированный путь. Эта строка пуста, если документ не был сохранен или не имеет дискового файла, связанного с ним.

## <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail

Создает бит-карту, которая будет использоваться поставщиком эскизов для отображения эскиза.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Параметры

*Cx*<br/>
Определяет ширину и высоту битной карты.

*phbmp*<br/>
Содержит ручку к битной карте, когда функция успешно возвращается.

*pdwAlpha*<br/>
Содержит DWORD, определяющий значение альфа-канала, когда функция успешно возвращается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если бит-карта для эскиза была создана успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle

Позвоните в эту функцию, чтобы получить название документа, которое обычно происходит от имени файла документа.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название документа.

## <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent

Вызывается для инициализации содержимого поиска для обработчика поиска.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе, чтобы инициализировать содержимое поиска. Содержимое должно быть строкой с частями, делимитированным ";". Например, "точка; прямоугольник; ole пункт".

## <a name="cdocumentismodified"></a><a name="ismodified"></a>CDocument::Ismodified

Вызовите эту функцию, чтобы определить, был ли документ изменен с момента его последнего сохранения.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если документ был изменен с момента его последнего сохранения; в противном случае 0.

## <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>Документ::IsSearchandорганизуехендлер

Сообщает, `CDocument` был ли этот экземпляр создан для обработчика «Поиск & организации».

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если `CDocument` этот экземпляр был создан для обработчика & организации поиска.

### <a name="remarks"></a>Примечания

В настоящее время эта функция возвращает TRUE только для обработчиков Rich Preview, реализованных в сервере, не работаемом процессу. Вы можете установить соответствующие флаги (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) на уровне приложения, чтобы сделать эту функцию вернуться true.

## <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream

Вызывается для загрузки данных документов из потока.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на поток. Этот поток поставляется Shell.

*dwGrfMode*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция нагрузки удалась, в противном случае HRESULT с кодом ошибки.

### <a name="remarks"></a>Примечания

Этот метод можно переопределить в производном классе, чтобы настроить способзагрузки данных из потока.

## <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode

Уточняется, что `CDocument` объект был создан dllhost для эскизов. Следует проверить `CView::OnDraw`.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Примечания

`TRUE`указывает на то, что документ был создан dllhost для эскизов.

## <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode

Уточняется, что `CDocument` объект был создан превхостом для Rich Preview. Следует проверить `CView::OnDraw`.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Примечания

TRUE указывает, что документ был создан prevhost для Рич Предварительный просмотр.

## <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode

Уточняется, что `CDocument` объект был создан индексатором или другим поисковым приложением.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Примечания

`TRUE`указывает на то, что документ был создан индексатором или другим поисковым приложением.

## <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor

Определяет цвет фона окна Rich Preview. Этот цвет устанавливается хостом.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor

Определяет цвет переднего плана окна Rich Preview. Этот цвет устанавливается хостом.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont

Определяет текстовый шрифт для окна Rich Preview. Эта информация о шрифте устанавливается хостом.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>Документ::НапредсяРихПревьюфонтизменен

Вызывается до того, как шрифт Rich Preview будет изменен.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>Документ::Измененныйввввлист

Вызывается инфраструктурой после добавления представления или удаления из документа.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию проверяет, удаляется ли последнее представление, и, если да, удаляет документ. Переопределить эту функцию, если вы хотите выполнить специальную обработку, когда фреймворк добавляет или удаляет представление. Например, если вы хотите, чтобы документ оставался открытым, даже если к нему нет представлений, отмените эту функцию.

## <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a>Документ::OnCloseDocument

Вызывается системой при закрытии документа, как правило, как часть команды File Close.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию уничтожает все кадры, используемые для просмотра документа, закрывает представление, очищает содержимое документа, а затем вызывает функцию участника [DeleteContents,](#deletecontents) чтобы удалить данные документа.

Переопределить эту функцию, если вы хотите выполнить специальную очистку, когда фреймворк закрывает документ. Например, если документ представляет запись в базе данных, можно переопределить эту функцию для закрытия базы данных. Вы должны вызвать версию базового класса этой функции из переопределения.

## <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>Документ::OnCreatePreviewFrame

Вызывается по системе, когда это необходимо для создания рамки предварительного просмотра для Рич Предварительный просмотр.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если кадр создан успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a>Документ::OnDocumentEvent

Вызывается рамками в ответ на событие документа.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Параметры

*deEvent*<br/>
(в) Перечисленный тип данных, описывающий тип события.

### <a name="remarks"></a>Примечания

События документов могут повлиять на несколько классов. Этот метод отвечает за обработку событий документов, которые влияют на классы, отличные от [класса CDocument.](../../mfc/reference/cdocument-class.md) В настоящее время единственным классом, который должен реагировать на события документа, является [класс CDataRecoveryHandler.](../../mfc/reference/cdatarecoveryhandler-class.md) Класс `CDocument` имеет другие переизменяемые методы, ответственные за обработку эффекта `CDocument`на .

В следующей таблице перечислены возможные значения *для deEvent* и события, которым они соответствуют.

|Значение|Соответствующее событие|
|-----------|-------------------------|
|`onAfterNewDocument`|Был создан новый документ.|
|`onAfterOpenDocument`|Был открыт новый документ.|
|`onAfterSaveDocument`|Документ был сохранен.|
|`onAfterCloseDocument`|Документ был закрыт.|

## <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>Документ::OndrawThumbnail

Переопределить этот метод в производном классе, чтобы нарисовать эскиз.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
Ссылка на контекст устройства.

*lprcBounds*<br/>
Определяет ограничивающий прямоугольник области, где эскиз должен быть нарисован.

### <a name="remarks"></a>Примечания

## <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>Документ::OnFileSendMail

Отправляет сообщение через резидента почты хост (если таковые имеется) с документом в качестве вложения.

```cpp
void OnFileSendMail();
```

### <a name="remarks"></a>Примечания

`OnFileSendMail`вызывает [OnSaveDocument](#onsavedocument) для сериализации (сохранения) безымянных и измененных документов во временный файл, который затем отправляется по электронной почте. Если документ не был изменен, временный файл не нужен; оригинал отправляется. `OnFileSendMail`загружает MAPI32. DLL, если он еще не загружен.

Специальная реализация `OnFileSendMail` для [COleDocument](../../mfc/reference/coledocument-class.md) обрабатывает сложные файлы правильно.

`CDocument`поддерживает отправку документа по почте, если поддержка почты (MAPI) присутствует. Смотрите статьи [MAPI Темы](../../mfc/mapi.md) и [MAPI поддержки в МФЦ](../../mfc/mapi-support-in-mfc.md).

## <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>Документ::OnloadDocumentFromstream

Вызывается инфраструктурой, когда необходимо загрузить данные документа из потока.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на входящий поток.

*grfMode*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если нагрузка удачна; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a>Документ::OnNewDocument

Вызывается в рамках команды File New.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Незерно, если документ был успешно инициализирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию вызывает функцию элемента [DeleteContents,](#deletecontents) чтобы убедиться, что документ пуст, а затем помечает новый документ как чистый. Переопределить эту функцию, чтобы инициализировать структуру данных для нового документа. Вы должны вызвать версию базового класса этой функции из переопределения.

Если пользователь выбирает команду File New в приложении SDI, платформа использует эту функцию для репренезификализации существующего документа, а не для создания нового. Если пользователь выбирает File New в приложении с несколькими документами интерфейса (MDI), платформа каждый раз создает новый документ, а затем вызывает эту функцию, чтобы инициализировать его. Вы должны поместить код инициализации в эту функцию, а не в конструктор, чтобы команда File New была эффективной в приложениях SDI.

Обратите внимание, что `OnNewDocument` Есть случаи, когда называется дважды. Это происходит, когда документ встраивается в качестве сервера документов ActiveX. Функция сначала вызывается `CreateInstance` методом (подвергается `COleObjectFactory`-производным классом) `InitNew` и второй `COleServerDoc`раз методом (подвергается -производным классом).

### <a name="example"></a>Пример

Следующие примеры иллюстрируют альтернативные методы инициализации объекта документа.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

## <a name="cdocumentonopendocument"></a><a name="onopendocument"></a>Документ::OnOpenDocument

Вызывается инфраструктурой в рамках команды File Open.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает на путь открытия документа.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если документ был успешно загружен; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию открывает указанный файл, вызывает функцию элемента [DeleteContents,](#deletecontents) чтобы убедиться, что документ пуст, вызывает [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для чтения содержимого файла, а затем помечает документ как чистый. Переопределить эту функцию, если вы хотите использовать что-то другое, чем механизм архива или файловый механизм. Например, можно написать приложение, в котором документы представляют записи в базе данных, а не отдельные файлы.

Если пользователь выбирает команду File Open в приложении SDI, платформа использует эту `CDocument` функцию для репренезификализации существующего объекта, а не для создания нового. Если пользователь выбирает File Open в приложении MDI, `CDocument` платформа каждый раз выстраивает новый объект, а затем вызывает эту функцию, чтобы инициализировать его. Вы должны поместить код инициализации в эту функцию, а не в конструктор, чтобы команда File Open была эффективной в приложениях SDI.

### <a name="example"></a>Пример

Следующие примеры иллюстрируют альтернативные методы инициализации объекта документа.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

## <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>Документ::НаPreviewHandler'sfocus

Направляет обработчик предварительного просмотра, чтобы вернуть `GetFocus` HWND, извлеченный из вызова функции.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Параметры

*phwnd*<br/>
(ваут) Когда этот метод возвращается, содержит указатель на HWND, возвращенный из вызова `GetFocus` функции из переднего плана обработчика предварительного просмотра.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха; или значение ошибки в противном случае.

### <a name="remarks"></a>Примечания

## <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerПеревод

Направляет обработчик предварительного просмотра для обработки нажатия клавиши, пройденный от насоса сообщения процесса, в котором работает обработчик предварительного просмотра.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Параметры

*pmsg*<br/>
(в) Указатель на сообщение окна.

### <a name="return-value"></a>Возвращаемое значение

Если сообщение нажатия клавишможет может быть обработано обработчиком предварительного просмотра, обработчик обрабатывает его и возвращает S_OK. Если обработчик предварительного просмотра не может обработать `IPreviewHandlerFrame::TranslateAccelerator`сообщение нажатия клавиши, он предлагает его хосу через . Если узла обрабатывает сообщение, этот метод возвращается S_OK. Если узел не обрабатывает сообщение, этот метод возвращается S_FALSE.

### <a name="remarks"></a>Примечания

## <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>Документ::OnRichPreviewBackColorChanged

Вызывается, когда Богатый Предварительный фон овый цвет изменился.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>Документ::OnRichPreviewFont

Вызывается, когда ричный шрифт Preview изменился.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>Документ::OnRichPreviewSiteИзменен

Вызывается, когда Богатые Предварительный сайт изменился.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>Документ::OnRichPreviewTextColorChanged

Вызывается, когда Богатый Предварительный текст цвет изменился.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a>Документ::OnSaveDocument

Вызывается инфраструктурой как часть команды Сохранения файлов или файла.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает на полностью квалифицированный путь, на котором файл должен быть сохранен.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если документ был успешно сохранен; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию открывает указанный файл, вызывает [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для записи данных документа в файл, а затем помечает документ как чистый. Переопределить эту функцию, если требуется выполнять специальную обработку, когда фреймворк сохраняет документ. Например, можно написать приложение, в котором документы представляют записи в базе данных, а не отдельные файлы.

## <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>Документ::OnunloadHandler

Вызывается системой при выгрузке обработчика предварительного просмотра.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Примечания

## <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>Документ::OnUpdateFileSendMail

Позволяет ID_FILE_SEND_MAIL команду, если поддержка почты (MAPI) присутствует.

```cpp
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на объект [CCmdUI,](../../mfc/reference/ccmdui-class.md) связанный с командой ID_FILE_SEND_MAIL.

### <a name="remarks"></a>Примечания

В противном случае функция удаляет ID_FILE_SEND_MAIL команду из меню, включая сепараторы выше или ниже пункта меню по мере необходимости. MAPI включен, если MAPI32. DLL присутствует на пути и, в разделе «Почта» WIN. Файл INI, МАДИ-1. Большинство приложений помещают эту команду в меню файла.

`CDocument`поддерживает отправку документа по почте, если поддержка почты (MAPI) присутствует. Смотрите статьи [MAPI Темы](../../mfc/mapi.md) и [MAPI поддержки в МФЦ](../../mfc/mapi-support-in-mfc.md).

## <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame

Эта функция члена вызывается фрестью перед тем, как окно кадра будет уничтожено.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Указатель на [CFrameWnd,](../../mfc/reference/cframewnd-class.md) который `CDocument` содержит связанный объект.

### <a name="remarks"></a>Примечания

Он может быть отменен, чтобы обеспечить пользовательские очистки, но не забудьте позвонить в базовый класс, а также.

По умолчанию ничего не `PreCloseFrame` делает в `CDocument`. Полученные `CDocument`классы [COleDocument](../../mfc/reference/coledocument-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) используют эту функцию участника.

## <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue

Читает следующее значение фрагмента.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Параметры

*ppValue*<br/>
(ваут) Когда функция возвращается, *ppValue* содержит значение, которое было прочитано.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

## <a name="cdocumentreleasefile"></a><a name="releasefile"></a>Документ::ReleaseFile

Эта функция члена вызывается инфраструктурой для выпуска файла, что делает его доступным для использования другими приложениями.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на объект CFile, который будет выпущен.

*bAbort*<br/>
Уточняется, должен ли файл быть освобожден `CFile::Close` с `CFile::Abort`помощью любого или . FALSE, если файл должен быть выпущен с помощью [CFile::Закрыть](../../mfc/reference/cfile-class.md#close); ПРАВДА, если файл должен быть выпущен с помощью [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Примечания

Если *bAbort* является `ReleaseFile` `CFile::Abort`правдой, звонки, и файл освобождается. `CFile::Abort`не будет бросать исключение.

Если *bAbort* является `ReleaseFile` `CFile::Close` FALSE, звонки и файл освобождается.

Переопределить эту функцию участника, чтобы потребовать действия пользователя до выхода файла.

## <a name="cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk

Удаляет кусок с указанным GUID.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*Guid*<br/>
Определяет GUID части, которая будет удалена.

*Pid*<br/>
Определяет PID части, которая будет удалена.

### <a name="remarks"></a>Примечания

## <a name="cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView

Вызовите эту функцию, чтобы отделить представление от документа.

```cpp
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указывает на удаление представления.

### <a name="remarks"></a>Примечания

Эта функция удаляет указанное представление из списка представлений, связанных с документом; он также устанавливает указатель документа представления на NULL. Эта функция вызывается фреймворкой, когда окно кадра закрыто или стекло окна сплиттера закрыто.

Вызов ими функции только в том случае, если вы вручную отсоедините представление. Обычно вы позволяете шаблону отсеивать документы и представления, определяя объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для ассоциирования класса документа, класса представления и класса окна кадра.

Ознакомьтесь с примером [в AddView](#addview) для реализации примера.

## <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException

Вызывается, если выброшено исключение (обычно [CFileException](../../mfc/reference/cfileexception-class.md) или [CArchiveException)](../../mfc/reference/carchiveexception-class.md)при сохранении или загрузке документа.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает на имя сохраненного или загруженного документа.

*E*<br/>
Очки за исключением, которые были брошены. Может иметь значение "NULL".

*bSaving*<br/>
Флаг с указанием того, какая операция продолжается; нетно, если документ был сохранен, 0, если документ был загружен.

*nIDPDefault*<br/>
Идентификация сообщения об ошибке, которая будет отображаться, если функция не указывает более конкретную.

### <a name="remarks"></a>Примечания

Реализация по умолчанию изучает объект исключения и ищет сообщение об ошибке, которое конкретно описывает причину. Если конкретное сообщение не найдено или если *e* является NULL, используется общее сообщение, указанное параметром *nIDPDefault.* Функция затем отображает окно сообщения, содержащее сообщение об ошибке. Переопределить эту функцию, если вы хотите предоставить дополнительные, настраиваемые сообщения о сбое. Это передовой overridable.

## <a name="cdocumentsavemodified"></a><a name="savemodified"></a>CDocument::СохранениеИзменено

Вызывается рамками перед тем, как измененный документ должен быть закрыт.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если безопасно продолжать и закрывать документ; 0, если документ не должен быть закрыт.

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию отображает поле сообщения, задавая пользователю вопрос о том, следует ли сохранять изменения в документе, если таковые были внесены. Переопределить эту функцию, если ваша программа требует другой процедуры побуждения. Это передовой overridable.

## <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue

Устанавливает значение куска.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Определяет значение куска для установки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

## <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag

Позвоните в эту функцию после внесения каких-либо изменений в документ.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bИзменено*<br/>
Пометить, был ли изменен документ.

### <a name="remarks"></a>Примечания

Вызывая эту функцию последовательно, вы гарантируете, что фреймворк подсказывает пользователю сохранить изменения перед закрытием документа. Обычно для параметра *bModified* следует использовать значение TRUE по умолчанию. Чтобы отметить документ чистым (неизмененным), назовите эту функцию значением FALSE.

## <a name="cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName

Позвоните в эту функцию, чтобы указать полностью квалифицированный путь дискового файла документа.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает на строку, которая будет использоваться в качестве пути для документа.

*bAddToMRU*<br/>
Определяет, добавляется ли имя файла в список самых последних используемых файлов (MRU). Если true, имя файла добавляется; если FALSE, он не добавляется.

### <a name="remarks"></a>Примечания

В зависимости от значения *bAddToMRU* путь добавляется или не добавляется в список MRU, поддерживаемый приложением. Обратите внимание, что некоторые документы не связаны с дисковым файлом. Вызовите эту функцию только в том случае, если вы переопределяете реализацию по умолчанию для открытия и сохранения файлов, используемых инфраструктурой.

## <a name="cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle

Позвоните в эту функцию, чтобы указать название документа (строка, отображаемые в строке заголовка окна кадра).

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Параметры

*lpszНазвание*<br/>
Указывает на строку, которая будет использоваться в качестве заголовка документа.

### <a name="remarks"></a>Примечания

Вызов этой функции обновляет названия всех окон кадра, отображающих документ.

## <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument:UpdateAllViews

Вызовите эту функцию после изменения документа.

```cpp
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Параметры

*pСендер*<br/>
Указывает на точку зрения, которая изменила документ, или NULL, если все представления должны быть обновлены.

*lHint*<br/>
Содержит информацию об модификации.

*Phint*<br/>
Указывает на объект, хранятую информацию об изменении.

### <a name="remarks"></a>Примечания

Эту функцию следует вызвать после вызова функции участника [SetModifiedFlag.](#setmodifiedflag) Эта функция информирует каждое представление, приложено к документу, за исключением представления, указанного *pSender,* о том, что документ был изменен. Обычно эта функция называется из класса представления после того, как пользователь изменил документ через представление.

Эта функция вызывает функцию [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) для каждого из представлений документа, за исключением отправки представления, прохождения *pHint* и *lHint.* Используйте эти параметры для передачи информации мнениям о внесении изменений в документ. Вы можете кодировать информацию с помощью *lHint* и/или определить класс [CObject,](../../mfc/reference/cobject-class.md)полученный для хранения информации об изменениях и передачи объекта этого класса с помощью *pHint.* Переопределить `CView::OnUpdate` функцию участника в классе [CView,](../../mfc/reference/cview-class.md)полученных в качестве для оптимизации обновления дисплея представления на основе пройденой информации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец АЭС](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
