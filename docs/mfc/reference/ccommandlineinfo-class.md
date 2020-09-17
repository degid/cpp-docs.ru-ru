---
title: Класс CCommandLineInfo
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 0b4d5e5d253f2eb10388a69286d21e2190826eba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369460"
---
# <a name="ccommandlineinfo-class"></a>Класс CCommandLineInfo

Помогает в синтаксическом разборе командной строки при запуске приложения.

## <a name="syntax"></a>Синтаксис

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Строит объект `CCommandLineInfo` по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|Переопределить этот обратный вызов для разбора отдельных параметров.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Указывает на то, что вариант командной строки `/Automation` найден.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Указывает на то, что вариант командной строки `/Embedding` найден.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Указывает, должен ли быть показан экран всплеска.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Указывает команду оболочки, которая должна быть обработана.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Указано имя драйвера, если команда оболочки — Print To; в противном случае пустой.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Указывает имя файла, которое должно быть открыто или напечатано; пусто, если команда оболочки новая или DDE.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|Указывает название порта, если команда оболочки распечатана; в противном случае пустой.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Указывает имя принтера, если команда оболочки — Print To; в противном случае пустой.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Указывает уникальный идентификатор перезагрузки для менеджера перезагрузки, если менеджер перезагрузки перезапустил приложение.|

## <a name="remarks"></a>Примечания

