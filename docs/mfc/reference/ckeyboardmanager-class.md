---
title: Класс CKeyboardManager
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: e67bbb18b6a87edfaa4bc4c410ec28eb613ed51d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841497"
---
# <a name="ckeyboardmanager-class"></a>Класс CKeyboardManager

Управляет таблицами клавиш быстрого доступа для окна главного и дочерних фреймов.

## <a name="syntax"></a>Синтаксис

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|[CKeyboardManager:: CKeyboardManager](#ckeyboardmanager)|Формирует объект `CKeyboardManager`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[CKeyboardManager:: CleanUp](#cleanup)|Очищает таблицы сочетаний клавиш.|
|[CKeyboardManager:: Финддефаултакцелератор](#finddefaultaccelerator)|Извлекает сочетание клавиш по умолчанию для указанной команды и окна.|
|[CKeyboardManager:: Искэйхандлед](#iskeyhandled)|Определяет, обрабатывается ли ключ с помощью таблицы сочетаний клавиш.|
|[CKeyboardManager:: Искэйпринтабле](#iskeyprintable)|Указывает, доступен ли символ для печати.|
|[CKeyboardManager:: Исшоваллакцелераторс](#isshowallaccelerators)|Указывает, отображаются ли в меню все сочетания клавиш для команды или только сочетание клавиш по умолчанию.|
|[CKeyboardManager:: LoadState](#loadstate)|Загружает таблицы сочетаний клавиш из реестра Windows.|
|[CKeyboardManager:: Ресеталл](#resetall)|Перезагружает таблицы сочетаний клавиш из ресурса приложения.|
|[CKeyboardManager:: SaveState](#savestate)|Сохраняет таблицы сочетаний клавиш в реестре Windows.|
|[CKeyboardManager:: Шоваллакцелераторс](#showallaccelerators)|Указывает, отображаются ли в платформе все сочетания клавиш для всех команд или одна комбинация клавиш для каждой команды. Этот метод не влияет на команды, которые имеют только одну связанную клавишу.|
|[CKeyboardManager:: Транслатечартауппер](#translatechartoupper)|Преобразует символ в его верхнюю регистр.|
|[CKeyboardManager:: Упдатеакцелтабле](#updateacceltable)|Обновляет таблицу сочетаний клавиш с помощью новой таблицы сочетаний клавиш.|

## <a name="remarks"></a>Примечания

Члены этого класса позволяют сохранять и загружать таблицы сочетаний клавиш в реестр Windows, использовать шаблон для обновления коротких ключевых таблиц и находить сочетание клавиш по умолчанию для команды в окне фрейма. Кроме того, `CKeyboardManager` объект позволяет управлять отображением сочетаний клавиш для пользователя.

Не следует создавать `CKeyboardManager` объект вручную. Он будет создан автоматически платформой приложения. Однако в процессе инициализации приложения следует вызвать [CWinAppEx:: иниткэйбоардманажер](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) . Чтобы получить указатель на диспетчер клавиатуры для своего приложения, вызовите [CWinAppEx:: жеткэйбоардманажер](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).

## <a name="example"></a>Пример

В следующем примере показано, как получить указатель на `CKeyboardManager` объект из `CWinAppEx` класса и как отобразить все сочетания клавиш, связанные с командами меню. Этот фрагмент кода является частью [примера пользовательских страниц](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкскэйбоардманажер.h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a> CKeyboardManager:: CKeyboardManager

Формирует объект `CKeyboardManager`.

```
CKeyboardManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев нет необходимости создавать `CKeyboardManager` напрямую. По умолчанию платформа создает ее. Чтобы получить указатель на `CKeyboardManager` , вызовите метод [CWinAppEx:: жеткэйбоардманажер](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Если создать его вручную, необходимо инициализировать его с помощью метода [CWinAppEx:: иниткэйбоардманажер](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a> CKeyboardManager:: CleanUp

Освобождает `CKeyboardManager` ресурсы и удаляет все сочетания клавиш.

```
static void CleanUp();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о сочетаниях клавиш см. в разделе [Настройка клавиатуры и мыши](../../mfc/keyboard-and-mouse-customization.md).

Вам не нужно вызывать эту функцию при выходе из приложения, так как инфраструктура вызывает ее автоматически во время выхода приложения.

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a> CKeyboardManager:: Финддефаултакцелератор

Извлекает сочетание клавиш по умолчанию для указанной команды и окна.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор команды.

*str*<br/>
[out] Ссылка на объект `CString`.

*пвндфраме*<br/>
окне Указатель на окно фрейма.

*бисдефаултфраме*<br/>
окне Указывает, является ли окно фрейма окном фрейма по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если ярлык найден; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод выполняет поиск команды, заданной параметром *уикмд* , и получает сочетание клавиш по умолчанию. Затем метод принимает строку, связанную с этим сочетанием клавиш, и записывает значение в параметр *str* .

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a> CKeyboardManager:: Искэйхандлед

Определяет, обрабатывается ли указанный ключ [классом CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md).

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Параметры

*нкэй*\
окне Проверяемый ключ.

*фвирт*\
окне Задает поведение сочетания клавиш. Список возможных значений см. в разделе «доступ к [структуре](/windows/win32/api/winuser/ns-winuser-accel)».

*пвндфраме*\
окне Окно фрейма. Этот метод определяет, обрабатывается ли в этом кадре сочетание клавиш.

*бисдефаултфраме*\
окне Логический параметр, указывающий, является ли *пвндфраме* окном фрейма по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сочетание клавиш обработано. Значение FALSE, если ключ не обрабатывается или если *пвндфраме* имеет значение null.

### <a name="remarks"></a>Примечания

Входные параметры должны соответствовать записи в таблице сочетаний клавиш для *нкэй* и *фвирт* , чтобы определить, обрабатывается ли сочетание клавиш в *пвндфраме*.

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a> CKeyboardManager:: Искэйпринтабле

Указывает, доступен ли символ для печати.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Параметры

*nChar*\
окне Символ, который проверяет этот метод.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если символ доступен для печати, нуль, если нет.

### <a name="remarks"></a>Примечания

Этот метод завершается ошибкой, если вызов [жеткэйбоардстате](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) завершается ошибкой.

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a> CKeyboardManager:: Исшоваллакцелераторс

Указывает, отображаются ли в меню все сочетания клавиш, связанные с командами меню, или только сочетания клавиш по умолчанию.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если приложение перечисляет все сочетания клавиш для команд меню; 0, если приложение отображает только сочетания клавиш по умолчанию.

### <a name="remarks"></a>Примечания

Приложение выводит список сочетаний клавиш для команд меню в строке меню. Используйте функцию [CKeyboardManager:: шоваллакцелераторс](#showallaccelerators) , чтобы указать, отображает ли приложение все сочетания клавиш или только сочетания клавиш по умолчанию.

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a> CKeyboardManager:: LoadState

Загружает таблицы сочетаний клавиш из реестра Windows.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Путь реестра, в который `CKeyboardManager` сохраняются данные.

*пдефаултфраме*<br/>
окне Указатель на окно фрейма, используемое в качестве окна по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние было успешно загружено, или 0 в противном случае.

### <a name="remarks"></a>Примечания

Если параметр *лпсзпрофиленаме* имеет значение null, этот метод проверяет расположение данных в реестре по умолчанию `CKeyboardManager` . Расположение реестра по умолчанию указывается [классом CWinAppEx](../../mfc/reference/cwinappex-class.md). Данные должны быть предварительно записаны с помощью метода [CKeyboardManager:: SaveState](#savestate).

Если не указать окно по умолчанию, будет использоваться главное окно приложения.

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a> CKeyboardManager:: Ресеталл

Перезагружает таблицы сочетаний клавиш из ресурса приложения.

```cpp
void ResetAll();
```

### <a name="remarks"></a>Примечания

Эта функция очищает ярлыки, хранящиеся в `CKeyboardManager` экземпляре. Затем состояние диспетчера клавиатуры будет перезагружено из ресурса приложения.

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a> CKeyboardManager:: SaveState

Сохраняет таблицы сочетаний клавиш в реестре Windows.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Путь реестра для сохранения `CKeyboardManager` состояния.

*пдефаултфраме*<br/>
окне Указатель на окно фрейма, которое станет окном по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние диспетчера клавиатуры сохранено успешно, или 0 в противном случае.

### <a name="remarks"></a>Примечания

Если параметр *лпсзпрофиленаме* имеет значение null, этот метод записывает `CKeyboardManager` состояние в расположение по умолчанию, заданное [классом CWinAppEx](../../mfc/reference/cwinappex-class.md). Если указать расположение, данные можно загрузить позже с помощью метода [CKeyboardManager:: LoadState](#loadstate).

Если окно по умолчанию не задано, в качестве окна по умолчанию будет использоваться главное окно фрейма.

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a> CKeyboardManager:: Шоваллакцелераторс

Отображает все сочетания клавиш, связанные с командами меню.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Параметры

*бшовалл*<br/>
окне Если задано значение TRUE, будут отображаться все сочетания клавиш. Если задано значение FALSE, то отображается только первый ярлык.

*лпсзделимитер*<br/>
окне Строка для вставки между сочетаниями клавиш. Этот разделитель не действует, если отображается только одна комбинация клавиш.

### <a name="remarks"></a>Примечания

По умолчанию, если с командой связано несколько сочетаний клавиш, будет отображаться только первый ярлык. Эта функция позволяет получить список всех сочетаний клавиш, связанных со всеми командами.

Сочетания клавиш будут перечислены в строке меню рядом с командой. Если отображаются все сочетания клавиш, строка, предоставленная *лпсзделимитер* , будет разделять отдельные сочетания клавиш.

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a> CKeyboardManager:: Транслатечартауппер

Преобразует символ в его верхнюю регистр.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Параметры

*nChar*<br/>
окне Преобразуемый символ.

### <a name="return-value"></a>Возвращаемое значение

Символ, который является верхним регистром входного параметра.

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a> CKeyboardManager:: Упдатеакцелтабле

Обновляет таблицу сочетаний клавиш с помощью новой таблицы сочетаний клавиш.

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*птемплате*<br/>
окне Указатель на шаблон документа.

*лпакцел*<br/>
окне Указатель на новую комбинацию клавиш.

*нсизе*<br/>
окне Размер новой таблицы ярлыков.

*пдефаултфраме*<br/>
окне Указатель на окно фрейма по умолчанию.

*хакцелнев*<br/>
окне Маркер новой таблицы ярлыков.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция используется для замены существующей таблицы ярлыка новыми сочетаниями клавиш для нескольких объектов окна фрейма. Функция получает шаблон документа в качестве параметра для получения доступа ко всем объектам окна кадров, подключенным к данному шаблону документа.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx:: Иниткэйбоардманажер](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Настройка клавиатуры и мыши](../../mfc/keyboard-and-mouse-customization.md)
