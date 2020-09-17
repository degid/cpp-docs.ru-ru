---
title: Класс CToolBar
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: cbb2d1bb797737a14e9728d339305bf9c371b543
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752209"
---
# <a name="ctoolbar-class"></a>Класс CToolBar

Панели элементов управления, имеющие строку растровых кнопок и необязательные разделители.

## <a name="syntax"></a>Синтаксис

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|Формирует объект `CToolBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ctoolbar::CommandtoIndex](#commandtoindex)|Возвращает индекс кнопки с заданным идентификатором команды.|
|[CToolBar::Создание](#create)|Создает панель инструментов Windows и `CToolBar` прикрепляет ее к объекту.|
|[CToolBar::CreateEx](#createex)|Создает `CToolBar` объект с дополнительными `CToolBarCtrl` стилями для встроенного объекта.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Извлекает идентификатор, стиль и номер изображения кнопки.|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Извлекает стиль для кнопки.|
|[CToolBar::GetButtonText](#getbuttontext)|Извлекает текст, который будет отображаться на кнопке.|
|[CToolBar::GetItemID](#getitemid)|Возвращает идентификатор команды кнопки или сепаратора в данном индексе.|
|[CToolBar::GetItemRect](#getitemrect)|Извлекает прямоугольник дисплея для элемента в данном индексе.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Позволяет прямой доступ к базовому общему элементу управления.|
|[CToolBar::LoadBitmap](#loadbitmap)|Загружает битную карту, содержащую изображения bitmap-button.|
|[CToolBar::LoadToolBar](#loadtoolbar)|Загружает ресурс панели инструментов, созданный с помощью редактора ресурсов.|
|[CToolBar::SetBitmap](#setbitmap)|Устанавливает битототовое изображение.|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Устанавливает идентификатор, стиль и номер изображения кнопки.|
|[CToolBar::SetButtons](#setbuttons)|Устанавливает стили кнопок и индекс изображений кнопок в биткарте.|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Устанавливает стиль для кнопки.|
|[CToolBar::SetButtonText](#setbuttontext)|Устанавливает текст, который будет отображаться на кнопке.|
|[CToolBar::SetHeight](#setheight)|Устанавливает высоту панели инструментов.|
|[CToolBar::SetSizes](#setsizes)|Устанавливает размеры кнопок и их bitmaps.|

## <a name="remarks"></a>Примечания

Кнопки могут действовать как кнопки, кнопки флажка или кнопки радио. `CToolBar`объекты обычно являются встроенными членами объектов окна кадра, полученных из класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIFrameWnd.](../../mfc/reference/cmdiframewnd-class.md)

[CToolBar::GetToolBarCtrl](#gettoolbarctrl), функция участника, новая для MFC 4.0, позволяет воспользоваться поддержкой общего управления Windows для настройки панели инструментов и дополнительной функциональности. `CToolBar`функции членов дают вам большую часть функциональности общих элементов управления Windows; однако, когда `GetToolBarCtrl`вы звоните, вы можете дать ваши панели инструментов еще больше характеристик Windows 95/98 панели инструментов. Когда вы `GetToolBarCtrl`звоните, он возвращает `CToolBarCtrl` ссылку на объект. Дополнительную информацию о проектировании панелей инструментов с помощью общих элементов управления Windows можно узнать в [CToolBarCtrl.](../../mfc/reference/ctoolbarctrl-class.md) Более подробную информацию об общих элементах управления [можно](/windows/win32/Controls/common-controls-intro) узнать в SDK Windows.

Визуальный C ' предоставляет вам два метода для создания панели инструментов. Чтобы создать ресурс панели инструментов с помощью редактора ресурсов, выполните следующие действия:

1. Создайте ресурс панели инструментов.

1. Постройте `CToolBar` объект.

1. Вызов функции [Create](#create) (или [CreateEx)](#createex)для создания панели `CToolBar` инструментов Windows и прикрепите ее к объекту.

1. Вызов [LoadToolBar](#loadtoolbar) для загрузки ресурса панели инструментов.

В противном случае выполните следующие действия.

1. Постройте `CToolBar` объект.

1. Вызов функции [Create](#create) (или [CreateEx)](#createex)для создания панели `CToolBar` инструментов Windows и прикрепите ее к объекту.

1. Позвоните [LoadBitmap](#loadbitmap) для загрузки битовой карты, содержащей изображения кнопки панели инструментов.

1. Позвоните [SetButtons,](#setbuttons) чтобы установить стиль кнопки и связать каждую кнопку с изображением в битной карте.

Все изображения кнопок в панели инструментов взяты из одной битовой карты, которая должна содержать одно изображение для каждой кнопки. Все изображения должны быть одного размера; по умолчанию 16 пикселей в ширину и 15 пикселей. Изображения должны быть бок о бок в бит-карте.

Функция `SetButtons` принимает указатель на массив идентификаторов управления и целый ряд, который определяет количество элементов в массиве. Функция устанавливает идентификатор каждой кнопки к значению соответствующего элемента массива и присваивает каждой кнопке индекс изображения, который определяет положение изображения кнопки в битной карте. Если элемент массива имеет значение ID_SEPARATOR, индекс изображения не назначается.

Порядок изображений в битной карте, как правило, порядок, в котором они нарисованы на экране, но вы можете использовать функцию [SetButtonInfo,](#setbuttoninfo) чтобы изменить связь между порядком изображения и порядком рисования.

Все кнопки в панели инструментов имеют одинаковый размер. По умолчанию 24 х 22 пикселей, в соответствии с *Windows Интерфейс Руководящие принципы для разработки программного обеспечения*. Любое дополнительное пространство между размерами изображения и кнопки используется для формирования границы вокруг изображения.

Каждая кнопка имеет одно изображение. Различные состояния и стили кнопок (нажатые, вверх, вниз, отключенные, отключенные и неопределенные) генерируются из этого одного изображения. Хотя bitmaps может быть любого цвета, вы можете достичь наилучших результатов с изображениями в черном и оттенки серого.

> [!WARNING]
> `CToolBar`поддерживает bitmaps с максимум 16 цветов. При загрузке изображения в редактор панели инструментов Visual Studio автоматически преобразует изображение в 16-цветную бит-карту, если это необходимо, и отображает предупреждающее сообщение, если изображение было преобразовано. Если вы используете изображение с более чем 16 цветами (с помощью внешнего редактора для редактировок), приложение может вести себя неожиданно.

Кнопки панели инструментов имитируют кнопки по умолчанию. Тем не менее, кнопки панели инструментов могут также имитировать кнопки флажка или кнопки радио. Кнопки чек-бокса имеют три состояния: проверенные, очищенные и неопределенные. Кнопки радио имеют только два состояния: проверены и очищены.

Чтобы установить индивидуальную кнопку или стиль сепаратора, не указывая на массив, позвоните в `SetButtons` [GetButtonStyle,](#getbuttonstyle) чтобы получить стиль, а затем позвоните в [SetButtonStyle](#setbuttonstyle) вместо . `SetButtonStyle`является наиболее полезным, когда вы хотите изменить стиль кнопки во время выполнения.

Чтобы назначить текст для отображаться на кнопке, позвоните [GetButtonText,](#getbuttontext) чтобы получить текст, чтобы появиться на кнопке, а затем позвоните [SetButtonText,](#setbuttontext) чтобы установить текст.

Чтобы создать кнопку флажка, назначайте `CCmdUI` ей TBBS_CHECKBOX `SetCheck` стиля или используйте функцию члена объекта в обработчике ON_UPDATE_COMMAND_UI. Вызов `SetCheck` превращает кнопку в кнопку чек-бокса. Передайте `SetCheck` аргумент 0 для бесконтрольного, 1 для проверенного или 2 для неопределенного.

Чтобы создать кнопку радио, позвоните функции члена [setRadio](../../mfc/reference/ccmdui-class.md#setradio) объекта [CCmdUI](../../mfc/reference/ccmdui-class.md) от ON_UPDATE_COMMAND_UI обработчика. Передайте `SetRadio` аргумент 0 для бесконтрольного или ненулевого для проверки. Для того, чтобы обеспечить взаимоисключающее поведение радиогруппы, вы должны иметь ON_UPDATE_COMMAND_UI обработчики для всех кнопок в группе.

Для получения дополнительной `CToolBar`информации об использовании, см. статью [MFC Toolbar Реализация](../../mfc/mfc-toolbar-implementation.md) и [техническое примечание 31: Контроль баров](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="ctoolbarcommandtoindex"></a><a name="commandtoindex"></a>Ctoolbar::CommandtoIndex

Эта функция участника возвращает индекс первой кнопки панели инструментов, начиная `nIDFind`с позиции 0, идентификатор команды совпадает с идентификатором.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

*nIDFind*<br/>
Идентификатор команды кнопки панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Индекс кнопки, или -1, если ни одна кнопка не имеет данный идентификатор команды.

## <a name="ctoolbarcreate"></a><a name="create"></a>CToolBar::Создание

Эта функция члена создает панель инструментов Windows (детское `CToolBar` окно) и связывает ее с объектом.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на окно, которое является родителем панели инструментов.

*dwStyle*<br/>
Стиль панели инструментов. Дополнительные стили панели инструментов поддерживаются:

- CBRS_TOP панель управления находится в верхней части окна рамы.

- CBRS_BOTTOM панель управления находится в нижней части окна кадра.

- CBRS_NOALIGN панель управления не перепозиционируется при повторном размере.

- CBRS_TOOLTIPS панели Управления отображает советы инструментов.

- CBRS_SIZE_DYNAMIC панель управления динамична.

- CBRS_SIZE_FIXED панель управления фиксируется.

- CBRS_FLOATING панель управления плавает.

- CBRS_FLYBY-хау отображает информацию о кнопке.

- CBRS_HIDE_INPLACE панель управления не отображается пользователю.

*nID*<br/>
Идентификатор панели инструментов для окна ребенка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Он также устанавливает высоту панели инструментов на значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

## <a name="ctoolbarcreateex"></a><a name="createex"></a>CToolBar::CreateEx

Вызовите эту функцию, чтобы создать панель инструментов `CToolBar` Windows (детское окно) и связать ее с объектом.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на окно, которое является родителем панели инструментов.

*dwCtrlStyle*<br/>
Дополнительные стили для создания встроенного объекта [CToolBarCtrl.](../../mfc/reference/ctoolbarctrl-class.md) По умолчанию это значение устанавливается в TBSTYLE_FLAT. Полный список стилей панели инструментов можно узнать *на dwStyle.*

*dwStyle*<br/>
Стиль панели инструментов. В списке соответствующих стилей можно ознакомиться со [стилями управления инструментами и кнопками](/windows/win32/Controls/toolbar-control-and-button-styles) в SDK Windows.

*rcГраници*<br/>
Объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) определяющий ширину границ окна панели инструментов. Эти границы установлены до 0,0,0,0 0 по умолчанию, что приводит к окну панели инструментов без границ.

*nID*<br/>
Идентификатор панели инструментов для окна ребенка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Он также устанавливает высоту панели инструментов на значение по умолчанию.

Используйте, `CreateEx`а не [создать](#create), когда определенные стили должны присутствовать во время создания встроенного управления панели инструментов. Например, установите *dwCtrlStyle* для TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT для создания панели инструментов, напоминающей панели инструментов Internet Explorer 4.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

## <a name="ctoolbarctoolbar"></a><a name="ctoolbar"></a>CToolBar::CToolBar

Эта функция члена `CToolBar` строит объект и устанавливает размеры по умолчанию.

```
CToolBar();
```

### <a name="remarks"></a>Примечания

Вызов функции [члена Create](#create) для создания окна панели инструментов.

## <a name="ctoolbargetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBar::GetButtonInfo

Эта функция элемента получает идентификатор управления, стиль и индекс изображения кнопки панели инструментов или сепаратора в месте, указанном *nIndex.*

```cpp
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс кнопки панели инструментов или сепаратора, информация которого должна быть извлечена.

