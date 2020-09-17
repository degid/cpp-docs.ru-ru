---
title: Класс CEditView
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: 33b5975eea534eeaf308f73b5ca7fca2cd76787f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753202"
---
# <a name="ceditview-class"></a>Класс CEditView

Тип класса представления, который предоставляет функциональные возможности элемента управления "поле ввода" Windows и может использоваться для реализации простой функциональности текстового редактора.

## <a name="syntax"></a>Синтаксис

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CEditView:CEditView](#ceditview)|Создает объект типа `CEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CEditView:FindText](#findtext)|Поиск строки в тексте.|
|[CEditView:GetBufferLength](#getbufferlength)|Получает длину буфера символов.|
|[CEditView:GetEditCtrl](#geteditctrl)|Обеспечивает доступ `CEdit` к части `CEditView` объекта (управление отсвакой Windows).|
|[CEditView::GetPrinterFont](#getprinterfont)|Извлекает текущий шрифт принтера.|
|[CEditView::GetSelectedText](#getselectedtext)|Извлекает текущий выбор текста.|
|[CEditView:LockBuffer](#lockbuffer)|Блокирует буфер.|
|[CEditView::PrintInsideRect](#printinsiderect)|Рендерс текста внутри заданного прямоугольника.|
|[CEditView::SerializeRaw](#serializeraw)|Сериализирует `CEditView` объект на диске как необработанный текст.|
|[CEditView::SetPrinterFont](#setprinterfont)|Устанавливает новый шрифт принтера.|
|[CEditView::SetTabStops](#settabstops)|Устанавливает остановки вкладок как для отображения экрана, так и для печати.|
|[CEditView::UnlockBuffer](#unlockbuffer)|Открывает буфер.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|Находит следующее появление строки текста.|
|[CEditView::OnReplaceAll](#onreplaceall)|Заменяет все случаи данной строки новой строкой.|
|[CEditView::ReplaceSel](#onreplacesel)|Заменяет текущий выбор.|
|[CEditView::OnTextNotFound](#ontextnotfound)|Вызывается, когда операция поиска не соответствует любому дальнейшему тексту.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|Стиль по умолчанию `CEditView`для объектов типа .|

## <a name="remarks"></a>Примечания

Класс `CEditView` предоставляет следующие дополнительные функции:

- Печать.

- Найти и заменить.

Поскольку `CEditView` класс является `CView`производной `CEditView` от класса, объекты класса могут использоваться с документами и шаблонами документов.

Текст `CEditView` каждого элемента управления хранится в своем глобальном объекте памяти. Ваше приложение может иметь `CEditView` любое количество объектов.

Создавайте объекты типа, `CEditView` если требуется окно редактирования с указанной выше функциональностью, или простофункциональность текстового редактора. Объект `CEditView` может занимать всю область клиента окна. Вывести свои `CEditView` собственные классы, чтобы добавить или изменить основную функциональность, или объявить классы, которые могут быть добавлены в шаблон документа.

Реализация класса `CEditView` по умолчанию обрабатывает следующие команды: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT и ID_FILE_PRINT.

Лимит символов `CEditView` по умолчанию составляет \* (1024 1024 - 1 - 1048575). Это можно изменить, позвонив EM_LIMITTEXT функции базового элемента управления правки. Тем не менее, ограничения различны в зависимости от операционной системы и типа управления отсеиванием (одиночный или многолинейный). Для получения дополнительной информации об этих ограничениях [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)см.

Чтобы изменить этот лимит в элементе управления, переизобить функцию `OnCreate()` для вашего `CEditView` класса и вставить следующую строку кода:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Объекты `CEditView` типа (или типов, `CEditView`полученных из) имеют следующие ограничения:

- `CEditView`не реализует истинное то, что вы видите, это то, что вы получаете (WYSIWYG) редактирования. Там, где есть выбор между читаемостью на `CEditView` экране и соответствием печатного вывода, выбирает для чтения экрана.

- `CEditView`может отображать текст только одним шрифтом. Специальный форматирование символов не поддерживается. См класс [CRichEditView](../../mfc/reference/cricheditview-class.md) для больших возможностей.

- Количество текста, `CEditView` содержащего банку, ограничено. Ограничения такие же, как `CEdit` и для управления.

Для получения `CEditView`дополнительной информации о , см. [Производные Классы просмотра доступны в MFC](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="ceditviewceditview"></a><a name="ceditview"></a>CEditView:CEditView

Создает объект типа `CEditView`.

```
CEditView();
```

### <a name="remarks"></a>Примечания

После построения объекта необходимо вызвать [CWnd::Create](../../mfc/reference/cwnd-class.md#create) function перед тем, как будет использоваться элемент управления отсеивания. Если вы получаете `CEditView` класс из и `CWinApp::AddDocTemplate`добавляете его в шаблон с `Create` помощью, фреймворк вызывает как этот конструктор, так и функцию.

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dwStyleDefault

Содержит стиль объекта `CEditView` по умолчанию.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Примечания

Передайте этот статический член в качестве параметра *dwStyle* `Create` функции для получения стиля по умолчанию для `CEditView` объекта.

## <a name="ceditviewfindtext"></a><a name="findtext"></a>CEditView:FindText

Вызов `FindText` функции для `CEditView` поиска текстового буфера объекта.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который можно найти.

*bСледующий*<br/>
Определяет направление поиска. Если true, направление поиска находится в конце буфера. Если FALSE, направление поиска находится к началу буфера.

*bCase*<br/>
Уточняется, является ли поиск конфиденциальным случаем. Если правда, поиск является чувствительным случаем. Если FALSE, поиск не является случае чувствительным.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если текст поиска найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция ищет текст в буфере для текста, указанного *lpszFind*, начиная с текущего выбора, в направлении, указанном *bNext,* и с чувствительностью случая, указанной *bCase*. Если текст найден, он устанавливает выделение к найденного тексту и возвращает ненулевое значение. Если текст не найден, функция возвращает 0.

Обычно вам не нужно вызывать `FindText` функцию, `OnFindNext`если вы `FindText`не переопределить, который вызывает.

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView:GetBufferLength

Вызовите эту функцию участника, чтобы получить количество символов, наданных в настоящее время в буфере управления редактирования, не включая терминатор null.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина строки в буфере.

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView:GetEditCtrl

Вызов, `GetEditCtrl` чтобы получить ссылку на элемент управления отсечения, используемый представлением отсвагиваемого.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CEdit`.

### <a name="remarks"></a>Примечания

Этот элемент управления имеет тип [CEdit,](../../mfc/reference/cedit-class.md)так что вы можете `CEdit` манипулировать управлением отобрачного элемента Windows непосредственно с помощью функций члена.

> [!CAUTION]
> Использование `CEdit` объекта может изменить состояние базового элемента управления изменениями Windows. Например, не следует изменять настройки вкладок с помощью [функции CEdit::SetTabStops,](../../mfc/reference/cedit-class.md#settabstops) поскольку `CEditView` кэширует эти параметры для использования как в элементаре управления изменениями, так и в печати. Вместо этого используйте [CEditView::SetTabStops](#settabstops).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::GetPrinterFont

Позвоните, `GetPrinterFont` чтобы получить указатель на объект [CFont,](../../mfc/reference/cfont-class.md) описывающий текущий шрифт принтера.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFont` объект, опознававший текущий шрифт принтера; NULL, если шрифт принтера не установлен. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Примечания

Если шрифт принтера не установлен, поведение печати `CEditView` по умолчанию класса состоит в том, чтобы распечатать с помощью того же шрифта, используемого для отображения.

Используйте эту функцию для определения текущего шрифта принтера. Если это не нужный шрифт принтера, используйте [CEditView::SetPrinterFont,](#setprinterfont) чтобы изменить его.

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::GetSelectedText

Вызов `GetSelectedText` копирования выбранного текста `CString` в объект, до конца выделения или символ, предшествующий первому символу перевозки-возврату в выборе.

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Параметры

*strResult*<br/>
Ссылка на `CString` объект, который должен получать выбранный текст.

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView:LockBuffer

Вызовите эту функцию участника, чтобы получить указатель на буфер. Буфер не должен быть изменен.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель буфера управления элемента действия.

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::OnFindNext

Поиск текста в буфере для текста, указанного *lpszFind*, в направлении, указанном *bNext*, с чувствительностью случая, указанной *bCase*.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который можно найти.

*bСледующий*<br/>
Определяет направление поиска. Если true, направление поиска находится в конце буфера. Если FALSE, направление поиска находится к началу буфера.

*bCase*<br/>
Уточняется, является ли поиск конфиденциальным случаем. Если правда, поиск является чувствительным случаем. Если FALSE, поиск не является случае чувствительным.

### <a name="remarks"></a>Примечания

Поиск начинается в начале текущего выбора и выполняется через вызов [в FindText.](#findtext) В реализации `OnFindNext` по умолчанию вызовы [OnTextNotFound,](#ontextnotfound) если текст не найден.

Переопределить, `OnFindNext` чтобы изменить `CEditView`способ поиска текста объекта, полученного полученным. `CEditView`звонки, `OnFindNext` когда пользователь выбирает кнопку «Найти следующую» в стандартном диалоговом окне Find.

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::OnReplaceAll

`CEditView`вызовы, `OnReplaceAll` когда пользователь выбирает кнопку «Заменить все» в стандартном диалоговом поле Replace.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который можно найти.

*lpszReplace*<br/>
Текст для замены текста поиска.

*bCase*<br/>
Уточняется, является ли поиск конфиденциальным случаем. Если правда, поиск является чувствительным случаем. Если FALSE, поиск не является случае чувствительным.

### <a name="remarks"></a>Примечания

`OnReplaceAll`поиск текста в буфере для текста, указанного *lpszFind*, с чувствительностью случая, указанной *bCase*. Поиск начинается в начале текущего выбора. Каждый раз, когда поиск текста найдено, эта функция заменяет, что возникновение текста с текстом, указанным *lpszReplace*. Поиск выполняется с помощью вызова [в FindText](#findtext). В реализации по [умолчанию, OnTextNotFound](#ontextnotfound) вызывается, если текст не найден.

Если текущий выбор не соответствует *lpsz'Find,* выбор обновляется до первого появления текста, указанного *lpszFind* и замена не выполняется. Это позволяет пользователю подтвердить, что это то, что он хочет сделать, когда выбор не соответствует тексту, который будет заменен.

Переопределение, `OnReplaceAll` чтобы изменить `CEditView`способ замены текста- производный объект.

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::ReplaceSel

`CEditView`вызовы, `OnReplaceSel` когда пользователь выбирает кнопку «Заменить» в стандартном диалоговом поле Replace.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который можно найти.

*bСледующий*<br/>
Определяет направление поиска. Если true, направление поиска находится в конце буфера. Если FALSE, направление поиска находится к началу буфера.

*bCase*<br/>
Уточняется, является ли поиск конфиденциальным случаем. Если правда, поиск является чувствительным случаем. Если FALSE, поиск не является случае чувствительным.

*lpszReplace*<br/>
Текст для замены найденного текста.

### <a name="remarks"></a>Примечания

После замены выделения, эта функция ищет текст в буфере для следующего появления текста, указанного *lpszFind*, в направлении, указанном *bNext*, с чувствительностью случая, указанной *bCase*. Поиск выполняется с помощью вызова [в FindText](#findtext). Если текст не найден, [называется OnTextNotFound.](#ontextnotfound)

Переопределение, `OnReplaceSel` чтобы изменить `CEditView`способ замены выбранного текста.

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNotFound

Переизбь эту функцию для изменения реализации по умолчанию, которая вызывает функцию `MessageBeep`Windows.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который можно найти.

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::PrintInsideRect

Вызов `PrintInsideRect` для печати текста в прямоугольнике, указанном *прямой линией.*

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства принтера.

*rectLayout*<br/>
Ссылка на объект [CRect](../../atl-mfc-shared/reference/crect-class.md) или [структуру RECT](/windows/win32/api/windef/ns-windef-rect) с указанием прямоугольника, в котором должен быть отрисован текст.

*nИндексСтарт*<br/>
Индекс в буфере первого символа, который будет отрисован.

*nIndexStop*<br/>
Индекс в буфере символа после отображаемого последнего символа.

### <a name="return-value"></a>Возвращаемое значение

Индекс следующего символа, который будет напечатан (т.е. символ, следующий за последним визуализированным символом).

### <a name="remarks"></a>Примечания

Если `CEditView` элемент управления не имеет стиля ES_AUTOHSCROLL, текст заворачивается в прямоугольник рендеринга. Если элемент управления имеет стиль ES_AUTOHSCROLL, текст обрезается на правом краю прямоугольника.

Элемент `rect.bottom` объекта *прямой кишки* изменяется таким образом, что размеры прямоугольника определяют часть исходного прямоугольника, занятого текстом.

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a>CEditView::SerializeRaw

Звоните, `SerializeRaw` `CArchive` чтобы объект прочитал или `CEditView` написал текст в объекте в текстовый файл.

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Ссылка `CArchive` на объект, который хранит сериализованный текст.

### <a name="remarks"></a>Примечания

`SerializeRaw`отличается `CEditView`от внутренней `Serialize` реализации в том, что он читает и пишет только текст, без предшествующих данных описания объекта.

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a>CEditView::SetPrinterFont

Вызов `SetPrinterFont` для установки шрифта принтера к шрифту, указанному *pFont.*

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на объект типа `CFont`. Если NULL, шрифт, используемый для печати, основан на шрифте дисплея.

### <a name="remarks"></a>Примечания

Если вы хотите, чтобы ваше представление всегда использовало `SetPrinterFont` определенный шрифт `OnPreparePrinting` для печати, включите вызов в функцию вашего класса. Эта виртуальная функция называется до печати, поэтому изменение шрифта происходит до печати содержимого представления.

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabStops

Вызов эту функцию для установки стопов вкладок, используемых для отображения и печати.

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Параметры

*nTabStops*<br/>
Ширина каждой остановки вкладки, в диалоговых единицах.

### <a name="remarks"></a>Примечания

Поддерживается только одна ширина вкладки-стоп. (объекты `CEdit` поддерживают несколько ширин вкладок.) Ширины находятся в единицах диалога, которые равны одной четверти средней ширины символа (на основе только алфавитных символов верхнего регистра и нижнего регистра) шрифта, используемого во время печати или отображения. Вы не `CEdit::SetTabStops` должны `CEditView` использовать, потому что необходимо кэшировать значение tab-stop.

Эта функция изменяет только вкладки объекта, для которого он называется. Чтобы изменить остановки вкладки для каждого `CEditView` объекта в `SetTabStops` приложении, позвоните в функцию каждого объекта.

### <a name="example"></a>Пример

Этот фрагмент кода устанавливает вкладку останавливается в управлении на каждого четвертого символа, тщательно измеряя шрифт, который использует элемент управления.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::UnlockBuffer

Вызов эту функцию участника, чтобы разблокировать буфер.

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>Примечания

Позвоните `UnlockBuffer` после того, как вы закончили с помощью указателя, возвращенного [LockBuffer.](#lockbuffer)

## <a name="see-also"></a>См. также раздел

[MFC Образец SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Класс CrichEditView](../../mfc/reference/cricheditview-class.md)
