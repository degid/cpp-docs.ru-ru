---
title: Класс CMFCPropertySheet
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 9b1bb2ce9a957b9cd9f7add983b4da7a228d7a1d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750059"
---
# <a name="cmfcpropertysheet-class"></a>Класс CMFCPropertySheet

Класс `CMFCPropertySheet` поддерживает таблицу свойств, каждая страница свойств в которой обозначается вкладкой, кнопкой панели инструментов, узлом элемента управления «Дерево» или элементом списка.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Формирует объект `CMFCPropertySheet`.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Добавляет новую страницу свойств в элемент управления «Дерево».|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Добавляет новый узел в элемент управления «Дерево».|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Получает высоту текущего заголовка.|
|[CMFCPropertySheet::GetLook](#getlook)|Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Получает ширину панели навигации в пикселях.|
|[CMFCPropertySheet::GetTab](#gettab)|Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».|
|`CMFCPropertySheet::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Инициализирует появление текущего элемента управления «Страница свойств».|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Вызывается платформой при включении страницы свойств.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Вызывается платформой для отрисовки пользовательского заголовка страницы свойств.|
|`CMFCPropertySheet::OnInitDialog`|Обрабатывает [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) сообщение. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».|
|`CMFCPropertySheet::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. (Переопределяет `CPropertySheet::PreTranslateMessage`.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Удаляет узел из элемента управления «Дерево».|
|[CMFCPropertySheet::RemovePage](#removepage)|Удаляет страницу свойств из таблицы свойств.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Указывает список изображений, используемых в элементе управления навигации панели Outlook.|
|[CMFCPropertySheet::SetLook](#setlook)|Задает внешний вид таблицы свойств.|

## <a name="remarks"></a>Примечания

Класс `CMFCPropertySheet` представляет таблицы свойств, также называемые диалоговыми окнами с вкладками. Класс `CMFCPropertySheet` может отображать страницу свойств различными способами.

Чтобы использовать класс `CMFCPropertySheet` в приложении, выполните следующие действия.

1. Создайте класс из класса `CMFCPropertySheet` и дайте ему имя, например CMyPropertySheet.

1. Постройте объект [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) для каждой страницы свойств.

1. Позвоните в [CMFCPropertySheet::SetLook](#setlook) метод в конструкторе CMyPropertySheet. Параметр этого метода указывает, что страницы свойств должны отображаться как вкладки вдоль верхней или левой стороны таблицы свойств, как вкладки в стиле таблицы свойств Microsoft OneNote свойств, как кнопки в элементе управления «Панель инструментов» Microsoft Outlook, как узлы дерева или как список элементов с левой стороны таблицы свойств.

1. Если вы создаете лист свойств в стиле панели инструментов Microsoft Outlook, позвоните в [метод CMFCPropertySheet::SetIconsList,](#seticonslist) чтобы связать список изображений вместе со страницами свойств.

1. Позвоните в [CMFCPropertySheet::AddPage](#addpage) метод для каждой страницы свойства.

1. Создайте элемент управления `CMFCPropertySheet` и вызовите его метод `DoModal`.

## <a name="illustrations"></a>Рисунки

На следующем рисунке показана таблица свойств в стиле встроенной панели инструментов Microsoft Outlook. Панель инструментов Outlook отображается с левой стороны таблицы свойств.

![Элементы управления цветов CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "Элементы управления цветов CMFCPropertySheet")

На следующей иллюстрации изображен лист свойств, содержащий объект [класса CMFCPropertyGridCtrl.](../../mfc/reference/cmfcpropertygridctrl-class.md) Этот объект является таблицей свойств в стиле стандартной страницы свойств общих элементов управления.

![Элементы управления свойств и списков CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "Элементы управления свойств и списков CMFCPropertySheet")

На следующем рисунке показана таблица свойств в стиле элемента управления «Дерево».

![Дерево свойств](../../mfc/reference/media/proptree.png "Дерево свойств")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertysheet.h

## <a name="cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFCPropertySheet::AddPage

Добавляет страницу в таблицу свойств.

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
(в) Указатель на объект страницы. Значение этого параметра не может быть равно NULL.

### <a name="remarks"></a>Примечания

Этот метод добавляет указанную страницу свойств в качестве самой правильной вкладки в листе свойств. Поэтому используйте этот метод для добавления страниц в порядке слева направо.

Если лист свойств находится в стиле Microsoft Outlook, в фреймворке отображается список кнопок навигации слева от листа свойств. После того, как этот метод добавляет страницу свойств, он добавляет соответствующую кнопку в список. Чтобы отобразить страницу свойств, нажмите соответствующую кнопку. Для получения дополнительной информации о стилях листов собственности, см [CMFCPropertySheet::SetLook](#setlook).

## <a name="cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFCPropertySheet::AddPageTotree

Добавляет новую страницу свойств в элемент управления «Дерево».

```cpp
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Параметры

*pКатегория*<br/>
(в) Указатель на узловое родительское дерево или NULL для ассоциировать указанную страницу с узлами верхнего уровня. Позвоните в [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод, чтобы получить этот указатель.

*pPage*<br/>
(в) Указатель на объект страницы свойств.

*nIconNum*<br/>
(в) Нулевой индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойства управления деревом, когда страница не выбрана. Значение по умолчанию — -1.

*nSelIconNum*<br/>
(в) Нулевой индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойства управления деревом при выборе страницы. Значение по умолчанию — -1.

### <a name="remarks"></a>Примечания

Этот метод добавляет страницу свойств в виде листа управления деревом. Чтобы добавить страницу `CMFCPropertySheet` свойств, создайте объект, позвоните в метод [CMFCPropertySheet::SetLook](#setlook) с набором параметров `CMFCPropertySheet::PropSheetLook_Tree` *взгляда,* а затем используйте этот метод для добавления страницы свойств.

## <a name="cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFCPropertySheet::AddTreeКатегория

Добавляет новый узел в элемент управления «Дерево».

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Название узла.

*nIconNum*<br/>
(в) Нулевой индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойства управления деревом, когда страница не выбрана. Значение по умолчанию — -1.

*nSelectedIconNum*<br/>
(в) Нулевой индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойства управления деревом при выборе страницы. Значение по умолчанию — -1.

*pРодительскаякатегория*<br/>
(в) Указатель на узловое родительское дерево или NULL для ассоциировать указанную страницу с узлами верхнего уровня. Установите этот параметр методом [CMFCPropertySheet::AddTreeCategory.](#addtreecategory)

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый узлы в управлении дерева.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы добавить новый узлы, который также называют категорией, в управление дерева. Чтобы добавить узла, `CMFCPropertySheet` создайте объект, позвоните в [метод CMFCPropertySheet::SetLook](#setlook) с набором параметров `CMFCPropertySheet::PropSheetLook_Tree` *взгляда,* а затем используйте этот метод для добавления узла.

Используйте значение возврата этого метода в последующих вызовах на [CMFCPropertySheet::AddPageToTree](#addpagetotree) и [CMFCPropertySheet::AddTreeCategory](#addtreecategory).

## <a name="cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet

Формирует объект `CMFCPropertySheet`.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>Параметры

*pszCaption*<br/>
(в) Строка, содержащая подпись листа свойств. Не может быть NULL.

*nIDCaption*<br/>
(в) Идентификатор ресурса, содержащий подпись листа свойств.

*pParentWnd*<br/>
(в) Указатель на родительское окно листа свойств или NULL, если родительское окно является основным окном приложения. Значение по умолчанию — NULL.

*iSelectPage*<br/>
(в) Индекс с нулевым уровнем верхней страницы свойства. Значение по умолчанию — 0.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см. [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet)

## <a name="cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader

Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.

```cpp
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Параметры

*nHeaderВысота*<br/>
(в) Высота заголовка, в пикселях.

### <a name="remarks"></a>Примечания

Чтобы использовать значение параметра *nHeaderHeight* для рисования пользовательского заголовка, переопределить метод [CMFCPropertySheet::OnDrawPageHeader.](#ondrawpageheader)

## <a name="cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight

Получает высоту текущего заголовка.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота заголовка, в пикселях.

### <a name="remarks"></a>Примечания

Позвоните в [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод, прежде чем вы позвоните по этому методу.

## <a name="cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFCPropertySheet::GetLook

Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления, которое определяет внешний вид листа свойств. Список возможных значений можно найти в разделе Remarks [CMFCPropertySheet::SetLook](#setlook).

## <a name="cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFCPropertySheet::GetNavBarWidth

Получает ширину панели навигации.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина панели навигации в пикселях.

## <a name="cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFCPropertySheet::GetTab

Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Возвращаемое значение

Внутренний объект управления вкладками.

### <a name="remarks"></a>Примечания

Можно настроить лист свойств таким образом, чтобы он отосужался в разных стилях, таких как управление деревом, список кнопок навигации или набор страниц с вкладками.

Прежде чем вызвать этот метод, позвоните [в CMFCPropertySheet::SetLook](#setlook) метод, чтобы установить внешний вид управления листом свойства. Затем позвоните в [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) метод для инициализации внутреннего объекта управления вкладками. Используйте этот метод для извлечения объекта управления вкладками, а затем используйте этот объект для работы со вкладками на листе свойств.

Этот метод утверждает в режиме отладки, если управление листом свойств не отображается в стиле Microsoft OneNote.

## <a name="cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl

Инициализирует появление текущего элемента управления «Страница свойств».

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно управления листом свойства.

### <a name="remarks"></a>Примечания

Управление листом свойств может отображаться в нескольких различных формах, таких как набор страниц вкладок, управление деревом или список кнопок навигации. Используйте метод [CMFCPropertySheet::SetLook,](#setlook) чтобы указать внешний вид управления листом свойства.

## <a name="cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage

Вызывается платформой при включении страницы свойств.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
(в) Указатель на объект страницы свойств, представляющий страницу включенного свойства.

### <a name="remarks"></a>Примечания

По умолчанию этот метод гарантирует прокрутку страницы включенного свойства в представление. Если стиль текущего листа свойств содержит панель Microsoft Outlook, этот метод устанавливает соответствующую кнопку Outlook в проверенном состоянии.

## <a name="cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader

Вызывается в рамках, чтобы нарисовать заголовок для пользовательской страницы свойства.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*nСтраница*<br/>
(в) Номер страницы свойства с нулевым уровнем.

*rectHeader*<br/>
(в) Ограничивающий прямоугольник, который определяет, где нарисовать заголовок.

### <a name="remarks"></a>Примечания

По умолчанию этот метод не выполняет никаких действий. Если вы переопределяете этот метод, позвоните в [метод CMFCPropertySheet::EnablePageHeader](#enablepageheader) перед вызовом этого метода.

## <a name="cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage

Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
(в) Указатель на объект страницы свойств, представляющий страницу свойств для удаления.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCPropertySheet::УдалитьКатегория

Удаляет узел из элемента управления «Дерево».

```cpp
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Параметры

*pКатегория*<br/>
(в) Указатель на категорию (узла) для удаления.

### <a name="remarks"></a>Примечания

Используйте этот метод для удаления узла, который также называют категорией, из управления деревом. Используйте метод [CMFCPropertySheet::AddTreeCategory,](#addtreecategory) чтобы добавить узла в управление деревом.

## <a name="cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCPropertySheet::RemovePage

Удаляет страницу свойств из таблицы свойств.

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Параметры

*pPage*<br/>
(в) Указатель на объект страницы свойств, представляющий страницу свойств для удаления. Не может быть NULL.

*nСтраница*<br/>
(в) Нулевой индекс страницы для удаления.

### <a name="remarks"></a>Примечания

Этот метод удаляет указанную страницу свойств и уничтожает связанное с ней окно. Объект страницы свойства, который указывает параметр *pPage,* не разрушается до тех пор, пока окно [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) не будет закрыто.

## <a name="cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFCPropertySheet::SetIconsList

Указывает список изображений, используемых в элементе управления навигации панели Outlook.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>Параметры

*uiImageListResID*<br/>
(в) Идентификатор ресурса списка изображений.

*Cx*<br/>
(в) Ширина, в пикселях, иконок в списке изображений.

*clrПрозрачный*<br/>
(в) Прозрачный цвет изображения. Части изображения, которые этого цвета будут прозрачными. Значение по умолчанию является пурпурный цвет, RGB (255,0,255).

*hIcons*<br/>
(в) Ручка к существующему списку изображений.

### <a name="return-value"></a>Возвращаемое значение

В первом методе перегрузки синтаксиса, TRUE, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Если лист свойств находится в стиле Microsoft Outlook, в рамках отображается список кнопок навигации, называемый элементом управления панелью Outlook, слева от листа свойств. Используйте этот метод для настройки списка изображений, которые будут использоваться в управлении панелью Outlook.

Для получения дополнительной информации о методах, поддерживающих этот метод, см. [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) и [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Для получения дополнительной информации о том, как установить стиль листа свойств, [см. CMFCPropertySheet::SetLook](#setlook).

## <a name="cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFCPropertySheet::SetLook

Задает внешний вид таблицы свойств.

```cpp
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Параметры

*Посмотрите*<br/>
(в) Одно из значений перечисления, которое определяет внешний вид листа свойств. Стиль по умолчанию для `CMFCPropertySheet::PropSheetLook_Tabs`листа свойств. Для получения дополнительной информации смотрите таблицу в разделе Замечания по этой теме.

*nNavControlWidth*<br/>
(в) Ширина управления навигацией в пикселях. По умолчанию используется значение 100.

### <a name="remarks"></a>Примечания

Чтобы отобразить лист свойств в стиле, кроме по умолчанию, позвоните по этому методу перед созданием окна листа свойств.

В следующей таблице перечислены значения перечисления, которые могут быть указаны в параметре *взгляда.*

|Значение|Описание|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(По умолчанию) Отображает вкладку для каждой страницы свойств. Вкладки отображаются в верхней части листа свойств и укладываются, если есть больше вкладок, чем помещается в одном ряду.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Отображает список кнопок навигации в стиле панели Microsoft Outlook в левой части листа свойств. Каждая кнопка в списке соответствует странице свойств. Рамки отображает стрелка миги, если кнопок больше, чем помещается в видимую область списка.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Отображает элемент управления деревьями в левой части листа свойств. Каждый родительский или детский узлы управления деревом соответствует странице свойства. Рамки отображает стрелки прокрутки, если есть больше узлов, чем помещается в видимой области управления деревом.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Отображает вкладку в стиле Microsoft OneNote для каждой страницы свойств. Рамки отображают вкладки в верхней части листа свойств и прокрутки стрелок, если есть больше вкладок, чем помещается в одном ряду.|
|`CMFCPropertySheet::PropSheetLook_List`|Отображает список в левой части листа свойств. Каждый элемент списка соответствует странице свойств. Рамки отображает стрелка мигирования, если есть больше элементов списка, чем помещается в видимой области списка.|

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
