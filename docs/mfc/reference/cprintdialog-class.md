---
title: Класс CPrintDialog
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: 6490e5488c5ab3b808a02e3608b75541e4063d8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364066"
---
# <a name="cprintdialog-class"></a>Класс CPrintDialog

Инкапсулирует службы, предоставляемые стандартным диалоговым окном Windows для печати.

## <a name="syntax"></a>Синтаксис

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Формирует объект `CPrintDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна Print.|
|[CPrintDialog::DoModal](#domodal)|Отображает диалоговую коробку и позволяет пользователю сделать выбор.|
|[CPrintDialog::GetCopies](#getcopies)|Извлекает количество запрошенных копий.|
|[CPrintDialog::GetDefaults](#getdefaults)|Извлекает устройство по умолчанию без отображения диалогового окна.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Извлекает имя выбранного в настоящее время устройства принтера.|
|[CPrintDialog::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуру.|
|[CPrintDialog::GetDriverName](#getdrivername)|Извлекает имя выбранного в настоящее время драйвера принтера.|
|[CPrintDialog:GetFromPage](#getfrompage)|Извлекает начальную страницу диапазона печати.|
|[CPrintDialog::GetPortName](#getportname)|Извлекает название выбранного в настоящее время порта принтера.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Извлекает ручку в контекст устройства принтера.|
|[КпечатнтДиалог:GetToPage](#gettopage)|Извлекает завершающую страницу диапазона печати.|
|[CPrintDialog::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|
|[CPrintDialog::PrintCollate](#printcollate)|Определяет, запрашиваются ли собранные копии.|
|[CPrintDialog::PrintRange](#printrange)|Определяет, следует ли печатать только определенный диапазон страниц.|
|[CPrintDialog::PrintВыбор](#printselection)|Определяет, следует ли печатать только выбранные в настоящее время элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Структура, используемая для `CPrintDialog` настройки объекта.|

## <a name="remarks"></a>Примечания

Общие печатные диалоговые ящики обеспечивают простой способ реализации диалоговых коробок print и Print Setup в соответствии со стандартами Windows.

> [!NOTE]
> Класс `CPrintDialogEx` инкапсулирует услуги, предоставляемые листом свойств Windows Print. Для получения дополнительной информации смотрите обзор [CPrintDialogEx.](../../mfc/reference/cprintdialogex-class.md)

`CPrintDialog`функциональность 'S заменена [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), которая предназначена для предоставления вам общего диалогового окна как для настройки печати, так и для настройки страницы.

Вы можете положиться на рамки для обработки многих аспектов процесса печати для вашего приложения. В этом случае фреймворк автоматически отображает общий диалоговый ящик Windows для печати. Вы также можете иметь рамочной ручкой печати для вашего приложения, но переопределить общий журнал печати поле с вашей собственной печати диалогового окна. Для получения дополнительной информации об использовании платформы для обработки задач печати см. [Printing](../../mfc/printing.md)

Если вы хотите, чтобы ваше приложение обрабатывало печать без `CPrintDialog` участия фреймворка, вы можете использовать класс «как `CPrintDialog` есть» с предоставленным конструктором, или вы можете получить свой собственный класс диалога и написать конструктор в соответствии с вашими потребностями. В любом случае, эти диалоговые коробки будут вести себя как стандартные диалоговые коробки MFC, потому что они получены из класса. `CCommonDialog`

Чтобы использовать `CPrintDialog` объект, сначала создайте `CPrintDialog` объект с помощью конструктора. После построения диалогового окна можно установить или изменить любые значения в структуре [m_pd](#m_pd) для инициализации значений элементов управления диалогового окна. Структура `m_pd` типа [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga). Для получения дополнительной информации об этой структуре см.

Если вы не поставляете свои `m_pd` собственные `hDevMode` `hDevNames` ручки для и членов, `GlobalFree` не забудьте позвонить функции Windows для этих ручки, когда вы закончите с диалогового окна. При использовании предоставленной инфраструктурой реализации `CWinApp::OnFilePrintSetup`настройки печати вам не нужно освобождать эти ручки. Ручки поддерживаются `CWinApp` и освобождаются `CWinApp`в деструкторе. Это только необходимо, чтобы освободить `CPrintDialog` эти ручки при использовании автономных.

После инициализации элементов `DoModal` управления диалоговым полем позвоните функции участника для отображения диалогового окна и позвольте пользователю выбрать параметры печати. `DoModal`возвращает сярот, выбрал ли пользователь кнопку OK (IDOK) или «Отменить» (IDCANCEL).

При `DoModal` возврате IDOK можно `CPrintDialog`использовать одну из функций участника для получения информации, вводимых пользователем.

Функция `CPrintDialog::GetDefaults` члена полезна для извлечения текущего принтера по умолчанию без отображения диалогового окна. Эта функция члена не требует взаимодействия с пользователем.

Вы можете использовать `CommDlgExtendedError` функцию Windows, чтобы определить, произошла ли ошибка во время инициализации диалогового окна, и узнать больше об ошибке. Для получения дополнительной информации об этой функции, см.

`CPrintDialog`опирается на COMMDLG. DLL файл, который поставляется с версиями Windows 3.1 и позже.

Чтобы настроить диалоговое окно, вывежьте класс из, `CPrintDialog`предоставьте пользовательский шаблон диалогов и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться базовому классу. Настройка функции крючка не требуется.

Чтобы обрабатывать одно и то же сообщение по-разному в зависимости от того, является ли диалоговое поле Print или Print Setup, необходимо получить класс для каждого диалогового окна. Необходимо также переопределить `AttachOnSetup` функцию Windows, которая обрабатывает создание нового диалогового окна при выборе кнопки настройки печати в поле диалога Print.

Для получения дополнительной `CPrintDialog`информации об использовании см. [Common Dialog Classes](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cprintdialogcprintdialog"></a><a name="cprintdialog"></a>CPrintDialog::CPrintDialog

Строит либо объект диалога Windows Print, либо Print Setup.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*bPrintSetupТолько*<br/>
Уточняется, отображается ли стандартный диалоговый ящик Windows Print или диалоговая коробка Print Setup. Установите этот параметр для отображения стандартного диалогового окна Windows Print Setup. Установите его на FALSE для отображения диалогового окна Windows Print. Если *bPrintSetupТолько* FALSE, кнопка настройки печати по-прежнему отображается в диалоговом поле Print.

*dwFlags*<br/>
Один или несколько флагов можно использовать для настройки настроек диалогового окна, объединенных с помощью оператора bitwise OR. Например, PD_ALLPAGES флаг устанавливает диапазон печати по умолчанию на всех страницах документа. Дополнительную информацию об этих флагах можно узнать о структуре [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) в SDK Windows.

*pParentWnd*<br/>
Указатель на родительское или владельца окна диалогового окна.

### <a name="remarks"></a>Примечания

Эта функция члена только строит объект. Используйте `DoModal` функцию участника для отображения диалогового окна.

Обратите внимание, что при вызове конструктора с *bPrintSetupТолько* настроенный на FALSE, PD_RETURNDC флаг автоматически используется. После `DoModal`вызова, `GetDefaults` `GetPrinterDC`или , принтер DC `m_pd.hDC`будет возвращен в . Этот DC должен быть освобожден с вызовом [deleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) абонентом `CPrintDialog`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

## <a name="cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES.](/windows/win32/api/commdlg/ns-commdlg-devnames)

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработка к недавно созданному контексту устройства принтера.

### <a name="remarks"></a>Примечания

Этот DC считается текущим dc принтера, и любые другие ранее полученные D-интерфейсы принтера должны быть удалены пользователем. Эта функция может быть вызвана, и в результате DC используется, даже не отображая печать диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

## <a name="cprintdialogdomodal"></a><a name="domodal"></a>CPrintDialog::DoModal

Отображает общий диалоговый ящик Печати Windows и позволяет пользователю выбирать различные варианты печати, такие как количество копий, диапазон страниц и следует ли собирать копии.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL. Если IDCANCEL возвращается, позвоните в функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константами, указывающими на то, выбрал ли пользователь кнопку OK или Cancel.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные параметры `m_pd` диалога печати, установив члены структуры, вы должны сделать это до вызова, `DoModal`но после построения объекта диалога.

После `DoModal`вызова можно вызвать другие функции участника, чтобы получить настройки или ввод информации пользователем в диалоговую будку.

Обратите внимание, что при вызове конструктора с *bPrintSetupТолько* настроенный на FALSE, PD_RETURNDC флаг автоматически используется. После `DoModal`вызова, `GetDefaults` `GetPrinterDC`или , принтер DC `m_pd.hDC`будет возвращен в . Этот DC должен быть освобожден с вызовом [deleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) абонентом `CPrintDialog`.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::CreatePrinterDC](#createprinterdc).

## <a name="cprintdialoggetcopies"></a><a name="getcopies"></a>CPrintDialog::GetCopies

Извлекает количество запрошенных копий.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество запрошенных копий.

### <a name="remarks"></a>Примечания

Вызовите эту `DoModal` функцию после вызова, чтобы получить количество запрошенных копий.

### <a name="example"></a>Пример

  Смотрите пример [CPrintDialog: :PrintCollate](#printcollate).

## <a name="cprintdialoggetdefaults"></a><a name="getdefaults"></a>CPrintDialog::GetDefaults

Извлекает устройство по умолчанию принтера по умолчанию без отображения диалогового окна.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Извлеченные значения помещаются `m_pd` в структуру.

В некоторых случаях вызов к этой [constructor](#cprintdialog) функции `CPrintDialog` вызовет конструктор для с *bPrintSetupТолько* настроенный на FALSE. В этих случаях автоматически `hDevNames` выделяется DC принтера и `hDevMode` (две ручки, `m_pd` расположенные в члене данных).

Если конструктор был `CPrintDialog` вызван с *bPrintSetupТолько* установленный на FALSE, `hDevNames` `hDevMode` эта `m_pd.hDevNames` функция `m_pd.hDevMode`будет не только вернуться и расположен `m_pd.hDC`в и ) к абоненту, но также будет возвращать принтер DC в . Абонент несет ответственность за удаление DC принтера и вызов функции Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) на ручках, когда вы закончите с объектом. `CPrintDialog`

### <a name="example"></a>Пример

Этот фрагмент кода получает контекст устройства принтера по умолчанию и сообщает пользователю разрешение принтера в точках на дюйм. (Этот атрибут возможностей принтера часто называют DPI.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

## <a name="cprintdialoggetdevicename"></a><a name="getdevicename"></a>CPrintDialog::GetDeviceName

Извлекает имя выбранного в настоящее время устройства принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название выбранного в настоящее время принтера.

### <a name="remarks"></a>Примечания

Вызов истечения этой функции после вызова [DoModal](#domodal) для получения имени выбранного в настоящее время принтера или после вызова [GetDefaults](#getdefaults) для получения текущего устройства по умолчанию принтера по умолчанию. Используйте указатель `CString` на объект, `GetDeviceName` возвращенный `lpszDeviceName` в качестве значения в вызове в [CDC:CreateDC.](../../mfc/reference/cdc-class.md#createdc)

### <a name="example"></a>Пример

Этот фрагмент кода показывает имя принтера пользователя по умолчанию и порт, к которому он подключен, а также имя spooler, которое использует принтер. В коде может отображаться окно сообщений, в которое \\говорится: «Ваш принтер по умолчанию — это HP LaserJet IIIP на «сервере»- и использовании winspool».

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

## <a name="cprintdialoggetdevmode"></a><a name="getdevmode"></a>CPrintDialog::GetDevMode

Извлекает `DEVMODE` структуру.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE,](/windows/win32/api/wingdi/ns-wingdi-devmodea) содержащая информацию о инициализации устройства и среде драйвера печати. Вы должны разблокировать память, взятую этой структурой, с помощью функции Windows [GlobalUnlock,](/windows/win32/api/winbase/nf-winbase-globalunlock) описанной в SDK Windows.

### <a name="remarks"></a>Примечания

Позвоните в эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить информацию о печатном устройстве.

### <a name="example"></a>Пример

  Смотрите пример [CPrintDialog: :PrintCollate](#printcollate).

## <a name="cprintdialoggetdrivername"></a><a name="getdrivername"></a>CPrintDialog::GetDriverName

Извлекает имя выбранного в настоящее время драйвера принтера.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указание `CString` системного имени драйвера.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить имя драйвера устройства принтера, определяемого системой. Используйте указатель `CString` на объект, `GetDriverName` возвращенный `lpszDriverName` в качестве значения в вызове в [CDC:CreateDC.](../../mfc/reference/cdc-class.md#createdc)

### <a name="example"></a>Пример

  Смотрите пример [для CPrintDialog::GetDeviceName](#getdevicename).

## <a name="cprintdialoggetfrompage"></a><a name="getfrompage"></a>CPrintDialog:GetFromPage

Извлекает начальную страницу диапазона печати.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер стартовой страницы в диапазоне страниц, которые будут напечатаны.

### <a name="remarks"></a>Примечания

Вызов исчисляй эту функцию после вызова, `DoModal` чтобы получить номер стартовой страницы в диапазоне страниц, которые будут напечатаны.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::m_pd](#m_pd).

## <a name="cprintdialoggetportname"></a><a name="getportname"></a>CPrintDialog::GetPortName

Извлекает название выбранного в настоящее время порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название выбранного в настоящее время порта принтера.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить имя выбранного в настоящее время порта принтера.

### <a name="example"></a>Пример

  Смотрите пример [для CPrintDialog::GetDeviceName](#getdevicename).

## <a name="cprintdialoggetprinterdc"></a><a name="getprinterdc"></a>CPrintDialog::GetPrinterDC

Извлекает ручку в контекст устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к контексту устройства принтера в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если *параметр bPrintSetupТолько* конструктор `CPrintDialog` был FALSE (указывая на отображение диалогового окна Print), то `GetPrinterDC` возвращает ручку в контекст устройства принтера. Вы должны вызвать функцию Windows [DeleteDC,](/windows/win32/api/wingdi/nf-wingdi-deletedc) чтобы удалить контекст устройства, когда вы закончите использовать его.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

## <a name="cprintdialoggettopage"></a><a name="gettopage"></a>КпечатнтДиалог:GetToPage

Извлекает завершающую страницу диапазона печати.

```
int GetToPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер конечной страницы в диапазоне страниц, которые должны быть напечатаны.

