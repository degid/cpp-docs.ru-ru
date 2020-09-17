---
title: CmFCToolBarEditButtonButton класса
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: 064ebe1c8fe377064d410d09e5ef60ed628df2f3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753997"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CmFCToolBarEditButtonButton класса

Кнопка панели инструментов, содержащая элемент управления эдитом [(Класс CEdit).](../../mfc/reference/cedit-class.md)

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarEditButton::CMFCToolBarEditButton](#cmfctoolbareditboxbutton)|Формирует объект `CMFCToolBarEditBoxButton`.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarEditButton::CanBeStretched](#canbestretched)|Уточняется, может ли пользователь растягивать кнопку во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarEditButton::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов на текущую кнопку. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditButton::CreateEdit](#createedit)|Создает новое управление элементами управления в кнопке.|
|`CMFCToolBarEditBoxButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCToolBarEditButton::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении с указанным идентификатором команды.|
|[CMFCToolBarEditButton::GetContentsAll](#getcontentsall)|Извлекает текст первого элемента управления панели инструментов для редактирования, в который есть указанный идентификатор команды.|
|[CMFCToolBarEditButton::GetContextMenuID](#getcontextmenuid)|Извлекает идентификатор ресурса меню ярлыка, который связан с кнопкой.|
|[CMFCToolBarEditButton::GetEditBorder](#geteditborder)|Извлекает прямоугольник ограниченной части кнопки отодевать окно.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditButton::GetEditBox](#geteditbox)|Возвращает указатель на элемент управления отсечения, встроенный в кнопку.|
|[CMFCToolBarEditButton::GetHwnd](#gethwnd)|Извлекает ручку окна, связанную с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[CMFCToolBarEditButton::GetInvalidateRect](#getinvalidaterect)|Извлекает область клиентской области кнопки, которая должна быть перерисована. (Переопределяет [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCToolBarEditButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли граница кнопки при нажатии на кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarEditButton::IsFlatMode](#isflatmode)|Определяет, имеют ли кнопки для отсечения кнопок коробки плоский стиль.|
|[CMFCToolBarEditButton::NotifyCommand](#notifycommand)|Уточняется, обрабатывает ли кнопка [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarEditButton::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается по фреймворку при добавлении кнопки в поле **настраиваемых** диалогов. (Переопределяет [CMFCToolBarButton::OnAddTo CustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Вызывается фреймворком для расчета размера кнопки для заданного контекста устройства и состояния стыковки. (Переопределяет [CMFCToolBarButton::OncalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarEditButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarEditButton::OnClick](#onclick)|Вызывается по фреймворку, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarEditButton::OnCtlColor](#onctlcolor)|Вызывается по системе, когда панель родительских инструментов обрабатывает WM_CTLCOLOR сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Вызывается в рамках, чтобы нарисовать кнопку с помощью указанных стилей и опций. (Переопределяет [CMFCToolBarButton::Ondraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Вызывается фреймворком, чтобы нарисовать кнопку в панели **команд** в поле **настраивания** диалогов. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarEditButton::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается рамками, когда глобальный шрифт изменился. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarEditButton::OnMove](#onmove)|Вызывается по фреймворку при движении родительской панели инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarEditButton::OnShow](#onshow)|Вызывается по фрейму, когда кнопка становится видимой или невидимой. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[CMFCToolBarEditButton::OnSize](#onsize)|Вызывается в фреймворке, когда панель родительских инструментов изменяет свой размер или положение, и это изменение приводит к изменению размера кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarEditButton::OnUpdateToolTip](#onupdatetooltip)|Вызывается по фреймворку, когда панель родительских инструментов обновляет свой текст инструментария. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Читает этот объект из архива или запишет его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Заполняет предоставленный `CAccessibilityData` объект данными о доступности из кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditButton::SetContents](#setcontents)|Устанавливает текст в элементару кнопки.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditButton::SetContentsAll](#setcontentsall)|Находит кнопку управления редактированием с указанным идентификатором команды и устанавливает текст в управлении редактированием этой кнопки.|
|[CMFCToolBarEditButton::SetContextMenuID](#setcontextmenuid)|Упоняет идентификатор ресурса меню ярлыка, который связан с кнопкой.|
|[CMFCToolBarEditButton::SetFlatMode](#setflatmode)|Определяет плоский стиль внешний вид кнопок коробки для отсечения в приложении.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditButton::SetStyle](#setstyle)|Определяет стиль кнопки. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Примечания

Чтобы добавить кнопку ящика для отсечения в панель инструментов, выполните следующие действия:

1. Зарезервируйте идентификатор ресурсов для кнопки в родительском ресурсе панели инструментов.

2. Постройте `CMFCToolBarEditBoxButton` объект.

3. В обработчике сообщений, который обрабатывает AFX_WM_RESETTOOLBAR сообщение, замените кнопку манекена новой кнопкой комбо-бокса с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Для получения дополнительной информации, [см. Walkthrough: Ввод контроля на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarEditBoxButton` . На примере показано, как указать, что пользователь может растянуть кнопку во время настройки, указать, что граница кнопки отображается, когда пользователь нажимает на кнопку, установить текст в управлении текстовым ящиком, указать плоский стиль внешний вид кнопок редактирования в приложении, а также указать стиль управления окном панели инструментов.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbareditboxbutton.h

## <a name="cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarEditButton::CanBeStretched

Уточняется, может ли пользователь растягивать кнопку во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает TRUE.

### <a name="remarks"></a>Примечания

По умолчанию фреймворк не позволяет пользователю растягивать кнопку панели инструментов во время настройки. Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растягивать кнопку панели инструментов для отодвивания во время настройки.

## <a name="cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditButton::CMFCToolBarEditButton

Строит объект [CMFCToolBarEditButtonButton.](../../mfc/reference/cmfctoolbareditboxbutton-class.md)

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Упогоняет идентификатор управления.

*iImage*<br/>
(в) Определяет нулевой индекс изображения панели инструментов. Изображение находится в объекте [класса CMFCToolBarImages,](../../mfc/reference/cmfctoolbarimages-class.md) который поддерживает класс [CMFCToolBar.](../../mfc/reference/cmfctoolbar-class.md)

*dwStyle*<br/>
(в) Определяет стиль управления изменением.

*iWidth*<br/>
(в) Определяет ширину пикселей управления отсеивательь.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию устанавливает стиль управления изменением в следующую комбинацию:

WS_CHILD WS_VISIBLE ES_AUTOHSCROLL

Ширина элемента управления по умолчанию составляет 150 пикселей.

## <a name="cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarEditButton::CopyFrom

Копирует свойства другой кнопки панели инструментов на текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Ссылка на кнопку исходного кода, из которой можно скопировать.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен быть `CMFCToolBarEditBoxButton`типа .

## <a name="cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarEditButton::CreateEdit

Создает новое управление элементами управления в кнопке.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Определяет родительское окно элемента управления отсечения. Она не должна быть NULL.

*rect*<br/>
(в) Определяет размер и положение элемента управления отсечения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на недавно созданный элемент управления правкой; это NULL, если создание элемента управления и вложение не удается.

### <a name="remarks"></a>Примечания

Вы строите `CMFCToolBarEditBoxButton` объект в два этапа. Сначала вызов конструктора, а `CreateEdit`затем вызов , который создает управление windows `CMFCToolBarEditBoxButton` отсвазание и прикрепляет его к объекту.

## <a name="cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarEditButton::GetByCmd

Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении с указанным идентификатором команды.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarEditBoxButton` объект в приложении, который имеет указанный идентификатор команды, или NULL, если такой объект не существует.

### <a name="remarks"></a>Примечания

Этот общий метод утилиты используется такими методами, как [CMFCToolBarEditButtonButton::SetContentsAll](#setcontentsall) и [CMFCToolBarEditButton::GetContentsAll](#getcontentsall) установить или получить текст первого элемента управления панели редактирования, который имеет указанный идентификатор команды.

## <a name="cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>CMFCToolBarEditButton::GetContentsAll

Извлекает текст первого элемента управления панели инструментов для редактирования, в который есть указанный идентификатор команды.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки, из которой можно получить содержимое.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий текст первого элемента управления панели инструментов для редактирования, который имеет указанный идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод возвращает пустую `CMFCToolBarEditBoxButton` строку, если у объектов нет указанного идентификатора команды.

## <a name="cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarEditButton::GetContextMenuID

Извлекает идентификатор ресурса меню ярлыка, который связан с кнопкой.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню ярлыка, который связан с кнопкой или 0, если кнопка не имеет связанного меню ярлыка.

### <a name="remarks"></a>Примечания

Платформа использует идентификатор ресурса для создания меню ярлыка, когда пользователь справа нажимает на кнопку.

## <a name="cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>CMFCToolBarEditButton::GetEditBorder

Извлекает прямоугольник ограниченной части кнопки отодевать окно.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Параметры

*rectBorder*<br/>
(ваут) Ссылка на `CRect` объект, который получает ограничивающий прямоугольник.

### <a name="remarks"></a>Примечания

Этот метод извлекает прямоугольник ограничивающего элемента управления правки в координатах клиента. Он расширяет размер прямоугольника в каждом направлении на один пиксель.

[Метод CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) вызывает этот метод, когда `CMFCToolBarEditBoxButton` он рисует границу вокруг объекта.

## <a name="cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>CMFCToolBarEditButton::GetEditBox

Возвращает указатель на элемент управления [класса CEdit,](../../mfc/reference/cedit-class.md) встроенный в кнопку.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на управление [cEdit Class,](../../mfc/reference/cedit-class.md) содержащееся в кнопке. Это NULL, `CEdit` если элемент управления еще не создан.

### <a name="remarks"></a>Примечания

Вы создаете `CEdit` элемент управления, позвонив [по CMFCToolBarEditButton::CreateEdit](#createedit).

## <a name="cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarEditButton::GetHwnd

Извлекает ручку окна, связанную с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка окна, связанная с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод переопределяет [метод CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод, вернув ручку окна части управления правкой кнопки отображаемого окна.

## <a name="cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarEditButton::GetInvalidateRect

Извлекает область клиентской области кнопки, которая должна быть перерисована.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CRect` опознававший область, который должен быть перерисован.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), путем включения в регионе области текстовой метки.

