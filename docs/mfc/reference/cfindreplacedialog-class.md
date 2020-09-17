---
title: Класс диалоговое CFindReplaceDialog
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: 92429bc17301d6615c87de958f38a717528e9544
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212440"
---
# <a name="cfindreplacedialog-class"></a>Класс диалоговое CFindReplaceDialog

Позволяет реализовать стандартные диалоговые окна поиска и замены строк в приложении.

## <a name="syntax"></a>Синтаксис

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Диалоговое CFindReplaceDialog:: диалоговое CFindReplaceDialog](#cfindreplacedialog)|Вызовите эту функцию для создания `CFindReplaceDialog` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Диалоговое CFindReplaceDialog:: Create](#create)|Создает и отображает `CFindReplaceDialog` диалоговое окно.|
|[Диалоговое CFindReplaceDialog:: FindNext](#findnext)|Вызовите эту функцию, чтобы определить, нужно ли пользователю найти следующее вхождение строки поиска.|
|[Диалоговое CFindReplaceDialog:: Жетфиндстринг](#getfindstring)|Вызовите эту функцию, чтобы получить текущую строку поиска.|
|[Диалоговое CFindReplaceDialog:: "уведомление"](#getnotifier)|Вызовите эту функцию, чтобы получить `FINDREPLACE` структуру в зарегистрированном обработчике сообщений.|
|[Диалоговое CFindReplaceDialog:: Жетреплацестринг](#getreplacestring)|Вызовите эту функцию, чтобы получить текущую строку замены.|
|[Диалоговое CFindReplaceDialog:: завершения](#isterminating)|Вызовите эту функцию, чтобы определить, завершается ли диалоговое окно.|
|[Диалоговое CFindReplaceDialog:: Матчкасе](#matchcase)|Вызовите эту функцию, чтобы определить, нужно ли точно сопоставить регистр поиска строки find.|
|[Диалоговое CFindReplaceDialog:: Матчвхолеворд](#matchwholeword)|Вызовите эту функцию, чтобы определить, желаете ли пользователь сопоставлять только целые слова.|
|[Диалоговое CFindReplaceDialog:: ReplaceAll](#replaceall)|Вызовите эту функцию, чтобы определить, хочет ли пользователь заменять все вхождения строки.|
|[Диалоговое CFindReplaceDialog:: Реплацекуррент](#replacecurrent)|Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить текущее слово.|
|[Диалоговое CFindReplaceDialog:: Сеарчдовн](#searchdown)|Вызовите эту функцию, чтобы определить, должен ли пользователь искать переходы в направлении вниз.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Диалоговое CFindReplaceDialog:: m_fr](#m_fr)|Структура, используемая для настройки `CFindReplaceDialog` объекта.|

## <a name="remarks"></a>Примечания

В отличие от других общих диалоговых окон Windows, `CFindReplaceDialog` объекты являются немодальными, что позволяет пользователям взаимодействовать с другими окнами, когда они находятся на экране. Существует два вида `CFindReplaceDialog` объектов: диалоговое окно Поиск и замена. Хотя диалоговые окна позволяют пользователю вводить и искать, и заменять строки, они не выполняют функции поиска и замены. Их необходимо добавить в приложение.

Для создания `CFindReplaceDialog` объекта используйте предоставленный конструктор (не имеющий аргументов). Поскольку это немодальное диалоговое окно, выделяйте объект в куче с помощью **`new`** оператора, а не в стеке.

После `CFindReplaceDialog` создания объекта необходимо вызвать функцию [создания](#create) члена, чтобы создать и отобразить диалоговое окно.

Используйте структуру [m_fr](#m_fr) для инициализации диалогового окна перед вызовом метода `Create` . `m_fr`Структура имеет тип [финдреплаце](/windows/win32/api/commdlg/ns-commdlg-findreplacew). Дополнительные сведения об этой структуре см. в Windows SDK.

Чтобы родительское окно было уведомлено о запросах Find/Replace, необходимо использовать функцию Windows [регистервиндовмессаже](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) и использовать в окне фрейма макрос схемы сообщения [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) , который обрабатывает это зарегистрированное сообщение.

Можно определить, решил ли пользователь закрыть диалоговое окно с помощью `IsTerminating` функции члена.

`CFindReplaceDialog`зависит от файла COMMDLG.DLL, поставляемого с Windows версии 3,1 и более поздних версий.

Чтобы настроить диалоговое окно, создайте производный класс от `CFindReplaceDialog` , предоставьте пользовательский шаблон диалогового окна и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Все необработанные сообщения должны передаваться в базовый класс.

Настройка функции-обработчика не является обязательной.

Дополнительные сведения об использовании см `CFindReplaceDialog` . в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс.h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>Диалоговое CFindReplaceDialog:: диалоговое CFindReplaceDialog

Формирует объект `CFindReplaceDialog`.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Примечания

Поскольку `CFindReplaceDialog` объект является немодальным диалоговым окном, его необходимо создать в куче с помощью **`new`** оператора.

Во время уничтожения платформа пытается выполнить **Удаление** в указателе на диалоговое окно. Если в стеке было создано диалоговое окно, то **`this`** указатель не существует, и может возникнуть неопределенное поведение.

Дополнительные сведения о построении `CFindReplaceDialog` объектов см. в обзоре [диалоговое CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) . Используйте функцию члена [диалоговое CFindReplaceDialog:: Create](#create) для вывода диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a>Диалоговое CFindReplaceDialog:: Create

Создает и отображает объект диалогового окна найти или найти/заменить в зависимости от значения `bFindDialogOnly` .

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*бфинддиалогонли*<br/>
Задайте для этого параметра значение TRUE, чтобы отобразить диалоговое окно **поиска** . Задайте для него значение FALSE, чтобы отобразить диалоговое окно **Найти/заменить** .

*лпсзфиндвхат*<br/>
Указатель на строку поиска по умолчанию при появлении диалогового окна. Если значение равно NULL, диалоговое окно не содержит строку поиска по умолчанию.

*лпсзреплацевис*<br/>
Указатель на строку замены по умолчанию при появлении диалогового окна. Если значение равно NULL, то диалоговое окно не содержит строку замены по умолчанию.

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна в сочетании с помощью побитового оператора или. Значение по умолчанию — FR_DOWN, которое указывает, что поиск должен выполняться в направлении вниз. Дополнительные сведения об этих флагах см. в описании структуры [финдреплаце](/windows/win32/api/commdlg/ns-commdlg-findreplacew) в Windows SDK.

*ппарентвнд*<br/>
Указатель на родительский узел или окно-владелец диалогового окна. Это окно, которое будет принимать специальное сообщение, указывающее, что запрошено действие найти/заменить. Если значение равно NULL, используется главное окно приложения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект диалогового окна был успешно создан; в противном случае — 0.

### <a name="remarks"></a>Примечания

Чтобы родительское окно было уведомлено о запросах Find/Replace, необходимо использовать функцию Windows [регистервиндовмессаже](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) , возвращаемое значение которой является номером сообщения, уникальным для экземпляра приложения. В окне фрейма должна быть запись схемы сообщений, объявляющая функцию обратного вызова ( `OnFindReplace` в следующем примере), которая обрабатывает это зарегистрированное сообщение. В следующем фрагменте кода приведен пример того, как это сделать для класса окна фрейма с именем `CMyRichEditView` :

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

Внутри `OnFindReplace` функции вы интерпретируете намерения пользователя с помощью методов [диалоговое CFindReplaceDialog:: FindNext](#findnext) и [диалоговое CFindReplaceDialog::](#isterminating) -a, а также создаете код для операций поиска и замены.

### <a name="example"></a>Пример

  См. пример для [диалоговое CFindReplaceDialog:: диалоговое CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a>Диалоговое CFindReplaceDialog:: FindNext

Вызовите эту функцию из функции обратного вызова, чтобы определить, нужно ли пользователю найти следующее вхождение строки поиска.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет найти следующее вхождение строки поиска; в противном случае — 0.

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>Диалоговое CFindReplaceDialog:: Жетфиндстринг

Вызовите эту функцию из функции обратного вызова, чтобы получить строку по умолчанию для поиска.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Искомая строка по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>Диалоговое CFindReplaceDialog:: "уведомление"

Вызовите эту функцию, чтобы получить указатель на текущее диалоговое окно найти замену.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*lParam*<br/>
Значение *lParam* , передаваемое функции члена окна фрейма `OnFindReplace` .

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущее диалоговое окно.

### <a name="remarks"></a>Примечания

Он должен использоваться в функции обратного вызова для доступа к текущему диалоговому окну, вызова его функций члена и доступа к `m_fr` структуре.

### <a name="example"></a>Пример

Пример регистрации обработчика Онфиндреплаце для получения уведомлений из диалогового окна "Поиск и замена" см. в разделе [диалоговое CFindReplaceDialog:: Create](#create) .

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>Диалоговое CFindReplaceDialog:: Жетреплацестринг

Вызовите эту функцию, чтобы получить текущую строку замены.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка по умолчанию, по которой заменяются найденные строки.

### <a name="example"></a>Пример

  См. пример для [диалоговое CFindReplaceDialog:: жетфиндстринг](#getfindstring).

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a>Диалоговое CFindReplaceDialog:: завершения

Вызовите эту функцию в функции обратного вызова, чтобы определить, решил ли пользователь закрыть диалоговое окно.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь решил закрыть диалоговое окно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если эта функция возвращает ненулевое значение, следует вызвать `DestroyWindow` функцию члена текущего диалогового окна и установить для любой переменной указателя диалогового окна значение null. При необходимости можно также сохранить последний введенный текст в поле Найти/заменить и использовать его для инициализации следующего диалогового окна Найти/заменить.

### <a name="example"></a>Пример

  См. пример для [диалоговое CFindReplaceDialog:: жетфиндстринг](#getfindstring).

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a>Диалоговое CFindReplaceDialog:: m_fr

Используется для настройки `CFindReplaceDialog` объекта.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Примечания

`m_fr`представляет собой структуру типа [финдреплаце](/windows/win32/api/commdlg/ns-commdlg-findreplacew). Его члены хранят характеристики объекта диалогового окна. После создания `CFindReplaceDialog` объекта можно использовать `m_fr` для изменения различных значений в диалоговом окне.

Дополнительные сведения об этой структуре см. в описании `FINDREPLACE` структуры в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [диалоговое CFindReplaceDialog:: диалоговое CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a>Диалоговое CFindReplaceDialog:: Матчкасе

Вызовите эту функцию, чтобы определить, нужно ли точно сопоставить регистр поиска строки find.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет найти вхождения строки поиска, которая точно соответствует регистру строки поиска; в противном случае — 0.

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>Диалоговое CFindReplaceDialog:: Матчвхолеворд

Вызовите эту функцию, чтобы определить, желаете ли пользователь сопоставлять только целые слова.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет сопоставить только целые слова строки поиска. в противном случае — 0.

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a>Диалоговое CFindReplaceDialog:: ReplaceAll

Вызовите эту функцию, чтобы определить, хочет ли пользователь заменять все вхождения строки.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь запросил, чтобы все строки, соответствующие строке замены, были заменены. в противном случае — 0.

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>Диалоговое CFindReplaceDialog:: Реплацекуррент

Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить текущее слово.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь запросил, чтобы строка, выбранная в текущий момент, была заменена строкой замены. в противном случае — 0.

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a>Диалоговое CFindReplaceDialog:: Сеарчдовн

Вызовите эту функцию, чтобы определить, должен ли пользователь искать переходы в направлении вниз.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет, чтобы поиск продвигается в направлении вниз; 0, если пользователь хочет, чтобы поиск пройдет в направлении вверх.

## <a name="see-also"></a>См. также раздел

[Класс Ккоммондиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