### <a name="remarks"></a>Примечания

Вызов исчисляй эту функцию после вызова, `DoModal` чтобы получить номер конечной страницы в диапазоне страниц, которые будут напечатаны.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::m_pd](#m_pd).

## <a name="cprintdialogm_pd"></a><a name="m_pd"></a>CPrintDialog::m_pd

Структура, члены которой хранят характеристики объекта диалога.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Примечания

После построения `CPrintDialog` объекта можно `m_pd` использовать различные аспекты диалогового окна, прежде чем вызывать функцию члена [DoModal.](#domodal) Для получения дополнительной `m_pd` информации о структуре, см. [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) в Windows SDK.

Если вы `m_pd` измените напрямую данный, вы отмените любое поведение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

## <a name="cprintdialogprintall"></a><a name="printall"></a>CPrintDialog::PrintAll

Определяет, следует ли печатать все страницы документа.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если все страницы в документе должны быть напечатаны; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать все страницы в документе.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::m_pd](#m_pd).

## <a name="cprintdialogprintcollate"></a><a name="printcollate"></a>CPrintDialog::PrintCollate

Определяет, запрашиваются ли собранные копии.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь выбирает ящик для проверки в диалоговом поле; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, должен ли принтер сопоставлять все печатные копии документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

## <a name="cprintdialogprintrange"></a><a name="printrange"></a>CPrintDialog::PrintRange

Определяет, следует ли печатать только определенный диапазон страниц.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если только диапазон страниц в документе должны быть напечатаны; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать только диапазон страниц в документе.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::m_pd](#m_pd).

## <a name="cprintdialogprintselection"></a><a name="printselection"></a>CPrintDialog::PrintВыбор

Определяет, следует ли печатать только выбранные в настоящее время элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если только выбранные элементы должны быть напечатаны; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать только выбранные в настоящее время элементы.

### <a name="example"></a>Пример

  Смотрите пример [Для CPrintDialog::m_pd](#m_pd).

## <a name="see-also"></a>См. также раздел

[MFC Образец DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