## <a name="cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarEditButton::HaveHotBorder

Определяет, отображается ли граница кнопки при нажатии на кнопку.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка отображает свою границу при выборе; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), путем возвращения ненулевого значения, если элемент управления виден.

## <a name="cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarEditButton::IsFlatMode

Определяет, имеют ли кнопки для отсечения кнопок коробки плоский стиль.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопки имеют плоский стиль; в противном случае, 0.

### <a name="remarks"></a>Примечания

По умолчанию кнопки для отсеивания коробок имеют плоский стиль. Используйте метод [CMFCToolBarEditButtonButton::SetFlatMode,](#setflatmode) чтобы изменить внешний вид плоского стиля для вашего приложения.

## <a name="cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarEditButton::NotifyCommand

Уточняется, обрабатывает ли кнопка [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*iNotifyCode*<br/>
(в) Сообщение об уведомлении, связанное с командой.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если кнопка обрабатывает WM_COMMAND сообщение, или FALSE, чтобы указать, что сообщение должно быть обработано родительской панели инструментов.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, когда он собирается отправить [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение в родительское окно.

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::NotifyCommand)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)путем обработки [EN_UPDATE](/windows/win32/Controls/en-update) уведомления. Для каждого редактирования окна с тем же идентификатором команды, что и этот объект, он устанавливает свою текстовую метку на текстовую метку этого объекта.

## <a name="cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarEditButton::OnAddToCustomizePage

Вызывается по фреймворку при добавлении кнопки в поле **настраиваемых** диалогов.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) путем копирования свойств из управления коробкой отсечения в любой панели инструментов, которая имеет тот же идентификатор команды, что и этот объект. Этот метод ничего не делает, если ни одна панель инструментов не имеет элементуправления коробки для отсечения, которое имеет тот же идентификатор команды, что и этот объект.