Приложение MFC обычно создает локальный экземпляр этого класса в функции [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) объекта приложения. Этот объект затем передается [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), который неоднократно вызывает `CCommandLineInfo` [ParseParam](#parseparam) для заполнения объекта. Затем `CCommandLineInfo` объект передается [cWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) для обработки аргументов и флагов командной строки.

Этот объект можно использовать для инкапсулировать следующие параметры и параметры командной строки:

|Аргумент командной строки|Командование выполнено|
|----------------------------|----------------------|
|*app*|Новый файл.|
|имя *файла приложения*|Открытый файл.|
|имя *файла приложения* `/p`|Печать файла для принтера по умолчанию.|
|*Порт* `/pt` драйвера драйвера файла приложения|Печать файла для указанного принтера.|
|*app* `/dde`|Запустите и ждите команды DDE.|
|*app* `/Automation`|Запуск в качестве сервера автоматизации OLE.|
|*app* `/Embedding`|Запустите для отсечения встроенного элемента OLE.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|Информирует приложение для выполнения любых задач регистрации.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|Информирует приложение для выполнения любых задач оон-регистрации.|

Вывести новый `CCommandLineInfo` класс из обработки других флагов и значений параметров. Переопределить [ParseParam](#parseparam) для обработки новых флагов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo

Этот конструктор создает `CCommandLineInfo` объект с значениями по умолчанию.

```
CCommandLineInfo();
```

### <a name="remarks"></a>Примечания

По умолчанию, чтобы показать `m_bShowSplash=TRUE`всплеск экрана ( ) и выполнить новую команду в меню файла ( `m_nShellCommand` **»NewFile**).

Платформа приложения вызывает [ParseParam](#parseparam) для заполнения данных членов этого объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated

Указывает, `/Automation` что флаг был найден на командной строке.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Примечания

Если true, это означает запуск в качестве сервера автоматизации OLE.

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded

Указывает, `/Embedding` что флаг был найден на командной строке.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Примечания

Если true, это означает запуск для редактирования встроенного элемента OLE.

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash

Означает, что экран всплеска должен отображаться.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Примечания

Если true, это означает, что экран всплеска для этого приложения должен отображаться во время запуска. По умолчанию реализация [ParseParam](#parseparam) устанавливает этот член данных в TRUE, если [m_nShellCommand](#m_nshellcommand) равен `CCommandLineInfo::FileNew`.

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand

Указывает команду оболочки для данного экземпляра приложения.

```
m_nShellCommand;
```

### <a name="remarks"></a>Примечания

Тип для этого участника данных является следующим перечисленным типом, который определяется в `CCommandLineInfo` классе.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

Краткое описание этих значений приведено в следующем списке.

- `CCommandLineInfo::FileNew`Указывается, что имя файла не было найдено в командной строке.

- `CCommandLineInfo::FileOpen`Указывает, что имя файла было найдено на командной строке и что `/p` `/pt`ни `/dde`один из следующих флагов не был найден на командной строке: , .

- `CCommandLineInfo::FilePrint`Указывает, `/p` что флаг был найден на командной строке.

- `CCommandLineInfo::FilePrintTo`Указывает, `/pt` что флаг был найден на командной строке.

- `CCommandLineInfo::FileDDE`Указывает, `/dde` что флаг был найден на командной строке.

- `CCommandLineInfo::AppRegister`Указывается, `/Register` `/Regserver` что флаг был найден на командной строке и заявке было предложено зарегистрироваться.

- `CCommandLineInfo::AppUnregister`Указывается, `/Unregister` `/Unregserver` что или заявление было предложено отменить регистрацию.

- `CCommandLineInfo::RestartByRestartManager`Указывает, что приложение было перезапущено менеджером перезагрузки.

- `CCommandLineInfo::FileNothing`Выключает отображение нового окна ребенка MDI на запуске. По замыслу MDI-приложений, генерируемых Application Wizard, в запуске отображается новое окно ребенка. Чтобы отключить эту функцию, `CCommandLineInfo::FileNothing` приложение может использовать в качестве команды оболочки при вызове [ProcessShellCommand.](../../mfc/reference/cwinapp-class.md#processshellcommand) `ProcessShellCommand`называется всеми `InitInstance( )` `CWinApp` производными классами.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName

Хранит значение третьего параметра без флага на командной строке.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является именем драйвера принтера для команды оболочки Print To. Реализация [ParseParam](#parseparam) по умолчанию устанавливает этот `/pt` член данных только в том случае, если флаг был найден на командной строке.

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a>CCommandLineInfo::m_strFileName

Сохраняет значение первого параметра без флага на командной строке.

```
CString m_strFileName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является для открытия файла.

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a>CCommandLineInfo::m_strPortName

Хранит значение четвертого параметра без флага на командной строке.

```
CString m_strPortName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является названием порта принтера для команды оболочки Print To. Реализация [ParseParam](#parseparam) по умолчанию устанавливает этот `/pt` член данных только в том случае, если флаг был найден на командной строке.

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName

Хранит значение второго параметра без флага на командной строке.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является именем принтера для команды оболочки Print To. Реализация [ParseParam](#parseparam) по умолчанию устанавливает этот `/pt` член данных только в том случае, если флаг был найден на командной строке.

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier

Уникальный идентификатор перезагрузки на командной строке.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Примечания

Идентификатор перезагрузки уникален для каждого экземпляра приложения.

Если менеджер перезагрузки выходит из приложения и настроен для его перезапуска, менеджер перезагрузки выполняет приложение из командной строки с идентификатором перезагрузки в качестве дополнительного параметра. Когда менеджер перезагрузки использует идентификатор перезагрузки, приложение может вновь открыть ранее открытые документы и восстановить автоматически сохраненные файлы.

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a>CCommandLineInfo::ParseParam

Фрейм вызывает эту функцию для разбора/интерпретации отдельных параметров из командной строки. Вторая версия отличается от первой только в проектах Unicode.

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>Параметры

*pszParam*<br/>
Параметр или флаг.

*bФлаг*<br/>
Указывает, является ли *pszParam* параметром или флагом.

*Взрыв*<br/>
Указывает, является ли это последним параметром или флагом на командной строке.

### <a name="remarks"></a>Примечания

[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) `ParseParam` вызывает один раз для каждого параметра или флага на командной строке, передавая аргумент *pszParam*. Если первый символ параметра **-** является ' **/** или ' ', то он удаляется и *bFlag* установлен на TRUE. При разборе окончательного параметра, *bLast* установлен на TRUE.

Реализация этой функции по умолчанию `/p`распознает следующие флаги: `/pt`, `/dde`, `/Automation`, и `/Embedding`, как показано в следующей таблице:

|Аргумент командной строки|Командование выполнено|
|----------------------------|----------------------|
|*app*|Новый файл.|
|имя *файла приложения*|Открытый файл.|
|имя *файла приложения* `/p`|Печать файла для принтера по умолчанию.|
|*Порт* `/pt` драйвера драйвера файла приложения|Печать файла для указанного принтера.|
|*app* `/dde`|Запустите и ждите команды DDE.|
|*app* `/Automation`|Запуск в качестве сервера автоматизации OLE.|
|*app* `/Embedding`|Запустите для отсечения встроенного элемента OLE.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|Информирует приложение для выполнения любых задач регистрации.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|Информирует приложение для выполнения любых задач оон-регистрации.|

Эта информация хранится в [m_bRunAutomated,](#m_brunautomated) [m_bRunEmbedded](#m_brunembedded)и [m_nShellCommand.](#m_nshellcommand) Флаги отмечены либо вперед-слэш ' **/** **-** или дефис ' ' .

Реализация по умолчанию помещает первый параметр без флага в [m_strFileName.](#m_strfilename) `/pt` В случае флага реализация по умолчанию помещает второй, третий и четвертый параметры без флага в [m_strPrinterName,](#m_strprintername) [m_strDriverName](#m_strdrivername)и [m_strPortName](#m_strportname)соответственно.

Реализация по умолчанию также устанавливает [m_bShowSplash](#m_bshowsplash) к TRUE только в случае нового файла. В случае нового файла пользователь предпринял действия, связанные с самим приложением. В любом другом случае, включая открытие существующих файлов с помощью оболочки, пользовательское действие включает файл напрямую. В точке зрения, ориентированной на документ, экран всплеска не должен объявлять о запуске приложения.

Переопределить эту функцию в выдвитом классе для обработки других значений флага и параметров.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
