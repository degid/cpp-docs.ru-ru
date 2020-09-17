---
title: Класс CrichEditView
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: b72daac576411b45908d1e91bd86bbd9aeacf738
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754451"
---
# <a name="cricheditview-class"></a>Класс CrichEditView

С [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), обеспечивает функциональность богатого управления рекреацией в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CrichEditView:CRichEditView](#cricheditview)|Формирует объект `CRichEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CrichEditView::AdjustDialogPosition](#adjustdialogposition)|Перемещает диалоговую коробку таким образом, чтобы он не заслонял текущий выбор.|
|[CRichEditView:CanPaste](#canpaste)|Сообщает, содержит ли Clipboard данные, которые могут быть вставлены в представление с богатым реитриетом.|
|[CRichEditView::DoPaste](#dopaste)|Вставляет элемент OLE в этот богатый вид отодвилость.|
|[CrichEditView::FindText](#findtext)|Находит указанный текст, ссылаясь на курсор ожидания.|
|[CrichEditView::FindTextSimple](#findtextsimple)|Находит указанный текст.|
|[CrichEditView:GetCharFormatВыбор](#getcharformatselection)|Извлекает атрибуты форматирования символов для текущего выбора.|
|[CrichEditView:GetDocument](#getdocument)|Получает указатель на связанные [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|
|[CrichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Извлекает элемент OLE, который в настоящее время находится на месте, активно еле в представлении с богатым рекреативным.|
|[CRichEditView:GetMargins](#getmargins)|Получает поля для этого богатого представления отсвазаний.|
|[CRichEditView::GetPageRect](#getpagerect)|Извлекает прямоугольник страницы для этого богатого представления отсвагивания.|
|[CrichEditView:GetPaperSize](#getpapersize)|Получает размер бумаги для этого богатого представления отсвагивания.|
|[CrichEditView:GetParaFormatВыбор](#getparaformatselection)|Извлекает атрибуты форматирования параграфа для текущего выбора.|
|[CRichEditView::GetPrintRect](#getprintrect)|Извлекает прямоугольник печати для этого богатого представления отсваги.|
|[CrichEditView:GetPrintWidth](#getprintwidth)|Получает ширину печати для этого богатого представления отсваги.|
|[CrichEditView:GetRichEditCtrl](#getricheditctrl)|Получает богатый элемент управления ретритами.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|Извлекает выбранный элемент из представления с богатым реитриетом.|
|[CrichEditView:GetTextДлина](#gettextlength)|Извлекает длину текста в представлении с богатым редактированием.|
|[CrichEditView::GetTextLengthEx](#gettextlengthex)|Извлекает количество символов или байтов в богатом представлении редактирования. Расширенный список флагов для метода определения длины.|
|[CrichEditView::InsertFileAsObject](#insertfileasobject)|Вставляет файл в качестве элемента OLE.|
|[CrichEditView::InsertItem](#insertitem)|Вставляет новый элемент в виде элемента OLE.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Сообщает, содержит ли Clipboard данные в формате с богатым редактированием или текстом.|
|[CrichEditView:OnCharEffect](#onchareffect)|Переключает форматирование персонажа для текущего выбора.|
|[CrichEditView::OnParaAlign](#onparaalign)|Изменяет выравнивание абзацев.|
|[CrichEditView::OnUpdateCharEffect](#onupdatechareffect)|Обновляет uI Командования для функций публичного члена символов.|
|[CrichEditView::OnUpdateParaAlign](#onupdateparaalign)|Обновляет uI Командования для функций абзацев.|
|[CRichEditView: :PrintInsideRect](#printinsiderect)|Форматирует указанный текст в данном прямоугольнике.|
|[CRichEditView::PrintPage](#printpage)|Форматы указанного текста в данной странице.|
|[CrichEditView:SetCharFormat](#setcharformat)|Устанавливает атрибуты форматирования символов для текущего выбора.|
|[CRichEditView:SetMargins](#setmargins)|Устанавливает поля для этого богатого представления о ретрите.|
|[CrichEditView::SetPaperSize](#setpapersize)|Устанавливает размер бумаги для этого богатого представления отсвасывания.|
|[CrichEditView:SetParaFormat](#setparaformat)|Устанавливает атрибуты форматирования параграфа для текущего выбора.|
|[CrichEditView::TextNotFound](#textnotfound)|Сброс внутреннее состояние поиска элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CrichEditView::GetClipboardData](#getclipboarddata)|Извлекает объект Clipboard для диапазона в этом богатом представлении правки.|
|[CrichEditView:GetContextMenu](#getcontextmenu)|Извлекает контекстное меню для использования на правой кнопке мыши вниз.|
|[CrichEditView::IsSelected](#isselected)|Указывает, выбран данный элемент OLE или нет.|
|[CrichEditView::OnFindNext](#onfindnext)|Находит следующее появление подстроки.|
|[CrichEditView:OnInitialUpdate](#oninitialupdate)|Обновляет представление при его первом присоединении к документу.|
|[CRichEditView::PasteNativeObject](#onpastenativeobject)|Извлекает данные из элемента OLE.|
|[CrichEditView::OnPrinterChanged](#onprinterchanged)|Устанавливает характеристики печати к данному устройству.|
|[CrichEditView::OnReplaceAll](#onreplaceall)|Заменяет все случаи данной строки новой строкой.|
|[CrichEditView::OnReplaceSel](#onreplacesel)|Заменяет текущий выбор.|
|[CrichEditView::OnTextNotFound](#ontextnotfound)|Ручки уведомление пользователя о том, что запрошенный текст не был найден.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Запросы, чтобы увидеть о `IDataObject`данных на .|
|[CrichEditView::WrapChanged](#wrapchanged)|Настраивает целевое устройство вывода для этого богатого представления `m_nWordWrap`отсвагиваемого, основанного на значении .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CrichEditView::m_nBulletIndent](#m_nbulletindent)|Указывает количество отступа для списков пуль.|
|[CrichEditView::m_nWordWrap](#m_nwordwrap)|Указывает на ограничения обертывания слова.|

## <a name="remarks"></a>Примечания

"Богатый элемент управления редактированием" — это окно, в котором пользователь может вводить и отстранять текст. Текст может быть назначен символ и форматирование абзацев, и может включать встроенные объекты OLE. Управление богатым редактированием обеспечивает интерфейс программирования для форматирования текста. Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для того, чтобы операции форматирования были доступны пользователю.

`CRichEditView`сохраняет текст и форматирование характеристики текста. `CRichEditDoc`ведет список элементов клиента OLE, которые находятся в представлении. `CRichEditCntrItem`обеспечивает доступ к клиенту OL со стороны контейнера.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанных с ними классов) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Например, при использовании богатого представления о редемикировании в приложении MFC см. [WORDPAD](../../overview/visual-cpp-samples.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxrich.h

## <a name="cricheditviewadjustdialogposition"></a><a name="adjustdialogposition"></a>CrichEditView::AdjustDialogPosition

Вызовите эту функцию, чтобы переместить данный диалоговый ящик, чтобы она не заслоняла текущий выбор.

```cpp
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Параметры

*pDlg*<br/>
Указатель на `CDialog` объект.

## <a name="cricheditviewcanpaste"></a><a name="canpaste"></a>CRichEditView:CanPaste

Позвоните в эту функцию, чтобы определить, содержит ли Clipboard информацию, которая может быть вставлена в это богатое представление отсваги.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если Clipboard содержит данные в формате, который может принять это богатое представление для реадформирования; в противном случае, 0.

## <a name="cricheditviewcricheditview"></a><a name="cricheditview"></a>CrichEditView:CRichEditView

Вызовите эту `CRichEditView` функцию для создания объекта.

```
CRichEditView();
```

## <a name="cricheditviewdopaste"></a><a name="dopaste"></a>CRichEditView::DoPaste

Вызовите эту функцию, чтобы вставить элемент OLE в *dataobj* в этот богатый документ/просмотр отсылки от сотре.

```cpp
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Параметры

*dataobj*<br/>
[COleDataObject,](../../mfc/reference/coledataobject-class.md) содержащий данные для вставки.

*CF*<br/>
Нужный формат Clipboard.

*hMetaPict*<br/>
Метафайл, представляющий элемент, который будет вставлен.

### <a name="remarks"></a>Примечания

Платформа называет эту функцию частью реализации [queryAcceptData](#queryacceptdata)по умолчанию.

Эта функция определяет тип пасты на основе результатов обработчика для Paste Special. Если *cf* 0, новый элемент использует текущее культовое представление. Если *cf* является ненулевой и *hMetaPict* не является NULL, новый пункт использует *hMetaPict* для своего представления.

## <a name="cricheditviewfindtext"></a><a name="findtext"></a>CrichEditView::FindText

Вызовите эту функцию, чтобы найти указанный текст и установите его в текущий выбор.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит строку для поиска.

*bCase*<br/>
Указывает, является ли поиск конфиденциальным.

*bWord*<br/>
Указывает, должен ли поиск соответствовать только целым словам, а не частям слов.

*bСледующий*<br/>
Указывает направление поиска. Если true, направление поиска находится в конце буфера. Если FALSE, направление поиска находится к началу буфера.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если *lpszFind* текст найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция отображает курсора ожидания во время операции поиска.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

## <a name="cricheditviewfindtextsimple"></a><a name="findtextsimple"></a>CrichEditView::FindTextSimple

Вызовите эту функцию, чтобы найти указанный текст и установите его в текущий выбор.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит строку для поиска.

*bCase*<br/>
Указывает, является ли поиск конфиденциальным.

*bWord*<br/>
Указывает, должен ли поиск соответствовать только целым словам, а не частям слов.

*bСледующий*<br/>
Указывает направление поиска. Если true, направление поиска находится в конце буфера. Если FALSE, направление поиска находится к началу буфера.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если *lpszFind* текст найден; в противном случае 0.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::FindText](#findtext).

## <a name="cricheditviewgetcharformatselection"></a><a name="getcharformatselection"></a>CrichEditView:GetCharFormatВыбор

Вызовите эту функцию, чтобы получить атрибуты форматирования символов текущего выбора.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Структура [CHARFORMAT2,](/windows/win32/api/richedit/ns-richedit-charformat2w) содержащая атрибуты форматирования символов текущего выбора.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации смотрите [сообщение EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat) и структуру [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewgetclipboarddata"></a><a name="getclipboarddata"></a>CrichEditView::GetClipboardData

Платформа называет эту функцию частью обработки [IRichEditOleCallback::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata).

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Параметры

*lpchrg*<br/>
Указатель на структуру [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) с указанием диапазона символов (и элементов OLE) для копирования на объект данных, указанный *lplpdataobj.*

*dwReco*<br/>
Флаг операции Клипборд. Может быть одним из этих значений.

- RECO_COPY Копия на буфер обмена.

- RECO_CUT Вырезать на клипборде.

- RECO_DRAG операцию перетаскивания (перетащите и падение).

- RECO_DROP операции Drop (перетаскивание и падение).

- RECO_PASTE паста из клипборда.

*lpRichDataObj*<br/>
Указатель на объект [IDataObject,](/windows/win32/api/objidl/nn-objidl-idataobject) содержащий данные Clipboard из богатого управления рекреацией [(IRichEditOle::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
Указатель на переменную указателя, которая `IDataObject` получает адрес объекта, представляющего диапазон, указанный в параметре *lpchrg.* Значение *lplpdataobj* игнорируется при возврате ошибки.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщая об успехе операции. Для получения дополнительной информации о HRESULT, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="remarks"></a>Примечания

Если значение возврата указывает `IRichEditOleCallback::GetClipboardData` на `IDataObject` успех, возвращает доступ *lplpdataobj;* в противном случае, он возвращает тот, доступ к *lpRichDataObj*. Переизобить эту функцию, чтобы предоставить свои собственные данные Clipboard. Реализация этой функции по умолчанию возвращается E_NOTIMPL.

Это передовой overridable.

Для получения дополнительной информации, [см. IRichEditOle::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata), и [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) в Windows SDK и увидеть [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) в Windows SDK.

## <a name="cricheditviewgetcontextmenu"></a><a name="getcontextmenu"></a>CrichEditView:GetContextMenu

Фрейм называет эту функцию частью обработки [IRichEditOleCallback::GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Параметры

*seltyp*<br/>
Тип выбора. Значения типа выбора описаны в разделе Замечания.

*lpoleobj*<br/>
Указатель на `OLEOBJECT` структуру, определяющую первый выбранный объект OLE, если в выборе содержится один или несколько элементов OLE. Если выбор не содержит элементов, *lpoleobj* является NULL. Структура `OLEOBJECT` содержит указатель на v-таблицу объекта OLE.

*lpchrg*<br/>
Указатель на структуру [CHARRANGE,](/windows/win32/api/richedit/ns-richedit-charrange) содержащую текущий выбор.

### <a name="return-value"></a>Возвращаемое значение

Обработка контекстного меню.

### <a name="remarks"></a>Примечания

Эта функция является типичной частью правильной мыши кнопки вниз обработки.

Тип выбора может быть любым сочетанием следующих флагов:

- SEL_EMPTY указывает на отсутствие текущего выбора.

- SEL_TEXT указывает на то, что текущий выбор содержит текст.

- SEL_OBJECT указывает на то, что текущий выбор содержит по крайней мере один элемент OLE.

- SEL_MULTICHAR указывает на то, что текущий выбор содержит более одного символа текста.

- SEL_MULTIOBJECT указывает на то, что текущий выбор содержит более одного объекта OLE.

Реализация по умолчанию возвращает NULL. Это передовой overridable.

Для получения дополнительной информации см. [IRichEditOleCallback::GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu) и [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) в Windows SDK.

## <a name="cricheditviewgetdocument"></a><a name="getdocument"></a>CrichEditView:GetDocument

Вызовите эту функцию, `CRichEditDoc` чтобы получить указатель на связанные с этим представлением.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CRichEditDoc,](../../mfc/reference/cricheditdoc-class.md) связанный с объектом. `CRichEditView`

## <a name="cricheditviewgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>CrichEditView::GetInPlaceActiveItem

Вызовите эту функцию, чтобы получить элемент OLE, который в настоящее время активирован на месте в этом `CRichEditView` объекте.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на один, на месте активного объекта [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) в этом богатом представлении отсваги; NULL, если в настоящее время нет элемента OLE в активном состоянии.

## <a name="cricheditviewgetmargins"></a><a name="getmargins"></a>CRichEditView:GetMargins

Вызовите эту функцию, чтобы получить текущую поля, используемую в печати.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Возвращаемое значение

Поля, используемые в печати, измеряются в MM_TWIPS.

## <a name="cricheditviewgetpagerect"></a><a name="getpagerect"></a>CRichEditView::GetPageRect

Вызовите эту функцию, чтобы получить размеры страницы, используемой в печати.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы страницы, используемой в печати, измеряются в MM_TWIPS.

### <a name="remarks"></a>Примечания

Это значение основано на размере бумаги.

## <a name="cricheditviewgetpapersize"></a><a name="getpapersize"></a>CrichEditView:GetPaperSize

Вызовите эту функцию, чтобы получить текущий размер бумаги.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер бумаги, используемой при печати, измеряется в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

## <a name="cricheditviewgetparaformatselection"></a><a name="getparaformatselection"></a>CrichEditView:GetParaFormatВыбор

Вызовите эту функцию, чтобы получить атрибуты форматирования абзацев текущего выбора.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Структура [PARAFORMAT2,](/windows/win32/api/richedit/ns-richedit-paraformat2) содержащая параграф, форматирующий атрибуты текущего выбора.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации смотрите [EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat) сообщение и [структуру PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) в Windows SDK.

## <a name="cricheditviewgetprintrect"></a><a name="getprintrect"></a>CRichEditView::GetPrintRect

Вызовите эту функцию, чтобы получить границы области печати в прямоугольнике страницы.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы области изображения, используемой при печати, измеряются в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

## <a name="cricheditviewgetprintwidth"></a><a name="getprintwidth"></a>CrichEditView:GetPrintWidth

Вызовите эту функцию, чтобы определить ширину области печати.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина печатной области, измеряемая в MM_TWIPS.

## <a name="cricheditviewgetricheditctrl"></a><a name="getricheditctrl"></a>CrichEditView:GetRichEditCtrl

Вызовите эту функцию, чтобы получить объект [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) связанный с объектом. `CRichEditView`

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CRichEditCtrl` для этого представления.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::FindText](#findtext).

## <a name="cricheditviewgetselecteditem"></a><a name="getselecteditem"></a>CRichEditView::GetSelectedItem

Вызовите эту функцию, чтобы `CRichEditCntrItem` получить элемент OLE `CRichEditView` (объект), выбранный в настоящее время в этом объекте.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CRichEditCntrItem,](../../mfc/reference/cricheditcntritem-class.md) `CRichEditView` выбранный в объекте; NULL, если в этом представлении не выбран элемент.

## <a name="cricheditviewgettextlength"></a><a name="gettextlength"></a>CrichEditView:GetTextДлина

Вызов исчерпе эту функцию для `CRichEditView` получения длины текста на этом объекте.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина текста в `CRichEditView` этом объекте.

## <a name="cricheditviewgettextlengthex"></a><a name="gettextlengthex"></a>CrichEditView::GetTextLengthEx

Вызов исчисляйте эту функцию `CRichEditView` участника для расчета длины текста в этом объекте.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Значение, определяющее метод, который будет использоваться при определении длины текста. Этот участник может быть одним или более значениями, перечисленными в флагах члена [GETTEXTLENGTHEX,](/windows/win32/api/richedit/ns-richedit-gettextlengthex) описанных в Windows SDK.

*uCodePage*<br/>
Страница кода для перевода (CP_ACP для страницы кода ANSI, 1200 для Unicode).

### <a name="return-value"></a>Возвращаемое значение

Количество символов или байтов в элементе управления редактированием. Если несовместимые флаги были установлены в *dwFlags,* эта функция участника возвращается E_INVALIDARG.

### <a name="remarks"></a>Примечания

`GetTextLengthEx`дополнительные способы определения длины текста. Он поддерживает функциональность Rich Edit 2.0. Для получения дополнительной информации [см.](/windows/win32/Controls/about-rich-edit-controls)

## <a name="cricheditviewinsertfileasobject"></a><a name="insertfileasobject"></a>CrichEditView::InsertFileAsObject

Вызовите эту функцию, чтобы вставить указанный файл (как объект [CRichEditCntrItem)](../../mfc/reference/cricheditcntritem-class.md) в богатое представление отсвагиваемого.

```cpp
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, содержащая имя файла, который будет вставлен.

## <a name="cricheditviewinsertitem"></a><a name="insertitem"></a>CrichEditView::InsertItem

Вызовите эту функцию, чтобы вставить объект [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) в богатое представление отсвагиваем.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент, который будет вставлен.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее на успешность вставки.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о HRESULT, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

## <a name="cricheditviewisricheditformat"></a><a name="isricheditformat"></a>CRichEditView::IsRichEditFormat

Позвоните в эту функцию, чтобы определить, является ли *cf* форматом Clipboard, который является текстом, богатым текстом или богатым текстом с элементами OLE.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Формат Clipboard, представляющий интерес.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если *cf* является богатым редактированием или текстом Clipboard формата.

## <a name="cricheditviewisselected"></a><a name="isselected"></a>CrichEditView::IsSelected

Вызовите эту функцию, чтобы определить, выбран ли указанный элемент OLE в настоящее время в этом представлении.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Параметры

*pDocItem*<br/>
Указатель на объект в представлении.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект выбран; в противном случае 0.

### <a name="remarks"></a>Примечания

Переизбь эту функцию, если ваш производный класс представления имеет другой метод обработки выбора элементов OLE.

## <a name="cricheditviewm_nbulletindent"></a><a name="m_nbulletindent"></a>CrichEditView::m_nBulletIndent

Отступы на пулевые элементы в списке; по умолчанию, 720 единиц, что составляет 1/2 дюйма.

```
int m_nBulletIndent;
```

## <a name="cricheditviewm_nwordwrap"></a><a name="m_nwordwrap"></a>CrichEditView::m_nWordWrap

Указывает тип обертывания слов для этого богатого представления отсвагивания.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Примечания

Одно из следующих значений:

- `WrapNone`Указывает отсутствие автоматической обертывания слов.

- `WrapToWindow`Указывает обертывание слов в зависимости от ширины окна.

- `WrapToTargetDevice`Указывает на обертку слов на основе характеристик целевого устройства.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::WrapChanged](#wrapchanged).

## <a name="cricheditviewonchareffect"></a><a name="onchareffect"></a>CrichEditView:OnCharEffect

Вызовите эту функцию, чтобы переключить эффекты форматирования символов для текущего выбора.

```cpp
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*dwMask*<br/>
Эффекты форматирования символов для изменения в текущем выборе.

*dwEffect*<br/>
Нужный список эффектов форматирования символов для переключения.

### <a name="remarks"></a>Примечания

Каждый вызов этой функции переключает указанные эффекты форматирования для текущего выбора.

Более подробную информацию о параметрах *dwMask* и *dwEffect* и их [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) потенциальных значениях можно узнать в SDK Windows с мною о соответствующих данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

## <a name="cricheditviewonfindnext"></a><a name="onfindnext"></a>CrichEditView::OnFindNext

Вызывается фреймворком при обработке команд из окна диалога «Найти/Замена».

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Строка, которую нужно найти.

*bСледующий*<br/>
Направление для поиска: TRUE указывает вниз; FALSE, вверх.

*bCase*<br/>
Указывает, должен ли поиск быть конфиденциальным.

*bWord*<br/>
Указывает, соответствует ли поиск только целым словам или нет.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы найти текст в пределах `CRichEditView`. Переизвейдите эту функцию, чтобы изменить характеристики поиска для производного класса представления.

## <a name="cricheditviewoninitialupdate"></a><a name="oninitialupdate"></a>CrichEditView:OnInitialUpdate

Вызывается фреймворком после того, как представление сначала прикрепляется к документу, но до отображения представления.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию вызывает функцию [cView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) без информации о подсказке (т.е. используя значения по умолчанию 0 для параметра *lHint* и NULL для параметра *pHint).* Переопределить эту функцию для выполнения любой одноразовой инициализации, которая требует информации о документе. Например, если в приложении есть документы фиксированного размера, эту функцию можно использовать для инициализации ограничений прокрутки представления на основе размера документа. Если приложение поддерживает документы переменного размера, используйте `OnUpdate` для обновления ограничений прокрутки при каждом изменении документа.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::m_nWordWrap](#m_nwordwrap).

## <a name="cricheditviewonpastenativeobject"></a><a name="onpastenativeobject"></a>CRichEditView::PasteNativeObject

Используйте эту функцию для загрузки нативок наивных данных со встроенного элемента.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Параметры

*lpStg*<br/>
Указатель на объект [IStorage.](/windows/win32/api/objidl/nn-objidl-istorage)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае, 0;

### <a name="remarks"></a>Примечания

Как правило, вы сделали бы это, создавая [COleStreamFile](../../mfc/reference/colestreamfile-class.md) вокруг `IStorage`. Можно `COleStreamFile` прикрепить к архиву и [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) вызванный для того чтобы нагрузить данные.

Это передовой overridable.

Для получения дополнительной [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) информации см.

## <a name="cricheditviewonparaalign"></a><a name="onparaalign"></a>CrichEditView::OnParaAlign

Вызовите эту функцию, чтобы изменить выравнивание абзаца для выбранных абзацев.

```cpp
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Параметры

*wAlign*<br/>
Пожеланное выравнивание параграфа. Одно из следующих значений:

- PFA_LEFT согласовать абзацы с левым краем.

- PFA_RIGHT согласовать абзацы с правом отрывом.

- PFA_CENTER центр епараграфы между полями.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

## <a name="cricheditviewonprinterchanged"></a><a name="onprinterchanged"></a>CrichEditView::OnPrinterChanged

Переопределить эту функцию, чтобы изменить характеристики для этого богатого представления отсвагиваемого при изменении принтера.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Параметры

*dcPrinter*<br/>
Объект [CDC](../../mfc/reference/cdc-class.md) для нового принтера.

### <a name="remarks"></a>Примечания

Реализация по умолчанию устанавливает размер бумаги на физическую высоту и ширину для выходного устройства (принтера). Если нет контекста устройства, связанного с *dcPrinter,* реализация по умолчанию устанавливает размер бумаги до 8,5 на 11 дюймов.

## <a name="cricheditviewonreplaceall"></a><a name="onreplaceall"></a>CrichEditView::OnReplaceAll

Вызывается фректовпри обработкой Заменить все команды из окна диалога Replace.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который будет заменен.

*lpszReplace*<br/>
Текст замены.

*bCase*<br/>
Указывает, является ли поиск конфиденциальным.

*bWord*<br/>
Указывает, должен ли поиск выбрать целые слова или нет.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы заменить все случаи определенного текста другой строкой. Переизвеймите эту функцию, чтобы изменить характеристики поиска для этого представления.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::FindText](#findtext).

## <a name="cricheditviewonreplacesel"></a><a name="onreplacesel"></a>CrichEditView::OnReplaceSel

Вызывается фректовпри обработкой Заменить команды из окна диалога Replace.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который будет заменен.

*bСледующий*<br/>
Указывает направление поиска: TRUE не работает; FALSE, вверх.

*bCase*<br/>
Указывает, является ли поиск конфиденциальным.

*bWord*<br/>
Указывает, должен ли поиск выбрать целые слова или нет.

*lpszReplace*<br/>
Текст замены.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы заменить одно появление определенного текста другой строкой. Переизвеймите эту функцию, чтобы изменить характеристики поиска для этого представления.

## <a name="cricheditviewontextnotfound"></a><a name="ontextnotfound"></a>CrichEditView::OnTextNotFound

Вызывается по системе всякий раз, когда поиск не удается.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который не найден.

### <a name="remarks"></a>Примечания

Переизобить эту функцию, чтобы изменить уведомление вывода из [MessageBeep.](/windows/win32/api/winuser/nf-winuser-messagebeep)

Для получения дополнительной информации смотрите [MessageBeep](/windows/win32/api/winuser/nf-winuser-messagebeep) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

## <a name="cricheditviewonupdatechareffect"></a><a name="onupdatechareffect"></a>CrichEditView::OnUpdateCharEffect

Платформа вызывает эту функцию для обновления утилиты управления для команд эффекта символов.

```cpp
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на объект [CCmdUI.](../../mfc/reference/ccmdui-class.md)

*dwMask*<br/>
Указывает маску форматирования персонажа.

*dwEffect*<br/>
Указывает эффект форматирования символов.

### <a name="remarks"></a>Примечания

Маска *dwMask* определяет, какие атрибуты форматирования символов для проверки. Флаги *dwEffect* перечислять атрибуты форматирования символов для установки/ясности.

Более подробную информацию о параметрах *dwMask* и *dwEffect* и их [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) потенциальных значениях можно узнать в SDK Windows с мною о соответствующих данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

## <a name="cricheditviewonupdateparaalign"></a><a name="onupdateparaalign"></a>CrichEditView::OnUpdateParaAlign

Платформа вызывает эту функцию для обновления утилиты управления командой для команд эффекта абзацев.

```cpp
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на объект [CCmdUI.](../../mfc/reference/ccmdui-class.md)

*wAlign*<br/>
Выравнивание параграфа для проверки. Одно из следующих значений:

- PFA_LEFT согласовать абзацы с левым краем.

- PFA_RIGHT согласовать абзацы с правом отрывом.

- PFA_CENTER центр епараграфы между полями.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

## <a name="cricheditviewprintinsiderect"></a><a name="printinsiderect"></a>CRichEditView: :PrintInsideRect

Вызовите эту функцию для формата диапазона текста в богатом элемента управления редактированием, чтобы поместиться в *rectLayout* для устройства, указанного *pDC.*

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для области вывода.

*rectLayout*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) или [CRect,](../../atl-mfc-shared/reference/crect-class.md) который определяет область вывода.

*nИндексСтарт*<br/>
Нулевой индекс первого символа, который будет отформатирован.

*nIndexStop*<br/>
Нулевой индекс последнего символа, подаваемый форматировать.

*bOutput*<br/>
Указывает, должен ли быть отображен текст. Если FALSE, текст просто измеряется.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа, который помещается в область вывода плюс один.

### <a name="remarks"></a>Примечания

Как правило, за этим вызовом следует вызов [cRichEditCtrl::DisplayBand,](../../mfc/reference/cricheditctrl-class.md#displayband) который генерирует выход.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::GetPaperSize](#getpapersize).

## <a name="cricheditviewprintpage"></a><a name="printpage"></a>CRichEditView::PrintPage

Вызовите эту функцию для формата диапазона текста в богатом элемента управления редактированием для устройства вывода, указанного *pDC.*

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для вывода страницы.

*nИндексСтарт*<br/>
Нулевой индекс первого символа, который будет отформатирован.

*nIndexStop*<br/>
Нулевой индекс последнего символа, подаваемый форматировать.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа, который помещается на странице плюс один.

### <a name="remarks"></a>Примечания

Макет каждой страницы контролируется [GetPageRect](#getpagerect) и [GetPrintRect.](#getprintrect) Как правило, за этим вызовом следует вызов [cRichEditCtrl::DisplayBand,](../../mfc/reference/cricheditctrl-class.md#displayband) который генерирует выход.

Обратите внимание, что поля относительно физической страницы, а не логической страницы. Таким образом, поля нуля часто обрезают текст, так как многие принтеры имеют непечатные области на странице. Чтобы избежать отсечения текста, следует вызвать [SetMargins](#setmargins) и установить разумные поля перед печатью.

## <a name="cricheditviewqueryacceptdata"></a><a name="queryacceptdata"></a>CRichEditView::QueryAcceptData

Вызывается фреймворком для вставки объекта в богатое речение.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>Параметры

*lpdataobj*<br/>
Указатель на [запрос IDataObject.](/windows/win32/api/objidl/nn-objidl-idataobject)

*lpcfFormat*<br/>
Указатель на приемлемый формат данных.

*dwReco*<br/>
Не используется.

*bReally*<br/>
Указывает, должна ли операция пасты продолжаться или нет.

*hMetaFile*<br/>
Ручка к метафайлу, используемая для рисования значка элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщая об успехе операции.

### <a name="remarks"></a>Примечания

Переопределить эту функцию для обработки различных элементов COM в классе производных документов. Это передовой overridable.

Для получения дополнительной информации о HRESULT и `IDataObject`, см. Структура [кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) и [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject), соответственно, в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

## <a name="cricheditviewsetcharformat"></a><a name="setcharformat"></a>CrichEditView:SetCharFormat

Вызовите эту функцию, чтобы настроить атрибуты `CRichEditView` форматирования символов для нового текста в этом объекте.

```cpp
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Структура [CHARFORMAT2,](/windows/win32/api/richedit/ns-richedit-charformat2w) содержащая новые атрибуты форматирования символов по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция меняет только `dwMask` атрибуты, указанные членом *cf.*

Для получения дополнительной информации смотрите [EM_SETCHARFORMAT](/windows/win32/Controls/em-setcharformat) сообщение и [структуру CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewsetmargins"></a><a name="setmargins"></a>CRichEditView:SetMargins

Вызовите эту функцию, чтобы установить поля печати для этого богатого представления отсвагания.

```cpp
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Параметры

*rectMargin*<br/>
Новые значения маржи для печати, измеренные в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) m_nWordWrap `WrapToTargetDevice`есть, следует позвонить [в WrapChanged](#wrapchanged) после использования этой функции для настройки характеристик печати.

Обратите внимание, что поля, используемые [PrintPage,](#printpage) относятся к физической странице, а не к логической странице. Таким образом, поля нуля часто обрезают текст, так как многие принтеры имеют непечатные области на странице. Чтобы избежать отсечения `SetMargins` текста, перед печатью следует вызвать использование для установки разумных полей принтера.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::GetPaperSize](#getpapersize).

## <a name="cricheditviewsetpapersize"></a><a name="setpapersize"></a>CrichEditView::SetPaperSize

Вызовите эту функцию, чтобы установить размер бумаги для печати этого богатого представления отсвагания.

```cpp
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Параметры

*размербумаги*<br/>
Значения нового размера бумаги для печати, измеренные в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) m_nWordWrap `WrapToTargetDevice`есть, следует позвонить [в WrapChanged](#wrapchanged) после использования этой функции для настройки характеристик печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

## <a name="cricheditviewsetparaformat"></a><a name="setparaformat"></a>CrichEditView:SetParaFormat

Вызовите эту функцию, чтобы установить атрибуты `CRichEditView` форматирования параграфа для текущего выбора в этом объекте.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Параметры

*Pf*<br/>
Структура [PARAFORMAT2,](/windows/win32/api/richedit/ns-richedit-paraformat2) содержащая новый параграф по умолчанию, форматируя атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае, 0.

### <a name="remarks"></a>Примечания

Эта функция меняет только `dwMask` атрибуты, указанные членом *pf.*

Для получения дополнительной информации смотрите [EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat) сообщение и [структуру PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

## <a name="cricheditviewtextnotfound"></a><a name="textnotfound"></a>CrichEditView::TextNotFound

Вызов ими функции для сбросить внутреннее состояние поиска управления [CRichEditView](../../mfc/reference/cricheditview-class.md) после неудачного вызова [FindText.](#findtext)

```cpp
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит строку текста, которая не была найдена.

### <a name="remarks"></a>Примечания

Этот метод рекомендуется вызывать сразу после неудачных вызовов [FindText,](#findtext) чтобы внутреннее состояние поиска элемента управления было правильно сбрано.

Параметр *lpszFind* должен включать в себя то же содержимое, что и строка, предоставляемая [FindText.](#findtext) После сброса состояния внутреннего поиска этот метод вызовет метод [OnTextNotFound](#ontextnotfound) с предоставленной строкой поиска.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::FindText](#findtext).

## <a name="cricheditviewwrapchanged"></a><a name="wrapchanged"></a>CrichEditView::WrapChanged

Вызовите эту функцию, когда характеристики печати изменились [(SetMargins](#setmargins) или [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы изменить способ, которым богатое представление отсеивательь отреагирует на изменения в [m_nWordWrap](#m_nwordwrap) или характеристики печати [(OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Класс CrichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)
