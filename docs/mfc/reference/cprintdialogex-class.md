---
title: Класс CPrintDialogEx
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 52e992cf021a592198daeddf0a4321fcea487f72
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364032"
---
# <a name="cprintdialogex-class"></a>Класс CPrintDialogEx

Инкапсулирует услуги, предоставляемые листом недвижимости Windows Print.

## <a name="syntax"></a>Синтаксис

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Формирует объект `CPrintDialogEx`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна Print.|
|[CPrintDialogEx::DoModal](#domodal)|Отображает диалоговую коробку и позволяет пользователю делать выбор.|
|[CPrintDialogEx::GetCopies](#getcopies)|Извлекает количество запрошенных копий.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Извлекает устройство по умолчанию без отображения диалогового окна.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Извлекает имя выбранного в настоящее время устройства принтера.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуру.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Извлекает имя драйвера устройства принтера, определяемого системой.|
|[CPrintDialogEx::GetPortName](#getportname)|Извлекает название выбранного в настоящее время порта принтера.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Извлекает ручку в контекст устройства принтера.|
|[CPrintDialogEx::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Определяет, запрашиваются ли собранные копии.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Определяет, следует ли печатать текущую страницу документа.|
|[CPrintDialogEx::PrintRange](#printrange)|Определяет, следует ли печатать только определенный диапазон страниц.|
|[CPrintDialogEx::PrintВыбор](#printselection)|Определяет, следует ли печатать только выбранные в настоящее время элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPrintDialogEx:::m_pdex](#m_pdex)|Структура, используемая для `CPrintDialogEx` настройки объекта.|

## <a name="remarks"></a>Примечания

Вы можете положиться на рамки для обработки многих аспектов процесса печати для вашего приложения. Для получения дополнительной информации об использовании платформы для обработки задач печати см. [Printing](../../mfc/printing.md)

Если вы хотите, чтобы ваше приложение обрабатывало печать без `CPrintDialogEx` участия фреймворка, вы можете использовать класс «как `CPrintDialogEx` есть» с предоставленным конструктором, или вы можете получить свой собственный класс диалога и написать конструктор в соответствии с вашими потребностями. В любом случае, эти диалоговые коробки будут вести себя как стандартные диалоговые коробки MFC, потому что они получены из класса. `CCommonDialog`

Чтобы использовать `CPrintDialogEx` объект, сначала создайте `CPrintDialogEx` объект с помощью конструктора. После построения диалогового окна можно установить или изменить любые значения в структуре [m_pdex](#m_pdex) для инициализации значений элементов управления диалогового окна. Структура `m_pdex` типа [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw). Для получения дополнительной информации об этой структуре см.

Если вы не поставляете свои `m_pdex` собственные `hDevMode` `hDevNames` ручки для и членов, `GlobalFree` не забудьте позвонить функции Windows для этих ручки, когда вы закончите с диалогового окна.

После инициализации элементов `DoModal` управления диалоговым полем позвоните функции участника для отображения диалогового окна и позвольте пользователю выбрать параметры печати. При `DoModal` возврате можно определить, выбрал ли пользователь кнопку OK, Apply или Cancel.

Если пользователь нажал OK, `CPrintDialogEx`вы можете использовать функции члена 's для получения информации, вводимых пользователем.

Функция `CPrintDialogEx::GetDefaults` члена полезна для извлечения текущего принтера по умолчанию без отображения диалогового окна. Этот метод не требует взаимодействия с пользователем.

Вы можете использовать `CommDlgExtendedError` функцию Windows, чтобы определить, произошла ли ошибка во время инициализации диалогового окна, и узнать больше об ошибке. Для получения дополнительной информации об этой функции, см.

Для получения дополнительной `CPrintDialogEx`информации об использовании см. [Common Dialog Classes](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx

Строит лист свойств Windows Print.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов можно использовать для настройки настроек диалогового окна, объединенных с помощью оператора bitwise OR. Например, PD_ALLPAGES флаг устанавливает диапазон печати по умолчанию на всех страницах документа. Дополнительную информацию об этих флагах можно узнать о структуре [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) в SDK Windows.

*pParentWnd*<br/>
Указатель на родительское или владельца окна диалогового окна.

### <a name="remarks"></a>Примечания

Эта функция члена только строит объект. Используйте `DoModal` функцию участника для отображения диалогового окна.

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES.](/windows/win32/api/commdlg/ns-commdlg-devnames)

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработка к недавно созданному контексту устройства принтера.

### <a name="remarks"></a>Примечания

Возвращенный DC также хранится в члене `hDC` [m_pdex.](#m_pdex)

Этот DC считается текущим DC принтером, и любые другие ранее полученные DCS принтера должны быть удалены. Эта функция может быть вызвана, и в результате DC используется, даже не отображая печать диалогового окна.

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal

Вызовите эту функцию для отображения листа свойств Windows Print и позвольте пользователю выбрать различные варианты печати, такие как количество копий, диапазон страниц и следует ли собирать копии.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Значение возврата INT_PTR на самом деле является HRESULT. Смотрите раздел "Значения возврата" в [разделе PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) в SDK windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные параметры `m_pdex` диалога печати, установив члены структуры, вы должны сделать это до вызова, `DoModal`но после построения объекта диалога.

После `DoModal`вызова можно вызвать другие функции участника, чтобы получить настройки или ввод информации пользователем в диалоговую будку.

Если при вызове `DoModal`используется PD_RETURNDC флаг, принтер DC `hDC` будет возвращен в член [m_pdex.](#m_pdex) Этот DC должен быть освобожден с вызовом [deleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) абонентом `CPrintDialogEx`.

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::GetCopies

Вызовите эту `DoModal` функцию после вызова, чтобы получить количество запрошенных копий.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество запрошенных копий.

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults

Вызов ими функции для извлечения устройства по умолчанию принтера по умолчанию без отображения диалогового окна.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА в случае успеха, в противном случае FALSE.

### <a name="remarks"></a>Примечания

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES.](/windows/win32/api/commdlg/ns-commdlg-devnames)

`GetDefaults`не отображается лист свойства печати. Вместо этого он `hDevNames` `hDevMode` устанавливает и членов [m_pdex](#m_pdex) для обработки конструкций [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES,](/windows/win32/api/commdlg/ns-commdlg-devnames) которые инициализированы для принтера системы по умолчанию. Оба `hDevNames` `hDevMode` и должны быть `GetDefaults` NULL, или не.

Если PD_RETURNDC флаг установлен, эта функция `hDevNames` не `hDevMode` только `m_pdex.hDevNames` вернется `m_pdex.hDevMode`и (находится в и) вызывающему, но также вернет принтер DC в `m_pdex.hDC`. Абонент несет ответственность за удаление DC принтера и вызов функции Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) на ручках, когда вы закончите с объектом. `CPrintDialogEx`

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName

Вызов исчерпав эту функцию после вызова [DoModal,](#domodal) чтобы получить имя выбранного в настоящее время принтера, или после вызова [GetDefaults,](#getdefaults) чтобы получить имя принтера по умолчанию.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название выбранного в настоящее время принтера.

### <a name="remarks"></a>Примечания

Используйте указатель `CString` на объект, `GetDeviceName` возвращенный `lpszDeviceName` в качестве значения в вызове в [CDC:CreateDC.](../../mfc/reference/cdc-class.md#createdc)

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode

Позвоните в эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить информацию о печатном устройстве.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE,](/windows/win32/api/wingdi/ns-wingdi-devmodea) содержащая информацию о инициализации устройства и среде драйвера печати. Вы должны разблокировать память, взятую этой структурой, с помощью функции Windows [GlobalUnlock,](/windows/win32/api/winbase/nf-winbase-globalunlock) описанной в SDK Windows.

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName

Вызов исчерпав эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить имя драйвера устройства принтера, определяемого системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указание `CString` системного имени драйвера.

### <a name="remarks"></a>Примечания

Используйте указатель `CString` на объект, возвращенный `GetDriverName` в качестве значения *lpszDrivername* в вызове [в CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName

Вызов исчерпав эту функцию после вызова [DoModal](#domodal) или [GetDefaults,](#getdefaults) чтобы получить имя выбранного в настоящее время порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название выбранного в настоящее время порта принтера.

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC

Возвращает ручку в контекст устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка контекста устройства принтера.

### <a name="remarks"></a>Примечания

Вы должны вызвать функцию Windows [DeleteDC,](/windows/win32/api/wingdi/nf-wingdi-deletedc) чтобы удалить контекст устройства, когда вы закончите использовать его.

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a>CPrintDialogEx:::m_pdex

Структура PRINTDLGEX, члены которой хранят характеристики объекта диалога.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Примечания

После построения `CPrintDialogEx` объекта можно `m_pdex` использовать различные аспекты диалогового окна, прежде чем вызывать функцию члена [DoModal.](#domodal) Более подробную `m_pdex` информацию о структуре [можно](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) опереть в SDK для Windows.

Если вы `m_pdex` измените напрямую данный, вы отмените любое поведение по умолчанию.

## <a name="cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать все страницы в документе.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если все страницы в документе должны быть напечатаны; в противном случае FALSE.

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, должен ли принтер сопоставлять все печатные копии документа.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если пользователь выбирает сборный флажок в диалоговом поле; в противном случае FALSE.

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли распечатать текущую страницу в документе.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если **печатная текущая страница** выбрана в диалоге печати; в противном случае FALSE.

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать только диапазон страниц в документе.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если только диапазон страниц в документе должны быть напечатаны; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Указанные диапазоны страниц можно определить `nPageRanges`из `nMaxPageRanges` `lpPageRanges` [m_pdex](#m_pdex) (см. , и в структуре [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) в Windows SDK).

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintВыбор

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы определить, следует ли печатать только выбранные в настоящее время элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если только выбранные элементы должны быть напечатаны; в противном случае FALSE.

## <a name="see-also"></a>См. также раздел

[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