Для получения дополнительной информации о **настраиваемый** диалоговый ящик, [см.](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)

## <a name="cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarEditButton::OnChangeParentWnd

Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::OnChangeParentWnd)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)путем воссоздания внутреннего `CEdit` объекта.

## <a name="cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarEditButton::OnClick

Вызывается по фреймворку, когда пользователь нажимает кнопку мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Не используется.

*bDelay*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка обрабатывает сообщение щелчка; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::OnClick),](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)вернув `CEdit` ненулевое значение, если виден внутренний объект.

## <a name="cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarEditButton::OnCtlColor

Вызывается по системе, когда панель родительских инструментов обрабатывает WM_CTLCOLOR сообщение.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображаемый кнопкой.

*nCtlColor*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Ручка к глобальной оконной щетке.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), установив текст и фоновые цвета предоставленного контекста устройства на глобальный текст и фоновые цвета, соответственно.

Для получения дополнительной информации о глобальных опциях, доступных для вашего приложения, с [AFX_GLOBAL_DATAм.](../../mfc/reference/afx-global-data-structure.md)

## <a name="cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarEditButton::OnGlobalFontsChanged

Вызывается рамками, когда глобальный шрифт изменился.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта управления на глобальный шрифт.

Для получения дополнительной информации о глобальных опциях, доступных для вашего приложения, с [AFX_GLOBAL_DATAм.](../../mfc/reference/afx-global-data-structure.md)

