---
title: Класс CDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
ms.openlocfilehash: 69b94a4188804f47c950ca31fb5cba80d85176e9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753303"
---
# <a name="cdoctemplate-class"></a>Класс CDocTemplate

Абстрактный базовый класс, который определяет базовую функциональность шаблонов документов.

## <a name="syntax"></a>Синтаксис

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Формирует объект `CDocTemplate`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDocTemplate::AddDocument](#adddocument)|Добавляет документ в шаблон.|
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Закрывает все документы, связанные с этим шаблоном.|
|[CDocTemplate::CreateNewДокумент](#createnewdocument)|Создает новый документ.|
|[CDocTemplate::CreateNewFrame](#createnewframe)|Создает новое окно кадра, содержащее документ и представление.|
|[CDocTemplate::CreateOleFrame](#createoleframe)|Создает окно кадра с поддержкой OLE.|
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Создает детскую рамку, используемую для Рич Авт..|
|[CDocTemplate::GetDocString](#getdocstring)|Извлекает строку, связанную с типом документа.|
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Извлекает позицию первого документа, связанного с этим шаблоном.|
|[CDocTemplate::GetNextDoc](#getnextdoc)|Извлекает документ и положение следующего.|
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Инициализирует окно рамы и дополнительно делает его видимым.|
|[CDocTemplate::LoadTemplate](#loadtemplate)|Загружает ресурсы `CDocTemplate` для данного или производного класса.|
|[CDocTemplate::MatchDocType](#matchdoctype)|Определяет степень достоверности в матче между типом документа и этим шаблоном.|
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|Открывает файл, указанный по имени пути.|
|[CDocTemplate::RemoveDocument](#removedocument)|Удаляет документ из шаблона.|
|[CDocTemplate::SaveAllModified](#saveallmodified)|Сохраняет все документы, связанные с этим шаблоном, которые были изменены.|
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Определяет ресурсы контейнеров OLE при редактировании элемента OLE на месте.|
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Отображает заголовок по умолчанию в панели заголовка окна документа.|
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Настройки из обработчика просмотра процесса.|
|[CDocTemplate::SetServerInfo](#setserverinfo)|Определяет ресурсы и классы при встраивании или редактировании серверного документа.|

## <a name="remarks"></a>Примечания

Обычно при реализации `InitInstance` функции приложения обычно создается один или несколько шаблонов документов. Шаблон документа определяет отношения между тремя типами классов:

- Класс документов, который `CDocument`вы получаете из .

- Класс представления, отображаемый данными из класса документов, перечисленных выше. Вы можете получить `CView`этот `CScrollView` `CFormView`класс `CEditView`из , , или . (Вы также `CEditView` можете использовать непосредственно.)

- Класс окна кадра, который содержит представление. Для одного интерфейса документа (SDI) приложение, `CFrameWnd`вы получаете этот класс из . Для приложения с несколькими документами интерфейса (MDI) вы получаете этот класс из. `CMDIChildWnd` Если вам не нужно настраивать поведение окна кадра, `CFrameWnd` вы `CMDIChildWnd` можете использовать или непосредственно без произвольности собственного класса.

Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например, если приложение поддерживает как электронные таблицы, так и текстовые документы, приложение имеет два объекта шаблона документов. Каждый шаблон документа отвечает за создание и управление всеми документами такого типа.

Шаблон документа хранит указатели `CRuntimeClass` на объекты для классов оконов документа, представления и рамы. Эти `CRuntimeClass` объекты указаны при построении шаблона документа.

Шаблон документа содержит идентификатор ресурсов, используемых с типом документа (например, ресурсы таблицы меню, значка или таблицы акселератора). Шаблон документа также содержит строки, содержащие дополнительную информацию о типе документа. К ним относятся название типа документа (например, "Рабочий лист") и расширение файла (например, ".xls"). В качестве опционов он может содержать другие строки, используемые пользовательским интерфейсом приложения, службой поиска файлов Windows и поддержкой ссылок и встраивания объектов (OLE).

Если ваше приложение является контейнером OLE и/или сервером, шаблон документа также определяет идентификатор меню, используемого во время активации на месте. Если ваше приложение является сервером OLE, шаблон документа определяет идентификатор панели инструментов и меню, используемый во время активации на месте. Вы указываете эти дополнительные ресурсы OLE, позвонив `SetContainerInfo` и `SetServerInfo`.

Поскольку `CDocTemplate` это абстрактный класс, вы не можете использовать класс напрямую. Типичное приложение использует один `CDocTemplate`из двух производных классов, `CSingleDocTemplate`предоставляемых библиотекой microsoft `CMultiDocTemplate`Foundation Class Library: , которая реализует SDI, и , которая реализует MDI. Ознакомьтесь с этими классами для получения дополнительной информации об использовании шаблонов документов.

Если вашему приложению требуется парадигма пользовательского интерфейса, которая принципиально отличается `CDocTemplate`от SDI или MDI, вы можете получить свой собственный класс из .

Для получения `CDocTemplate`дополнительной информации о, см. [Document Templates and the Document/View Creation Process](../../mfc/document-templates-and-the-document-view-creation-process.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cdoctemplateadddocument"></a><a name="adddocument"></a>CDocTemplate::AddDocument

Используйте эту функцию, чтобы добавить документ в шаблон.

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указатель на добавленный документ.

### <a name="remarks"></a>Примечания

Полученные классы [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) и [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) переопределяют эту функцию. Если вы получаете свой собственный класс документа-шаблона из, `CDocTemplate`ваш производный класс должен переопределить эту функцию.

## <a name="cdoctemplatecdoctemplate"></a><a name="cdoctemplate"></a>CDocTemplate::CDocTemplate

Формирует объект `CDocTemplate`.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Упогоняет идентификатор ресурсов, используемых с типом документа. Это может включать меню, значок, таблицу акселератора и строковые ресурсы.

Ресурс строки состоит из семи подстроек, разделенных символом 'n' (символ 'n' необходим в качестве держателя места, если подстрока не включена; однако, задние символы 'n' не являются необходимыми); эти подстроки описывают тип документа. Для получения информации о [GetDocString](#getdocstring)подстроках см. Этот ресурс строки находится в файле ресурса приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Обратите внимание, что строка начинается с символа 'n'; это связано с тем, что первая подстрока не используется для приложений MDI и поэтому не включена. Эту строку можно отредконить с помощью строки редактора; вся строка отображается как одна запись в строке редактора, а не как семь отдельных записей.

*pDocClass*<br/>
Указывает на `CRuntimeClass` объект класса документов. Этот класс `CDocument`— это класс, который вы определяете для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объект класса окна кадра. Этот класс может `CFrameWnd`быть -производным `CFrameWnd` классом, или он может быть сам, если вы хотите поведение по умолчанию для окна основного кадра.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объект класса представления. Этот класс `CView`является классом, который вы определяете для отображения документов.

### <a name="remarks"></a>Примечания

Используйте эту функцию `CDocTemplate` члена для построения объекта. Динамически выделите `CDocTemplate` объект и передайте его [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) из функции `InitInstance` участника вашего класса приложений.

## <a name="cdoctemplateclosealldocuments"></a><a name="closealldocuments"></a>CDocTemplate::CloseAllDocuments

Вызовите эту функцию участника, чтобы закрыть все открытые документы.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Параметры

*bEndSession*<br/>
Не используется.

### <a name="remarks"></a>Примечания

Эта функция члена обычно используется как часть команды File Exit. Реализация этой функции по умолчанию вызывает функцию члена [CDocument::DeleteContents,](../../mfc/reference/cdocument-class.md#deletecontents) чтобы удалить данные документа, а затем закрывает окна кадра для всех представлений, прилагаемых к документу.

Переопределить эту функцию, если вы хотите потребовать от пользователя выполнить специальную очистку перед завершением документа. Например, если документ представляет запись в базе данных, можно переопределить эту функцию для закрытия базы данных.

## <a name="cdoctemplatecreatenewdocument"></a><a name="createnewdocument"></a>CDocTemplate::CreateNewДокумент

Вызовите эту функцию участника для создания нового документа типа, связанного с этим шаблоном документа.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный документ или NULL, если происходит ошибка.

## <a name="cdoctemplatecreatenewframe"></a><a name="createnewframe"></a>CDocTemplate::CreateNewFrame

Создает новое окно кадра, содержащее документ и представление.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Документ, на который должно ссылаться новое окно кадра. Может иметь значение NULL.

*pДругие*<br/>
Окно рамы, на котором будет базироваться новое окно кадра. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданное окно кадра или NULL, если происходит ошибка.

### <a name="remarks"></a>Примечания

`CreateNewFrame`использует `CRuntimeClass` объекты, переданные конструктору, для создания нового окна кадра с прикрепленным представлением и документом. Если параметр *pDoc* является NULL, фреймворк выводит сообщение TRACE.

Параметр *pOther* используется для реализации новой команды Window. Он обеспечивает окно рамы, на котором моделирует сяруло новое окно кадра. Новое окно кадра обычно создается невидимым. Вызовите эту функцию для создания окон кадра за пределами стандартной реализации рамок File New и File Open.

## <a name="cdoctemplatecreateoleframe"></a><a name="createoleframe"></a>CDocTemplate::CreateOleFrame

Создает окно рамы OLE.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно кадра.

*pDoc*<br/>
Указатель на документ, на который должно ссылаться новое окно кадра OLE.

*bCreateView*<br/>
Определяет, создается ли представление вместе с кадром.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно рамы в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если *bCreateView* равен нулю, создается пустая рамка.

## <a name="cdoctemplategetdocstring"></a><a name="getdocstring"></a>CDocTemplate::GetDocString

Извлекает строку, связанную с типом документа.

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылка на `CString` объект, который будет содержать строку при возврате функции.

*Индекс*<br/>
Индекс подстроки, извлеченный из строки, описывающий тип документа. Этот параметр может принимать одно из следующих значений:

- `CDocTemplate::windowTitle`Имя, которое отображается в заглавной панели окна приложения (например, "Microsoft Excel"). Присутствует только в шаблоне документа для приложений SDI.

- `CDocTemplate::docName`Корень для имени документа по умолчанию (например, "Лист"). Этот корень, а также число используется для имени нового документа этого типа по умолчанию всякий раз, когда пользователь выбирает новую команду из меню файла (например, "Sheet1" или "Sheet2"). Если не указано, "Без названия" используется в качестве по умолчанию.

- `CDocTemplate::fileNewName`Название этого типа документа. Если приложение поддерживает более одного типа документа, эта строка отображается в поле диалога File New (например, "Worksheet"). Если не указано, тип документа недоступен с помощью команды File New.

- `CDocTemplate::filterName`Описание типа документа и фильтра подстановочных знаков, соответствующих документам этого типа. Эта строка отображается в списке файлов типа выпадающих вниз в файле Открыть диалоговое окно (например, "Рабочие листы (.xls)). Если не указано, тип документа недоступен с помощью команды File Open.

- `CDocTemplate::filterExt`Расширение для документов этого типа (например, ".xls"). Если не указано, тип документа недоступен с помощью команды File Open.

- `CDocTemplate::regFileTypeId`Идентификатор типа документа, который будет храниться в базе данных регистрации, поддерживаемой Windows. Эта строка предназначена только для внутреннего использования (например, "ExcelWorksheet"). Если не указано, тип документа не может быть зарегистрирован в менеджере файлов Windows.

- `CDocTemplate::regFileTypeName`Наименование типа документа, который будет храниться в базе данных регистрации. Эта строка может отображаться в диалоговых коробках приложений, которые получают доступ к базе данных регистрации (например, "Microsoft Excel Worksheet").

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанная подстрока была найдена; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы получить определенный подстроку, описывающую тип документа. Строка, содержащая эти подстроки, хранится в шаблоне документа и выводится из строки в файле ресурса для приложения. Платформа вызывает эту функцию, чтобы получить строки, необходимые для пользовательского интерфейса приложения. Если вы указали расширение имени файла для документов приложения, платформа также вызывает эту функцию при добавлении записи в базу данных регистрации Windows; это позволяет открывать документы из диспетчера файлов Windows.

Позвоните в эту функцию только в `CDocTemplate`том случае, если вы выравлите свой собственный класс из.

## <a name="cdoctemplategetfirstdocposition"></a><a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition

Извлекает позицию первого документа, связанного с этим шаблоном.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерирования через список документов, связанных с этим шаблоном документа; или NULL, если список пуст.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы получить позицию первого документа в списке документов, связанных с этим шаблоном. Используйте значение POSITION в качестве аргумента для [CDocTemplate::GetNextDoc](#getnextdoc) для итерации через список документов, связанных с шаблоном.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) и [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) оба переопределить эту чистую виртуальную функцию. Любой класс, `CDocTemplate` из который вы получаете, должен также переопределить эту функцию.

## <a name="cdoctemplategetnextdoc"></a><a name="getnextdoc"></a>CDocTemplate::GetNextDoc

Извлекает элемент списка, определенный *rPos,* затем устанавливает *rPos* к значению POSITION следующей записи в списке.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий документ в списке документов, связанных с этим шаблоном.

### <a name="parameters"></a>Параметры

*rPos*<br/>
Ссылка на значение POSITION, возвращенное предыдущим вызовом [в GetFirstDocPosition](#getfirstdocposition) или `GetNextDoc`.

### <a name="remarks"></a>Примечания

Если извлеченный элемент является последним в списке, то новое значение *rPos* устанавливается на NULL.

Вы можете `GetNextDoc` использовать в цикле передних итерации, если вы установите исходное положение с вызовом [на GetFirstDocPosition.](#getfirstdocposition)

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

## <a name="cdoctemplateinitialupdateframe"></a><a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame

Инициализирует окно рамы и дополнительно делает его видимым.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Окно кадра, которое нуждается в первоначальном обновлении.

*pDoc*<br/>
Документ, к которому связан кадр. Может иметь значение NULL.

*bMakeVisible*<br/>
Указывает, должен ли кадр стать видимым и активным.

### <a name="remarks"></a>Примечания

Вызов `IntitialUpdateFrame` после создания нового `CreateNewFrame`кадра с . Вызов этой функции приводит к тому, `OnInitialUpdate` что представления в этом окне кадра принимают их вызовы. Кроме того, если ранее не было активного представления, основное представление окна кадра становится активным; основным представлением является представление с идентификатором ребенка AFX_IDW_PANE_FIRST. Наконец, окно кадра становится видимым, если *bMakeVisible* не является нулевым. Если *bMakeVisible* равен нулю, текущее фокусии и видимое состояние окна кадра останутся неизменными.

Нет необходимости называть эту функцию при использовании реализации платформы File New и File Open.

## <a name="cdoctemplateloadtemplate"></a><a name="loadtemplate"></a>CDocTemplate::LoadTemplate

Загружает ресурсы `CDocTemplate` для данного или производного класса.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>Примечания

Эта функция члена вызывается инфраструктурой для загрузки ресурсов для данного `CDocTemplate` или производного класса. Обычно он называется во время строительства, за исключением случаев, когда шаблон строится глобально. В этом случае вызов `LoadTemplate` задерживается до вызова [CWinApp:AddDocTemplate.](../../mfc/reference/cwinapp-class.md#adddoctemplate)

## <a name="cdoctemplatematchdoctype"></a><a name="matchdoctype"></a>CDocTemplate::MatchDocType

Определяет степень достоверности в матче между типом документа и этим шаблоном.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Имя файла, тип которого должен быть определен.

*rpDocMatch*<br/>
Указатель на документ, которому присваивается соответствующий документ, если файл, указанный *lpszPathName,* уже открыт.

### <a name="return-value"></a>Возвращаемое значение

Значение из перечисления **доверия,** которое определяется следующим образом:

```
enum Confidence
    {
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };
```

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы определить тип шаблона документа для открытия файла. Например, если приложение поддерживает несколько типов файлов, эту функцию можно использовать, чтобы определить, `MatchDocType` какой из доступных шаблонов документов подходит для данного файла, вызывая каждый шаблон по очереди и выбирая шаблон в соответствии с возвращенным значением доверия.

Если файл, указанный *lpszPathName,* уже `CDocTemplate::yesAlreadyOpen` открыт, эта функция `CDocument` возвращается и копирует объект файла в объект на *rpDocMatch*.

Если файл не открыт, но расширение в *lpszPathName* соответствует указанному расширением, `CDocTemplate::filterExt`эта функция возвращается `CDocTemplate::yesAttemptNative` и устанавливает *rpDocMatch* в NULL. Для получения `CDocTemplate::filterExt`дополнительной информации о , см. [CDocTemplate::GetDocString](#getdocstring).

Если ни один из случаев не соответствует действительности, функция возвращается. `CDocTemplate::yesAttemptForeign`

Реализация по умолчанию `CDocTemplate::maybeAttemptForeign` `CDocTemplate::maybeAttemptNative`не возвращается или . Переопределить эту функцию для реализации логики сопоставления типов, соответствующей вашему приложению, возможно, используя эти два значения из перечисления **доверия.**

## <a name="cdoctemplateopendocumentfile"></a><a name="opendocumentfile"></a>CDocTemplate::OpenDocumentFile

Открывает файл, указанный по пути.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
(в) Указатель на путь файла, содержащего открытый документ.

*bAddToMRU*<br/>
(в) TRUE указывает на то, что документ является одним из самых последних файлов; FALSE указывает, что документ не является одним из последних файлов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, файл которого назван *lpszPathName*; NULL, если безуспешно.

### <a name="remarks"></a>Примечания

Открывает файл, путь которого указан *lpszPathName.* Если *lpszPathName* является NULL, создается новый файл, содержащий документ типа, связанного с этим шаблоном.

## <a name="cdoctemplateremovedocument"></a><a name="removedocument"></a>CDocTemplate::RemoveDocument

Удаляет документ, на который указывает *pDoc,* из списка документов, связанных с этим шаблоном.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указатель на документ, который будет удален.

### <a name="remarks"></a>Примечания

Полученные `CMultiDocTemplate` классы `CSingleDocTemplate` и переопределить эту функцию. Если вы получаете свой собственный класс документа-шаблона из, `CDocTemplate`ваш производный класс должен переопределить эту функцию.

## <a name="cdoctemplatesaveallmodified"></a><a name="saveallmodified"></a>CDocTemplate::SaveAllModified

Сохраняет все документы, которые были изменены.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевой, если успешно; в противном случае 0.

## <a name="cdoctemplatesetcontainerinfo"></a><a name="setcontainerinfo"></a>CDocTemplate::SetContainerInfo

Определяет ресурсы контейнеров OLE при редактировании элемента OLE на месте.

```cpp
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>Параметры

*nIDOleInPlaceContainer*<br/>
Идентификатор ресурсов, используемых при активации встроенного объекта.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы настроить ресурсы, которые будут использоваться при активации объекта OLE. Эти ресурсы могут включать меню и таблицы акселераторов. Эта функция обычно вызывается в [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функции вашего приложения.

Меню, связанное с *nIDOleInPlaceContainer,* содержит сепараторы, которые позволяют меню активированного элемента на месте сливаться с меню контейнерного приложения. Для получения дополнительной информации о слиянии меню [Menus and Resources (OLE)](../../mfc/menus-and-resources-ole.md)сервера и контейнеров, см.

## <a name="cdoctemplatesetdefaulttitle"></a><a name="setdefaulttitle"></a>CDocTemplate::SetDefaultTitle

Вызовите эту функцию, чтобы загрузить заголовок документа по умолчанию и отобразить его в заглавной панели документа.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>Параметры

*pДокумент*<br/>
Указатель на документ, название которого должно быть установлено.

### <a name="remarks"></a>Примечания

Для получения информации о `CDocTemplate::docName` названии [CDocTemplate::GetDocString](#getdocstring)по умолчанию, см.

## <a name="cdoctemplatesetserverinfo"></a><a name="setserverinfo"></a>CDocTemplate::SetServerInfo

Определяет ресурсы и классы при встраивании или редактировании серверного документа.

```cpp
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>Параметры

*nIDOleEmbedding*<br/>
Идентификатор ресурсов, используемых при открытии встроенного объекта в отдельном окне.

*nIDOleInPlaceServer*<br/>
Идентификатор ресурсов, используемых при активации встроенного объекта на месте.

*pOleFrameClass*<br/>
Указатель на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) содержащую информацию о классе для объекта окна кадра, созданный при активации на месте.

*pOleViewClass*<br/>
Указатель на `CRuntimeClass` структуру, содержащую информацию о классе для объекта представления, созданный при активации на месте.

### <a name="remarks"></a>Примечания

Вызов ими функции участника для идентификации ресурсов, которые будут использоваться серверным приложением, когда пользователь запрашивает активацию встроенного объекта. Эти ресурсы состоят из меню и таблиц акселератора. Эта функция обычно вызывается в приложении. `InitInstance`

Меню, связанное с *nIDOleInPlaceServer,* содержит сепараторы, которые позволяют меню сервера сливаться с меню контейнера. Для получения дополнительной информации о слиянии меню [Menus and Resources (OLE)](../../mfc/menus-and-resources-ole.md)сервера и контейнеров, см.

## <a name="cdoctemplatecreatepreviewframe"></a><a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame

Создает детскую рамку, используемую для Рич Авт..

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно (обычно предоставляемый Shell).

*pDoc*<br/>
Указатель на объект документа, содержимое которого будет предварительно просмотрено.

### <a name="return-value"></a>Возвращаемое значение

Действительный `CFrameWnd` указатель на объект, или NULL, если создание не удается.

### <a name="remarks"></a>Примечания

## <a name="cdoctemplatesetpreviewinfo"></a><a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo

Настраивайте обработчик предварительного просмотра процесса.

```cpp
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>Параметры

*nIDPreviewFrame*<br/>
Упоняет идентификатор ресурса кадра предварительного просмотра.

*pPreviewFrameClass*<br/>
Определяет указатель на информационную структуру класса выполнения кадра предварительного просмотра.

*pPreviewViewClass*<br/>
Определяет указатель на информационную структуру класса выполнения представления предварительного просмотра.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)<br/>
[Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CScrollView](../../mfc/reference/cscrollview-class.md)<br/>
[Класс CEditView](../../mfc/reference/ceditview-class.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