*nID*<br/>
Ссылка на UINT, установленную на идентификатор команды кнопки.

*nStyle*<br/>
Ссылка на UINT, который установлен на стиль кнопки.

*iImage*<br/>
Ссылка на ряд, который устанавливается к индексу изображения кнопки в биткарте.

### <a name="remarks"></a>Примечания

Эти значения присваиваются переменным, на которые ссылаются *nID,* *nStyle*и *iImage.* Индекс изображения — это положение изображения в битной карте, содержащее изображения для всех кнопок панели инструментов. Первое изображение находится на позиции 0.

Если *nIndex* определяет сепаратор, *iImage* устанавливается на ширину сепаратора в пикселях.

## <a name="ctoolbargetbuttonstyle"></a><a name="getbuttonstyle"></a>CToolBar::GetButtonStyle

Вызов эту функцию участника, чтобы получить стиль кнопки или сепаратора на панели инструментов.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Извлекается индекс кнопки панели инструментов или стиль сепаратора.

### <a name="return-value"></a>Возвращаемое значение

Стиль кнопки или сепаратора, указанный *nIndex.*

### <a name="remarks"></a>Примечания

Стиль кнопки определяет, как отображается кнопка и как она реагирует на ввод пользователя. Ознакомьтесь с примерами стилей кнопок [SetButtonStyle.](#setbuttonstyle)

## <a name="ctoolbargetbuttontext"></a><a name="getbuttontext"></a>CToolBar::GetButtonText

Вызов эту функцию участника для извлечения текста, который отображается на кнопке.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс текста, который необходимо получить.

*rString*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) который будет содержать текст для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий текст кнопки.