## <a name="cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarEditButton::OnMove

Вызывается по фреймворку при движении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию [(CMFCToolBarButton::OnMove)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)путем обновления положения внутреннего `CEdit` объекта

## <a name="cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarEditButton::OnShow

Вызывается по фрейму, когда кнопка становится видимой или невидимой.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) Определяет, видна ли кнопка. Если этот параметр является правдой, кнопка видна. В противном случае кнопка не видна.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) путем отображения кнопки, если *bShow* является правдой. В противном случае этот метод скрывает кнопку.

## <a name="cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarEditButton::OnSize

Вызывается в фреймворке, когда панель родительских инструментов изменяет свой размер или положение, и это изменение приводит к изменению размера кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*iSize*<br/>
(в) Новая ширина кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию, [CMFCToolBarButton::OnSize,](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)обновляя размер и положение внутреннего `CEdit` объекта.

## <a name="cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarEditButton::OnUpdateToolTip

Вызывается по фреймворку, когда панель родительских инструментов обновляет свой текст инструментария.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Не используется.

*iButtonIndex*<br/>
[in] Не используется.

*wndToolTip*<br/>
(в) Элемент управления, отображаемого текстом tooltip.

*Ул*<br/>
(ваут) Объект, `CString` который получает обновленный текст tooltip.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод обновляет текст инструментария; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) путем отображения текста инструментария, который связан с частью редактирования кнопки. Если внутренний `CEdit` объект NULL или ручка окна `CEdit` объекта не идентифицирует существующее окно, этот метод ничего не делает и возвращает FALSE.

## <a name="cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>CMFCToolBarEditButton::SetContents

Устанавливает текст в элементуправления текстового поля.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Параметры

*sContents*<br/>
(в) Определяет новый текст для настройки.

## <a name="cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>CMFCToolBarEditButton::SetContentsAll

Находит объект [CMFCToolBarEditButtonButton,](../../mfc/reference/cmfctoolbareditboxbutton-class.md) который имеет указанный идентификатор команды и устанавливает указанный текст в своем текстовом поле.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Упогоняет идентификатор команды управления, для которого текст будет изменен.

*strСодержимо*<br/>
(в) Определяет новый текст для настройки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если текст был установлен; 0, `CMFCToolBarEditBoxButton` если элемент управления с указанным идентификатором команды не существует.

## <a name="cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarEditButton::SetContextMenuID

Упоняет идентификатор ресурса меню ярлыка, который связан с кнопкой.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор ресурса меню ярлыка.

### <a name="remarks"></a>Примечания

Платформа использует идентификатор ресурса для создания меню ярлыка, когда пользователь справа щелкает кнопку панели инструментов.

## <a name="cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarEditButton::SetFlatMode

Определяет плоский стиль внешний вид кнопок коробки для отсечения в приложении.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Параметры

*bFlat*<br/>
(в) Плоский стиль для отсеивания кнопок коробки. Если этот параметр является правдой, плоский вид стиля включен; в противном случае плоский вид стиля отключен.

### <a name="remarks"></a>Примечания

По умолчанию плоский стиль для отсеивания кнопок коробки является правдой. Используйте метод [CMFCToolBarEditButtonButton::IsFlatMode](#isflatmode) для получения плоского стиля для вашего приложения.

## <a name="cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarEditButton::SetStyle

Определяет стиль управления коробкой для проверки панели инструментов.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
(в) Новый стиль для установки.

### <a name="remarks"></a>Примечания

Этот метод устанавливает [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) *nStyle* Он также отстраняет текстовый ящик, когда приложение находится в режиме настройки, и позволяет ему, когда приложение не находится в режиме настройки (см. [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) и [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Посмотреть [стили управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) для получения списка действительных флагов стиля.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::Заменить кнопку](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
