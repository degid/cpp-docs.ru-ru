---
title: Класс CWinApp
ms.date: 07/15/2019
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: f8ca4ad2023902d40a1f63c881a8dd2fd38a9ae9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837610"
---
# <a name="cwinapp-class"></a>Класс CWinApp

Базовый класс, от которого необходимо наследовать объект приложения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinApp:: CWinApp](#cwinapp)|Формирует объект `CWinApp`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp:: AddDocTemplate](#adddoctemplate)|Добавляет шаблон документа в список доступных шаблонов документов приложения.|
|[CWinApp:: Аддторецентфилелист](#addtorecentfilelist)|Добавляет имя файла в список последних использованных файлов.|
|[CWinApp:: Аппликатионрековерикаллбакк](#applicationrecoverycallback)|Вызывается платформой при внезапном завершении работы приложения.|
|[CWinApp:: Клосеаллдокументс](#closealldocuments)|Закрывает все открытые документы.|
|[CWinApp:: Креатепринтердк](#createprinterdc)|Создает контекст печатающего устройства.|
|[CWinApp::D Елрегтри](#delregtree)|Удаляет указанный ключ и все его подразделы.|
|[CWinApp::D Омессажебокс](#domessagebox)|Реализует [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для приложения.|
|[CWinApp::D Оваиткурсор](#dowaitcursor)|Включает и выключает курсор ожидания.|
|[CWinApp:: EnableD2DSupport](#enabled2dsupport)|Включает поддержку приложений D2D. Данный метод следует вызывать до инициализации основного окна.|
|[CWinApp:: Енаблехтмлхелп](#enablehtmlhelp)|Реализует HTMLHelp для приложения, а не WinHelp.|
|[CWinApp:: Енаблетаскбаринтерактион](#enabletaskbarinteraction)|Включает взаимодействие с панелью задач.|
|[CWinApp:: ExitInstance](#exitinstance)|Переопределите для очистки при завершении работы приложения.|
|[CWinApp:: Жетаппликатионрековерипараметер](#getapplicationrecoveryparameter)|Получает входной параметр для метода восстановления приложения.|
|[CWinApp:: Жетаппликатионрековерипингинтервал](#getapplicationrecoverypinginterval)|Возвращает период времени, в течение которого диспетчер перезапуска ожидает возврата функции обратного вызова восстановления.|
|[CWinApp:: Жетаппликатионрестартфлагс](#getapplicationrestartflags)|Возвращает флаги для диспетчера перезапуска.|
|[CWinApp:: Жетаппрегистрикэй](#getappregistrykey)|Возвращает ключ для HKEY_CURRENT_USER \\ "Software" \регистрикэй\профиленаме.|
|[CWinApp:: Жетдатарековерихандлер](#getdatarecoveryhandler)|Возвращает обработчик восстановления данных для этого экземпляра приложения.|
|[CWinApp:: Жетфирстдоктемплатепоситион](#getfirstdoctemplateposition)|Извлекает расположение первого шаблона документа.|
|[CWinApp:: Жеселпмоде](#gethelpmode)|Извлекает тип справки, используемый приложением.|
|[CWinApp:: Жетнекстдоктемплате](#getnextdoctemplate)|Извлекает расположение шаблона документа. Может использоваться рекурсивно.|
|[CWinApp:: Жетпринтердевицедефаултс](#getprinterdevicedefaults)|Извлекает значения по умолчанию для устройств принтера.|
|[CWinApp:: Жетпрофилебинари](#getprofilebinary)|Извлекает двоичные данные из записи в приложении. INI-файл.|
|[CWinApp:: Жетпрофилеинт](#getprofileint)|Извлекает целое число из записи в приложении. INI-файл.|
|[CWinApp:: Жетпрофилестринг](#getprofilestring)|Извлекает строку из записи в приложении. INI-файл.|
|[CWinApp:: Жетсектионкэй](#getsectionkey)|Возвращает ключ для HKEY_CURRENT_USER \\ "Software" \регистрикэй\аппнаме\лпсзсектион.|
|[CWinApp:: Хидеаппликатион](#hideapplication)|Скрывает приложение перед закрытием всех документов.|
|[CWinApp:: HtmlHelp](#htmlhelp)|Вызывает `HTMLHelp` функцию Windows.|
|[CWinApp:: InitInstance](#initinstance)|Переопределение для выполнения инициализации экземпляра Windows, например создание объектов окна.|
|[CWinApp:: Истаскбаринтерактионенаблед](#istaskbarinteractionenabled)|Указывает, включено ли взаимодействие с панелью задач Windows 7.|
|[CWinApp:: Лоадкурсор](#loadcursor)|Загружает ресурс курсора.|
|[CWinApp:: Лоадикон](#loadicon)|Загружает ресурс значка.|
|[CWinApp:: Лоадоемкурсор](#loadoemcursor)|Загружает предопределенный курсор Windows OEM, который **OCR_** константы, указанные в Windows. Высоты.|
|[CWinApp:: Лоадоемикон](#loadoemicon)|Загружает стандартный значок Windows OEM, который задается **OIC_** константах в Windows. Высоты.|
|[CWinApp:: Лоадстандардкурсор](#loadstandardcursor)|Загружает стандартный курсор Windows, который задается **IDC_** константами в Windows. Высоты.|
|[CWinApp:: Лоадстандардикон](#loadstandardicon)|Загружает стандартный значок Windows, который задается **IDI_** константами в Windows. Высоты.|
|[CWinApp:: Онддекомманд](#onddecommand)|Вызывается платформой в ответ на команду динамического обмена данными (DDE) Execute.|
|[CWinApp:: OnIdle](#onidle)|Переопределение для выполнения обработки времени простоя, зависящей от приложения.|
|[CWinApp:: Опендокументфиле](#opendocumentfile)|Вызывается платформой для открытия документа из файла.|
|[CWinApp::P Арсекоммандлине](#parsecommandline)|Анализирует отдельные параметры и флаги в командной строке.|
|[CWinApp::P Ретранслатемессаже](#pretranslatemessage)|Фильтрует сообщения до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).|
|[CWinApp::P Роцессмессажефилтер](#processmessagefilter)|Перехватывает определенные сообщения до того, как они достигают приложения.|
|[CWinApp::P Роцессшеллкомманд](#processshellcommand)|Обрабатывает аргументы и флаги командной строки.|
|[CWinApp::P Роцессвндпроцексцептион](#processwndprocexception)|Перехватывает все необработанные исключения, вызванные сообщением приложения и обработчиками команд.|
|[CWinApp:: Register](#register)|Выполняет настраиваемую регистрацию.|
|[CWinApp:: Регистервисрестартманажер](#registerwithrestartmanager)|Регистрирует приложение в диспетчере перезапуска.|
|[CWinApp:: Реопенпревиаусфилесатрестарт](#reopenpreviousfilesatrestart)|Определяет, повторно ли диспетчер перезапуска открывает файлы, открытые при неожиданном завершении работы приложения.|
|[CWinApp:: Рестартинстанце](#restartinstance)|Обрабатывает перезапуск приложения, инициированный диспетчером перезапуска.|
|[CWinApp:: Рестореаутосаведфилесатрестарт](#restoreautosavedfilesatrestart)|Определяет, восстанавливает ли диспетчер перезапуска автоматически сохраненные файлы при перезапуске приложения.|
|[CWinApp:: Run](#run)|Выполняет цикл обработки сообщений по умолчанию. Переопределите, чтобы настроить цикл обработки сообщений.|
|[CWinApp:: Рунаутоматед](#runautomated)|Проверяет командную строку приложения для параметра **/Automation** . Является устаревшей. Вместо этого используйте значение в [ккоммандлинеинфо:: m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) после вызова [парсекоммандлине](#parsecommandline).|
|[CWinApp:: Рунембеддед](#runembedded)|Проверяет командную строку приложения для параметра **параметром/Embedding** . Является устаревшей. Вместо этого используйте значение в [ккоммандлинеинфо:: m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) после вызова [парсекоммандлине](#parsecommandline).|
|[CWinApp:: Савеаллмодифиед](#saveallmodified)|Предлагает пользователю сохранить все измененные документы.|
|[CWinApp:: Селектпринтер](#selectprinter)|Выбирает принтер, ранее указанный пользователем, в диалоговом окне «Печать».|
|[CWinApp:: Сеселпмоде](#sethelpmode)|Задает и инициализирует тип справки, используемой приложением.|
|[CWinApp:: Суппортсаппликатионрековери](#supportsapplicationrecovery)|Определяет, восстанавливает ли диспетчер перезапуска приложение, которое неожиданно завершило работу.|
|[CWinApp:: Суппортсаутосавеатинтервал](#supportsautosaveatinterval)|Определяет, будет ли диспетчер перезапуска автоматически сохранять открытые документы через равные промежутки времени.|
|[CWinApp:: Суппортсаутосавеатрестарт](#supportsautosaveatrestart)|Определяет, будет ли диспетчер перезапуска автоматически сохранять все открытые документы при перезапуске приложения.|
|[CWinApp:: Суппортсрестартманажер](#supportsrestartmanager)|Определяет, поддерживает ли приложение Диспетчер перезапуска.|
|[CWinApp:: Отмена регистрации](#unregister)|Отменяет регистрацию всех элементов, зарегистрированных в `CWinApp` объекте.|
|[CWinApp:: WinHelp](#winhelp)|Вызывает `WinHelp` функцию Windows.|
|[CWinApp:: Вритепрофилебинари](#writeprofilebinary)|Записывает двоичные данные в запись в приложении. INI-файл.|
|[CWinApp:: Вритепрофилеинт](#writeprofileint)|Записывает целое число в запись в приложении. INI-файл.|
|[CWinApp:: Вритепрофилестринг](#writeprofilestring)|Записывает строку в запись в приложении. INI-файл.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp:: Енаблешеллопен](#enableshellopen)|Позволяет пользователю открывать файлы данных из диспетчера файлов Windows.|
|[CWinApp:: Лоадстдпрофилесеттингс](#loadstdprofilesettings)|Загружает стандартный. Параметры INI-файла и включает функцию списка MRU-файлов.|
|[CWinApp:: Онконтексселп](#oncontexthelp)|Обрабатывает SHIFT + Справка F1 в приложении.|
|[CWinApp:: Онфиленев](#onfilenew)|Реализует команду ID_FILE_NEW.|
|[CWinApp:: Онфилеопен](#onfileopen)|Реализует команду ID_FILE_OPEN.|
|[CWinApp:: Онфилепринтсетуп](#onfileprintsetup)|Реализует команду ID_FILE_PRINT_SETUP.|
|[CWinApp:: OnHelp](#onhelp)|Обрабатывает справку F1 в приложении (с использованием текущего контекста).|
|[CWinApp:: Онхелпфиндер](#onhelpfinder)|Обрабатывает команды ID_HELP_FINDER и ID_DEFAULT_HELP.|
|[CWinApp:: Онхелпиндекс](#onhelpindex)|Обрабатывает команду ID_HELP_INDEX и предоставляет раздел справки по умолчанию.|
|[CWinApp:: Онхелпусинг](#onhelpusing)|Обрабатывает команду ID_HELP_USING.|
|[CWinApp:: RegisterShellFileTypes](#registershellfiletypes)|Регистрирует все типы документов приложения с помощью диспетчера файлов Windows.|
|[CWinApp:: Сетаппид](#setappid)|Явно задает идентификатор модели пользователя приложения. Этот метод должен вызываться перед тем, как пользовательский интерфейс будет представлен пользователю (лучшим местом является конструктор приложения).|
|[CWinApp:: Сетрегистрикэй](#setregistrykey)|Приводит к сохранению параметров приложения в реестре, а не в. INI-файлы.|
|[CWinApp:: Унрегистершеллфилетипес](#unregistershellfiletypes)|Отменяет регистрацию всех типов документов приложения с помощью диспетчера файлов Windows.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinApp:: m_bHelpMode](#m_bhelpmode)|Указывает, находится ли пользователь в контекстном режиме справки (обычно он вызывается с помощью SHIFT + F1).|
|[CWinApp:: m_eHelpType](#m_ehelptype)|Указывает тип справки, используемой приложением.|
|[CWinApp:: m_hInstance](#m_hinstance)|Определяет текущий экземпляр приложения.|
|[CWinApp:: m_lpCmdLine](#m_lpcmdline)|Указывает на строку, завершающуюся нулем, которая указывает командную строку для приложения.|
|[CWinApp:: m_nCmdShow](#m_ncmdshow)|Указывает, как должно отображаться окно первоначально.|
|[CWinApp:: m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера, когда OLE-сервер находится в активном месте.|
|[CWinApp:: m_pszAppID](#m_pszappid)|Идентификатор модели пользователя приложения.|
|[CWinApp:: m_pszAppName](#m_pszappname)|Указывает имя приложения.|
|[CWinApp:: m_pszExeName](#m_pszexename)|Имя модуля приложения.|
|[CWinApp:: m_pszHelpFilePath](#m_pszhelpfilepath)|Путь к файлу справки приложения.|
|[CWinApp:: m_pszProfileName](#m_pszprofilename)|Приложение. Имя INI-файла.|
|[CWinApp:: m_pszRegistryKey](#m_pszregistrykey)|Используется для определения полного раздела реестра для хранения параметров профиля приложения.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinApp:: m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Флаги, определяющие работу диспетчера перезапуска.|
|[CWinApp:: m_nAutosaveInterval](#m_nautosaveinterval)|Продолжительность времени в миллисекундах между автосохранением.|
|[CWinApp:: m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Указатель на обработчик восстановления данных для приложения.|

## <a name="remarks"></a>Примечания

Объект приложения предоставляет функции-члены для инициализации приложения (и каждого его экземпляра) и для запуска приложения.

Каждое приложение, использующее классы Microsoft Foundation, может содержать только один объект, производный от `CWinApp` . Этот объект создается при создании других глобальных объектов C++ и уже доступен, когда Windows вызывает `WinMain` функцию, которая предоставляется библиотека Microsoft Foundation Class. Объявите производный `CWinApp` объект на глобальном уровне.

При наследовании класса приложения от необходимо `CWinApp` переопределить функцию элемента [InitInstance](#initinstance) , чтобы создать главный объект окна приложения.

В дополнение к `CWinApp` функциям элементов Библиотека Microsoft Foundation Class предоставляет следующие глобальные функции для доступа к `CWinApp` объекту и другим глобальным сведениям:

- [Афксжетапп](application-information-and-management.md#afxgetapp) Получает указатель на `CWinApp` объект.

- [Афксжетинстанцехандле](application-information-and-management.md#afxgetinstancehandle) Получает маркер текущего экземпляра приложения.

- [Афксжетресаурцехандле](application-information-and-management.md#afxgetresourcehandle) Получает маркер для ресурсов приложения.

- [Афксжетаппнаме](application-information-and-management.md#afxgetappname) Получает указатель на строку, содержащую имя приложения. Кроме того, если у вас есть указатель на `CWinApp` объект, используйте `m_pszExeName` для получения имени приложения.

См [. раздел CWinApp: класс Application](../../mfc/cwinapp-the-application-class.md) для получения дополнительных `CWinApp` сведений о классе, включая общие сведения о следующих компонентах:

- `CWinApp`— Производный код, написанный мастером приложений.

- `CWinApp`роль в последовательности выполнения приложения.

- `CWinApp`реализации функций элементов по умолчанию.

- `CWinApp`ключ оверридаблес.

`m_hPrevInstance`Элемент данных больше не существует. Чтобы определить, работает ли другой экземпляр приложения, используйте именованный мьютекс. При неудачном открытии мьютекса другие экземпляры приложения не выполняются.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cwinappadddoctemplate"></a><a name="adddoctemplate"></a> CWinApp:: AddDocTemplate

Вызовите эту функцию-член, чтобы добавить шаблон документа в список доступных шаблонов документов, поддерживаемых приложением.

```cpp
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Параметры

*птемплате*<br/>
Указатель на `CDocTemplate` добавляемый объект.

### <a name="remarks"></a>Примечания

Перед вызовом [RegisterShellFileTypes](#registershellfiletypes)необходимо добавить все шаблоны документов в приложение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

## <a name="cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a> CWinApp:: Аддторецентфилелист

Вызовите эту функцию члена, чтобы добавить *лпсзпаснаме* в список файлов MRU.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*лпсзпаснаме*<br/>
Путь к файлу.

### <a name="remarks"></a>Примечания

Перед использованием этой функции члена следует вызвать функцию члена [лоадстдпрофилесеттингс](#loadstdprofilesettings) , чтобы загрузить текущий список файлов MRU.

Платформа вызывает эту функцию-член при открытии файла или выполняет команду Сохранить как, чтобы сохранить файл с новым именем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

## <a name="cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a> CWinApp:: Аппликатионрековерикаллбакк

Вызывается платформой при внезапном завершении работы приложения.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Параметры

*лпвпарам*<br/>
[in] Зарезервирован для будущего использования.

### <a name="return-value"></a>Возвращаемое значение

0, если этот метод успешно выполнен; ненулевое значение, если возникает ошибка.

### <a name="remarks"></a>Примечания

Если приложение поддерживает диспетчер перезапуска, платформа вызывает эту функцию при неожиданном завершении работы приложения.

Реализация по умолчанию `ApplicationRecoveryCallback` использует `CDataRecoveryHandler` для сохранения списка документов, открытых в данный момент в реестре. Этот метод не выполняет Автосохранение файлов.

Чтобы настроить поведение, переопределите эту функцию в производном [классе CWinApp](../../mfc/reference/cwinapp-class.md) или передайте собственный метод восстановления приложения в качестве параметра для [CWinApp:: регистервисрестартманажер](#registerwithrestartmanager).

## <a name="cwinappclosealldocuments"></a><a name="closealldocuments"></a> CWinApp:: Клосеаллдокументс

Вызовите эту функцию члена, чтобы закрыть все открытые документы перед выходом.

```cpp
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Параметры

*бендсессион*<br/>
Указывает, завершается ли сеанс Windows. Значение TRUE, если сеанс завершается; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Вызовите [хидеаппликатион](#hideapplication) перед вызовом `CloseAllDocuments` .

## <a name="cwinappcreateprinterdc"></a><a name="createprinterdc"></a> CWinApp:: Креатепринтердк

Вызовите эту функцию-член, чтобы создать контекст устройства печати (DC) на выбранном принтере.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Параметры

*Постоянный*<br/>
Ссылка на контекст устройства принтера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если контекст печатающего устройства успешно создан; в противном случае — 0.

### <a name="remarks"></a>Примечания

`CreatePrinterDC` Инициализирует контекст устройства, который передается по ссылке, поэтому его можно использовать для печати.

Если функция выполнена успешно, то после завершения печати необходимо уничтожить контекст устройства. Можно разрешить деструктор объекта [CDC](../../mfc/reference/cdc-class.md) , или же выполнить его явным образом, вызвав [CDC::D елетедк](../../mfc/reference/cdc-class.md#deletedc).

## <a name="cwinappcwinapp"></a><a name="cwinapp"></a> CWinApp:: CWinApp

Конструирует `CWinApp` объект и передает *лпсзаппнаме* для сохранения в качестве имени приложения.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзаппнаме*<br/>
Строка, заканчивающаяся нулем и содержащая имя приложения, которое используется в Windows. Если этот аргумент не указан или имеет значение NULL, `CWinApp` использует строку ресурса AFX_IDS_APP_TITLE или имя файла исполняемого файла.

### <a name="remarks"></a>Примечания

Необходимо создать один глобальный объект `CWinApp` производного класса. В приложении может быть только один `CWinApp` объект. Конструктор сохраняет указатель на `CWinApp` объект, чтобы `WinMain` можно было вызывать функции-члены объекта для инициализации и запуска приложения.

## <a name="cwinappdelregtree"></a><a name="delregtree"></a> CWinApp::D Елрегтри

Удаляет конкретный раздел реестра и все его подразделы.

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*хпаренткэй*<br/>
Обработчик для раздела реестра.

*стркэйнаме*<br/>
Имя удаляемого раздела реестра.

*pTM*<br/>
Указатель на объект Катлтрансактионманажер.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы удалить указанный ключ и его подразделы.

## <a name="cwinappdomessagebox"></a><a name="domessagebox"></a> CWinApp::D Омессажебокс

Платформа вызывает эту функцию-член для реализации окна сообщения для глобальной функции [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Параметры

*лпсзпромпт*<br/>
Адрес текста в окне сообщения.

*nType*<br/>
[Стиль](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)окна сообщения.

*нидпромпт*<br/>
Индекс строки контекста справки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает те же значения, что и `AfxMessageBox` .

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию-член для открытия окна сообщения; `AfxMessageBox` вместо этого используйте.

Переопределите эту функцию-член, чтобы настроить обработку вызовов на уровне приложения `AfxMessageBox` .

## <a name="cwinappdowaitcursor"></a><a name="dowaitcursor"></a> CWinApp::D Оваиткурсор

Эта функция-член вызывается платформой для реализации [кваиткурсор](../../mfc/reference/cwaitcursor-class.md), [от CCmdTarget:: бегинваиткурсор](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [от CCmdTarget:: Ендваиткурсор](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)и [от CCmdTarget:: рестореваиткурсор](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Параметры

*нкоде*<br/>
Если этот параметр равен 1, то появляется курсор ожидания. Если значение равно 0, то курсор ожидания восстанавливается без увеличения счетчика ссылок. Если значение равно-1, то курсор ожидания заканчивается.

### <a name="remarks"></a>Примечания

По умолчанию реализуется курсор песочных часов. `DoWaitCursor` поддерживает счетчик ссылок. При положительном значении отображается курсор песочных часов.

Хотя обычно не вызывается `DoWaitCursor` напрямую, можно переопределить эту функцию-член, чтобы изменить курсор ожидания или выполнить дополнительную обработку, пока отображается курсор ожидания.

Для более простого и упрощенного способа реализации курсора ожидания используйте `CWaitCursor` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

## <a name="cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a> CWinApp:: EnableD2DSupport

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Включает поддержку приложений D2D. Данный метод следует вызывать до инициализации основного окна.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Параметры

*d2dFactoryType*<br/>
Потоковая модель фабрики D2D и ресурсов, которые она создает.

*вритефакторитипе*<br/>
Значение типа, указывающее, будет ли объект фабрики записи общим или изолированным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если поддержка D2D включена, в противном случае — FALSE.

## <a name="cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a> CWinApp:: Енаблехтмлхелп

Вызовите эту функцию-член из конструктора `CWinApp` производного класса, чтобы использовать HTMLHelp для справки вашего приложения.

```cpp
void EnableHtmlHelp();
```

### <a name="remarks"></a>Примечания

## <a name="cwinappenableshellopen"></a><a name="enableshellopen"></a> CWinApp:: Енаблешеллопен

Вызывайте эту функцию, как правило, из `InitInstance` переопределения, чтобы пользователи приложения могли открывать файлы данных, когда они дважды щелкают файлы в диспетчере файлов Windows.

```cpp
void EnableShellOpen();
```

### <a name="remarks"></a>Примечания

Вызовите `RegisterShellFileTypes` функцию-член в сочетании с этой функцией или предоставьте. Файл REG с приложением для регистрации типов документов вручную.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

## <a name="cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a> CWinApp:: Енаблетаскбаринтерактион

Включает взаимодействие с панелью задач.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, должно ли быть включено взаимодействие с панелью задач Windows 7 (TRUE) или отключено (FALSE).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если можно включить или отключить взаимодействие с панелью задач.

### <a name="remarks"></a>Примечания

Этот метод должен вызываться перед созданием главного окна, в противном случае он утверждает и возвращает значение FALSE.

## <a name="cwinappexitinstance"></a><a name="exitinstance"></a> CWinApp:: ExitInstance

Вызвано платформой из `Run` функции члена для выхода из этого экземпляра приложения.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Код выхода приложения; 0 означает отсутствие ошибок, а значения больше 0 указывают на ошибку. Это значение используется в качестве возвращаемого значения из `WinMain` .

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию члена из любого места, но внутри `Run` функции члена.

Реализация по умолчанию этой функции записывает параметры платформы в приложение. INI-файл. Переопределите эту функцию для очистки после завершения работы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

## <a name="cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a> CWinApp:: Жетаппликатионрековерипараметер

Получает входной параметр для метода восстановления приложения.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Возвращаемое значение

Входной параметр по умолчанию для метода восстановления приложения.

### <a name="remarks"></a>Примечания

Поведение этой функции по умолчанию возвращает значение NULL.

Дополнительные сведения см. в разделе [CWinApp:: аппликатионрековерикаллбакк](#applicationrecoverycallback).

## <a name="cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a> CWinApp:: Жетаппликатионрековерипингинтервал

Возвращает период времени, в течение которого диспетчер перезапуска ожидает возврата функции обратного вызова восстановления.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность времени в миллисекундах.

### <a name="remarks"></a>Примечания

Когда приложение, зарегистрированное в диспетчере перезапуска, неожиданно завершает работу, приложение пытается сохранить открытые документы и вызвать функцию обратного вызова восстановления. Функция обратного вызова восстановления по умолчанию — [CWinApp:: аппликатионрековерикаллбакк](#applicationrecoverycallback).

Период времени, в течение которого платформа ожидает возврата функцией обратного вызова восстановления, является интервалом проверки связи. Интервал проверки связи можно настроить путем переопределения `CWinApp::GetApplicationRecoveryPingInterval` или путем предоставления пользовательского значения для `RegisterWithRestartManager` .

## <a name="cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a> CWinApp:: Жетаппликатионрестартфлагс

Возвращает флаги для диспетчера перезапуска.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Возвращаемое значение

Флаги для диспетчера перезапуска. Реализация по умолчанию возвращает 0.

### <a name="remarks"></a>Примечания

Флаги для диспетчера перезапуска не влияют на реализацию по умолчанию. Они предоставляются для использования в будущем.

Флаги задаются при регистрации приложения в диспетчере перезапуска с помощью команды [CWinApp:: регистервисрестартманажер](#registerwithrestartmanager).

Ниже приведены возможные значения для флагов диспетчера перезапуска.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappgetappregistrykey"></a><a name="getappregistrykey"></a> CWinApp:: Жетаппрегистрикэй

Возвращает ключ для HKEY_CURRENT_USER \\ "Software" \регистрикэй\профиленаме.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ приложения, если функция выполнена. в противном случае — NULL.

### <a name="remarks"></a>Примечания

## <a name="cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a> CWinApp:: Жетдатарековерихандлер

Возвращает обработчик восстановления данных для этого экземпляра приложения.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик восстановления данных для этого экземпляра приложения.

### <a name="remarks"></a>Примечания

Каждое приложение, использующее диспетчер перезапуска, должно иметь один экземпляр [класса кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md). Этот класс отвечает за отслеживание открытых документов и автоматическое сохранение файлов. Поведение объекта `CDataRecoveryHandler` зависит от конфигурации диспетчера перезапуска. Дополнительные сведения см. в разделе [класс кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md).

Этот метод возвращает значение NULL в операционных системах, предшествующих Windows Vista. Диспетчер перезапуска не поддерживается в операционных системах, предшествующих Windows Vista.

Если в приложении нет обработчика восстановления данных, этот метод создает его и возвращает указатель на него.

## <a name="cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a> CWinApp:: Жетфирстдоктемплатепоситион

Возвращает расположение первого шаблона документа в приложении.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

### <a name="remarks"></a>Примечания

Используйте значение value, возвращаемое в вызове [жетнекстдоктемплате](#getnextdoctemplate) , чтобы получить первый объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) .

## <a name="cwinappgethelpmode"></a><a name="gethelpmode"></a> CWinApp:: Жеселпмоде

Извлекает тип справки, используемый приложением.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Возвращаемое значение

Тип справки, используемый приложением. Дополнительные сведения см. в разделе [CWinApp:: m_eHelpType](#m_ehelptype) .

## <a name="cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a> CWinApp:: Жетнекстдоктемплате

Возвращает шаблон документа, идентифицируемый *POS*, а затем задает *торговому терминалу* значение "позиция".

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение ПОЗИЦИЕЙ, возвращенное предыдущим вызовом метода `GetNextDocTemplate` или [жетфирстдоктемплатепоситион](#getfirstdoctemplateposition). Значение обновляется до следующей позицией с помощью этого вызова.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) .

### <a name="remarks"></a>Примечания

Можно использовать `GetNextDocTemplate` в цикле прямой итерации, если исходное расположение устанавливается с вызовом `GetFirstDocTemplatePosition` .

Необходимо убедиться, что ваше значение должно быть допустимым. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если полученный шаблон документа является последним доступным, новое значение *POS* устанавливается в NULL.

## <a name="cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a> CWinApp:: Жетпринтердевицедефаултс

Вызовите эту функцию-член для подготовки контекста печатающего устройства для печати.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Параметры

*ппринтдлг*<br/>
Указатель на структуру [принтдлг](/windows/win32/api/commdlg/ns-commdlg-printdlga) .

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Извлекает текущие значения по умолчанию принтера из окна. INI-файл по мере необходимости или использует последнюю конфигурацию принтера, заданную пользователем в окне настройки печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

## <a name="cwinappgetprofilebinary"></a><a name="getprofilebinary"></a> CWinApp:: Жетпрофилебинари

Вызовите эту функцию-член для получения двоичных данных из записи в указанном разделе реестра приложения или. INI-файл.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, значение которой необходимо получить.

*ппдата*<br/>
Указывает на указатель, который получит адрес данных.

*пбитес*<br/>
Указывает на UINT, который будет принимать размер данных (в байтах).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член не учитывает регистр, поэтому строки в параметрах *лпсзсектион* и *лпсзентри* могут различаться в случае.

> [!NOTE]
> `GetProfileBinary` выделяет буфер и возвращает его адрес в \* *ппдата*. Вызывающий объект отвечает за освобождение буфера с помощью инструкции **Delete []**.

> [!IMPORTANT]
> Данные, возвращаемые этой функцией, не обязательно завершаются НУЛЕМ, и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Дополнительные примеры см. в разделе [CWinApp:: вритепрофилебинари](#writeprofilebinary).

## <a name="cwinappgetprofileint"></a><a name="getprofileint"></a> CWinApp:: Жетпрофилеинт

Вызовите эту функцию-член, чтобы получить значение целого числа из записи в указанном разделе реестра приложения или. INI-файл.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, значение которой необходимо получить.

*ндефаулт*<br/>
Указывает значение по умолчанию, возвращаемое, если платформе не удается найти эту запись.

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение строки, следующей за заданной записью, если функция выполнена успешно. Возвращаемое значение является значением параметра *ндефаулт* , если функция не находит запись. Возвращаемое значение равно 0, если значение, соответствующее указанной записи, не является целым числом.

Эта функция члена поддерживает шестнадцатеричную нотацию для значения в. INI-файл. При извлечении целого числа со знаком необходимо привести значение в **`int`** .

### <a name="remarks"></a>Примечания

Эта функция-член не учитывает регистр, поэтому строки в параметрах *лпсзсектион* и *лпсзентри* могут различаться в случае.

> [!IMPORTANT]
> Данные, возвращаемые этой функцией, не обязательно завершаются НУЛЕМ, и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Дополнительные примеры см. в разделе [CWinApp:: вритепрофилеинт](#writeprofileint).

## <a name="cwinappgetprofilestring"></a><a name="getprofilestring"></a> CWinApp:: Жетпрофилестринг

Вызовите эту функцию члена, чтобы получить строку, связанную с записью в указанном разделе реестра приложения или. INI-файл.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, строку которой необходимо извлечь. Это значение не должно быть равно NULL.

*лпсздефаулт*<br/>
Указывает строковое значение по умолчанию для заданной записи, если запись не найдена в файле инициализации.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение — это строка из приложения. INI-файл или *лпсздефаулт* , если строка не найдена. Максимальная длина строки, поддерживаемая платформой, — _MAX_PATH. Если *лпсздефаулт* имеет значение null, возвращаемое значение является пустой строкой.

### <a name="remarks"></a>Примечания

> [!IMPORTANT]
> Данные, возвращаемые этой функцией, не обязательно завершаются НУЛЕМ, и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример см. в примере для [CWinApp:: жетпрофилеинт](#getprofileint).

## <a name="cwinappgetsectionkey"></a><a name="getsectionkey"></a> CWinApp:: Жетсектионкэй

Возвращает ключ для HKEY_CURRENT_USER \\ "Software" \регистрикэй\аппнаме\лпсзсектион.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Имя получаемого ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ раздела, если функция выполнена. в противном случае — NULL.

### <a name="remarks"></a>Примечания

## <a name="cwinapphideapplication"></a><a name="hideapplication"></a> CWinApp:: Хидеаппликатион

Вызовите эту функцию члена, чтобы скрыть приложение перед закрытием открытых документов.

```cpp
void HideApplication();
```

## <a name="cwinapphtmlhelp"></a><a name="htmlhelp"></a> CWinApp:: HtmlHelp

Вызовите эту функцию члена, чтобы вызвать приложение HTMLHelp.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Параметры

*двдата*<br/>
Указывает дополнительные данные. Используемое значение зависит от значения параметра *нкмд* . По умолчанию `0x000F` — [HH_HELP_CONTEXT](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command).

*нкмд*<br/>
Задает тип запрошенной справки. Список возможных значений и их влияние на параметр *двдата* см. в описании параметра *укомманд* , как описано в разделе функции API [хтмлхелпв](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw) или [хтмлхелпа](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa) в Windows SDK.

### <a name="remarks"></a>Примечания

Платформа также вызывает эту функцию для вызова приложения HTMLHelp.

Платформа автоматически закроет приложение HTMLHelp при завершении работы приложения.

## <a name="cwinappinitinstance"></a><a name="initinstance"></a> CWinApp:: InitInstance

Windows позволяет одновременно выполнять несколько копий одной программы.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Инициализация приложения концептуально делится на два раздела: однократная инициализация приложения, выполняемая при первом запуске программы, и инициализация экземпляра, которая выполняется каждый раз при выполнении копии программы, включая первый раз. Реализация этой функции в инфраструктуре `WinMain` вызывает эту функцию.

Переопределите `InitInstance` для инициализации каждого нового экземпляра приложения, работающего под управлением Windows. Как правило, переопределяется `InitInstance` для создания основного объекта окна и установки `CWinThread::m_pMainWnd` элемента данных для указания на это окно. Дополнительные сведения о переопределении этой функции – члена см. [в разделе CWinApp: класс Application](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в `InitInstance` переопределении укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

## <a name="cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a> CWinApp:: Истаскбаринтерактионенаблед

Указывает, включено ли взаимодействие с панелью задач Windows 7.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE `EnableTaskbarInteraction` , если был вызван, а операционная система — Windows 7 или более поздней версии.

### <a name="remarks"></a>Примечания

Взаимодействие с панелью задач означает, что приложение MDI отображает содержимое дочерних элементов MDI в отдельных эскизах, отображаемых при наведении указателя мыши на кнопку на панели задач приложения.

## <a name="cwinapploadcursor"></a><a name="loadcursor"></a> CWinApp:: Лоадкурсор

Загружает ресурс курсора с именем *лпсзресаурценаме* или заданный параметром *нидресаурце* из текущего исполняемого файла.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*лпсзресаурценаме*<br/>
Указывает на строку, завершающуюся нулем, которая содержит имя ресурса курсора. `CString`Для этого аргумента можно использовать.

*нидресаурце*<br/>
Идентификатор ресурса курсора. Список ресурсов см. в разделе [лоадкурсор](/windows/win32/api/winuser/nf-winuser-loadcursorw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Указатель на курсор в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Примечания

`LoadCursor` загружает курсор в память только в том случае, если он не был загружен ранее. в противном случае он извлекает маркер существующего ресурса.

Используйте функцию члена [лоадстандардкурсор](#loadstandardcursor) или [лоадоемкурсор](#loadoemcursor) для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

## <a name="cwinapploadicon"></a><a name="loadicon"></a> CWinApp:: Лоадикон

Загружает ресурс значка с именем *лпсзресаурценаме* или заданный параметром *нидресаурце* из исполняемого файла.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*лпсзресаурценаме*<br/>
Указывает на строку, завершающуюся нулем, которая содержит имя ресурса значка. `CString`Для этого аргумента также можно использовать.

*нидресаурце*<br/>
ИДЕНТИФИКАЦИОНный номер ресурса значка.

### <a name="return-value"></a>Возвращаемое значение

Маркер для значка в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Примечания

`LoadIcon` Загружает значок, только если он не был загружен ранее. в противном случае он извлекает маркер существующего ресурса.

Для доступа к стандартным значкам Windows можно использовать функцию члена [лоадстандардикон](#loadstandardicon) или [лоадоемикон](#loadoemicon) .

> [!NOTE]
> Эта функция-член вызывает функцию Win32 API [лоадикон](/windows/win32/api/winuser/nf-winuser-loadiconw), которая может загрузить только значок, размер которого соответствует значениям системных метрик SM_CXICON и SM_CYICON.

## <a name="cwinapploadoemcursor"></a><a name="loadoemcursor"></a> CWinApp:: Лоадоемкурсор

Загружает стандартный ресурс курсора Windows, указанный параметром *нидкурсор*.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Параметры

*нидкурсор*<br/>
Идентификатор константы манифеста **OCR_** , указывающий предопределенный курсор Windows. Для `#define OEMRESOURCE` `#include \<afxwin.h>` получения доступа к константам **OCR_** в Windows необходимо иметь до. Высоты.

### <a name="return-value"></a>Возвращаемое значение

Указатель на курсор в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadOEMCursor` функцию члена [лоадстандардкурсор](#loadstandardcursor) или для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

## <a name="cwinapploadoemicon"></a><a name="loadoemicon"></a> CWinApp:: Лоадоемикон

Загружает стандартный ресурс значков Windows, заданный параметром *нидикон*.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Параметры

*нидикон*<br/>
Идентификатор константы манифеста **OIC_** , указывающий стандартный значок Windows. `#define OEMRESOURCE` `#include \<afxwin.h>` Для доступа к константам **OIC_** в Windows необходимо иметь до. Высоты.

### <a name="return-value"></a>Возвращаемое значение

Маркер для значка в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadOEMIcon` функцию члена [лоадстандардикон](#loadstandardicon) или для доступа к предопределенным значкам Windows.

## <a name="cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a> CWinApp:: Лоадстандардкурсор

Загружает стандартный ресурс курсора Windows, который *лпсзкурсорнаме* указывает.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Параметры

*лпсзкурсорнаме*<br/>
Идентификатор константы манифеста **IDC_** , указывающий предопределенный курсор Windows. Эти идентификаторы определяются в WINDOWS. Высоты. В следующем списке приведены возможные стандартные значения и смысл для *лпсзкурсорнаме*:

- IDC_ARROW стандартный курсор со стрелкой

- IDC_IBEAM стандартный курсор вставки текста

- Курсор IDC_WAIT песочных часов, когда Windows выполняет трудоемкую задачу

- IDC_CROSS курсора перекрестных крестиков для выбора

- IDC_UPARROW стрелка, указывающая на прямую

- IDC_SIZE устарел и не поддерживается; Использование IDC_SIZEALL

- IDC_SIZEALL стрелка, указывающая на четыре элемента. Курсор, используемый для изменения размера окна.

- IDC_ICON устарел и не поддерживается. Используйте IDC_ARROW.

- IDC_SIZENWSE двусторонняя стрелка с концом в верхнем левом и нижнем правом углу

- IDC_SIZENESW двусторонняя стрелка с концом в правом верхнем и нижнем левом углу

- IDC_SIZEWE горизонтальная двунаправленная стрелка

- Вертикальная двунаправленная стрелка IDC_SIZENS

### <a name="return-value"></a>Возвращаемое значение

Указатель на курсор в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadStandardCursor` функцию члена [лоадоемкурсор](#loadoemcursor) или для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

## <a name="cwinapploadstandardicon"></a><a name="loadstandardicon"></a> CWinApp:: Лоадстандардикон

Загружает стандартный ресурс значков Windows, который *лпсзиконнаме* указывает.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Параметры

*лпсзиконнаме*<br/>
Идентификатор константы манифеста, указывающий стандартный значок Windows. Эти идентификаторы определяются в WINDOWS. Высоты. Список возможных стандартных значений и их описания см. в описании параметра *лпиконнаме* в [лоадикон](/windows/win32/api/winuser/nf-winuser-loadiconw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Маркер для значка в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadStandardIcon` функцию члена [лоадоемикон](#loadoemicon) или для доступа к предопределенным значкам Windows.

## <a name="cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a> CWinApp:: Лоадстдпрофилесеттингс

Вызовите эту функцию-член из функции-члена [InitInstance](#initinstance) , чтобы включить и загрузить список последних использованных файлов (MRU) и Последнее состояние предварительного просмотра.

```cpp
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Параметры

*нмаксмру*<br/>
Число недавно использовавшихся файлов для трассировки.

### <a name="remarks"></a>Примечания

Если *нмаксмру* имеет значение 0, список MRU не будет сохранен.

## <a name="cwinappm_bhelpmode"></a><a name="m_bhelpmode"></a> CWinApp:: m_bHelpMode

Значение TRUE, если приложение находится в контекстном режиме справки (в соответствии с соглашением, которое вызывается с помощью SHIFT + F1); в противном случае — FALSE.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Примечания

В режиме контекста справки курсор превращается в вопросительный знак, и пользователь может переместить его на экран. Изучите этот флаг, если в режиме справки необходимо реализовать специальную обработку. `m_bHelpMode` — Это открытая переменная типа BOOL.

## <a name="cwinappm_dwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a> CWinApp:: m_dwRestartManagerSupportFlags

Флаги, определяющие работу диспетчера перезапуска.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Примечания

Чтобы включить диспетчер перезапуска, задайте нужное `m_dwRestartManagerSupportFlags` поведение. В следующей таблице показаны доступные флаги.

|Flag|Описание|
|-|-|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Приложение регистрируется с помощью команды [CWinApp:: регистервисрестартманажер](#registerwithrestartmanager). Диспетчер перезапуска отвечает за перезапуск приложения, если он неожиданно завершает работу.|
|— AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Приложение регистрируется в диспетчере перезапуска, а диспетчер перезапуска вызывает функцию обратного вызова восстановления при перезапуске приложения. Функция обратного вызова восстановления по умолчанию — [CWinApp:: аппликатионрековерикаллбакк](#applicationrecoverycallback).|
|— AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Автосохранение включено, а диспетчер перезапуска автоматически сохраняет все открытые документы при перезапуске приложения.|
|— AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Автосохранение включено, а диспетчер перезапуска автоматически сохраняет все открытые документы через равные промежутки времени. Интервал определяется с помощью [CWinApp:: m_nAutosaveInterval](#m_nautosaveinterval).|
|— AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Диспетчер перезапуска открывает ранее открытые документы после перезапуска приложения с непредвиденным выходом. [Класс кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md) обрабатывает сохранение списка открытых документов и их восстановление.|
|— AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Диспетчер перезапуска предлагает пользователю восстановить автоматически сохраненные файлы после перезапуска приложения. `CDataRecoveryHandler`Класс запрашивает пользователя.|
|— AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|Объединение AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER и AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES.|
|— AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|— AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|— AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|OfAFX_RESTART_MANAGER_SUPPORT_RECOVERY Union, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

## <a name="cwinappm_ehelptype"></a><a name="m_ehelptype"></a> CWinApp:: m_eHelpType

Тип этого элемента данных — перечислимый тип AFX_HELP_TYPE, который определен в `CWinApp` классе.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Примечания

Перечисление AFX_HELP_TYPE определяется следующим образом:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Чтобы настроить справку приложения в HTML Help, вызовите [сеселпмоде](#sethelpmode) и укажите `afxHTMLHelp` .

- Чтобы задать справку приложения WinHelp, вызовите `SetHelpMode` и укажите `afxWinHelp` .

## <a name="cwinappm_hinstance"></a><a name="m_hinstance"></a> CWinApp:: m_hInstance

Соответствует параметру *HINSTANCE* , переданному Windows в `WinMain` .

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Примечания

`m_hInstance`Элемент данных является обработчиком текущего экземпляра приложения, работающего под управлением Windows. Это значение возвращается глобальной функцией [афксжетинстанцехандле](application-information-and-management.md#afxgetinstancehandle). `m_hInstance` — Это открытая переменная типа HINSTANCE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

## <a name="cwinappm_lpcmdline"></a><a name="m_lpcmdline"></a> CWinApp:: m_lpCmdLine

Соответствует параметру *лпкмдлине* , переданному Windows в `WinMain` .

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Примечания

Указывает на строку, завершающуюся нулем, которая указывает командную строку для приложения. Используйте `m_lpCmdLine` для доступа к любым аргументам командной строки, указанным пользователем при запуске приложения. `m_lpCmdLine` — Это открытая переменная типа LPTSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappm_nautosaveinterval"></a><a name="m_nautosaveinterval"></a> CWinApp:: m_nAutosaveInterval

Продолжительность времени в миллисекундах между автосохранением.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Примечания

Диспетчер перезапуска можно настроить для автосохранения открытых документов через заданные интервалы. Если приложение не выполняет Автосохранение файлов, этот параметр не действует.

## <a name="cwinappm_ncmdshow"></a><a name="m_ncmdshow"></a> CWinApp:: m_nCmdShow

Соответствует параметру *нкмдшов* , переданному Windows в `WinMain` .

```
int m_nCmdShow;
```

### <a name="remarks"></a>Примечания

При `m_nCmdShow` вызове метода [CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) для главного окна приложения необходимо передать в качестве аргумента. `m_nCmdShow` — Это открытая переменная типа **`int`** .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

## <a name="cwinappm_pactivewnd"></a><a name="m_pactivewnd"></a> CWinApp:: m_pActiveWnd

Используйте этот элемент данных для хранения указателя на главное окно приложения-контейнера OLE, в котором активировано приложение OLE-сервера на месте.

### <a name="remarks"></a>Примечания

Если этот элемент данных имеет значение NULL, это значит, что приложение не активно на месте.

Платформа устанавливает эту переменную-член, когда окно фрейма активируется приложением-контейнером OLE.

## <a name="cwinappm_pdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a> CWinApp:: m_pDataRecoveryHandler

Указатель на обработчик восстановления данных для приложения.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Примечания

Обработчик восстановления данных приложения наблюдает за открытием документов и автоматически сохраняет их. Платформа использует обработчик восстановления данных для восстановления автоматически сохраненных файлов при перезапуске приложения после его неожиданного завершения работы. Дополнительные сведения см. в разделе [класс кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md).

## <a name="cwinappm_pszappname"></a><a name="m_pszappname"></a> CWinApp:: m_pszAppName

Указывает имя приложения.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Примечания

Имя приложения может быть получено из параметра, переданного в конструктор [CWinApp](#cwinapp) , или, если не указано, в строку ресурса с идентификатором AFX_IDS_APP_TITLE. Если имя приложения не найдено в ресурсе, оно берется из программы. Имя файла EXE.

Возвращается глобальной функцией [афксжетаппнаме](application-information-and-management.md#afxgetappname). `m_pszAppName`— Это открытая переменная типа **const char** <strong>\*</strong> .

> [!NOTE]
> Если присвоить значение `m_pszAppName` , оно должно быть динамически выделено в куче. `CWinApp`Деструктор вызывает **Free**() с этим указателем. Многие из них хотят использовать `_tcsdup` функцию библиотеки времени выполнения () для выделения. Кроме того, перед назначением нового значения освободите память, связанную с текущим указателем. Пример:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

## <a name="cwinappm_pszexename"></a><a name="m_pszexename"></a> CWinApp:: m_pszExeName

Содержит имя исполняемого файла приложения без расширения.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Примечания

В отличие от [m_pszAppName](#m_pszappname), это имя не может содержать пробелы. `m_pszExeName`— Это открытая переменная типа **const char** <strong>\*</strong> .

> [!NOTE]
> Если присвоить значение `m_pszExeName` , оно должно быть динамически выделено в куче. `CWinApp`Деструктор вызывает **Free**() с этим указателем. Многие из них хотят использовать `_tcsdup` функцию библиотеки времени выполнения () для выделения. Кроме того, перед назначением нового значения освободите память, связанную с текущим указателем. Пример:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

## <a name="cwinappm_pszhelpfilepath"></a><a name="m_pszhelpfilepath"></a> CWinApp:: m_pszHelpFilePath

Содержит путь к файлу справки приложения.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Примечания

По умолчанию платформа инициализируется `m_pszHelpFilePath` именем приложения с помощью ". Добавлен в HLP. Чтобы изменить имя файла справки, задайте для параметра значение, `m_pszHelpFilePath` которое указывает на строку, содержащую полное имя нужного файла справки. Для этого удобно использовать функцию [InitInstance](#initinstance) приложения. `m_pszHelpFilePath`— Это открытая переменная типа **const char** <strong>\*</strong> .

> [!NOTE]
> Если присвоить значение `m_pszHelpFilePath` , оно должно быть динамически выделено в куче. `CWinApp`Деструктор вызывает **Free**() с этим указателем. Многие из них хотят использовать `_tcsdup` функцию библиотеки времени выполнения () для выделения. Кроме того, перед назначением нового значения освободите память, связанную с текущим указателем. Пример:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

## <a name="cwinappm_pszprofilename"></a><a name="m_pszprofilename"></a> CWinApp:: m_pszProfileName

Содержит имя приложения. INI-файл.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Примечания

`m_pszProfileName`— Это открытая переменная типа **const char** <strong>\*</strong> .

> [!NOTE]
> Если присвоить значение `m_pszProfileName` , оно должно быть динамически выделено в куче. `CWinApp`Деструктор вызывает **Free**() с этим указателем. Многие из них хотят использовать `_tcsdup` функцию библиотеки времени выполнения () для выделения. Кроме того, перед назначением нового значения освободите память, связанную с текущим указателем. Пример:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

## <a name="cwinappm_pszregistrykey"></a><a name="m_pszregistrykey"></a> CWinApp:: m_pszRegistryKey

Используется для определения места хранения параметров профиля приложения в реестре или INI-файле.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Примечания

Обычно этот элемент данных рассматривается как доступный только для чтения.

- Значение сохраняется в разделе реестра. Имя параметра профиля приложения добавляется к следующему разделу реестра: HKEY_CURRENT_USER/Софтваре/локалаппвизард-женератед/.

Если присвоить значение `m_pszRegistryKey` , оно должно быть динамически выделено в куче. `CWinApp`Деструктор вызывает **Free**() с этим указателем. Многие из них хотят использовать `_tcsdup` функцию библиотеки времени выполнения () для выделения. Кроме того, перед назначением нового значения освободите память, связанную с текущим указателем. Пример:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

## <a name="cwinappm_pszappid"></a><a name="m_pszappid"></a> CWinApp:: m_pszAppID

Идентификатор модели пользователя приложения.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Примечания

## <a name="cwinapponcontexthelp"></a><a name="oncontexthelp"></a> CWinApp:: Онконтексселп

Обрабатывает SHIFT + Справка F1 в приложении.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` оператор в `CWinApp` схему сообщений класса, а также добавить запись в таблице сочетаний клавиш, как правило, Shift + F1, чтобы включить эту функцию члена.

`OnContextHelp` переводит приложение в режим справки. Курсор превращается в стрелку и вопросительный знак, и пользователь может переместить указатель мыши и нажать левую кнопку мыши, чтобы выбрать диалоговое окно, окно, меню или кнопку команды. Эта функция члена получает контекст справки объекта в курсоре и вызывает функцию Windows WinHelp с этим контекстом справки.

## <a name="cwinapponddecommand"></a><a name="onddecommand"></a> CWinApp:: Онддекомманд

Вызывается структурой, когда основное окно фрейма получает сообщение о выполнении DDE.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Параметры

*лпсзкомманд*<br/>
Указывает на командную строку DDE, полученную приложением.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда обрабатывается; в противном случае — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию проверяет, является ли команда запросом на открытие документа, и, если да, открывает указанный документ. Диспетчер файлов Windows обычно отправляет такие строки команд DDE, когда пользователь дважды щелкает файл данных. Переопределите эту функцию для обработки других команд выполнения DDE, таких как команда для печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

## <a name="cwinapponfilenew"></a><a name="onfilenew"></a> CWinApp:: Онфиленев

Реализует команду ID_FILE_NEW.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_FILE_NEW, OnFileNew )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Если этот параметр включен, эта функция обрабатывает выполнение команды File New.

Сведения о поведении по умолчанию и рекомендации по переопределению этой функции члена см. в [техническом примечании 22](../../mfc/tn022-standard-commands-implementation.md) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileopen"></a><a name="onfileopen"></a> CWinApp:: Онфилеопен

Реализует команду ID_FILE_OPEN.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Если этот параметр включен, эта функция обрабатывает выполнение команды открытия файла.

Сведения о поведении по умолчанию и рекомендации по переопределению этой функции члена см. в [техническом примечании 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a> CWinApp:: Онфилепринтсетуп

Реализует команду ID_FILE_PRINT_SETUP.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Если этот параметр включен, эта функция обрабатывает выполнение команды File Print.

Сведения о поведении по умолчанию и рекомендации по переопределению этой функции члена см. в [техническом примечании 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponhelp"></a><a name="onhelp"></a> CWinApp:: OnHelp

Обрабатывает справку F1 в приложении (с использованием текущего контекста).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Примечания

Обычно также добавляется запись клавиши быстрого вызова для клавиши F1. Включение клавиши F1 — это только соглашение, а не требование.

`ON_COMMAND( ID_HELP, OnHelp )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Значение, если параметр включен, вызванный платформой при нажатии пользователем клавиши F1.

Реализация по умолчанию этой функции обработчика сообщений определяет контекст справки, соответствующий текущему окну, диалоговому окну или пункту меню, а затем вызывает WINHELP.EXE. Если контекст в данный момент недоступен, функция использует контекст по умолчанию.

Переопределите эту функцию-член, чтобы задать для контекста справки нечто отличное от окна, диалогового окна, пункта меню или кнопки панели инструментов, на которой в данный момент находится фокус. Вызовите метод `WinHelp` с требуемым идентификатором контекста справки.

## <a name="cwinapponhelpfinder"></a><a name="onhelpfinder"></a> CWinApp:: Онхелпфиндер

Обрабатывает команды ID_HELP_FINDER и ID_DEFAULT_HELP.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Если параметр включен, платформа вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает команду Help Finder для вызова `WinHelp` со стандартным **HELP_FINDER** разделе.

## <a name="cwinapponhelpindex"></a><a name="onhelpindex"></a> CWinApp:: Онхелпиндекс

Обрабатывает команду ID_HELP_INDEX и предоставляет раздел справки по умолчанию.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Если параметр включен, платформа вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает команду указателя справки для вызова `WinHelp` со стандартным **HELP_INDEXом** разделе.

## <a name="cwinapponhelpusing"></a><a name="onhelpusing"></a> CWinApp:: Онхелпусинг

Обрабатывает команду ID_HELP_USING.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Примечания

`ON_COMMAND( ID_HELP_USING, OnHelpUsing )` `CWinApp` Чтобы включить эту функцию члена, необходимо добавить оператор в схему сообщений класса. Платформа вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает справку с помощью команды для вызова `WinHelp` приложения со стандартным **HELP_HELPONHELPом** разделе.

## <a name="cwinapponidle"></a><a name="onidle"></a> CWinApp:: OnIdle

Переопределите эту функцию-член для выполнения обработки во время простоя.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Счетчик, увеличивающийся каждый раз, `OnIdle` вызывается, когда очередь сообщений приложения пуста. Этот счетчик сбрасывается в 0 каждый раз при обработке нового сообщения. С помощью параметра *lCount* можно определить относительный срок простоя приложения без обработки сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение для получения более длительного времени обработки; 0, если не требуется больше времени простоя.

### <a name="remarks"></a>Примечания

`OnIdle` вызывается в цикле сообщений по умолчанию, если очередь сообщений приложения пуста. Используйте переопределение для вызова собственных задач обработчика бездействия в фоновом режиме.

`OnIdle` должен возвращать значение 0, чтобы указать, что время простоя обработки не требуется. Параметр *lCount* увеличивается каждый раз, `OnIdle` когда очередь сообщений пуста, и сбрасывается в 0 каждый раз при обработке нового сообщения. В зависимости от этого числа можно вызывать различные подпрограммы бездействия.

Ниже приведены сводные сведения об обработке бездействующего цикла.

1. Если цикл обработки сообщений в библиотека Microsoft Foundation Class проверяет очередь сообщений и не находит ожидающих сообщений, он вызывает `OnIdle` для объекта приложения и предоставляет 0 в качестве аргумента *lCount* .

2. `OnIdle` выполняет некоторую обработку и возвращает ненулевое значение, чтобы указать, что его следует вызывать повторно для дальнейшей обработки.

3. Цикл обработки сообщений снова проверяет очередь сообщений. Если нет ожидающих сообщений, вызывается `OnIdle` повторный вызов, увеличивающий аргумент *lCount* .

4. В конечном итоге `OnIdle` завершает обработку всех задач, выполняемых в состоянии простоя, и возвращает 0. Это указывает, что цикл обработки сообщений должен прерывать вызов `OnIdle` до получения следующего сообщения из очереди сообщений, после чего цикл бездействия перезапускается с аргументом, равным 0.

Не выполняйте длительные задачи, `OnIdle` так как приложение не может обрабатывать ввод данных пользователем до `OnIdle` возврата.

> [!NOTE]
> Реализация по умолчанию служб `OnIdle` Updates для командного интерфейса пользователя, например элементы меню и кнопки панели инструментов, и выполняет внутреннюю очистку структуры данных. Поэтому при `OnIdle` `CWinApp::OnIdle` переопределении необходимо вызвать с параметром `lCount` в переопределенной версии. Сначала следует вызвать всю обработку бездействия базового класса (то есть до тех пор, пока базовый класс не `OnIdle` вернет 0). Если необходимо выполнить работу до завершения обработки базового класса, ознакомьтесь с реализацией базового класса, чтобы выбрать правильные *lCount* , в течение которых будет выполняться работа.

Если не нужно `OnIdle` вызывать при каждом извлечении сообщения из очереди сообщений, можно переопределить [квинсреадисидлемессаже](../../mfc/reference/cwinthread-class.md#isidlemessage). Если в приложении задан очень короткий таймер или система отправляет сообщение WM_SYSTIMER, то `OnIdle` оно будет вызываться многократно и снизит производительность.

### <a name="example"></a>Пример

В следующих двух примерах показано, как использовать `OnIdle` . Первый пример обрабатывает две задачи бездействия, используя аргумент *lCount* для определения приоритета задач. Первая задача имеет высокий приоритет, и ее следует выполнять везде, где это возможно. Вторая задача менее важна и должна выполняться только при длительной паузе в вводе данных пользователем. Обратите внимание на вызов версии базового класса `OnIdle` . Во втором примере осуществляется управление группой задач бездействия с разными приоритетами.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

## <a name="cwinappopendocumentfile"></a><a name="opendocumentfile"></a> CWinApp:: Опендокументфиле

Платформа вызывает этот метод, чтобы открыть именованный файл [CDocument](../../mfc/reference/cdocument-class.md) для приложения.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
окне Имя открываемого файла.

*баддтомру*<br/>
окне Значение TRUE указывает, что документ является одним из самых последних файлов; Значение FALSE указывает, что документ не является одним из самых последних файлов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на, `CDocument` если успешно; в противном случае — null.

### <a name="remarks"></a>Примечания

Если документ с таким именем уже открыт, фокус будет получен из первого окна фрейма, содержащего этот документ. Если приложение поддерживает несколько шаблонов документов, платформа использует расширение имени файла для поиска соответствующего шаблона документа, который пытается загрузить документ. В случае успеха шаблон документа создает фрейм окна и представление для документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappparsecommandline"></a><a name="parsecommandline"></a> CWinApp::P Арсекоммандлине

Вызовите эту функцию-член, чтобы проанализировать командную строку и отправить параметры по одной за раз в [ккоммандлинеинфо::P арсепарам](../../mfc/reference/ccommandlineinfo-class.md#parseparam).

```cpp
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*ркмдинфо*<br/>
Ссылка на объект [ккоммандлинеинфо](../../mfc/reference/ccommandlineinfo-class.md) .

### <a name="remarks"></a>Примечания

При запуске нового проекта MFC с помощью мастера приложений Мастер приложений создает локальный экземпляр `CCommandLineInfo` , а затем вызывает метод `ProcessShellCommand` и `ParseCommandLine` в функции-члене [InitInstance](#initinstance) . Командная строка соответствует маршруту, описанному ниже.

1. После создания `InitInstance` `CCommandLineInfo` объект передается в `ParseCommandLine` .

2. `ParseCommandLine` Затем вызывается `CCommandLineInfo::ParseParam` многократно, по одному разу для каждого параметра.

3. `ParseParam` заполняет `CCommandLineInfo` объект, который затем передается в [ProcessShellCommand](#processshellcommand).

4. `ProcessShellCommand` обрабатывает аргументы и флаги командной строки.

Обратите внимание, что при необходимости можно вызывать `ParseCommandLine` напрямую.

Описание флагов командной строки см. в разделе [ккоммандлинеинфо:: m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

## <a name="cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a> CWinApp::P Ретранслатемессаже

Переопределите эту функцию, чтобы отфильтровать сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . Реализация по умолчанию выполняет преобразование ключей ускорителя, поэтому необходимо вызвать `CWinApp::PreTranslateMessage` функцию-член в переопределенной версии.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
Указатель на структуру [MSG](/windows/win32/api/winuser/ns-winuser-msg) , содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение полностью обработано в `PreTranslateMessage` и не должно обрабатываться дальше. Нуль, если сообщение должно обрабатываться обычным образом.

## <a name="cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a> CWinApp::P Роцессмессажефилтер

Функция-ловушка платформы вызывает эту функцию-член для фильтрации и реагирования на определенные сообщения Windows.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*code*<br/>
Указывает код обработчика. Эта функция члена использует код, чтобы определить, как обрабатывать *лпмсг.*

*лпмсг*<br/>
Указатель на [сообщение](/windows/win32/api/winuser/ns-winuser-msg)Windows структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обрабатывается; в противном случае — 0.

### <a name="remarks"></a>Примечания

Функция-обработчик обрабатывает события перед их отправкой в обычную обработку сообщений приложения.

При переопределении этой дополнительной функции не забудьте вызвать версию базового класса, чтобы обеспечить обработку обработчика.

## <a name="cwinappprocessshellcommand"></a><a name="processshellcommand"></a> CWinApp::P Роцессшеллкомманд

Эта функция-член вызывается методом [InitInstance](#initinstance) для принятия параметров, передаваемых из `CCommandLineInfo` объекта, идентифицируемого *ркмдинфо*, и выполнения указанного действия.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*ркмдинфо*<br/>
Ссылка на объект [ккоммандлинеинфо](../../mfc/reference/ccommandlineinfo-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда оболочки успешно обработана. Если 0, возвращается значение FALSE из [InitInstance](#initinstance).

### <a name="remarks"></a>Примечания

При запуске нового проекта MFC с помощью мастера приложений Мастер приложений создаст локальный экземпляр `CCommandLineInfo` , а затем выполнит вызов `ProcessShellCommand` и [парсекоммандлине](#parsecommandline) в `InitInstance` функции-члене. Командная строка соответствует маршруту, описанному ниже.

1. После создания `InitInstance` `CCommandLineInfo` объект передается в `ParseCommandLine` .

2. `ParseCommandLine` затем вызывает [ккоммандлинеинфо::P арсепарам](../../mfc/reference/ccommandlineinfo-class.md#parseparam) несколько раз, по одному разу для каждого параметра.

3. `ParseParam` заполняет `CCommandLineInfo` объект, который затем передается в `ProcessShellCommand` .

4. `ProcessShellCommand` обрабатывает аргументы и флаги командной строки.

Элементы данных `CCommandLineInfo` объекта, идентифицируемые [ккоммандлинеинфо:: m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), имеют следующий перечислимый тип, который определен в `CCommandLineInfo` классе.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Краткое описание каждого из этих значений см. в разделе `CCommandLineInfo::m_nShellCommand` .

## <a name="cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a> CWinApp::P Роцессвндпроцексцептион

Платформа вызывает эту функцию члена всякий раз, когда обработчик не перехватывает исключение, выдаваемое в одном из сообщений приложения или обработчиков команд.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*e*<br/>
Указатель на неперехваченное исключение.

*пмсг*<br/>
Сообщение [структуры,](/windows/win32/api/winuser/ns-winuser-msg)содержащее сведения о сообщении Windows, которое привело к созданию исключения платформой.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое должно возвращаться в Windows. Обычно это 0L для сообщений Windows, 1L (TRUE) для командных сообщений.

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию члена напрямую.

Реализация по умолчанию этой функции-члена создает окно сообщения. Если неперехваченное исключение исходит из-за сбоя команды меню, панели инструментов или сочетания клавиш, в окне сообщения отображается сообщение "ошибка команды". в противном случае отображается сообщение "Внутренняя ошибка приложения".

Переопределите эту функцию члена, чтобы обеспечить глобальную обработку исключений. Вызывайте только базовую функциональность, если нужно, чтобы окно сообщения отображалось.

## <a name="cwinappregister"></a><a name="register"></a> CWinApp:: Register

Выполняет любые задачи регистрации, не обрабатываемые `RegisterShellFileTypes` .

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию просто возвращает значение TRUE. Переопределите эту функцию для предоставления настраиваемых шагов регистрации.

## <a name="cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a> CWinApp:: RegisterShellFileTypes

Вызовите эту функцию члена, чтобы зарегистрировать все типы документов приложения с помощью диспетчера файлов Windows.

```cpp
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Параметры

*бкомпат*<br/>
окне Значение TRUE добавляет записи регистрации для команд оболочки печати и печати в, позволяя пользователю печатать файлы непосредственно из оболочки или путем перетаскивания файла в объект принтера. Он также добавляет ключ Дефаултикон. По умолчанию для обратной совместимости этот параметр имеет значение FALSE.

### <a name="remarks"></a>Примечания

Это позволяет пользователю открыть файл данных, созданный приложением, дважды щелкнув его в диспетчере файлов. Вызовите метод `RegisterShellFileTypes` после вызова [AddDocTemplate](#adddoctemplate) для каждого шаблона документа в приложении. Кроме того, при вызове вызывается функция члена [енаблешеллопен](#enableshellopen) `RegisterShellFileTypes` .

`RegisterShellFileTypes` просматривает список объектов [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) , поддерживаемых приложением, и для каждого шаблона документа добавляет в базу данных регистрации записи, которые Windows поддерживает для сопоставлений файлов. Диспетчер файлов использует эти записи, чтобы открыть файл данных, когда пользователь дважды щелкнет его. Это устраняет необходимость в поставке. Файл REG с приложением.

> [!NOTE]
> `RegisterShellFileTypes` работает, только если пользователь запускает программу с правами администратора. Если программа не имеет прав администратора, она не может изменить разделы реестра.

Если база данных регистрации уже связывает заданное расширение имени файла с другим типом файла, Новая ассоциация не создается. `CDocTemplate`Сведения о формате строк, необходимых для регистрации этих сведений, см. в разделе класс.

## <a name="cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a> CWinApp:: Регистервисрестартманажер

Регистрирует приложение в диспетчере перезапуска.

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>Параметры

*брегистеррековерикаллбакк*\
окне Значение TRUE указывает, что этот экземпляр приложения использует функцию обратного вызова восстановления. Значение FALSE указывает, что это не так. Платформа вызывает функцию обратного вызова восстановления при неожиданном завершении работы приложения. Дополнительные сведения см. в разделе [CWinApp:: аппликатионрековерикаллбакк](#applicationrecoverycallback).

*стррестартидентифиер*\
окне Уникальная строка, идентифицирующая данный экземпляр диспетчера перезапуска. Идентификатор диспетчера перезапуска уникален для каждого экземпляра приложения.

*пвзкоммандлинеаргс*\
окне Строка, содержащая любые дополнительные аргументы из командной строки.

*дврестартфлагс*\
окне Необязательные флаги для диспетчера перезапуска. Дополнительные сведения см. в разделе "Замечания".

*прековерикаллбакк*\
окне Функция обратного вызова восстановления. Эта функция должна принимать параметр ЛПВОИД в качестве входных данных и возвращать DWORD. Функция обратного вызова восстановления по умолчанию имеет значение `CWinApp::ApplicationRecoveryCallback` .

*лпвпарам*\
окне Входной параметр функции обратного вызова восстановления. Дополнительные сведения см. в разделе [CWinApp:: аппликатионрековерикаллбакк](#applicationrecoverycallback).

*двпингинтервал*\
окне Период времени, в течение которого диспетчер перезапуска ожидает возврата функции обратного вызова восстановления. Этот параметр задается в миллисекундах.

*двкаллбаккфлагс*\
окне Флаги, передаваемые функции обратного вызова восстановления. Зарезервировано для будущего использования.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод выполнен успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

Если приложение использует стандартную реализацию MFC для файлов с автосохранением, следует использовать простую версию `RegisterWithRestartManager` . Используйте сложную версию, `RegisterWithRestartManager` Если требуется настроить поведение при сохранении приложения.

При вызове этого метода с пустой строкой для *стррестартидентифиер* `RegisterWithRestartManager` создает уникальную строку идентификатора для этого экземпляра диспетчера перезапуска.

При неожиданном завершении работы приложения Диспетчер перезапуска перезапускает приложение из командной строки и предоставляет уникальный идентификатор перезапуска в качестве необязательного аргумента. В этом сценарии платформа вызывается `RegisterWithRestartManager` два раза. Первый вызов поступает от [CWinApp:: InitInstance](#initinstance) с пустой строкой для идентификатора строки. Затем метод [CWinApp::P роцессшеллкомманд](#processshellcommand) вызывается `RegisterWithRestartManager` с уникальным идентификатором перезапуска.

После регистрации приложения с помощью диспетчера перезапуска диспетчер перезапуска отслеживает приложение. Если приложение неожиданно завершает работу, диспетчер перезапуска вызывает функцию обратного вызова восстановления во время завершения процесса. Диспетчер перезапуска ожидает ответа *двпингинтервал* от функции обратного вызова восстановления. Если функция обратного вызова восстановления не отвечает в течение этого времени, приложение завершает работу без выполнения функции обратного вызова восстановления.

По умолчанию Дврестартфлагс не поддерживаются, но предоставляются для будущего использования. Ниже приведены возможные значения для *дврестартфлагс* .

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a> CWinApp:: Реопенпревиаусфилесатрестарт

Определяет, повторно ли диспетчер перезапуска открывает файлы, открытые при неожиданном завершении работы приложения.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска повторно открывает ранее открытые файлы. Значение FALSE указывает, что диспетчер перезапуска не работает.

## <a name="cwinapprestartinstance"></a><a name="restartinstance"></a> CWinApp:: Рестартинстанце

Обрабатывает перезапуск приложения, инициированный диспетчером перезапуска.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчик восстановления данных открывает ранее открытые документы; Значение FALSE, если обработчик восстановления данных содержит ошибку или если ранее открытые документы отсутствуют.

### <a name="remarks"></a>Примечания

Когда диспетчер перезапуска перезапускает приложение, платформа вызывает этот метод. Этот метод получает обработчик восстановления данных и восстанавливает автоматически сохраненные файлы. Этот метод вызывает [кдатарековерихандлер:: рестореаутосаведдокументс](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) , чтобы определить, желаете ли пользователь восстановить автоматически сохраненные файлы.

Этот метод возвращает значение FALSE, если [кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md) определяет отсутствие открытых документов. Если открытых документов нет, приложение запускается обычно.

## <a name="cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a> CWinApp:: Рестореаутосаведфилесатрестарт

Определяет, восстанавливает ли диспетчер перезапуска автоматически сохраненные файлы при перезапуске приложения.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска восстанавливает автоматически сохраненные файлы. Значение FALSE указывает, что диспетчер перезапуска не работает.

## <a name="cwinapprun"></a><a name="run"></a> CWinApp:: Run

Предоставляет цикл обработки сообщений по умолчанию.

```
virtual int Run();
```

### <a name="return-value"></a>Возвращаемое значение

**`int`** Значение, возвращаемое методом `WinMain` .

### <a name="remarks"></a>Примечания

`Run` получение и отправка сообщений Windows до тех пор, пока приложение не получит WM_QUIT сообщение. Если очередь сообщений приложения в настоящий момент не содержит сообщений, `Run` вызывает [OnIdle](#onidle) для выполнения обработки во время простоя. Входящие сообщения переходят в функцию-член [претранслатемессаже](#pretranslatemessage) для специальной обработки, а затем в функцию Windows `TranslateMessage` для стандартного перевода с клавиатуры; наконец, `DispatchMessage` вызывается функция Windows.

`Run` параметр редко переопределяется, но его можно переопределить, чтобы обеспечить специальное поведение.

## <a name="cwinapprunautomated"></a><a name="runautomated"></a> CWinApp:: Рунаутоматед

Вызовите эту функцию, чтобы определить, имеется ли параметр " **/Automation**" или " **-Automation**", указывающий, было ли серверное приложение запущено клиентским приложением.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если параметр был найден; в противном случае — 0.

### <a name="remarks"></a>Примечания

При наличии параметра удаляется из командной строки. Дополнительные сведения о OLE Automation см. в статье [серверы автоматизации](../../mfc/automation-servers.md).

## <a name="cwinapprunembedded"></a><a name="runembedded"></a> CWinApp:: Рунембеддед

Вызовите эту функцию, чтобы определить, имеется ли параметр " **параметром/Embedding**" или " **-встраивание**", указывающий, было ли серверное приложение запущено клиентским приложением.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если параметр был найден; в противном случае — 0.

### <a name="remarks"></a>Примечания

При наличии параметра удаляется из командной строки. Дополнительные сведения о внедрении см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).

## <a name="cwinappsaveallmodified"></a><a name="saveallmodified"></a> CWinApp:: Савеаллмодифиед

Вызывается платформой для сохранения всех документов при закрытии окна главного фрейма приложения или при помощи сообщения WM_QUERYENDSESSION.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если в целях безопасности можно завершить работу приложения; 0, если не удается завершить работу приложения.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции члена вызывает функцию члена [CDocument:: савемодифиед](../../mfc/reference/cdocument-class.md#savemodified) , в свою очередь, для всех измененных документов в приложении.

## <a name="cwinappselectprinter"></a><a name="selectprinter"></a> CWinApp:: Селектпринтер

Вызовите эту функцию-член, чтобы выбрать конкретный принтер и освободить принтер, выбранный ранее в диалоговом окне Печать.

```cpp
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Параметры

*хдевнамес*<br/>
Описатель [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)структуры, который определяет имена драйверов, устройств и выходных портов конкретного принтера.

*хдевмоде*<br/>
Маркер структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , указывающий сведения об инициализации устройства и среде принтера.

*бфриолд*<br/>
Освобождает выбранный ранее принтер.

### <a name="remarks"></a>Примечания

Если оба *хдевмоде* и *хдевнамес* имеют значение null, `SelectPrinter` использует текущий принтер по умолчанию.

## <a name="cwinappsethelpmode"></a><a name="sethelpmode"></a> CWinApp:: Сеселпмоде

Задает тип справки приложения.

```cpp
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Параметры

*ехелптипе*<br/>
Указывает тип справки для использования. Дополнительные сведения см. в разделе [CWinApp:: m_eHelpType](#m_ehelptype) .

### <a name="remarks"></a>Примечания

Задает тип справки приложения.

Чтобы задать для приложения тип справки HTMLHelp, можно вызвать [енаблехтмлхелп](#enablehtmlhelp). После вызова `EnableHTMLHelp` приложение должно использовать HTMLHelp в качестве справочного приложения. Если вы хотите изменить для использования WinHelp, можно вызвать метод `SetHelpMode` и установить для *ехелптипе* значение `afxWinHelp` .

## <a name="cwinappsetregistrykey"></a><a name="setregistrykey"></a> CWinApp:: Сетрегистрикэй

Приводит к сохранению параметров приложения в реестре вместо INI-файлов.

```cpp
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Параметры

*лпсзрегистрикэй*<br/>
Указатель на строку, содержащую имя ключа.

*нидрегистрикэй*<br/>
Идентификатор строкового ресурса, содержащего имя раздела реестра.

### <a name="remarks"></a>Примечания

Эта функция задает *m_pszRegistryKey*, которая затем используется `GetProfileInt` функциями-членами, `GetProfileString` , `WriteProfileInt` и `WriteProfileString` `CWinApp` . Если эта функция вызвана, список недавно использовавшихся файлов также сохраняется в реестре. Раздел реестра обычно является именем компании. Он хранится в виде ключа следующей формы: HKEY_CURRENT_USER \Софтваре \\<название компании \> \\<имя приложения \> \\<раздел имя \> \\<значение имя \> .

## <a name="cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a> CWinApp:: Суппортсаппликатионрековери

Определяет, восстанавливает ли диспетчер перезапуска приложение, которое неожиданно завершило работу.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска восстанавливает приложение. Значение FALSE указывает, что диспетчер перезапуска не работает.

## <a name="cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a> CWinApp:: Суппортсаутосавеатинтервал

Определяет, будет ли диспетчер перезапуска автоматически сохранять открытые документы через равные промежутки времени.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска автоматически сохраняет открытые документы. Значение FALSE указывает, что диспетчер перезапуска не работает.

## <a name="cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a> CWinApp:: Суппортсаутосавеатрестарт

Определяет, будет ли диспетчер перезапуска автоматически сохранять все открытые документы при перезапуске приложения.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска автоматически сохраняет открытые документы при перезапуске приложения. Значение FALSE указывает, что диспетчер перезапуска не работает.

## <a name="cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a> CWinApp:: Суппортсрестартманажер

Определяет, поддерживает ли приложение Диспетчер перезапуска.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что приложение поддерживает диспетчер перезапуска; Значение FALSE указывает, что приложение не поддерживает.

## <a name="cwinappunregister"></a><a name="unregister"></a> CWinApp:: Отмена регистрации

Отменяет регистрацию всех файлов, зарегистрированных в объекте приложения.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

`Unregister`Функция отменяет регистрацию, выполненную объектом Application, и функцией [Register](#register) . Как правило, обе функции вызываются неявно библиотекой MFC и поэтому не будут отображаться в коде.

Переопределите эту функцию, чтобы выполнить пользовательские действия отмены регистрации.

## <a name="cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a> CWinApp:: Унрегистершеллфилетипес

Вызовите эту функцию члена, чтобы отменить регистрацию всех типов документов приложения с помощью диспетчера файлов Windows.

```cpp
void UnregisterShellFileTypes();
```

## <a name="cwinappwinhelp"></a><a name="winhelp"></a> CWinApp:: WinHelp

Вызовите эту функцию члена для вызова приложения WinHelp.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Параметры

*двдата*<br/>
Указывает дополнительные данные. Используемое значение зависит от значения параметра *нкмд* .

*нкмд*<br/>
Задает тип запрошенной справки. Список возможных значений и их влияние на параметр *двдата* см. в описании функции Windows [WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) .

### <a name="remarks"></a>Примечания

Платформа также вызывает эту функцию для вызова приложения WinHelp.

Платформа автоматически закроет приложение WinHelp после завершения работы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

## <a name="cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a> CWinApp:: Вритепрофилебинари

Вызывайте эту функцию члена для записи двоичных данных в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись. Если раздел не существует, он будет создан. Имя раздела зависит от регистра. Строка может быть любым сочетанием прописных и строчных букв.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, в которую должно быть записано значение. Если запись не существует в указанном разделе, она будет создана.

*pData*<br/>
Указывает на данные, которые необходимо записать.

*nBytes*<br/>
Содержит число записываемых байтов.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

В этом примере используется `CWinApp* pApp = AfxGetApp();` для получения класса CWinApp, иллюстрирующий способ, который `WriteProfileBinary` `GetProfileBinary` можно использовать из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Другой пример см. в примере для [CWinApp:: жетпрофилебинари](#getprofilebinary).

## <a name="cwinappwriteprofileint"></a><a name="writeprofileint"></a> CWinApp:: Вритепрофилеинт

Вызовите эту функцию члена, чтобы записать указанное значение в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись. Если раздел не существует, он будет создан. Имя раздела зависит от регистра. Строка может быть любым сочетанием прописных и строчных букв.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, в которую должно быть записано значение. Если запись не существует в указанном разделе, она будет создана.

*Nзначение*<br/>
Содержит записываемое значение.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

В этом примере используется `CWinApp* pApp = AfxGetApp();` , чтобы получить класс CWinApp, иллюстрирующий способ,, и, который `WriteProfileString` `WriteProfileInt` `GetProfileString` `GetProfileInt` можно использовать из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример см. в примере для [CWinApp:: жетпрофилеинт](#getprofileint).

## <a name="cwinappwriteprofilestring"></a><a name="writeprofilestring"></a> CWinApp:: Вритепрофилестринг

Вызовите эту функцию члена, чтобы записать указанную строку в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Параметры

*лпсзсектион*<br/>
Указывает на строку, завершающуюся нулем, которая указывает раздел, содержащий запись. Если раздел не существует, он будет создан. Имя раздела зависит от регистра. Строка может быть любым сочетанием прописных и строчных букв.

*лпсзентри*<br/>
Указывает на строку, завершающуюся нулем, которая содержит запись, в которую должно быть записано значение. Если запись не существует в указанном разделе, она будет создана. Если этот параметр имеет значение NULL, то раздел, заданный параметром *лпсзсектион* , удаляется.

*лпсзвалуе*<br/>
Указывает на строку, которая должна быть записана. Если этот параметр имеет значение NULL, то запись, указанная параметром *лпсзентри* , удаляется.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример см. в примере для [CWinApp:: жетпрофилеинт](#getprofileint).

## <a name="cwinappsetappid"></a><a name="setappid"></a> CWinApp:: Сетаппид

Явно задает идентификатор модели пользователя приложения. Этот метод должен вызываться перед тем, как пользовательский интерфейс будет представлен пользователю (лучшим местом является конструктор приложения).

```cpp
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Параметры

*лпксзаппид*<br/>
Указывает идентификатор модели пользователя приложения.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Класс CWinThread](../../mfc/reference/cwinthread-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Как добавить поддержку диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)