### <a name="remarks"></a>Примечания

Вторая форма этой функции `CString` члена заполняет объект текстом строки.

## <a name="ctoolbargetitemid"></a><a name="getitemid"></a>CToolBar::GetItemID

Эта функция участника возвращает идентификатор команды кнопки или сепаратора, указанный *nIndex.*

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента, идентификатор которого должен быть извлечен.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды кнопки или сепаратора, указанный *nIndex.*

### <a name="remarks"></a>Примечания

Сепараторы возвращаются ID_SEPARATOR.

## <a name="ctoolbargetitemrect"></a><a name="getitemrect"></a>CToolBar::GetItemRect

Эта функция члена `RECT` заполняет структуру, адрес которой содержится в *lpRect* с координатами кнопки или сепаратора, указанными *nIndex.*

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента (кнопка или сепаратор), координаты прямоугольника которого должны быть извлечены.

*lpRect*<br/>
Адрес структуры [RECT,](/windows/win32/api/windef/ns-windef-rect) которая будет содержать координаты товара.

### <a name="remarks"></a>Примечания

Координаты находятся в пикселях относительно верхнего левого угла панели инструментов.

Используйте `GetItemRect` для получения координат сепаратора, который вы хотите заменить комбо-коробкой или другим управлением.

### <a name="example"></a>Пример

  Смотрите пример [для CToolBar:SetSs](#setsizes).

## <a name="ctoolbargettoolbarctrl"></a><a name="gettoolbarctrl"></a>CToolBar::GetToolBarCtrl

Эта функция члена позволяет прямой доступ к базовому общему элементу управления.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CToolBarCtrl`.

### <a name="remarks"></a>Примечания

Используйте, `GetToolBarCtrl` чтобы воспользоваться функциональностью панели инструментов Windows общего управления, и воспользоваться поддержкой [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) обеспечивает настройку панели инструментов.

Для получения дополнительной информации об [Controls](../../mfc/controls-mfc.md) использовании [Common Controls](/windows/win32/Controls/common-controls-intro) общих элементов управления см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

## <a name="ctoolbarloadbitmap"></a><a name="loadbitmap"></a>CToolBar::LoadBitmap

Вызов исчерпайте эту функцию участника для загрузки битовой карты, указанной `lpszResourceName` или `nIDResource`.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на имя ресурса загружаемых битов.

*nIDResource*<br/>
Идентификатор ресурса битной карты, подавленной.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Бит-карта должна содержать одно изображение для каждой кнопки панели инструментов. Если изображения не имеют стандартного размера (16 пикселей в ширину и 15 пикселей в высоту), позвоните [SetSizes,](#setsizes) чтобы установить размеры кнопок и их изображения.

> [!WARNING]
> `CToolBar`поддерживает bitmaps с максимум 16 цветов. При загрузке изображения в редактор панели инструментов Visual Studio автоматически преобразует изображение в 16-цветную бит-карту, если это необходимо, и отображает предупреждающее сообщение, если изображение было преобразовано. Если вы используете изображение с более чем 16 цветами (с помощью внешнего редактора для редактировок), приложение может вести себя неожиданно.

## <a name="ctoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CToolBar::LoadToolBar

Позвоните в эту функцию участника для загрузки панели инструментов, указанной *lpszResourceName* или *nIDResource.*

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на имя панели ресурсов, подающейся загрузке.

*nIDResource*<br/>
Идентификатор ресурса панели инструментов, подавленной.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительную информацию о создании ресурса панели инструментов можно узнать в [редакторе панели инструментов.](../../windows/toolbar-editor.md)

### <a name="example"></a>Пример

  Смотрите пример [Для CToolBar::CreateEx](#createex).

## <a name="ctoolbarsetbitmap"></a><a name="setbitmap"></a>CToolBar::SetBitmap

Вызовите эту функцию участника, чтобы установить изображение биткарты для панели инструментов.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Параметры

*hbmImageWell*<br/>
Обработка изображения битовой карты, связанной с панелью инструментов.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Например, `SetBitmap` вызов для изменения битотного изображения после того, как пользователь предпринимает действие на документ, изменяя действие кнопки.

## <a name="ctoolbarsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBar::SetButtonInfo

Вызовите эту функцию участника, чтобы установить идентификатор команды, стиль и номер изображения кнопки.

```cpp
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс кнопки или сепаратора, для которого должна быть установлена информация.

*nID*<br/>
Значение, на которое устанавливается идентификатор команды кнопки.

*nStyle*<br/>
Новый стиль кнопки. Поддерживаются следующие стили кнопок:

- TBBS_BUTTON кнопка "Стандартная" (по умолчанию)

- TBBS_SEPARATOR сепаратор

- TBBS_CHECKBOX кнопка автоматического флажка

- TBBS_GROUP отмечает начало группы кнопок

- TBBS_CHECKGROUP отмечает начало группы кнопок флажков

- TBBS_DROPDOWN создает кнопку выпадающего списка.

- TBBS_AUTOSIZE Ширина кнопки будет рассчитываться на основе текста кнопки, а не на размере изображения.

- TBBS_NOPREFIX Текст кнопки не будет иметь акселератор префикс, связанный с ним.

*iImage*<br/>
Новый индекс для изображения кнопки в биткарте.

### <a name="remarks"></a>Примечания

Для сепараторов, которые имеют стиль TBBS_SEPARATOR, эта функция устанавливает ширину сепаратора в пикселях к значению, хранящемуся в *iImage.*

> [!NOTE]
> Вы также можете установить состояния кнопки с помощью параметра *nStyle;* однако, поскольку состояния кнопок управляются `SetButtonInfo` обработчиком [ON_UPDATE_COMMAND_UI,](message-map-macros-mfc.md#on_update_command_ui) любое состояние, установленное с помощью, будет потеряно во время следующей обработки простоя. [Узнайте, как обновить объекты пользователь-интерфейс](../../mfc/how-to-update-user-interface-objects.md) и [TN031: Панели управления](../../mfc/tn031-control-bars.md) для получения дополнительной информации.

Для получения информации о изображениях и кнопках bitmap смотрите обзор [CToolBar](../../mfc/reference/ctoolbar-class.md) и [CToolBar::LoadBitmap](#loadbitmap).

## <a name="ctoolbarsetbuttons"></a><a name="setbuttons"></a>CToolBar::SetButtons

Эта функция члена устанавливает идентификатор команды каждой кнопки панели инструментов на значение, указанное соответствующим элементом *массива lpIDArray.*

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

*lpIDArray*<br/>
Указатель на массив идентификаторов команд. Это может быть NULL для выделения пустых кнопок.

*nIDCount*<br/>
Количество элементов в массиве, на которые указывает *lpIDArray*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если элемент массива имеет значение ID_SEPARATOR, в соответствующем положении панели инструментов создается сепаратор. Эта функция также устанавливает стиль каждой кнопки, чтобы TBBS_BUTTON и стиль каждого сепаратора, чтобы TBBS_SEPARATOR, и назначает индекс изображения каждой кнопке. Индекс изображения определяет положение изображения кнопки в биткарте.

Вам не нужно учитывать сепараторы в битной карте, потому что эта функция не присваивывает индексы изображений для сепараторов. Если панель инструментов имеет кнопки на позициях 0, 1 и 3 и сепаратор в положении 2, изображения на позициях 0, 1 и 2 в вашей бит-карте назначаются кнопкам на позициях 0, 1 и 3 соответственно.

Если *lpIDArray* является NULL, эта функция выделяет место для количества элементов, указанных *nIDCount.* Используйте [SetButtonInfo](#setbuttoninfo) для установки атрибутов каждого элемента.

## <a name="ctoolbarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CToolBar::SetButtonStyle

Вызовите эту функцию участника, чтобы установить стиль кнопки или сепаратора, или к кнопкам группы.

```cpp
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс кнопки или сепаратора, информация которого должна быть установлена.

*nStyle*<br/>
Стиль пуговица. Поддерживаются следующие стили кнопок:

- TBBS_BUTTON кнопка "Стандартная" (по умолчанию)

- TBBS_SEPARATOR сепаратор

- TBBS_CHECKBOX кнопка автоматического флажка

- TBBS_GROUP отмечает начало группы кнопок

- TBBS_CHECKGROUP отмечает начало группы кнопок флажков

- TBBS_DROPDOWN создает кнопку выпадающего списка

- TBBS_AUTOSIZE Ширина кнопки будет рассчитываться на основе текста кнопки, а не на размере изображения

- TBBS_NOPREFIX Текст кнопки не будет иметь акселератор префикс, связанный с ним

### <a name="remarks"></a>Примечания

Стиль кнопки определяет, как отображается кнопка и как она реагирует на ввод пользователя.

Перед `SetButtonStyle`вызовом позвоните в функцию участника [GetButtonStyle,](#getbuttonstyle) чтобы получить кнопку или стиль сепаратора.

> [!NOTE]
> Вы также можете установить состояния кнопки с помощью параметра *nStyle;* однако, поскольку состояния кнопок управляются `SetButtonStyle` обработчиком [ON_UPDATE_COMMAND_UI,](message-map-macros-mfc.md#on_update_command_ui) любое состояние, установленное с помощью, будет потеряно во время следующей обработки простоя. [Узнайте, как обновить объекты пользователь-интерфейс](../../mfc/how-to-update-user-interface-objects.md) и [TN031: Панели управления](../../mfc/tn031-control-bars.md) для получения дополнительной информации.

## <a name="ctoolbarsetbuttontext"></a><a name="setbuttontext"></a>CToolBar::SetButtonText

Вызовите эту функцию, чтобы установить текст на кнопку.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс кнопки, текст которой должен быть установлен.

*lpszText*<br/>
Указывает на текст, который будет установлен на кнопке.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [для CToolBar::GetToolBarCtrl](#gettoolbarctrl).

## <a name="ctoolbarsetheight"></a><a name="setheight"></a>CToolBar::SetHeight

Эта функция члена устанавливает высоту панели инструментов к значению, в пикселях, указанных в *cyHeight.*

```cpp
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Параметры

*cyHeight*<br/>
Высота в пикселях панели инструментов.

### <a name="remarks"></a>Примечания

После вызова [SetSizes](#setsizes)используйте эту функцию члена, чтобы переопределить стандартную высоту панели инструментов. Если высота слишком мала, кнопки будут обрезаны внизу.

Если эта функция не называется, фреймворк использует размер кнопки для определения высоты панели инструментов.

## <a name="ctoolbarsetsizes"></a><a name="setsizes"></a>CToolBar::SetSizes

Вызов ифункции этого члена, чтобы установить кнопки панели инструментов в размере, в пикселях, указанных в *размереButton*.

```cpp
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Параметры

*размерКнопка*<br/>
Размер пикселей каждой кнопки.

*размерИзображение*<br/>
Размер пикселей каждого изображения.

### <a name="remarks"></a>Примечания

Параметр *sizeImage* должен содержать размер в пикселях изображений в битной карте панели инструментов. Размеры в *размерахButton* должны быть достаточными для удержания изображения плюс 7 пикселей дополнительно в ширину и 6 пикселей дополнительно в высоту. Эта функция также устанавливает высоту панели инструментов, чтобы соответствовать кнопкам.

Назовите эту функцию участника только для панели инструментов, которые не следуют рекомендациям Windows Interface для рекомендаций по *разработке программного обеспечения* для размеров кнопок и изображений.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)
