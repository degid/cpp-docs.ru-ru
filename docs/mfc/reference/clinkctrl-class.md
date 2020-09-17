---
title: Класс CLinkCtrl
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: 80548015ff9f24127280ee94421c8fbda7a647ea
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561418"
---
# <a name="clinkctrl-class"></a>Класс CLinkCtrl

Предоставляет функциональные возможности стандартного элемента управления SysLink Windows.

## <a name="syntax"></a>Синтаксис

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CLinkCtrl:: CLinkCtrl](#clinkctrl)|Формирует объект `CLinkCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CLinkCtrl:: Create](#create)|Создает элемент управления Link и прикрепляет его к `CLinkCtrl` объекту.|
|[CLinkCtrl:: Креатикс](#createex)|Создает элемент управления Link с расширенными стилями и прикрепляет его к `CLinkCtrl` объекту.|
|[CLinkCtrl:: Жетидеалхеигхт](#getidealheight)|Получает идеальную высоту элемента управления "ссылка".|
|[CLinkCtrl:: Жетидеалсизе](#getidealsize)|Вычисляет предпочтительную высоту текста ссылки для текущего элемента управления связью в зависимости от заданной ширины ссылки.|
|[CLinkCtrl:: DataItem](#getitem)|Извлекает состояния и атрибуты элемента управления ссылки.|
|[CLinkCtrl:: Жетитемид](#getitemid)|Возвращает идентификатор элемента управления ссылки.|
|[CLinkCtrl:: Жетитемстате](#getitemstate)|Возвращает состояние элемента управления ссылки.|
|[CLinkCtrl:: Жетитемурл](#getitemurl)|Извлекает URL-адрес, представленный элементом управления ссылки.|
|[CLinkCtrl:: HitTest](#hittest)|Определяет, щелкнул ли пользователь указанную ссылку.|
|[CLinkCtrl:: Сетитем](#setitem)|Задает состояния и атрибуты элемента управления ссылки.|
|[CLinkCtrl:: Сетитемид](#setitemid)|Задает идентификатор элемента управления ссылки.|
|[CLinkCtrl:: Сетитемстате](#setitemstate)|Задает состояние элемента управления ссылки.|
|[CLinkCtrl:: Сетитемурл](#setitemurl)|Задает URL-адрес, представленный элементом управления ссылки.|

## <a name="remarks"></a>Примечания

Элемент управления "ссылка" предоставляет удобный способ встраивания гипертекстовых ссылок в окно. Фактический элемент управления — это окно, которое отображает помеченный текст и запускает соответствующие приложения, когда пользователь щелкает внедренную ссылку. В одном элементе управления поддерживается несколько ссылок, доступ к которым можно получить с помощью индекса, начинающегося с нуля.

Этот элемент управления (и, следовательно, `CLinkCtrl` класс) доступен только для программ, работающих под управлением Windows XP и более поздних версий.

Дополнительные сведения см. в разделе [элемент управления Syslink](/windows/win32/Controls/syslink-overview) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a> CLinkCtrl:: CLinkCtrl

Формирует объект `CLinkCtrl`.

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a> CLinkCtrl:: Create

Создает элемент управления Link и прикрепляет его к `CLinkCtrl` объекту.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*лпсзлинкмаркуп*<br/>
Указатель на строку, завершающуюся нулем, которая содержит помеченный текст для вывода. Дополнительные сведения см. в подразделе «разметка и доступ к ссылкам» раздела [Общие сведения об элементах управления Syslink](/windows/win32/Controls/syslink-overview).

*двстиле*<br/>
Задает стиль элемента управления ссылки. Примените любое сочетание стилей элементов управления. Дополнительные сведения см. в разделе [общие стили элементов управления](/windows/win32/Controls/common-control-styles) `Windows SDK` .

*rect*<br/>
Задает размер и расположение элемента управления ссылки. Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Указывает родительское окно элемента управления ссылки. Оно не должно иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления ссылки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация прошла успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

`CLinkCtrl`Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который создает элемент управления Link и присоединяет его к `CLinkCtrl` объекту. Если вы хотите использовать расширенные стили Windows с элементом управления, вызовите [CLinkCtrl:: креатикс](#createex) вместо `Create` .

Вторая форма `Create` метода является нерекомендуемой. Используйте первую форму, задающую параметр *лпсзлинкмаркуп* .

### <a name="example"></a>Пример

В следующем примере кода определяются две переменные с именами `m_Link1` и `m_Link2` , которые используются для доступа к двум элементам управления "ссылка".

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода создается один элемент управления Link, основанный на расположении другого элемента управления Link. Загрузчик ресурсов создает первый элемент управления ссылки при запуске приложения. Когда приложение входит в метод Онинитдиалог, вы создаете второй элемент управления ссылки относительно положения первого элемента управления ссылки. Затем вы изменяете размер элемента управления второй ссылки в соответствии с отображаемым текстом.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a> CLinkCtrl:: Креатикс

Создает элемент управления Link с расширенными стилями и прикрепляет его к `CLinkCtrl` объекту.

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>Параметры

*лпсзлинкмаркуп*<br/>
Указатель на строку, завершающуюся нулем, которая содержит помеченный текст для вывода. Дополнительные сведения см. в подразделе «разметка и доступ к ссылкам» раздела [Общие сведения об элементах управления Syslink](/windows/win32/Controls/syslink-overview).

*двексстиле*<br/>
Задает расширенный стиль элемента управления "ссылка". Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Задает стиль элемента управления ссылки. Примените любое сочетание стилей элементов управления. Дополнительные сведения см. в разделе [общие стили элементов управления](/windows/win32/Controls/common-control-styles) в Windows SDK.

*rect*<br/>
Задает размер и расположение элемента управления ссылки. Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Указывает родительское окно элемента управления ссылки. Оно не должно иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления ссылки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация прошла успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные константы стиля Windows.

Вторая форма `CreateEx` метода является нерекомендуемой. Используйте первую форму, задающую параметр *лпсзлинкмаркуп* .

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a> CLinkCtrl:: Жетидеалхеигхт

Получает идеальную высоту элемента управления "ссылка".

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идеальная высота элемента управления (в пикселях).

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [LM_GETIDEALHEIGHT](/windows/win32/Controls/lm-getidealheight), как описано в Windows SDK.

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a> CLinkCtrl:: Жетидеалсизе

Вычисляет предпочтительную высоту текста ссылки для текущего элемента управления связью в зависимости от заданной ширины ссылки.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Параметры

*кксмаксвидс*\
окне Максимальная ширина ссылки в пикселях.

*псизе*\
заполняет Указатель на структуру [размера](/windows/win32/api/windef/ns-windef-size) Windows. При возврате из этого метода элемент *CY* `SIZE` структуры содержит идеальную высоту текста ссылки для ширины текста ссылки, заданной параметром *кксмаксвидс*. Элемент *CX* структуры содержит требуемую ширину текста ссылки.

### <a name="return-value"></a>Возвращаемое значение

Предпочтительная высота текста ссылки в пикселях. Возвращаемое значение совпадает со значением элемента *CY* `SIZE` структуры.

### <a name="remarks"></a>Примечания

Пример `GetIdealSize` метода см. в примере в [CLinkCtrl:: Create](#create).

Этот метод отправляет [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) сообщение, описанное в Windows SDK.

## <a name="clinkctrlgetitem"></a><a name="getitem"></a> CLinkCtrl:: DataItem

Извлекает состояния и атрибуты элемента управления ссылки.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на структуру [литем](/windows/win32/api/commctrl/ns-commctrl-litem) для получения сведений об элементе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [LM_GETITEM](/windows/win32/Controls/lm-getitem), как описано в Windows SDK.

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a> CLinkCtrl:: Жетитемид

Возвращает идентификатор элемента управления ссылки.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*стрид*<br/>
Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий идентификатор указанного элемента.

*сзид*<br/>
Строка, завершающаяся нулем, содержащая идентификатор указанного элемента.

*кчид*<br/>
Размер в символах буфера *сзид* .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

> [!NOTE]
> Эта функция также возвращает значение FALSE, если буфер *сзид или Стрид* меньше MAX_LINKID_TEXT.

### <a name="remarks"></a>Примечания

Возвращает идентификатор определенного элемента управления ссылки. Дополнительные сведения см. в [LM_GETITEM](/windows/win32/Controls/lm-getitem) сообщения Win32 в Windows SDK.

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a> CLinkCtrl:: Жетитемстате

Возвращает состояние элемента управления ссылки.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*пнстате*<br/>
Значение указанного элемента состояния.

*статемаск*<br/>
Сочетание флагов, описывающих, какой элемент состояния получить. Список значений см. в описании `state` элемента в структуре [литем](/windows/win32/api/commctrl/ns-commctrl-litem) . Допустимые элементы идентичны тем, которые допускаются в `state` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Извлекает значение указанного элемента состояния определенного элемента управления ссылки. Дополнительные сведения см. в [LM_GETITEM](/windows/win32/Controls/lm-getitem) сообщения Win32 в Windows SDK.

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a> CLinkCtrl:: Жетитемурл

Извлекает URL-адрес, представленный элементом управления ссылки.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*strUrl*<br/>
Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий URL-адрес, представленный указанным элементом.

*сзурл*<br/>
Строка, завершающаяся нулем, содержащая URL-адрес, представленный указанным элементом.

*кчурл*<br/>
Размер в символах буфера *сзурл* .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

> [!NOTE]
> Эта функция также возвращает значение FALSE, если буфер *сзурл или strUrl* меньше MAX_LINKID_TEXT.

### <a name="remarks"></a>Примечания

Извлекает URL-адрес, представленный указанным элементом управления ссылки. Дополнительные сведения см. в [LM_GETITEM](/windows/win32/Controls/lm-getitem) сообщения Win32 в Windows SDK.

## <a name="clinkctrlhittest"></a><a name="hittest"></a> CLinkCtrl:: HitTest

Определяет, щелкнул ли пользователь указанную ссылку.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Параметры

*фти*<br/>
Указатель на `LHITTESTINFO` структуру, содержащую сведения о ссылке, которую щелкнул пользователь.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [LM_HITTEST](/windows/win32/Controls/lm-hittest), как описано в Windows SDK.

## <a name="clinkctrlsetitem"></a><a name="setitem"></a> CLinkCtrl:: Сетитем

Задает состояния и атрибуты элемента управления ссылки.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на структуру [литем](/windows/win32/api/commctrl/ns-commctrl-litem) , содержащую сведения, которые необходимо задать.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [LM_SETITEM](/windows/win32/Controls/lm-setitem), как описано в Windows SDK.

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a> CLinkCtrl:: Сетитемид

Возвращает идентификатор элемента управления ссылки.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*сзид*<br/>
Строка, завершающаяся нулем, содержащая идентификатор указанного элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Задает идентификатор конкретного элемента управления ссылки. Дополнительные сведения см. в [LM_SETITEM](/windows/win32/Controls/lm-setitem) сообщения Win32 в Windows SDK.

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a> CLinkCtrl:: Сетитемстате

Возвращает состояние элемента управления ссылки.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*пнстате*<br/>
Заданное значение заданного элемента State.

*статемаск*<br/>
Сочетание флагов, описывающих заданный элемент состояния. Список значений см. в описании `state` элемента в структуре [литем](/windows/win32/api/commctrl/ns-commctrl-litem) . Допустимые элементы идентичны тем, которые допускаются в `state` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Задает значение указанного элемента состояния конкретного элемента управления ссылки. Дополнительные сведения см. в [LM_SETITEM](/windows/win32/Controls/lm-setitem) сообщения Win32 в Windows SDK.

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a> CLinkCtrl:: Сетитемурл

Задает URL-адрес, представленный элементом управления ссылки.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Параметры

*iLink*<br/>
Индекс элемента управления ссылки.

*сзурл*<br/>
Строка, завершающаяся нулем, содержащая URL-адрес, представленный указанным элементом.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Задает URL-адрес, представленный указанным элементом управления ссылки. Дополнительные сведения см. в [LM_SETITEM](/windows/win32/Controls/lm-setitem) сообщения Win32 в Windows SDK.

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)
