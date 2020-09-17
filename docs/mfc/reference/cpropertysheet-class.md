---
title: Класс CPropertySheet
ms.date: 11/04/2016
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
ms.openlocfilehash: e8ab91b9a6fe76070d79ea2eee2e5765db2e99e3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750970"
---
# <a name="cpropertysheet-class"></a>Класс CPropertySheet

Представляет страницы свойств, также известные как диалоговые окна вкладки.

## <a name="syntax"></a>Синтаксис

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Формирует объект `CPropertySheet`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|
|[CPropertySheet::Строительство](#construct)|Формирует объект `CPropertySheet`.|
|[CPropertySheet::Создание](#create)|Отображает лист без бесрежимного свойства.|
|[CPropertySheet::DoModal](#domodal)|Отображает лист модального свойства.|
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Указывает, использует ли лист свойств сложенные или прокрутки вкладок.|
|[CPropertySheet::EndDialog](#enddialog)|Прекращает действие листа свойств.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Извлекает индекс активной страницы листа свойств.|
|[CPropertySheet::GetActivePage](#getactivepage)|Возвращает объект активной страницы.|
|[CPropertySheet::GetPage](#getpage)|Извлекает указатель на указанную страницу.|
|[CPropertySheet::GetPageCount](#getpagecount)|Извлекает количество страниц в листе свойств.|
|[CPropertySheet::GetPageIndex](#getpageindex)|Извлекает индекс указанной страницы листа свойств.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|Извлекает указатель на элемент управления вкладками.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Преобразует единицы диалогового ящика прямоугольника в экранные блоки.|
|[CPropertySheet::ItDialog](#oninitdialog)|Переопределение для увеличения инициализации листа свойств.|
|[CPropertySheet::PressButton](#pressbutton)|Имитирует выбор указанной кнопки в листе свойства.|
|[CPropertySheet::RemovePage](#removepage)|Удаляет страницу из листа свойств.|
|[CPropertySheet::SetActivePage](#setactivepage)|Программно устанавливает активный объект страницы.|
|[CPropertySheet::SetFinishText](#setfinishtext)|Устанавливает текст для кнопки Отделка.|
|[CPropertySheet::SetTitle](#settitle)|Устанавливает подпись листа собственности.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Включает кнопки мастера.|
|[CPropertySheet::SetWizardMode](#setwizardmode)|Включает режим мастера.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPropertySheet:::m_psh](#m_psh)|Структура Windows [PROPSHEETHEADER.](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) Обеспечивает доступ к основным параметрам листа свойств.|

## <a name="remarks"></a>Примечания

Лист свойств состоит `CPropertySheet` из объекта и одного или нескольких объектов [CPropertyPage.](../../mfc/reference/cpropertypage-class.md) В фреймворке отображается лист свойств как окно с набором индексов вкладок и область, содержащая выбранную в настоящее время страницу. Пользователь переходит на конкретную страницу, используя соответствующую вкладку.

`CPropertySheet`обеспечивает поддержку расширенной структуры [PROPSHEETHEADER,](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) представленной в Windows 98 и Windows NT 2000. Структура содержит дополнительные флаги и членов, которые поддерживают с помощью "водяной знак" фоновой битной карты.

Чтобы автоматически отображать эти новые изображения в объекте листа свойств, передайте действительные значения для бит-карты и изображений палитры в вызове на [CPropertySheet::Construct](#construct) или [CPropertySheet::CPropertySheet.](#cpropertysheet)

Несмотря `CPropertySheet` на [то,](../../mfc/reference/cdialog-class.md)что управление объектом не происходит, управление объектом `CPropertySheet` подобно управлению объектом. `CDialog` Например, для создания листа свойств требуется двухстороннее строительство: вызов конструктора, а затем вызов [DoModal](#domodal) для листа модального свойства или [Создать](#create) для листа безрежима свойства. `CPropertySheet`имеет два типа конструкторов: [CPropertySheet::: Конструкция](#construct) и [CPropertySheet::CPropertySheet](#cpropertysheet).

При построении `CPropertySheet` объекта некоторые [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) могут привести к первому исключению. Это является результатом того, что система пытается изменить стиль листа свойств до создания листа. Чтобы избежать этого исключения, убедитесь, что вы `CPropertySheet`установите следующие стили при создании:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Следующие стили не являются обязательными и не вызовут исключения первого шанса:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Любые `Window Styles` другие запрещены, и вы не должны позволить им.

Обмен данными `CPropertySheet` между объектом и внешним объектом аналогичен обмену данными с объектом. `CDialog` Важное отличие заключается в том, что параметры листа `CPropertyPage` свойств, как `CPropertySheet` правило, являются переменными объектов, а не самим объектом.

Можно создать тип диалогового окна вкладок, называемый мастером, который состоит из листа свойств с последовательностью страниц свойств, которые направляют пользователя через этапы операции, такие как настройка устройства или создание бюллетеня. В диалоговом окне вкладок типа мастер-класса страницы свойств не имеют вкладок, и одновременно отображается только одна страница свойств. Кроме того, вместо того, **OK** и **Применить сейчас** кнопки, мастер типа вкладки диалог оваки имеет кнопку **"Назад",** **кнопку "Следующий"** или **"Закончить",** **кнопку "Отмена"** и кнопку **справки.**

Чтобы создать поле диалога типа мастера, выполните те же шаги, которые вы бы следовали, чтобы создать стандартный лист свойств, но позвоните [в SetWizardMode,](#setwizardmode) прежде чем позвонить [в DoModal.](#domodal) Чтобы включить кнопки мастера, позвоните [SetWizardButtons,](#setwizardbuttons)используя флаги, чтобы настроить их функцию и внешний вид. Чтобы включить кнопку **«Завершение»,** позвоните [в SetFinishText](#setfinishtext) после того, как пользователь принял меры на последней странице мастера.

Для получения дополнительной информации о том, как использовать `CPropertySheet` объекты, см. [Property Sheets and Property Pages](../../mfc/property-sheets-and-property-pages-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cpropertysheetaddpage"></a><a name="addpage"></a>CPropertySheet::AddPage

Добавляет предоставленную страницу с самой правильной вкладкой в листе свойств.

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
Очки на страницу, которая будет добавлена в лист свойств. Не может быть NULL.

### <a name="remarks"></a>Примечания

Добавить страницы в лист свойств в порядке слева направо, которые вы хотите, чтобы они отображались.

`AddPage`добавляет объект [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) `CPropertySheet` в список страниц объекта, но на самом деле не создает окно для страницы. Платформа откладывает создание окна для страницы до тех пор, пока пользователь не выберет эту страницу.

При добавлении страницы свойств с помощью, `AddPage` `CPropertySheet` является родителем `CPropertyPage`. Чтобы получить доступ к листу свойств со страницы свойств, позвоните [cWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).

Не стоит ждать, пока будет создано окно `AddPage`листа недвижимости для вызова. Как правило, `AddPage` вы будете звонить перед вызовом [DoModal](#domodal) или [Создать](#create).

Если вы `AddPage` звоните после отображения страницы свойств, строка вкладок будет отражать недавно добавленную страницу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

## <a name="cpropertysheetconstruct"></a><a name="construct"></a>CPropertySheet::Строительство

Формирует объект `CPropertySheet`.

```cpp
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Параметры

*nIDCaption*<br/>
Идентификатор подписи, который будет использоваться для листа собственности.

*pParentWnd*<br/>
Указатель на родительское окно листа свойств. Если NULL, родительское окно будет основным окном приложения.

*iSelectPage*<br/>
Индекс страницы, который первоначально будет на вершине. По умолчанию первая страница, добавленная в лист.

*pszCaption*<br/>
Указатель на строку, содержащую подпись, которая будет использоваться для листа свойств. Не может быть NULL.

*hbmWatermark*<br/>
Ручка к биккарте водяного знака страницы свойства.

*hpalWatermark*<br/>
Обработка к палитре водяного знака bitmap и / или заголовок bitmap.

*hbmHeader*<br/>
Ручка к битовой карте заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Вызовите эту функцию участника, если один из конструкторов класса еще не был вызван. Например, `Construct` вызов при объявлении или `CPropertySheet` распределении массивов объектов. В случае массивов необходимо вызвать `Construct` каждого участника массива.

Чтобы отобразить лист свойств, позвоните [doModal](#domodal) или [создайте](#create). Строка, содержащаяся в первом параметре, будет помещена в строку подписи для листа свойств.

Вы можете отображать водяные знаки и/или изображения заголовка `Construct`автоматически, если вы используете третий или четвертый прототипы, перечисленные выше, и вы передаете действительные значения для параметров *hbmWatermark,* *hpalWatermark*и/или *параметров hbmHeader.*

### <a name="example"></a>Пример

Следующий пример показывает, при каких обстоятельствах вы бы назвали `Construct`.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

## <a name="cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>CPropertySheet::CPropertySheet

Формирует объект `CPropertySheet`.

```
CPropertySheet();

explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Параметры

*nIDCaption*<br/>
Идентификатор подписи, который будет использоваться для листа собственности.

*pParentWnd*<br/>
Указывает на родительское окно листа свойств. Если NULL, родительское окно будет основным окном приложения.

*iSelectPage*<br/>
Индекс страницы, который первоначально будет на вершине. По умолчанию первая страница, добавленная в лист.

*pszCaption*<br/>
Указывает на строку, содержащую подпись, которая будет использоваться для листа свойств. Не может быть NULL.

*hbmWatermark*<br/>
Ручка к фоновой битной карте листа свойств.

*hpalWatermark*<br/>
Ручка к палитре bitmap водяного знака и/или bitmap заголовка.

*hbmHeader*<br/>
Ручка к битной карте заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Чтобы отобразить лист свойств, позвоните [doModal](#domodal) или [создайте](#create). Строка, содержащаяся в первом параметре, будет помещена в строку подписи для листа свойств.

Если у вас есть несколько параметров (например, [Construct](#construct) если `CPropertySheet`вы используете массив), используйте Construct вместо .

Вы можете отображать водяные знаки и / или заголовок `CPropertySheet`изображения автоматически, если вы используете третий или четвертый прототипы , выше, и вы проходите действительные значения для *hbmWatermark*, *hpalWatermark*, и / или *hbmHeader* параметров.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

## <a name="cpropertysheetcreate"></a><a name="create"></a>CPropertySheet::Создание

Отображает лист без бесрежимного свойства.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указывает на родительское окно. Если NULL, родитель является настольным компьютером.

*dwStyle*<br/>
Стили окон для листа свойств. Полный список доступных стилей можно найти в [стиле Window.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*dwExStyle*<br/>
Расширенные стили окон для листа свойств. Полный список доступных стилей можно найти в [расширенных стилях окон](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лист свойства создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов `Create` может быть внутри конструктора, или вы можете назвать его после вызова конструктора.

Стиль по умолчанию, выраженный при передаче -1 *как dwStyle,* на самом деле WS_SYSMENU&#124;WS_POPUP&#124;WS_CAPTION WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP DS_CONTEXTHELP&#124;WS_VISIBLE. По умолчанию расширенный стиль окна, выраженный путем передачи 0 *как dwExStyle*, на самом деле WS_EX_DLGMODALFRAME.

Функция `Create` участника возвращается сразу после создания листа свойств. Чтобы уничтожить лист имущества, звоните [CWnd: :DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).

Листы бесрежимного свойства, `Create` отображаемые с вызовом, чтобы не иметь OK, Отмена, Применить сейчас, и помощь кнопки, как модальные листы свойств делать. Нужные кнопки должны быть созданы пользователем.

Чтобы отобразить лист модального свойства, вместо этого позвоните [в DoModal.](#domodal)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

## <a name="cpropertysheetdomodal"></a><a name="domodal"></a>CPropertySheet::DoModal

Отображает лист модального свойства.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL, если функция была успешной; в противном случае 0 или -1. Если лист свойств был установлен как мастер (см. [SetWizardMode),](#setwizardmode) `DoModal` возвращает либо ID_WIZFINISH, либо IDCANCEL.

### <a name="remarks"></a>Примечания

Значение возврата соответствует идентификатору элемента управления, закрывавого лист свойства. После возвращения этой функции окна, соответствующие листу свойства, и все страницы будут уничтожены. Сами объекты все еще будут существовать. Как правило, вы получаете данные из `DoModal` объектов [CPropertyPage](../../mfc/reference/cpropertypage-class.md) после возврата IDOK.

Для отображения листа бесрежимного свойства вместо этого вызов [—свяжет.](#create)

Когда страница свойств создается из соответствующего ресурса диалогов, она может привести к исключению первого шанса. Это является результатом изменения страницы свойств в отношении стиля ресурса диалогов до требуемого стиля до создания страницы. Поскольку ресурсы, как правило, только для чтения, это приводит к исключению. Система обрабатывает исключение и делает копию измененного ресурса. Таким образом, исключение первого шанса может быть проигнорировано.

> [!NOTE]
> Это исключение должно обрабатываться операционной системой, если вы компилируете с помощью асинхронной модели обработки исключений. Для получения дополнительной информации о моделях обработки исключений [см.](../../build/reference/eh-exception-handling-model.md) В этом случае не обращайте вносы вызовов `CPropertySheet::DoModal` блоком попытки ловли СЗ, в котором улов обрабатывает все исключения, например, `catch (...)`. Этот блок будет обрабатывать исключение, предназначенное для операционной системы, и вызывает непредсказуемое поведение. Тем не менее, можно безопасно использовать обработку исключений с определенными типами исключений или структурированной обработкой исключений, когда исключение нарушения доступа передается в операционную систему.

Чтобы избежать создания этого исключения первого шанса, вы можете вручную гарантировать, что лист свойств имеет правильные [стили окон.](../../mfc/reference/styles-used-by-mfc.md#window-styles) Для листа свойств необходимо установить следующие стили:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Вы можете использовать следующие дополнительные стили, не вызывая первого случая исключения:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Отключите все другие стили Windows, поскольку они не совместимы с листами свойств. Этот совет не распространяется на расширенные стили. Установка этих стандартных стилей надлежащим образом гарантирует, что лист свойств не должен быть изменен и позволит избежать создания исключения первого шанса.

### <a name="example"></a>Пример

Смотрите пример [CPropertySheet::AddPage](#addpage).

## <a name="cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs

Указывается, следует ли укладывать строки вкладок в лист свойств.

```cpp
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Параметры

*bStacked*<br/>
Указывается, включены ли сложенные вкладки в листе свойств. Отпугивать сложенные ряды тегов, установив *bStacked* на FALSE.

### <a name="remarks"></a>Примечания

По умолчанию, если лист свойств имеет больше вкладок, чем помещается в один ряд в ширине листа свойств, вкладки будут стекать в несколько строк. Чтобы использовать вкладки прокрутки вместо `EnableStackedTabs` укладки вкладок, позвоните с *bStacked* набор FALSE перед вызовом [DoModal](#domodal) или [Создать](#create).

Вы должны `EnableStackedTabs` позвонить при создании модального или бесхозного листа свойств. Чтобы включить этот `CPropertySheet`стиль в класс, полученный в результате получения, напишите обработчик сообщений для WM_CREATE. В переочерченной версии [CWnd::OnCreate,](../../mfc/reference/cwnd-class.md#oncreate)вызов `EnableStackedTabs( FALSE )` перед вызовом реализации базового класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

## <a name="cpropertysheetenddialog"></a><a name="enddialog"></a>CPropertySheet::EndDialog

Прекращает действие листа свойств.

```cpp
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Параметры

*nEndID*<br/>
Идентификатор, который будет использоваться в качестве возвратной стоимости листа имущества.

### <a name="remarks"></a>Примечания

Эта функция участника вызывается инфраструктурой при нажатии кнопки OK, Cancel или Close. Вызовите эту функцию участника, если происходит событие, которое должно закрыть лист свойств.

Эта функция члена используется только с модальным диалоговом упаковочным окном.

### <a name="example"></a>Пример

Смотрите пример [CPropertySheet::PressButton](#pressbutton).

## <a name="cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>CPropertySheet::GetActiveIndex

Получает индексный номер активной страницы окна листа свойств, а затем `GetPage`использует возвращенный номер индекса в качестве параметра для.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер индекса активной страницы.

### <a name="example"></a>Пример

Смотрите пример [для CPropertySheet::GetActivePage](#getactivepage).

## <a name="cpropertysheetgetactivepage"></a><a name="getactivepage"></a>CPropertySheet::GetActivePage

Извлекает активную страницу окна свойства.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на активную страницу.

### <a name="remarks"></a>Примечания

Используйте эту функцию участника для выполнения некоторых действий на активной странице.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

## <a name="cpropertysheetgetpage"></a><a name="getpage"></a>CPropertySheet::GetPage

Возвращает указатель на указанную страницу в этом листе свойств.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Параметры

*nСтраница*<br/>
Индекс нужной страницы, начиная с 0. Должно быть от 0 до одного меньше, чем количество страниц в листе собственности, включительно.

### <a name="return-value"></a>Возвращаемое значение

Указатель на страницу, соответствующую параметру *nPage.*

### <a name="example"></a>Пример

Смотрите пример для [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

## <a name="cpropertysheetgetpagecount"></a><a name="getpagecount"></a>CPropertySheet::GetPageCount

Определяет количество страниц, наиболее наиболее вданных в настоящее время листа свойств.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество страниц в листе свойств.

### <a name="example"></a>Пример

Смотрите пример для [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

## <a name="cpropertysheetgetpageindex"></a><a name="getpageindex"></a>CPropertySheet::GetPageIndex

Извлекает номер индекса указанной страницы в листе свойства.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
Очки на страницу с найденным индексом. Не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Номер индекса страницы.

### <a name="remarks"></a>Примечания

Например, для `GetPageIndex` использования [SetActivePage](#setactivepage) или [GetPage](#getpage)можно использовать индекс страницы.

### <a name="example"></a>Пример

Смотрите пример [для CPropertySheet::GetActivePage](#getactivepage).

## <a name="cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>CPropertySheet::GetTabControl

Извлекает указатель на элемент управления вкладками, чтобы сделать что-то конкретное для управления вкладками (т.е. использовать любой из AI в [CTabCtrl).](../../mfc/reference/ctabctrl-class.md)

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на управление вкладками.

### <a name="remarks"></a>Примечания

Например, позвоните в эту функцию участника, если вы хотите добавить бит-карты к каждой из вкладок во время инициализации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

## <a name="cpropertysheetm_psh"></a><a name="m_psh"></a>CPropertySheet:::m_psh

Структура, члены которой хранят характеристики [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2).

### <a name="remarks"></a>Примечания

Используйте эту структуру, чтобы инициализировать внешний вид листа свойств после его построения, но прежде чем он отображается с функцией члена [DoModal.](#domodal) Например, установите член *dwSize* `m_psh` в размере, который вы хотите иметь лист свойства.

Более подробную информацию об этой структуре, включая список ее членов, можно узнать в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

## <a name="cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>CPropertySheet::MapDialogRect

Преобразует единицы диалогового ящика прямоугольника в экранные блоки.

```cpp
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) содержащий координаты диалогового ящика, которые должны быть преобразованы.

### <a name="remarks"></a>Примечания

Единицы Dialog-box указаны с точки зрения текущего базового блока диалог-бокса, полученного из средней ширины и высоты символов шрифта, используемого для текста диалог-бокса. Одна горизонтальная единица составляет одну четвертую часть базового блока-ширины диалог-бокса, а одна вертикальная единица — одна восьмая единицы базовой высоты диалогового ящика.

Функция [GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) Windows возвращает информацию о размере для системного шрифта, но можно указать другой шрифт для каждого листа свойств, если вы используете DS_SETFONT стиль в файле определения ресурсов. Функция [MapDialogRect](/windows/win32/api/winuser/nf-winuser-mapdialogrect) Windows, описанная в SDK Windows, использует соответствующий шрифт для этого диалогового окна.

Функция `MapDialogRect` члена заменяет единицы диалогового ящика в *lpRect* единицами экрана (пикселей), так что прямоугольник может быть использован для создания диалогового окна или расположения элемента управления в коробке.

## <a name="cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>CPropertySheet::ItDialog

Переопределения для увеличения инициализации листа свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Уточняется, установило ли приложение фокус ввода одного из элементов управления в листе свойств. Если `OnInitDialog` доходность незеро, Windows устанавливает фокус ввода для первого элемента управления в листе свойств. Приложение может вернуть 0 только в том случае, если оно явно установило фокус ввода на один из элементов управления в листе свойств.

### <a name="remarks"></a>Примечания

Эта функция члена вызывается в ответ на WM_INITDIALOG сообщение. Это сообщение отправляется в лист свойств во время вызовов [Create](#create) или [DoModal,](#domodal) которые возникают непосредственно перед отображением листа свойств.

Переопределить эту функцию участника, если вам нужно выполнить специальную обработку, когда лист свойства инициализирован. В перевернутой версии сначала `OnInitDialog` позвоните в базовый класс, но игнорируйте его значение возврата. Вы, как правило, вернуться TRUE от переопределенной функции члена.

Для этой функции участника не требуется запись на карту сообщений.

## <a name="cpropertysheetpressbutton"></a><a name="pressbutton"></a>CPropertySheet::PressButton

Имитирует выбор указанной кнопки в листе свойства.

```cpp
void PressButton(int nButton);
```

### <a name="parameters"></a>Параметры

*nКнопка*<br/>
nButton : Определяет кнопку для нажатия. Этот параметр может быть одним из следующих значений:

- PSBTN_BACK выбирает кнопку «Назад».

- PSBTN_NEXT выбирает кнопку «Следующая».

- PSBTN_FINISH выбирает кнопку Отделка.

- PSBTN_OK выбирает кнопку OK.

- PSBTN_APPLYNOW выбирает кнопку Apply Now.

- PSBTN_CANCEL выбирает кнопку Отмена.

- PSBTN_HELP выбирает кнопку справки.

### <a name="remarks"></a>Примечания

Более подробную информацию о сообщении Windows SDK Pressbutton смотрите [PSM_PRESSBUTTON.](/windows/win32/Controls/psm-pressbutton)

Вызов не `PressButton` отправляет [уведомление PSN_APPLY](/windows/win32/Controls/psn-apply) со страницы свойств в фреймворк. Чтобы отправить это уведомление, позвоните [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

## <a name="cpropertysheetremovepage"></a><a name="removepage"></a>CPropertySheet::RemovePage

Удаляет страницу из листа свойств и уничтожает связанное окно.

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
Очки на страницу, которая должна быть удалена из листа свойств. Не может быть NULL.

*nСтраница*<br/>
Индекс страницы, который будет удален. Должно быть от 0 до одного меньше, чем количество страниц в листе собственности, включительно.

### <a name="remarks"></a>Примечания

Сам объект [CPropertyPage](../../mfc/reference/cpropertypage-class.md) не разрушается до `CPropertySheet` тех пор, пока владелец окна не будет закрыт.

## <a name="cpropertysheetsetactivepage"></a><a name="setactivepage"></a>CPropertySheet::SetActivePage

Изменяет активную страницу.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*nСтраница*<br/>
Индекс страницы для установки. Она должна быть от 0 до одного меньше, чем количество страниц в листе собственности, включительно.

*pPage*<br/>
Указывает на страницу, установленную в листе свойства. Оно не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лист свойства активирован успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Например, `SetActivePage` используйте, если действие пользователя на одной странице должно привести к тому, что активная страница станет другой страницей.

### <a name="example"></a>Пример

Смотрите пример [для CPropertySheet::GetActivePage](#getactivepage).

## <a name="cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>CPropertySheet::SetFinishText

Устанавливает текст в кнопке команды Finish.

```cpp
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Очки на текст, который будет отображаться на кнопке команды Finish.

### <a name="remarks"></a>Примечания

Позвоните `SetFinishText` для отображения текста на кнопке команды Finish и спрячьте кнопки Next and Back после того, как пользователь выполнит действие на последней странице мастера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsettitle"></a><a name="settitle"></a>CPropertySheet::SetTitle

Упоняет подпись листа свойства (текст отображается в заглавной панели окна рамы).

```cpp
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
Определяет стиль названия листа недвижимости. Стиль должен быть указан в 0 или как PSH_PROPTITLE. Если стиль установлен как PSH_PROPTITLE, слово "Свойства" появляется после текста, указанного в качестве подписи. Например, `SetTitle`вызов ("Простой", PSH_PROPTITLE) приведет к заголовок листа свойства "Простые свойства".

*lpszText*<br/>
Указывает на текст, который будет использоваться в качестве подписи в заглавной панели листа собственности.

### <a name="remarks"></a>Примечания

По умолчанию лист свойств использует параметр подписи в конструкторе листа свойств.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

## <a name="cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons

Позволяет или отсваивает кнопку «Назад, следующая или финишная кнопка» в листе свойства мастера.

```cpp
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Набор флагов, настраивающие функцию и внешний вид кнопок мастера. Этот параметр может быть комбинацией следующих значений:

- кнопка PSWIZB_BACK назад

- PSWIZB_NEXT кнопка «Следующая»

- кнопка PSWIZB_FINISH отделка

- кнопка PSWIZB_DISABLEDFINISH отключена

### <a name="remarks"></a>Примечания

Звоните `SetWizardButtons` только после открытия диалога; Вы не можете `SetWizardButtons` позвонить, прежде чем позвонить [DoModal](#domodal). Как правило, `SetWizardButtons` вы должны звонить с [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).

Если вы хотите изменить текст на кнопке Отделка или скрыть кнопки Next and Back, как только пользователь доработает мастера, позвоните [в SetFinishText.](#setfinishtext) Обратите внимание, что та же кнопка используется для Finish and Next. Вы можете отображать кнопку Finish или Next одновременно, но не обе.

### <a name="example"></a>Пример

A `CPropertySheet` имеет три страницы `CColorPage`свойств `CShapePage`мастера: `CStylePage`, и .  Фрагмент кода ниже показывает, как включить и отключить кнопки **«Назад»** и **«Следующий»** на странице свойств мастера.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>CPropertySheet::SetWizardMode

Устанавливает страницу свойств как мастер.

```cpp
void SetWizardMode();
```

### <a name="remarks"></a>Примечания

Ключевой характеристикой страницы свойств мастера является то, что пользователь переходит с помощью кнопок Next или Finish, Back and Cancel вместо вкладок.

Позвоните `SetWizardMode` перед вызовом [DoModal](#domodal). После `SetWizardMode`вызова, `DoModal` будет вернуться либо ID_WIZFINISH (если пользователь закрывается с кнопкой отделки) или IDCANCEL.

`SetWizardMode`устанавливает PSH_WIZARD флаг.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
