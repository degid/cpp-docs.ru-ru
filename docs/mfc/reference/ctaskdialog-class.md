---
title: CTaskDialog Class
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: 3fd67eed7e80a2e594710df8ae8bc6fd13f0e96c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837675"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

Всплывающее диалоговое окно, которое функционирует как окно сообщения, но может отображать дополнительные сведения для пользователя. `CTaskDialog` также включает функции для получения сведений от пользователя.

## <a name="syntax"></a>Синтаксис

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[CTaskDialog:: CTaskDialog](#ctaskdialog)|Формирует объект `CTaskDialog`.|

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[CTaskDialog:: Аддкоммандконтрол](#addcommandcontrol)|Добавляет элемент управления «кнопка» в `CTaskDialog` .|
|[CTaskDialog:: AddRadioButton](#addradiobutton)|Добавляет переключатель в `CTaskDialog` .|
|[CTaskDialog:: Кликккоммандконтрол](#clickcommandcontrol)|Программно нажимает на командную кнопку или общую кнопку.|
|[CTaskDialog:: Кликкрадиобуттон](#clickradiobutton)|Программно щелкает переключатель.|
|[CTaskDialog::D Омодал](#domodal)|Отображает `CTaskDialog`.|
|[CTaskDialog:: Жеткоммонбуттонкаунт](#getcommonbuttoncount)|Получает количество доступных общих кнопок.|
|[CTaskDialog:: Жеткоммонбуттонфлаг](#getcommonbuttonflag)|Преобразует стандартную кнопку Windows в общий тип кнопки, связанный с `CTaskDialog` классом.|
|[CTaskDialog:: Жеткоммонбуттонид](#getcommonbuttonid)|Преобразует один из типов общих кнопок, связанных с `CTaskDialog` классом, в стандартную кнопку Windows.|
|[CTaskDialog:: параметр](#getoptions)|Возвращает флаги параметров для этого `CTaskDialog` .|
|[CTaskDialog:: Жетселектедкоммандконтролид](#getselectedcommandcontrolid)|Возвращает выбранный элемент управления кнопки команды.|
|[CTaskDialog:: Жетселектедрадиобуттонид](#getselectedradiobuttonid)|Возвращает выбранный переключатель.|
|[CTaskDialog:: Жетверификатиончеккбоксстате](#getverificationcheckboxstate)|Получает состояние флажка проверки.|
|[CTaskDialog:: Искоммандконтроленаблед](#iscommandcontrolenabled)|Определяет, включен ли элемент управления "Кнопка" или "Общая" кнопка.|
|[CTaskDialog:: Исрадиобуттоненаблед](#isradiobuttonenabled)|Определяет, включен ли переключатель.|
|[CTaskDialog:: не поддерживается](#issupported)|Определяет, поддерживает ли компьютер, на котором работает приложение, `CTaskDialog` .|
|[CTaskDialog:: Лоадкоммандконтролс](#loadcommandcontrols)|Добавляет элементы управления "Кнопка" с помощью данных из таблицы строк.|
|[CTaskDialog:: Лоадрадиобуттонс](#loadradiobuttons)|Добавляет переключатели, используя данные из таблицы строк.|
|[CTaskDialog:: NavigateTo](#navigateto)|Передает фокус на другой `CTaskDialog` .|
|[CTaskDialog:: Онкоммандконтролкликк](#oncommandcontrolclick)|Платформа вызывает этот метод, когда пользователь щелкает элемент управления "Кнопка".|
|[CTaskDialog:: OnCreate](#oncreate)|Платформа вызывает этот метод после создания `CTaskDialog` .|
|[CTaskDialog:: OnDestroy](#ondestroy)|Платформа вызывает этот метод непосредственно перед уничтожением `CTaskDialog` .|
|[CTaskDialog:: Онекспандбуттонкликк](#onexpandbuttonclick)|Платформа вызывает этот метод, когда пользователь нажимает кнопку расширения.|
|[CTaskDialog:: OnHelp](#onhelp)|Платформа вызывает этот метод, когда пользователь запрашивает справку.|
|[CTaskDialog:: Онхиперлинккликк](#onhyperlinkclick)|Платформа вызывает этот метод, когда пользователь щелкает гиперссылку.|
|[CTaskDialog:: OnInit](#oninit)|Платформа вызывает этот метод при `CTaskDialog` инициализации.|
|[CTaskDialog:: Оннавигатепаже](#onnavigatepage)|Платформа вызывает этот метод, когда пользователь перемещает фокус в отношении элементов управления в `CTaskDialog` .|
|[CTaskDialog:: Онрадиобуттонкликк](#onradiobuttonclick)|Платформа вызывает этот метод, когда пользователь выбирает элемент управления "переключатель".|
|[CTaskDialog:: OnTime](#ontimer)|Платформа вызывает этот метод по истечении срока действия таймера.|
|[CTaskDialog:: Онверификатиончеккбокскликк](#onverificationcheckboxclick)|Платформа вызывает этот метод, когда пользователь щелкает флажок проверки.|
|[CTaskDialog:: Ремовеаллкоммандконтролс](#removeallcommandcontrols)|Удаляет все командные элементы управления из `CTaskDialog` .|
|[CTaskDialog:: Ремовеаллрадиобуттонс](#removeallradiobuttons)|Удаляет все переключатели из `CTaskDialog` .|
|[CTaskDialog:: Сеткоммандконтролоптионс](#setcommandcontroloptions)|Обновляет элемент управления «кнопка» в `CTaskDialog` .|
|[CTaskDialog:: Сеткоммонбуттоноптионс](#setcommonbuttonoptions)|Обновляет подмножество общих кнопок для включения и требует повышения прав UAC.|
|[CTaskDialog:: SetCommonButtons](#setcommonbuttons)|Добавляет общие кнопки в `CTaskDialog` .|
|[CTaskDialog:: Сетконтент](#setcontent)|Обновляет содержимое `CTaskDialog` .|
|[CTaskDialog:: Сетдефаулткоммандконтрол](#setdefaultcommandcontrol)|Задает элемент управления "кнопка по умолчанию".|
|[CTaskDialog:: Сетдефаултрадиобуттон](#setdefaultradiobutton)|Задает переключатель по умолчанию.|
|[CTaskDialog:: Сетдиалогвидс](#setdialogwidth)|Корректирует ширину `CTaskDialog` .|
|[CTaskDialog:: SetExpansionArea](#setexpansionarea)|Обновляет область расширения `CTaskDialog` .|
|[CTaskDialog:: Сетфутерикон](#setfootericon)|Обновляет значок нижнего колонтитула для `CTaskDialog` .|
|[CTaskDialog:: Сетфутертекст](#setfootertext)|Обновляет текст нижнего колонтитула `CTaskDialog` .|
|[CTaskDialog:: Сетмаиникон](#setmainicon)|Обновляет основной значок `CTaskDialog` .|
|[CTaskDialog:: Сетмаининструктион](#setmaininstruction)|Обновляет основную инструкцию `CTaskDialog` .|
|[CTaskDialog:: Сетоптионс](#setoptions)|Настраивает параметры для `CTaskDialog` .|
|[CTaskDialog:: Сетпрогрессбармаркуи](#setprogressbarmarquee)|Настраивает полосу бегущей строки для `CTaskDialog` и добавляет ее в диалоговое окно.|
|[CTaskDialog:: Сетпрогрессбарпоситион](#setprogressbarposition)|Настраивает расположение индикатора выполнения.|
|[CTaskDialog:: Сетпрогрессбарранже](#setprogressbarrange)|Настраивает диапазон индикатора выполнения.|
|[CTaskDialog:: Сетпрогрессбарстате](#setprogressbarstate)|Задает состояние индикатора выполнения и отображает его в `CTaskDialog` .|
|[CTaskDialog:: Сетрадиобуттоноптионс](#setradiobuttonoptions)|Включает или отключает переключатель.|
|[CTaskDialog:: Сетверификатиончеккбокс](#setverificationcheckbox)|Устанавливает флажок проверять состояние проверки.|
|[CTaskDialog:: SetVerificationCheckboxText](#setverificationcheckboxtext)|Задает текст с правой стороны флажка проверки.|
|[CTaskDialog:: Сетвиндовтитле](#setwindowtitle)|Задает заголовок `CTaskDialog` .|
|[CTaskDialog:: ShowDialog](#showdialog)|Создает и отображает `CTaskDialog` .|
|[CTaskDialog:: Таскдиалогкаллбакк](#taskdialogcallback)|Платформа вызывает эту функцию в ответ на различные сообщения Windows.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|`m_aButtons`|Массив элементов управления кнопки команд для `CTaskDialog` .|
|`m_aRadioButtons`|Массив элементов управления "переключатель" для `CTaskDialog` .|
|`m_bVerified`|`TRUE` Указывает, что флажок проверки установлен; `FALSE` указывает, что это не так.|
|`m_footerIcon`|Значок в нижнем колонтитуле `CTaskDialog` .|
|`m_hWnd`|Маркер окна для `CTaskDialog` .|
|`m_mainIcon`|Основной значок `CTaskDialog` .|
|`m_nButtonDisabled`|Маска, указывающая, какая из общих кнопок отключена.|
|`m_nButtonElevation`|Маска, указывающая, какая из общих кнопок требует повышения прав UAC.|
|`m_nButtonId`|Идентификатор выбранного элемента управления кнопки команды.|
|`m_nCommonButton`|Маска, которая указывает, какие общие кнопки отображаются в `CTaskDialog` .|
|`m_nDefaultCommandControl`|Идентификатор элемента управления кнопки команды, выбранного при `CTaskDialog` отображении.|
|`m_nDefaultRadioButton`|Идентификатор элемента управления "переключатель", который выбран при `CTaskDialog` отображении.|
|`m_nFlags`|Маска, указывающая параметры для `CTaskDialog` .|
|`m_nProgressPos`|Текущее расположение индикатора выполнения.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|
|`m_nProgressRangeMax`|Максимальное значение индикатора выполнения.|
|`m_nProgressRangeMin`|Минимальное значение индикатора выполнения.|
|`m_nProgressState`|Состояние индикатора выполнения. Дополнительные сведения см. в разделе [CTaskDialog:: сетпрогрессбарстате](#setprogressbarstate).|
|`m_nRadioId`|Идентификатор выбранного элемента управления "переключатель".|
|`m_nWidth`|Ширина `CTaskDialog` (в пикселях).|
|`m_strCollapse`|Строка, `CTaskDialog` отображаемая справа от поля расширения, когда развернутая информация скрыта.|
|`m_strContent`|Строка содержимого `CTaskDialog` .|
|`m_strExpand`|Строка, `CTaskDialog` отображаемая справа от поля расширения при отображении расширенной информации.|
|`m_strFooter`|Нижний колонтитул `CTaskDialog` .|
|`m_strInformation`|Развернутая информация для `CTaskDialog` .|
|`m_strMainInstruction`|Основная инструкция `CTaskDialog` .|
|`m_strTitle`|Заголовок `CTaskDialog`.|
|`m_strVerification`|Строка, которая `CTaskDialog` отображается справа от флажка проверки.|

## <a name="remarks"></a>Примечания

`CTaskDialog`Класс заменяет стандартное окно сообщения Windows и имеет дополнительные функциональные возможности, такие как новые элементы управления для сбора информации от пользователя. Этот класс находится в библиотеке MFC в Visual Studio 2010 и более поздних версиях. `CTaskDialog`Доступен, начиная с Windows Vista. Более ранние версии Windows не могут отобразить `CTaskDialog` объект. Используйте `CTaskDialog::IsSupported` для определения во время выполнения, может ли текущий пользователь отображать диалоговое окно задачи. Стандартное окно сообщения Windows по-прежнему поддерживается.

`CTaskDialog`Доступен только при сборке приложения с помощью библиотеки Юникода.

`CTaskDialog`Имеет два разных конструктора. Один конструктор позволяет указать две командные кнопки и максимум шесть элементов управления "обычная кнопка". После создания можно добавить дополнительные кнопки команд `CTaskDialog` . Второй конструктор не поддерживает никаких командных кнопок, но можно добавить неограниченное число обычных элементов управления "Кнопка". Дополнительные сведения о конструкторах см. в разделе [CTaskDialog:: CTaskDialog](#ctaskdialog).

На следующем рисунке показан пример, `CTaskDialog` иллюстрирующий расположение некоторых элементов управления.

![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "Пример CTaskDialog") <br/>
Пример CTaskDialog

## <a name="requirements"></a>Требования

**Минимальная требуемая операционная система:** Windows Vista

**Заголовок:** афкстаскдиалог.h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a> CTaskDialog:: Аддкоммандконтрол

Добавляет новый элемент управления кнопки команд в `CTaskDialog` .

```cpp
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификационный номер элемента управления команды.

*стркаптион*<br/>
окне Строка, `CTaskDialog` отображаемая пользователю. Используйте эту строку, чтобы объяснить назначение команды.

*бенаблед*<br/>
окне Логический параметр, указывающий, включена или отключена кнопка "создать".

*брекуиреселеватион*<br/>
окне Логический параметр, указывающий, требует ли команда повышение прав.

### <a name="remarks"></a>Примечания

`CTaskDialog Class`Может отображать неограниченное количество элементов управления "Кнопка". Однако, если `CTaskDialog` отображает все элементы управления кнопки, она может отображать не более шести кнопок. Если у a `CTaskDialog` нет элементов управления "Кнопка", он может отобразить неограниченное количество кнопок.

Когда пользователь выбирает элемент управления «кнопка», `CTaskDialog` закрывается. Если приложение отображает диалоговое окно с помощью [CTaskDialog::D омодал](#domodal), `DoModal` возвращает *нкоммандконтролид* выбранного элемента управления "Кнопка".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a> CTaskDialog:: AddRadioButton

Добавляет переключатель в `CTaskDialog` .

```cpp
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификационный номер переключателя.

*стркаптион*<br/>
окне Строка, `CTaskDialog` отображаемая рядом с переключателем.

*бенаблед*<br/>
окне Логический параметр, указывающий, включен ли переключатель.

### <a name="remarks"></a>Примечания

Переключатели для [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md) позволяют собирать сведения от пользователя. Чтобы определить, какой переключатель выбран, используйте функцию [CTaskDialog:: жетселектедрадиобуттонид](#getselectedradiobuttonid) .

Не `CTaskDialog` требует, чтобы параметры *нрадиобуттонид* были уникальными для каждого переключателя. Однако может возникнуть непредвиденное поведение, если не используется отдельный идентификатор для каждого переключателя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a> CTaskDialog:: Кликккоммандконтрол

Программно нажимает на командную кнопку или общую кнопку.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификатор команды элемента управления для щелчка.

### <a name="remarks"></a>Примечания

Этот метод создает сообщение Windows TDM_CLICK_BUTTON.

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a> CTaskDialog:: Кликкрадиобуттон

Программно щелкает переключатель.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификатор переключателя, который нужно щелкнуть.

### <a name="remarks"></a>Примечания

Этот метод создает сообщение Windows TDM_CLICK_RADIO_BUTTON.

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a> CTaskDialog:: CTaskDialog

Создает экземпляр [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md).

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Параметры

*стрконтент*<br/>
окне Строка, используемая для содержимого `CTaskDialog` .

*стрмаининструктион*<br/>
окне Основная инструкция `CTaskDialog` .

*стртитле*<br/>
окне Заголовок `CTaskDialog` .

*нкоммонбуттонс*<br/>
окне Маска общих кнопок для добавления в `CTaskDialog` .

*нтаскдиалогоптионс*<br/>
окне Набор параметров, используемых для `CTaskDialog` .

*стрфутер*<br/>
окне Строка, используемая в качестве нижнего колонтитула.

*нидкоммандконтролсфирст*<br/>
окне Идентификатор строки первой команды.

*нидкоммандконтролсласт*<br/>
окне Идентификатор строки последней команды.

### <a name="remarks"></a>Примечания

Добавить в приложение можно двумя способами `CTaskDialog` . Первый способ — использовать один из конструкторов для создания `CTaskDialog` и вывода его с помощью [CTaskDialog::D омодал](#domodal). Второй способ — использовать статическую функцию [CTaskDialog:: ShowDialog](#showdialog), которая позволяет отображать `CTaskDialog` без явного создания `CTaskDialog` объекта.

Второй конструктор создает кнопки команд с помощью данных из файла ресурсов приложения. Таблица строк в файле ресурсов содержит несколько строк со связанными идентификаторами строк. Этот метод добавляет элемент управления «кнопка» для каждой допустимой записи в таблице строк между *нидкоммандконтролсфирст* и *нкоммандконтролсласт*включительно. Для этих элементов управления кнопки строка в таблице строк представляет собой заголовок элемента управления, а идентификатор строки — идентификатор элемента управления.

Список допустимых параметров см. в разделе [CTaskDialog:: сетоптионс](#setoptions) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a> CTaskDialog::D Омодал

Показывает `CTaskDialog` и делает его модальным.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Параметры

*хпарент*<br/>
окне Родительское окно для `CTaskDialog` .

### <a name="return-value"></a>Возвращаемое значение

Целое число, соответствующее выбору, сделанному пользователем.

### <a name="remarks"></a>Примечания

Отображает этот экземпляр [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Затем приложение ожидает закрытия диалогового окна пользователем.

`CTaskDialog`Закрывается, когда пользователь выбирает общую кнопку, элемент управления Command Link или закрывает `CTaskDialog` . Возвращаемое значение — это идентификатор, который указывает, как пользователь закрыл диалоговое окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a> CTaskDialog:: Жеткоммонбуттонкаунт

Получает количество общих кнопок.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число доступных общих кнопок.

### <a name="remarks"></a>Примечания

Общими кнопками являются кнопки по умолчанию, которые вы предоставляете [CTaskDialog:: CTaskDialog](#ctaskdialog). [Класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) отображает кнопки, расположенные в нижней части диалогового окна.

Нумерованный список кнопок предоставляется в Коммктрл.h.

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a> CTaskDialog:: Жеткоммонбуттонфлаг

Преобразует стандартную кнопку Windows в общий тип кнопки, связанный с [классом CTaskDialog](../../mfc/reference/ctaskdialog-class.md).

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Параметры

*нбуттонид*<br/>
окне Стандартное значение кнопки Windows.

### <a name="return-value"></a>Возвращаемое значение

Значение соответствующей `CTaskDialog` общей кнопки. Если соответствующей общей кнопки нет, этот метод возвращает значение 0.

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a> CTaskDialog:: Жеткоммонбуттонид

Преобразует один из типов общих кнопок, связанных с [классом CTaskDialog](../../mfc/reference/ctaskdialog-class.md) , в стандартную кнопку Windows.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Параметры

*нфлаг*<br/>
окне Общий тип кнопки, связанный с `CTaskDialog` классом.

### <a name="return-value"></a>Возвращаемое значение

Значение соответствующей стандартной кнопки Windows. Если соответствующей кнопки Windows нет, метод возвращает значение 0.

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a> CTaskDialog:: параметр

Возвращает флаги параметров для этого `CTaskDialog` .

```
int GetOptions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Флаги для `CTaskDialog` .

### <a name="remarks"></a>Примечания

Дополнительные сведения о параметрах, доступных для [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md), см. в разделе [CTaskDialog:: сетоптионс](#setoptions).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a> CTaskDialog:: Жетселектедкоммандконтролид

Возвращает выбранный элемент управления кнопки команды.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор выбранного в данный момент элемента управления кнопки команды.

### <a name="remarks"></a>Примечания

Не нужно использовать этот метод для получения идентификатора кнопки, выбранной пользователем. Этот идентификатор возвращается либо [CTaskDialog::D омодал](#domodal) , либо [CTaskDialog:: ShowDialog](#showdialog).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a> CTaskDialog:: Жетселектедрадиобуттонид

Возвращает выбранный переключатель.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор выбранного переключателя.

### <a name="remarks"></a>Примечания

Этот метод можно использовать после закрытия пользователем диалогового окна для получения выбранного переключателя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a> CTaskDialog:: Жетверификатиончеккбоксстате

Получает состояние флажка проверки.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если флажок установлен, в противном случае — FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a> CTaskDialog:: Искоммандконтроленаблед

Определяет, включен ли элемент управления или кнопка "Командная кнопка".

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификатор элемента управления или тестируемой кнопки команды.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент управления включен, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот метод можно использовать для определения доступности как элементов управления "Кнопка", так и общих кнопок `CTaskDialog` класса *.

Если *нкоммандконтролид* не является допустимым идентификатором для общей `CTaskDialog` кнопки или элемента управления кнопки, этот метод создает исключение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a> CTaskDialog:: Исрадиобуттоненаблед

Определяет, включен ли переключатель.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификатор переключателя для проверки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переключатель включен, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Если *нрадиобуттонид* не является допустимым идентификатором для переключателя, этот метод создает исключение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a> CTaskDialog:: не поддерживается

Определяет, поддерживает ли компьютер, на котором работает приложение, `CTaskDialog` .

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если компьютер поддерживает `CTaskDialog` ; В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция используется для определения во время выполнения, если компьютер, на котором работает приложение, поддерживает `CTaskDialog` класс. Если компьютер не поддерживает `CTaskDialog` , необходимо предоставить другой способ передачи информации пользователю. Приложение аварийно завершит работу, если попытается использовать `CTaskDialog` на компьютере, который не поддерживает `CTaskDialog` класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a> CTaskDialog:: Лоадкоммандконтролс

Добавляет элементы управления "Кнопка" с помощью данных из таблицы строк.

```cpp
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>Параметры

*нидкоммандконтролсфирст*<br/>
окне Идентификатор строки первой команды.

*нидкоммандконтролсласт*<br/>
окне Идентификатор строки последней команды.

### <a name="remarks"></a>Примечания

Этот метод создает командные элементы управления с помощью данных из файла ресурсов приложения. Таблица строк в файле ресурсов содержит несколько строк со связанными идентификаторами строк. Новые элементы управления кнопки команд, добавленные с помощью этого метода, используют строку для заголовка элемента управления и идентификатор строки для идентификатора элемента управления. Диапазон выбранных строк предоставляется *нидкоммандконтролсфирст* и *нкоммандконтролсласт*включительно. Если в диапазоне есть пустая запись, метод не добавляет элемент управления «кнопка» для этой записи.

По умолчанию новые элементы управления кнопки команд включены и не нуждаются в повышении прав.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a> CTaskDialog:: Лоадрадиобуттонс

Добавляет элементы управления "переключатель", используя данные из таблицы строк.

```cpp
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>Параметры

*нидрадиобуттонсфирст*<br/>
окне Идентификатор строки первого переключателя.

*нидрадиобуттонсласт*<br/>
окне Идентификатор строки последнего переключателя.

### <a name="remarks"></a>Примечания

Этот метод создает переключатели, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов содержит несколько строк со связанными идентификаторами строк. Новые переключатели, добавленные с помощью этого метода, используют строку для заголовка переключателя и идентификатор строки для идентификатора переключателя. Диапазон выбранных строк предоставляется *нидрадиобуттонсфирст* и *нрадиобуттонсласт*включительно. При наличии пустой записи в диапазоне метод не добавляет переключатель для этой записи.

По умолчанию новые переключатели включены.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a> CTaskDialog:: NavigateTo

Передает фокус на другой `CTaskDialog` .

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Параметры

*отаскдиалог*<br/>
окне Объект `CTaskDialog` , который получает фокус.

### <a name="remarks"></a>Примечания

Этот метод скрывает текущий `CTaskDialog` при отображении *отаскдиалог*. *Отаскдиалог* отображается в том же расположении, что и текущий `CTaskDialog` .

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a> CTaskDialog:: Онкоммандконтролкликк

Платформа вызывает этот метод, когда пользователь щелкает элемент управления "Кнопка".

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификатор элемента управления кнопки команды, выбранного пользователем.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a> CTaskDialog:: OnCreate

Платформа вызывает этот метод после создания `CTaskDialog` .

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a> CTaskDialog:: OnDestroy

Платформа вызывает этот метод непосредственно перед уничтожением `CTaskDialog` .

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a> CTaskDialog:: Онекспандбуттонкликк

Платформа вызывает этот метод, когда пользователь нажимает кнопку расширения.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>Параметры

*бекспандед*<br/>
окне Ненулевое значение указывает на то, что дополнительные сведения отображаются. значение 0 указывает, что дополнительные сведения скрыты.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a> CTaskDialog:: OnHelp

Платформа вызывает этот метод, когда пользователь запрашивает справку.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a> CTaskDialog:: Онхиперлинккликк

Платформа вызывает этот метод, когда пользователь щелкает гиперссылку.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>Параметры

*стрхреф*<br/>
окне Строка, представляющая гиперссылку.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Этот метод вызывает [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) перед возвратом S_OK.

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogoninit"></a><a name="oninit"></a> CTaskDialog:: OnInit

Платформа вызывает этот метод при `CTaskDialog` инициализации.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a> CTaskDialog:: Оннавигатепаже

Платформа вызывает этот метод в ответ на метод [CTaskDialog:: NavigateTo](#navigateto) .

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a> CTaskDialog:: Онрадиобуттонкликк

Платформа вызывает этот метод, когда пользователь выбирает элемент управления "переключатель".

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификатор элемента управления "переключатель", который щелкнул пользователь.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a> CTaskDialog:: OnTime

Платформа вызывает этот метод по истечении срока действия таймера.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Параметры

*лтиме*<br/>
окне Время в миллисекундах с момента `CTaskDialog` создания или сброса таймера.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a> CTaskDialog:: Онверификатиончеккбокскликк

Платформа вызывает этот метод, когда пользователь щелкает флажок проверки.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>Параметры

*бчеккед*<br/>
окне Значение TRUE указывает, что флажок проверки установлен; Значение FALSE указывает, что это не так.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a> CTaskDialog:: Ремовеаллкоммандконтролс

Удаляет все элементы управления «кнопка» из `CTaskDialog` .

```cpp
void RemoveAllCommandControls();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a> CTaskDialog:: Ремовеаллрадиобуттонс

Удаляет все переключатели из `CTaskDialog` .

```cpp
void RemoveAllRadioButtons();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a> CTaskDialog:: Сеткоммандконтролоптионс

Обновляет элемент управления «кнопка» в `CTaskDialog` .

```cpp
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификатор обновляемого элемента управления команды.

*бенаблед*<br/>
окне Логический параметр, указывающий, включен или отключен указанный элемент управления "кнопка команды".

*брекуиреселеватион*<br/>
окне Логический параметр, указывающий, требуется ли повышение прав для указанного элемента управления "Командная кнопка".

### <a name="remarks"></a>Примечания

Этот метод используется для изменения того, включен ли элемент управления "кнопка команды" или требует повышения прав после добавления в `CTaskDialog` класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a> CTaskDialog:: Сеткоммонбуттоноптионс

Обновляет подмножество общих кнопок для включения и требует повышения прав UAC.

```cpp
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Параметры

*ндисабледбуттонмаск*<br/>
окне Маска для общих кнопок для отключения.

*нелеватионбуттонмаск*<br/>
окне Маска для общих кнопок, требующих повышения прав.

### <a name="remarks"></a>Примечания

Можно задать общие кнопки, доступные экземпляру [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md) , с помощью конструктора [CTaskDialog:: CTaskDialog](#ctaskdialog) и метода [CTaskDialog:: SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` не поддерживает добавление новых общих кнопок.

При использовании этого метода для отключения или повышения уровня общей кнопки, которая недоступна для этого `CTaskDialog` метода, этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) .

Этот метод включает любую кнопку, доступную для, `CTaskDialog` но не в *ндисабледбуттонмаск*, даже если она была ранее отключена. Этот метод рассматривает повышение прав подобным образом: он записывает общие кнопки, не нуждающиеся в повышении прав, если общая кнопка доступна, но не включена в *нелеватионбуттонмаск*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a> CTaskDialog:: SetCommonButtons

Добавляет общие кнопки в `CTaskDialog` .

```cpp
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Параметры

*нбуттонмаск*<br/>
окне Маска кнопок, добавляемых в `CTaskDialog` .

*ндисабледбуттонмаск*<br/>
окне Маска кнопок для отключения.

*нелеватионбуттонмаск*<br/>
окне Маска кнопок, требующих повышения прав.

### <a name="remarks"></a>Примечания

Этот метод нельзя вызвать после создания окна просмотра для данного экземпляра `CTaskDialog` класса. В противном случае этот метод выдаст исключение.

Кнопки, указанные *нбуттонмаск* , переопределяют все общие кнопки, ранее добавленные в `CTaskDialog` . Доступны только кнопки, указанные в *нбуттонмаск* .

Если *ндисабледбуттонмаск* или *нелеватионбуттонмаск* содержат кнопку, которая не находится в *нбуттонмаск*, этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) .

По умолчанию все общие кнопки включены и не нуждаются в повышении прав.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a> CTaskDialog:: Сетконтент

Обновляет содержимое `CTaskDialog` .

```cpp
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Параметры

*стрконтент*<br/>
окне Строка, отображаемая пользователю.

### <a name="remarks"></a>Примечания

Содержимое `CTaskDialog` класса — это текст, который отображается для пользователя в основном разделе диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a> CTaskDialog:: Сетдефаулткоммандконтрол

Задает элемент управления "кнопка по умолчанию".

```cpp
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Параметры

*нкоммандконтролид*<br/>
окне Идентификатор элемента управления кнопки команды, который будет использоваться по умолчанию.

### <a name="remarks"></a>Примечания

Кнопка по умолчанию — это элемент управления, который выбирается при `CTaskDialog` первом отображении пользователю.

Этот метод создает исключение, если не удается найти элемент управления "кнопка команды", указанный параметром *нкоммандконтролид*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a> CTaskDialog:: Сетдефаултрадиобуттон

Задает переключатель по умолчанию.

```cpp
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификатор переключателя, который будет использоваться по умолчанию.

### <a name="remarks"></a>Примечания

Переключатель по умолчанию — это кнопка, которая выбирается при `CTaskDialog` первом отображении пользователя.

Этот метод создает исключение, если не удается найти переключатель, указанный параметром *нрадиобуттонид*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a> CTaskDialog:: Сетдиалогвидс

Корректирует ширину `CTaskDialog` .

```cpp
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>Параметры

*нвидс*<br/>
окне Ширина диалогового окна в пикселях.

### <a name="remarks"></a>Примечания

Параметр *нвидс* должен быть больше или равен 0. В противном случае этот метод выдает исключение.

Если *нвидс* имеет значение 0, этот метод задает для диалогового окна размер по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a> CTaskDialog:: SetExpansionArea

Обновляет область расширения `CTaskDialog` .

```cpp
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Параметры

*стрекспандединформатион*<br/>
окне Строка, `CTaskDialog` отображаемая в основном тексте диалогового окна при нажатии пользователем кнопки расширения.

*стрколлапседлабел*<br/>
окне Строка, `CTaskDialog` отображаемая рядом с кнопкой расширения при сворачивании развернутой области.

*стрекспандедлабел*<br/>
окне Строка, `CTaskDialog` отображаемая рядом с кнопкой расширения при отображении развернутой области.

### <a name="remarks"></a>Примечания

Область расширения `CTaskDialog` класса позволяет предоставить пользователю дополнительные сведения. Область расширения находится в основной части `CTaskDialog` , расположенной непосредственно под заголовком и строкой содержимого.

При `CTaskDialog` первом отображении она не отображает развернутую информацию и помещается `strCollapsedLabel` рядом с кнопкой расширения. Когда пользователь нажимает кнопку расширения, `CTaskDialog` отображает *стрекспандединформатион* и изменяет метку на *стрекспандедлабел*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a> CTaskDialog:: Сетфутерикон

Обновляет значок нижнего колонтитула `CTaskDialog` .

```cpp
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Параметры

*хфутерикон*<br/>
окне Новый значок для `CTaskDialog` .

*лпсзфутерикон*<br/>
окне Новый значок для `CTaskDialog` .

### <a name="remarks"></a>Примечания

Значок нижнего колонтитула отображается в нижней части [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md). У него может быть связанный текст нижнего колонтитула. Текст нижнего колонтитула можно изменить с помощью [CTaskDialog:: сетфутертекст](#setfootertext).

Этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) , если `CTaskDialog` отображается или если входной параметр имеет значение null.

`CTaskDialog`Может принимать только `HICON` или `LPCWSTR` в качестве значка нижнего колонтитула. Это можно настроить с помощью параметра TDF_USE_HICON_FOOTER в конструкторе или [CTaskDialog:: сетоптионс](#setoptions). По умолчанию параметр `CTaskDialog` настроен для использования в `LPCWSTR` качестве типа входных данных для значка нижнего колонтитула. Этот метод создает исключение при попытке установить значок с использованием недопустимого типа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a> CTaskDialog:: Сетфутертекст

Обновляет текст нижнего колонтитула `CTaskDialog` .

```cpp
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Параметры

*стрфутертекст*<br/>
окне Новый текст для нижнего колонтитула.

### <a name="remarks"></a>Примечания

Значок нижнего колонтитула отображается рядом с текстом нижнего колонтитула в нижней части `CTaskDialog` . Значок нижнего колонтитула можно изменить с помощью [CTaskDialog:: сетфутерикон](#setfootericon).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a> CTaskDialog:: Сетмаиникон

Обновляет основной значок `CTaskDialog` .

```cpp
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Параметры

*хмаиникон*<br/>
окне Новый значок.

*лпсзмаиникон*<br/>
окне Новый значок.

### <a name="remarks"></a>Примечания

Этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) , если `CTaskDialog` отображается или если входной параметр имеет значение null.

`CTaskDialog`Может принимать или только в `HICON` `LPCWSTR` качестве главного значка. Это можно настроить, задав параметр TDF_USE_HICON_MAIN в конструкторе или в методе [CTaskDialog:: сетоптионс](#setoptions) . По умолчанию параметр `CTaskDialog` настроен для использования в `LPCWSTR` качестве типа входных данных для главного значка. Этот метод создает исключение при попытке установить значок с использованием недопустимого типа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a> CTaskDialog:: Сетмаининструктион

Обновляет основную инструкцию `CTaskDialog` .

```cpp
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Параметры

*стринструктионс*<br/>
окне Новая основная инструкция.

### <a name="remarks"></a>Примечания

Основная инструкция `CTaskDialog` класса — текст, отображаемый пользователю полужирным шрифтом. Он находится в диалоговом окне под заголовком окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a> CTaskDialog:: Сетоптионс

Настраивает параметры для `CTaskDialog` .

```cpp
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Параметры

*ноптионфлаг*<br/>
окне Набор флагов, используемых для `CTaskDialog` .

### <a name="remarks"></a>Примечания

Этот метод очищает все текущие параметры для `CTaskDialog` . Чтобы сохранить текущие параметры, необходимо сначала извлечь их с помощью [CTaskDialog::](#getoptions) и объединить с параметрами, которые необходимо задать.

В следующей таблице перечислены все допустимые параметры.

|Имя|Описание|
|-|-|
|TDF_ENABLE_HYPERLINKS|Включает гиперссылки в `CTaskDialog` .|
|TDF_USE_HICON_MAIN|Настраивает `CTaskDialog` для использования `HICON` для главного значка. Альтернативой является использование `LPCWSTR` .|
|TDF_USE_HICON_FOOTER|Настраивает `CTaskDialog` для использования `HICON` для значка нижнего колонтитула. Альтернативой является использование `LPCWSTR` .|
|TDF_ALLOW_DIALOG_CANCELLATION|Позволяет пользователю закрывать объект с `CTaskDialog` помощью клавиатуры или значка в правом верхнем углу диалогового окна, даже если кнопка **Отмена** недоступна. Если этот флаг не установлен и кнопка **Отмена** не включена, пользователь не может закрыть диалоговое окно, нажав Alt + F4, клавишу Escape или кнопку Закрыть в строке заголовка.|
|TDF_USE_COMMAND_LINKS|Настраивает `CTaskDialog` для использования командных элементов управления.|
|TDF_USE_COMMAND_LINKS_NO_ICON|Настраивает `CTaskDialog` для использования командных элементов управления без отображения значка рядом с элементом управления. TDF_USE_COMMAND_LINKS переопределяет TDF_USE_COMMAND_LINKS_NO_ICON.|
|TDF_EXPAND_FOOTER_AREA|Указывает, что область расширения в настоящее время развернута.|
|TDF_EXPANDED_BY_DEFAULT|Определяет, развернута ли область расширения по умолчанию.|
|TDF_VERIFICATION_FLAG_CHECKED|Указывает, что флажок проверки установлен в данный момент.|
|TDF_SHOW_PROGRESS_BAR|Настраивает `CTaskDialog` для вывода индикатора выполнения.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|Настраивает индикатор выполнения, чтобы он был полосой выполнения бегущей строки. Если этот параметр включен, необходимо задать для TDF_SHOW_PROGRESS_BAR ожидаемое поведение.|
|TDF_CALLBACK_TIMER|Указывает, что `CTaskDialog` интервал обратного вызова равен приблизительно 200 миллисекундам.|
|TDF_POSITION_RELATIVE_TO_WINDOW|Настраивает объект `CTaskDialog` для центрирования относительно родительского окна. Если этот флаг не включен, `CTaskDialog` центр отсчитывается относительно монитора.|
|TDF_RTL_LAYOUT|Настраивает `CTaskDialog` для режима чтения справа налево.|
|TDF_NO_DEFAULT_RADIO_BUTTON|Указывает, что переключатель не выбран при `CTaskDialog` отображении.|
|TDF_CAN_BE_MINIMIZED|Позволяет пользователю в минимальном объеме `CTaskDialog` . Для поддержки этого параметра параметр `CTaskDialog` не может быть модальным. MFC не поддерживает этот параметр, так как MFC не поддерживает немодальное `CTaskDialog` .|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a> CTaskDialog:: Сетпрогрессбармаркуи

Настраивает полосу бегущей строки для `CTaskDialog` и добавляет ее в диалоговое окно.

```cpp
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Параметры

*бенаблед*<br/>
окне Значение TRUE, чтобы включить строку бегущей строки; Значение FALSE, чтобы отключить строку бегущей строки и удалить ее из `CTaskDialog` .

*нмаркуиспид*<br/>
окне Целое число, указывающее скорость полосы бегущей строки.

### <a name="remarks"></a>Примечания

Полоса бегущей строки отображается под основным текстом `CTaskDialog` класса.

Используйте *нмаркуиспид* , чтобы задать скорость линейки бегущей строки; большие значения указывают на более низкую скорость. Значение 0 для *нмаркуиспид* делает полосу бегущей строки в скорости по умолчанию для Windows.

Этот метод создает исключение с [помощью макроса](diagnostic-services.md#ensure) , если *нмаркуиспид* меньше 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a> CTaskDialog:: Сетпрогрессбарпоситион

Настраивает расположение индикатора выполнения.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Параметры

*нпрогресспос*<br/>
окне Расположение индикатора выполнения.

### <a name="remarks"></a>Примечания

Этот метод создает исключение с [помощью макроса](diagnostic-services.md#ensure) , если *нпрогресспос* не находится в области индикатора выполнения. Диапазон индикаторов выполнения можно изменить с помощью [CTaskDialog:: сетпрогрессбарранже](#setprogressbarrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a> CTaskDialog:: Сетпрогрессбарранже

Настраивает диапазон индикатора выполнения.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Параметры

*нранжемин*<br/>
окне Нижняя граница индикатора выполнения.

*нранжемакс*<br/>
окне Верхняя граница индикатора выполнения.

### <a name="remarks"></a>Примечания

Расположение индикатора выполнения задается относительно *нранжемин* и *нранжемакс*. Например, если *нранжемин* имеет значение 50, а *нранжемакс* — 100, то на индикаторе выполнения устанавливается расположение 75. Чтобы задать расположение индикатора выполнения, используйте [CTaskDialog:: сетпрогрессбарпоситион](#setprogressbarposition) .

Чтобы отобразить индикатор выполнения, параметр TDF_SHOW_PROGRESS_BAR должен быть включен и TDF_SHOW_MARQUEE_PROGRESS_BAR не должен быть включен. Этот метод автоматически задает TDF_SHOW_PROGRESS_BAR и очищает TDF_SHOW_MARQUEE_PROGRESS_BAR. Используйте [CTaskDialog:: сетоптионс](#setoptions) , чтобы вручную изменить параметры для этого экземпляра [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md).

Этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) , если *Нранжемин* не меньше *нранжемакс*. Этот метод также вызывает исключение, если объект `CTaskDialog` уже отображается и имеет полосу выполнения бегущей строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a> CTaskDialog:: Сетпрогрессбарстате

Задает состояние индикатора выполнения и отображает его в `CTaskDialog` .

```cpp
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Параметры

*Nсведения*<br/>
окне Состояние индикатора выполнения. Возможные значения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Этот метод создает исключение с [помощью макроса](diagnostic-services.md#ensure) , если объект `CTaskDialog` уже отображается и имеет полосу выполнения бегущей строки.

В следующей таблице перечислены возможные значения для *nсведения*. Во всех этих случаях индикатор выполнения будет заполняться обычным цветом до тех пор, пока не достигнет назначенной позиции окончания. На этом этапе цвет изменится в зависимости от состояния.

|Имя|Описание|
|-|-|
|PBST_NORMAL|После заполнения индикатора выполнения элемент `CTaskDialog` не меняет цвет линии. По умолчанию обычный цвет горит зеленым цветом.|
|PBST_ERROR|После заполнения индикатора выполнения `CTaskDialog` изменяет цвет полосы на цвет ошибки. По умолчанию это красный цвет.|
|PBST_PAUSED|После заполнения индикатора выполнения `CTaskDialog` изменится цвет полосы на приостановку. По умолчанию это желтый цвет.|

Вы можете задать место остановки индикатора выполнения с помощью [CTaskDialog:: сетпрогрессбарпоситион](#setprogressbarposition).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a> CTaskDialog:: Сетрадиобуттоноптионс

Включает или отключает переключатель.

```cpp
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*нрадиобуттонид*<br/>
окне Идентификатор элемента управления "переключатель".

*бенаблед*<br/>
окне Значение TRUE, чтобы включить переключатель; Значение FALSE, чтобы отключить переключатель.

### <a name="remarks"></a>Примечания

Этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) , если *нрадиобуттонид* не является допустимым идентификатором для переключателя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a> CTaskDialog:: Сетверификатиончеккбокс

Устанавливает флажок проверять состояние проверки.

```cpp
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Параметры

*бчеккед*<br/>
окне Значение TRUE, чтобы флажок проверки был установлен при `CTaskDialog` отображении. Значение FALSE, чтобы флажок проверки не был снят при `CTaskDialog` отображении.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a> CTaskDialog:: SetVerificationCheckboxText

Задает текст, отображаемый справа от флажка проверки.

```cpp
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Параметры

*стрверификатионтекст*<br/>
окне Текст, отображаемый этим методом рядом с флажком проверки.

### <a name="remarks"></a>Примечания

Этот метод создает исключение с помощью макроса [проверки](diagnostic-services.md#ensure) , если этот экземпляр `CTaskDialog` класса уже отображается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a> CTaskDialog:: Сетвиндовтитле

Задает заголовок `CTaskDialog` .

```cpp
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Параметры

*стрвиндовтитле*<br/>
окне Новый заголовок для `CTaskDialog` .

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a> CTaskDialog:: ShowDialog

Создает и отображает `CTaskDialog` .

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Параметры

*стрконтент*<br/>
окне Строка, используемая для содержимого `CTaskDialog` .

*стрмаининструктион*<br/>
окне Основная инструкция `CTaskDialog` .

*стртитле*<br/>
окне Заголовок `CTaskDialog` .

*нидкоммандконтролсфирст*<br/>
окне Идентификатор строки первой команды.

*нидкоммандконтролсласт*<br/>
окне Идентификатор строки последней команды.

*нкоммонбуттонс*<br/>
окне Маска кнопок, добавляемых в `CTaskDialog` .

*нтаскдиалогоптионс*<br/>
окне Набор параметров, используемых для `CTaskDialog` .

*стрфутер*<br/>
окне Строка, используемая в качестве нижнего колонтитула.

### <a name="return-value"></a>Возвращаемое значение

Целое число, соответствующее выбору, сделанному пользователем.

### <a name="remarks"></a>Примечания

Этот статический метод позволяет создать экземпляр `CTaskDialog` класса без явного создания `CTaskDialog` объекта в коде. Поскольку `CTaskDialog` объект отсутствует, вы не можете вызывать другие методы, `CTaskDialog` Если этот метод используется для отображения `CTaskDialog` пользователю.

Этот метод создает командные элементы управления с помощью данных из файла ресурсов приложения. Таблица строк в файле ресурсов содержит несколько строк со связанными идентификаторами строк. Этот метод добавляет элемент управления «кнопка» для каждой допустимой записи в таблице строк между *нидкоммандконтролсфирст* и *нкоммандконтролсласт*включительно. Для этих элементов управления кнопки строка в таблице строк представляет собой заголовок элемента управления, а идентификатор строки — идентификатор элемента управления.

Список допустимых параметров см. в разделе [CTaskDialog:: сетоптионс](#setoptions) .

`CTaskDialog`Закрывается, когда пользователь выбирает общую кнопку, элемент управления Command Link или закрывает `CTaskDialog` . Возвращаемое значение — это идентификатор, который указывает, как пользователь закрыл диалоговое окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a> CTaskDialog:: Таскдиалогкаллбакк

Платформа вызывает этот метод в ответ на различные сообщения Windows.

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>Параметры

*HWND*<br/>
окне Маркер `m_hWnd` структуры для `CTaskDialog` .

*унотификатион*<br/>
окне Код уведомления, указывающий созданное сообщение.

*wParam*<br/>
окне Дополнительные сведения о сообщении.

*lParam*<br/>
окне Дополнительные сведения о сообщении.

*дврефдата*<br/>
окне Указатель на `CTaskDialog` объект, к которому применяется сообщение обратного вызова.

### <a name="return-value"></a>Возвращаемое значение

Зависит от конкретного кода уведомления. Дополнительные сведения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Реализация по умолчанию `TaskDialogCallback` обрабатывает конкретное сообщение, а затем вызывает соответствующий метод в [классе CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Например, в ответ на сообщение TDN_BUTTON_CLICKED `TaskDialogCallback` вызывается метод [CTaskDialog:: онкоммандконтролкликк](#oncommandcontrolclick).

Значения параметров *wParam* и *lParam* зависят от конкретного созданного сообщения. Одно или оба этих значения могут быть пустыми. В следующей таблице перечислены поддерживаемые уведомления по умолчанию и значения параметров *wParam* и *lParam* . При переопределении этого метода в производном классе следует реализовать код обратного вызова для каждого сообщения в следующей таблице.

|Сообщение уведомления|*wParam* Значений|*lParam* Значений|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Не используется.|Не используется.|
|TDN_NAVIGATED|Не используется.|Не используется.|
|TDN_BUTTON_CLICKED|Идентификатор элемента управления кнопки команд.|Не используется.|
|TDN_HYPERLINK_CLICKED|Не используется.|Структура [лпквстр](/windows/win32/WinProg/windows-data-types) , содержащая ссылку.|
|TDN_TIMER|Время в миллисекундах с момента `CTaskDialog` создания или сброса таймера.|Не используется.|
|TDN_DESTROYED|Не используется.|Не используется.|
|TDN_RADIO_BUTTON_CLICKED|Идентификатор переключателя.|Не используется.|
|TDN_DIALOG_CONSTRUCTED|Не используется.|Не используется.|
|TDN_VERIFICATION_CLICKED|1, если флажок установлен, в противном случае — 0.|Не используется.|
|TDN_HELP|Не используется.|Не используется.|
|TDN_EXPANDO_BUTTON_CLICKED|0, если область расширения свернута; ненулевое значение, если текст расширения отображается.|Не используется.|

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Пошаговое руководство. Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
