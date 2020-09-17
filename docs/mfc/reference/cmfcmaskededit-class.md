---
title: CMFCMaskedEdit класс
ms.date: 11/04/2016
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
ms.openlocfilehash: 26617f10605fe2a8a94adcc477cccab7e2ba4919
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754219"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit класс

Класс `CMFCMaskedEdit` поддерживает элемент управления отсылкой, который проверяет пользовательский вход в маску и отображает проверенные результаты в соответствии с шаблоном.

## <a name="syntax"></a>Синтаксис

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|Конструктор по умолчанию.|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCMaskedEdit::DisableMask](#disablemask)|Отражает проверку ввода пользователя.|
|[CMFCMaskedEdit::EnableGetMaskedCharsТолько](#enablegetmaskedcharsonly)|Уточняется, получает `GetWindowText` ли метод только символы в масках.|
|[CMFCMaskedEdit::EnableMask](#enablemask)|Инициализирует управление отработками в масках.|
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Определяет, выбирает ли элемент управления отвечения в масках определенные группы пользовательских ввода или все пользовательские ввода.|
|[CMFCMaskedEdit::EnableSetMaskedCharsТолько](#enablesetmaskedcharsonly)|Уточняется, проверяется ли текст только против персонажей в масках или против всей маски.|
|`CMFCMaskedEdit::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Извлекает проверенный текст из управления редактирования в масках.|
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Определяет строку допустимых символов, которые пользователь может ввести.|
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Отображает подсказку в элементе управления отображением в масках.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Вызывается фреймворком для проверки указанного символа в отношении соответствующего символа маски.|

## <a name="remarks"></a>Примечания

Выполните следующие действия, чтобы использовать `CMFCMaskedEdit` элемент управления в приложении:

1. Встраивайте `CMFCMaskedEdit` объект в класс окон.

2. Позвоните в [CMFCMaskedEdit::EnableMask](#enablemask) метод, чтобы указать маску.

3. Позвоните в [метод CMFCMaskedEdit::SetValidChars,](#setvalidchars) чтобы указать список действительных символов.

4. Позвоните в метод [CMFCMaskedEdit::SetWindowText,](#setwindowtext) чтобы указать текст по умолчанию для управления редактированием в масках.

5. Позвоните в [метод CMFCMaskedEdit::GetWindowText](#getwindowtext) для получения проверенного текста.

Если вы не называете один или несколько методов для инициализации маски, действительных символов и текста по умолчанию, замаскированный элемент управления редактированием ведет себя так же, как ведет себя стандартный элемент управления редактированием.

## <a name="example"></a>Пример

В следующем примере показано, как настроить маску (например, `EnableMask` номер телефона) с помощью метода `SetValidChars` создания маски для управления редактированием в маске, метода указания строки действительных символов, которые пользователь может ввести, и `SetWindowText` метод отображения запроса в элементе управления редактированием в масках. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxmaskededit.h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a>CMFCMaskedEdit::DisableMask

Отражает проверку ввода пользователя.

```cpp
void DisableMask();
```

### <a name="remarks"></a>Примечания

Если проверка ввода пользователя отключена, управление элементами управления с маской ведет себя как стандартный элемент управления отсвагиванием.

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a>CMFCMaskedEdit::EnableGetMaskedCharsТолько

Уточняется, получает `GetWindowText` ли метод только символы в масках.

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) ПРАВДА указать, что [метод CMFCMaskedEdit::GetWindowText](#getwindowtext) получить только в масках символов; FALSE указать, что метод получить весь текст. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте этот метод для извлечения символов в масках. Затем создайте элемент управления в маске, который соответствует номеру телефона, например (425) 555-0187. Если вы `GetWindowText` называете метод, он возвращает "4255550187". Если вы откажетесь от извлечения символов в масках, `GetWindowText` метод возвращает текст, отображаемый в элементару редактирования, например "(425) 555-0187".

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a>CMFCMaskedEdit::EnableMask

Инициализирует управление отработками в масках.

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Параметры

*lpszMask*<br/>
(в) Строка маски, которая определяет тип символа, который может отображаться в каждой позиции в пользовательском входе. Длина строк *lpszInputTemplate* и *lpszMask* должна быть одинаковой. Более подробную информацию о символах масок можно просмотреть в разделе «Замечания».

*lpszInputTemplate*<br/>
(в) Строка шаблона маски, которая определяет буквальные символы, которые могут отображаться в каждой позиции в пользовательском входе. Используйте символ подчеркивателя ('') в качестве заполнителя персонажа. Длина строк *lpszInputTemplate* и *lpszMask* должна быть одинаковой.

*chmaskInputTemplate*<br/>
(в) Символ по умолчанию, который фреймворк заменяет каждому недействительному символу в входе пользователя. Значение этого параметра по умолчанию подчеркивается ('.

*lpszValid*<br/>
(в) Строка, содержащая набор допустимых символов. NULL указывает, что все символы являются действительными. Значение этого параметра по умолчанию является NULL.

### <a name="remarks"></a>Примечания

Используйте этот метод для создания маски для управления отсылки к отодвине. Выберите класс `CMFCMaskedEdit` из класса и переопределить [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) метод использовать свой собственный код для пользовательской обработки маски.

В следующей таблице приведены символы маски по умолчанию:

|Персонаж маски|Определение|
|--------------------|----------------|
|D|Цифра.|
|d|Digit или пространство.|
|+|Плюс (''), минус ('-'), или пространство.|
|C|Алфавитный характер.|
|с|Алфавитный характер или пространство.|
|Объект|Алфавитный характер.|
|а|Алфавитный характер или пространство.|
|*|Печатаемый персонаж.|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a>CMFCMaskedEdit::EnableSelectByGroup

Определяет, позволяет ли элемент управления отвагированию в масках выбрать определенные группы ввода или все входные данные.

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для выбора только групп; FALSE, чтобы выбрать весь текст. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы указать, позволяет ли элемент управления редактированием в масках выбрать по группе или весь текст.

По умолчанию выбор по группам включен. В этом случае пользователь может выбрать только непрерывные группы действительных символов.

Например, для проверки номера телефона можно использовать следующий элемент управления отвазным образом:

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

Если выбор по группе включен, пользователь может получить только "425", "555" или "0187" строки групп. Если выбор группы отключен, пользователь может получить весь текст номера телефона: "(425) 555-0187".

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a>CMFCMaskedEdit::EnableSetMaskedCharsТолько

Уточняется, проверяется ли текст только против символов в масках или против всей маски.

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для проверки пользовательского ввода только в отношении символов в масках; FALSE для проверки против всей маски. Значение по умолчанию — TRUE.

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a>CMFCMaskedEdit::GetWindowText

Извлекает проверенный текст из управления редактирования в масках.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>Параметры

*lpszStringBuf*<br/>
(ваут) Указатель на буфер, который получает текст из элемента управления редактирования.

*nMaxCount*<br/>
(в) Максимальное количество символов для получения.

*rstrString*<br/>
(ваут) Ссылка на объект строки, который получает текст из управления редактирования.

### <a name="return-value"></a>Возвращаемое значение

Перегрузка первого метода возвращает количество байтов строки, скопированных в буфер параметра *lpszStringBuf;* 0, если в замаскированном элементе управления редактирования нет текста.

### <a name="remarks"></a>Примечания

Этот метод копирует текст из замаскированного элемента управления редактированием в буфер *lpszStringBuf* или строку *rstrString.*

Этот метод переопределяет [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a>CMFCMaskedEdit::IsMaskedChar

Вызывается фреймворком для проверки указанного символа в отношении соответствующего символа маски.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>Параметры

*chChar*<br/>
(в) Символ, который необходимо проверить.

*chMaskChar*<br/>
(в) Соответствующий символ из строки маски.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если параметр *chChar* является типом символа, разрешенного параметром *chMaskChar;* в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Переопределить этот метод для проверки символов ввода по своему усмотрению. Для получения дополнительной информации о [CMFCMaskedEdit::EnableMask](#enablemask) символах маски см.

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a>CMFCMaskedEdit::SetValidChars

Определяет строку допустимых символов, которые пользователь может ввести.

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Параметры

*lpszValid*<br/>
(в) Строка, содержащая набор допустимых символов ввода. NULL означает, что все символы действительны. Значение этого параметра по умолчанию является NULL.

### <a name="remarks"></a>Примечания

Используйте этот метод для определения списка действительных символов. Если символв ввода не находится в этом списке, управление редактированием в маске не принимает его.

Следующий пример кода принимает только гексадецимальные числа.

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a>CMFCMaskedEdit::SetWindowText

Отображает подсказку в элементе управления отображением в масках.

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*lpszString*<br/>
(в) Указывает на нулевую строку, которая будет использоваться в качестве запроса.

### <a name="remarks"></a>Примечания

Этот метод устанавливает текст управления.

Этот метод переопределяет [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)
