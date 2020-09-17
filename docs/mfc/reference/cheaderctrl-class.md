---
title: Класс CHeaderCtrl
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: f225d406ab1560b4308a468ebd71b3dfd88cfa2a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562177"
---
# <a name="cheaderctrl-class"></a>Класс CHeaderCtrl

Предоставляет функциональные возможности стандартного элемента управления "заголовок" Windows.

## <a name="syntax"></a>Синтаксис

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeaderCtrl:: CHeaderCtrl](#cheaderctrl)|Формирует объект `CHeaderCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeaderCtrl:: Клеараллфилтерс](#clearallfilters)|Удаляет все фильтры для элемента управления "заголовок".|
|[CHeaderCtrl:: Клеарфилтер](#clearfilter)|Очищает фильтр для элемента управления "заголовок".|
|[CHeaderCtrl:: Create](#create)|Создает элемент управления "заголовок" и присоединяет его к `CHeaderCtrl` объекту.|
|[CHeaderCtrl:: Креатедрагимаже](#createdragimage)|Создает прозрачную версию изображения элемента в элементе управления "заголовок".|
|[CHeaderCtrl:: Креатикс](#createex)|Создает элемент управления "заголовок" с указанными расширенными стилями Windows и прикрепляет его к `CListCtrl` объекту.|
|[CHeaderCtrl::D Елетеитем](#deleteitem)|Удаляет элемент из элемента управления "заголовок".|
|[CHeaderCtrl::D Равитем](#drawitem)|Рисует указанный элемент элемента управления "заголовок".|
|[CHeaderCtrl:: Едитфилтер](#editfilter)|Начинает изменение указанного фильтра элемента управления "заголовок".|
|[CHeaderCtrl:: Жетбитмапмаргин](#getbitmapmargin)|Получает ширину поля точечного рисунка в элементе управления "заголовок".|
|[CHeaderCtrl:: Жетфокуседитем](#getfocuseditem)|Возвращает идентификатор элемента в текущем элементе управления "заголовок", который находится в фокусе.|
|[CHeaderCtrl::/ImageList](#getimagelist)|Получает маркер списка изображений, используемый для отображения элементов заголовка в элементе управления "заголовок".|
|[CHeaderCtrl:: DataItem](#getitem)|Извлекает сведения об элементе в элементе управления "заголовок".|
|[CHeaderCtrl:: GetItemCount](#getitemcount)|Извлекает количество элементов в элементе управления "заголовок".|
|[CHeaderCtrl:: Жетитемдропдовнрект](#getitemdropdownrect)|Возвращает сведения о ограничивающем прямоугольнике для указанной кнопки раскрывающегося списка в элементе управления "заголовок".|
|[CHeaderCtrl:: Жетитемрект](#getitemrect)|Извлекает ограничивающий прямоугольник для заданного элемента в элементе управления "заголовок".|
|[CHeaderCtrl:: Жетордераррай](#getorderarray)|Возвращает порядок элементов в элементе управления "заголовок" слева направо.|
|[CHeaderCtrl:: Жетоверфловрект](#getoverflowrect)|Возвращает ограничивающий прямоугольник кнопки переполнения для текущего элемента управления "заголовок".|
|[CHeaderCtrl:: HitTest](#hittest)|Определяет, какой элемент заголовка (если имеется) находится в указанной точке.|
|[CHeaderCtrl:: InsertItem](#insertitem)|Вставляет новый элемент в элемент управления "заголовок".|
|[CHeaderCtrl:: Layout](#layout)|Получает размер и расположение элемента управления "заголовок" в пределах данного прямоугольника.|
|[CHeaderCtrl:: Ордертоиндекс](#ordertoindex)|Извлекает значение индекса для элемента в зависимости от его порядка в элементе управления "заголовок".|
|[CHeaderCtrl:: Сетбитмапмаргин](#setbitmapmargin)|Задает ширину поля точечного рисунка в элементе управления "заголовок".|
|[CHeaderCtrl:: Сетфилтерчанжетимеаут](#setfilterchangetimeout)|Устанавливает интервал времени ожидания между временем изменения атрибутов фильтра и разноски `HDN_FILTERCHANGE` уведомления.|
|[CHeaderCtrl:: Сетфокуседитем](#setfocuseditem)|Устанавливает фокус на указанный элемент заголовка в элементе управления "текущий заголовок".|
|[CHeaderCtrl:: Сесотдивидер](#sethotdivider)|Изменяет разделитель между элементами заголовка, чтобы указать ручное перетаскивание элемента заголовка.|
|[CHeaderCtrl:: Сетимажелист](#setimagelist)|Назначает список изображений элементу управления заголовка.|
|[CHeaderCtrl:: Сетитем](#setitem)|Задает атрибуты указанного элемента в элементе управления "заголовок".|
|[CHeaderCtrl:: Сетордераррай](#setorderarray)|Задает порядок элементов в элементе управления "заголовок" слева направо.|

## <a name="remarks"></a>Примечания

Элемент управления "заголовок" — это окно, которое обычно располагается над набором столбцов текста или чисел. Он содержит заголовок для каждого столбца, который можно разделить на части. Пользователь может перетаскивать разделители, разделяющие части, для установки ширины каждого столбца. Рисунок элемента управления "заголовок" см. в разделе [элементы управления "заголовок](/windows/win32/Controls/header-controls)".

Этот элемент управления (и, следовательно, `CHeaderCtrl` класс) доступен только для программ, работающих под управлением windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Функции, добавленные для стандартных элементов управления Windows 95/Internet Explorer 4,0, включают следующие:

- Настраиваемое упорядочивание элемента заголовка.

- Перетаскивание элемента заголовка для изменения порядка элементов заголовка. При создании объекта используйте стиль HDS_DRAGDROP `CHeaderCtrl` .

- Текст столбца заголовков постоянно отображается во время изменения размера столбца. При создании объекта используйте стиль HDS_FULLDRAG `CHeaderCtrl` .

- Горячая трассировка заголовка, которая выделяет элемент заголовка при наведении указателя мыши на него. При создании объекта используйте стиль HDS_HOTTRACK `CHeaderCtrl` .

- Поддержка списка изображений. Элементы заголовка могут содержать изображения, хранящиеся в `CImageList` объекте или тексте.

Дополнительные сведения об использовании см `CHeaderCtrl` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a> CHeaderCtrl:: CHeaderCtrl

Формирует объект `CHeaderCtrl`.

```
CHeaderCtrl();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a> CHeaderCtrl:: Клеараллфилтерс

Удаляет все фильтры для элемента управления "заголовок".

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) со значением столбца-1, как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a> CHeaderCtrl:: Клеарфилтер

Очищает фильтр для элемента управления "заголовок".

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Параметры

*нколумн*<br/>
Значение столбца, указывающее, какой фильтр следует очистить.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a> CHeaderCtrl:: Create

Создает элемент управления "заголовок" и присоединяет его к `CHeaderCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль элемента управления заголовка. Описание стилей элементов управления заголовков см. в разделе [стили элементов управления "заголовок](/windows/win32/Controls/header-control-styles) " в Windows SDK.

*rect*<br/>
Задает размер и расположение элемента управления заголовка. Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Задает родительское окно элемента управления заголовка, обычно `CDialog` . Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления заголовка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — ноль.

### <a name="remarks"></a>Примечания

`CHeaderCtrl`Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который создает элемент управления "заголовок" и присоединяет его к `CHeaderCtrl` объекту.

В дополнение к стилям элемента управления "заголовок" можно использовать следующие стандартные стили элементов управления для определения положения и изменения размеров элемента управления "заголовок" (Дополнительные сведения см. в разделе [общие стили элементов управления](/windows/win32/Controls/common-control-styles) ):

- CCS_BOTTOM приводит к тому, что элемент управления позиционируется в нижней части клиентской области родительского окна и устанавливает ширину таким же образом, как и ширина родительского окна.

- CCS_NODIVIDER предотвращает прорисовку выделения с двумя пикселями в верхней части элемента управления.

- CCS_NOMOVEY заставляет элемент управления изменять размер и перемещаться по горизонтали, но не по вертикали в ответ на сообщение WM_SIZE. Если используется стиль CCS_NORESIZE, этот стиль не применяется. По умолчанию этот стиль есть у элементов управления "заголовок".

- CCS_NOPARENTALIGN не позволяет элементу управления автоматически перемещаться в верхнюю или нижнюю часть родительского окна. Вместо этого элемент управления сохраняет свое местоположение в родительском окне, несмотря на изменение размера родительского окна. Если используется также стиль CCS_TOP или CCS_BOTTOM, высота корректируется до значения по умолчанию, но ширина и толщина остаются неизменными.

- CCS_NORESIZE не дает элементу управления использовать ширину и высоту по умолчанию при задании начального размера или нового размера. Вместо этого элемент управления использует ширину и высоту, указанные в запросе на создание или изменение размера.

- CCS_TOP приводит к тому, что элемент управления позиционируется в верхней части клиентской области родительского окна и устанавливает ширину таким же образом, как и ширина родительского окна.

К элементу управления "заголовок" можно также применить следующие стили окна (Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) ):

- WS_CHILD создает дочернее окно. Не может использоваться с WS_POPUP стилем.

- WS_VISIBLE создает окно, которое изначально видимо.

- WS_DISABLED создает окно, которое изначально отключено.

- WS_GROUP указывает первый элемент управления группы элементов управления, в которой пользователь может перемещаться от одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с WS_GROUP стилем после первого элемента управления, принадлежат к одной группе. Следующий элемент управления с стилем WS_GROUP завершает группу стилей и запускает следующую группу (то есть одна группа заканчивается, где начинается следующая).

- WS_TABSTOP указывает одно из нескольких элементов управления, через которое пользователь может перемещаться с помощью клавиши TAB. Клавиша TAB перемещает пользователя к следующему элементу управления, указанному в WS_TABSTOP стиле.

Если вы хотите использовать расширенные стили Windows с элементом управления, вызовите [креатикс](#createex) вместо `Create` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a> CHeaderCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CHeaderCtrl` объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двексстиле*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Стиль элемента управления заголовка. Описание стилей элементов управления заголовков см. в разделе [стили элементов управления "заголовок](/windows/win32/Controls/header-control-styles) " в Windows SDK. Список дополнительных стилей см. в разделе [CREATE](#create) .

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо `Create` для применения расширенных стилей Windows, заданных **WS_EX_** в расширенном стиле Windows.

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a> CHeaderCtrl:: Креатедрагимаже

Создает прозрачную версию изображения элемента в элементе управления "заголовок".

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс элемента в элементе управления "заголовок". Изображение, назначенное этому элементу, является основанием для прозрачного изображения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) в случае успешного выполнения; в противном случае — NULL. Возвращаемый список содержит только одно изображение.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage), как описано в Windows SDK. Он предоставляется для поддержки перетаскивания элемента заголовка.

`CImageList`Объект, на который указывает возвращаемый указатель, является временным объектом и удаляется при следующей обработке времени простоя.

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a> CHeaderCtrl::D Елетеитем

Удаляет элемент из элемента управления "заголовок".

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает отсчитываемый от нуля индекс удаляемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a> CHeaderCtrl::D Равитем

Вызывается структурой при изменении визуального аспекта элемента управления "заголовок, рисуемый владельцем".

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , описывающую закрашиваемый элемент.

### <a name="remarks"></a>Примечания

`itemAction`Элемент `DRAWITEMSTRUCT` структуры определяет выполняемое действие рисования.

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта, рисуемого владельцем `CHeaderCtrl` .

Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* , перед завершением этой функции-члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a> CHeaderCtrl:: Едитфилтер

Начинает изменение указанного фильтра элемента управления "заголовок".

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Параметры

*нколумн*<br/>
Изменяемый столбец.

*бдискардчанжес*<br/>
Значение, указывающее, как обрабатывать изменения, внесенные пользователем, если пользователь находится в процессе изменения фильтра при отправке сообщения [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) .

Укажите значение TRUE, чтобы отменить изменения, внесенные пользователем, или FALSE, чтобы принять изменения, внесенные пользователем.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщения Win32 [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a> CHeaderCtrl:: Жетбитмапмаргин

Получает ширину поля точечного рисунка в элементе управления "заголовок".

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина поля точечного рисунка в пикселях.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a> CHeaderCtrl:: Жетфокуседитем

Возвращает индекс элемента, имеющего фокус в текущем заголовке элемента управления.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента заголовка, который находится в фокусе.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_headerCtrl` которая используется для доступа к текущему элементу управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируются `SetFocusedItem` `GetFocusedItem` методы и. В предыдущем разделе кода мы создали элемент управления "заголовок" с пятью столбцами. Однако можно перетащить разделитель столбцов, чтобы столбец не отображался. В следующем примере задается и проверяется последний заголовок столбца в качестве элемента фокуса.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a> CHeaderCtrl::/ImageList

Получает маркер списка изображений, используемый для отображения элементов заголовка в элементе управления "заголовок".

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) .

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist), как описано в Windows SDK. `CImageList`Объект, на который указывает возвращаемый указатель, является временным объектом и удаляется при следующей обработке времени простоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a> CHeaderCtrl:: DataItem

Извлекает сведения об элементе элемента управления "заголовок".

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает отсчитываемый от нуля индекс извлекаемого элемента.

*феадеритем*<br/>
Указатель на структуру [хдитем](/windows/win32/api/commctrl/ns-commctrl-hditemw) , которая получает новый элемент. Эта структура используется с функциями- `InsertItem` `SetItem` членами и. Все флаги, заданные в `mask` элементе, гарантируют правильность заполнения значений в соответствующих элементах при возврате. Если `mask` элемент имеет нулевое значение, значения в других элементах структуры не имеют смысла.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a> CHeaderCtrl:: GetItemCount

Извлекает количество элементов в элементе управления "заголовок".

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов элемента управления "заголовок" в случае успеха; в противном случае — 1.

### <a name="example"></a>Пример

  См. пример для [CHeaderCtrl::D елетеитем](#deleteitem).

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a> CHeaderCtrl:: Жетитемдропдовнрект

Возвращает ограничивающий прямоугольник кнопки раскрывающегося списка для элемента заголовка в элементе управления "текущий заголовок".

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*Член iItem*\
окне Отсчитываемый от нуля индекс элемента заголовка, стиль которого HDF_SPLITBUTTON. Дополнительные сведения см. в описании `fmt` члена структуры [хдитем](/windows/win32/api/commctrl/ns-commctrl-hditemw) .

*лпрект*\
заполняет Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) для получения сведений о ограничивающем прямоугольнике.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если эта функция выполнена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_headerCtrl` которая используется для доступа к текущему элементу управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируется `GetItemDropDownRect` метод. В предыдущем разделе кода мы создали элемент управления "заголовок" с пятью столбцами. В следующем примере кода трехмерный прямоугольник рисуется вокруг положения в первом столбце, зарезервированного для кнопки раскрывающегося списка заголовок.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a> CHeaderCtrl:: Жетитемрект

Извлекает ограничивающий прямоугольник для заданного элемента в элементе управления "заголовок".

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс элемента элемента управления "заголовок".

*лпрект*<br/>
Указатель на адрес структуры [Rect](/windows/win32/api/windef/ns-windef-rect) , которая получает сведения об ограничивающем прямоугольнике.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщения Win32 [HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect), как описано в Windows SDK.

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a> CHeaderCtrl:: Жетордераррай

Возвращает порядок элементов в элементе управления "заголовок" слева направо.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Параметры

*пиаррай*<br/>
Указатель на адрес буфера, который получает значения индекса элементов в элементе управления "заголовок" в порядке, в котором они отображаются слева направо.

*икаунт*<br/>
Количество элементов управления "заголовок". Значение не должно быть отрицательным.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray), как описано в Windows SDK. Он предоставляется для поддержки упорядочения элементов заголовка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a> CHeaderCtrl:: Жетоверфловрект

Возвращает ограничивающий прямоугольник кнопки переполнения текущего элемента управления "заголовок".

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*лпрект*\
заполняет Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая получает сведения о ограничивающем прямоугольнике.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если эта функция выполнена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если элемент управления "заголовок" содержит больше элементов, чем может одновременно отображаться, элемент управления может отобразить кнопку переполнения, которая прокручивается до невидимых элементов. Элемент управления "заголовок" должен иметь стили HDS_OVERFLOW и HDF_SPLITBUTTON для вывода кнопки переполнения. Ограничивающий прямоугольник включает кнопку переполнения и существует только при отображении кнопки переполнения. Дополнительные сведения см. в разделе [стили элементов управления "заголовок](/windows/win32/Controls/header-control-styles)".

Этот метод отправляет [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_headerCtrl` которая используется для доступа к текущему элементу управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируется `GetOverflowRect` метод. В предыдущем разделе кода мы создали элемент управления "заголовок" с пятью столбцами. Однако можно перетащить разделитель столбцов, чтобы столбец не отображался. Если некоторые столбцы не видны, элемент управления "заголовок" рисует кнопку переполнения. В следующем примере кода трехмерный прямоугольник рисуется вокруг положения кнопки переполнения.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a> CHeaderCtrl:: HitTest

Определяет, какой элемент заголовка (если имеется) находится в указанной точке.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Параметры

*фдхти*\
[вход, выход] Указатель на структуру [хдхиттестинфо](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) , указывающую точку для проверки и получающую результаты теста.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента заголовка, если он имеется, в указанной позиции; в противном случае — значение-1.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_headerCtrl` которая используется для доступа к текущему элементу управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируется `HitTest` метод. В предыдущем разделе этого примера кода мы создали элемент управления "заголовок" с пятью столбцами. Однако можно перетащить разделитель столбцов, чтобы столбец не отображался. В этом примере отображается индекс столбца, если он является видимым, и значение-1, если столбец не отображается.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a> CHeaderCtrl:: InsertItem

Вставляет новый элемент в элемент управления "заголовок" по указанному индексу.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Отсчитываемый от нуля индекс вставляемого элемента. Если значение равно нулю, элемент вставляется в начало элемента управления заголовка. Если значение больше максимального значения, элемент вставляется в конец элемента управления заголовка.

*фди*<br/>
Указатель на структуру [хдитем](/windows/win32/api/commctrl/ns-commctrl-hditemw) , содержащую сведения о вставляемом элементе.

### <a name="return-value"></a>Возвращаемое значение

Индекс нового элемента в случае успеха; в противном случае — 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a> CHeaderCtrl:: Layout

Получает размер и расположение элемента управления "заголовок" в пределах данного прямоугольника.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Параметры

*феадерлайаут*<br/>
Указатель на структуру [хдлайаут](/windows/win32/api/commctrl/ns-commctrl-hdlayout) , которая содержит сведения, используемые для задания размера и позиции элемента управления "заголовок".

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция используется для определения соответствующих измерений для нового элемента управления "заголовок", который должен занимать данный прямоугольник.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a> CHeaderCtrl:: Ордертоиндекс

Извлекает значение индекса для элемента в зависимости от его порядка в элементе управления "заголовок".

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Параметры

*нордер*<br/>
Отсчитываемый от нуля порядок, в котором элемент отображается в элементе управления "заголовок" слева направо.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента в зависимости от его порядка в элементе управления "заголовок". Индекс учитывается слева направо, начиная с 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение макроса Win32 [HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex), как описано в Windows SDK. Он предоставляется для поддержки упорядочения элементов заголовка.

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a> CHeaderCtrl:: Сетбитмапмаргин

Задает ширину поля точечного рисунка в элементе управления "заголовок".

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Параметры

*нвидс*<br/>
Ширина (в пикселях) поля, которое окружает точечный рисунок в существующем элементе управления "заголовок".

### <a name="return-value"></a>Возвращаемое значение

Ширина поля точечного рисунка в пикселях.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a> CHeaderCtrl:: Сетфилтерчанжетимеаут

Устанавливает интервал времени ожидания между временем изменения атрибутов фильтра и разноски уведомления [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) .

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Параметры

*двтимеаут*<br/>
Значение времени ожидания в миллисекундах.

### <a name="return-value"></a>Возвращаемое значение

Индекс изменяемого элемента управления фильтра.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a> CHeaderCtrl:: Сетфокуседитем

Устанавливает фокус на указанный элемент заголовка в элементе управления "текущий заголовок".

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Параметры

*Член iItem*\
окне Отсчитываемый от нуля индекс элемента заголовка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_headerCtrl` которая используется для доступа к текущему элементу управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируются `SetFocusedItem` `GetFocusedItem` методы и. В предыдущем разделе кода мы создали элемент управления "заголовок" с пятью столбцами. Однако можно перетащить разделитель столбцов, чтобы столбец не отображался. В следующем примере задается и проверяется последний заголовок столбца в качестве элемента фокуса.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a> CHeaderCtrl:: Сесотдивидер

Изменяет разделитель между элементами заголовка, чтобы указать ручное перетаскивание элемента заголовка.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Расположение указателя. Элемент управления "заголовок" выделяет соответствующий разделитель на основе позиции указателя.

*ниндекс*<br/>
Индекс выделенного разделителя.

### <a name="return-value"></a>Возвращаемое значение

Индекс выделенного разделителя.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider), как описано в Windows SDK. Он предоставляется для поддержки перетаскивания элемента заголовка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a> CHeaderCtrl:: Сетимажелист

Назначает список изображений элементу управления заголовка.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*пимажелист*<br/>
Указатель на объект, `CImageList` содержащий список изображений, назначаемый элементу управления "заголовок".

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) , ранее назначенный элементу управления заголовка.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist), как описано в Windows SDK. `CImageList`Объект, на который указывает возвращаемый указатель, является временным объектом и удаляется при следующей обработке времени простоя.

### <a name="example"></a>Пример

  См. пример для [CHeaderCtrl:: коimagelist](#getimagelist).

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a> CHeaderCtrl:: Сетитем

Задает атрибуты указанного элемента в элементе управления "заголовок".

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Отсчитываемый от нуля индекс элемента, который необходимо изменить.

*феадеритем*<br/>
Указатель на структуру [хдитем](/windows/win32/api/commctrl/ns-commctrl-hditemw) , содержащую сведения о новом элементе.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [CHeaderCtrl:: DataItem](#getitem).

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a> CHeaderCtrl:: Сетордераррай

Задает порядок элементов в элементе управления "заголовок" слева направо.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Параметры

*икаунт*<br/>
Количество элементов управления "заголовок".

*пиаррай*<br/>
Указатель на адрес буфера, который получает значения индекса элементов в элементе управления "заголовок" в порядке, в котором они отображаются слева направо.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение макроса Win32 [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray), как описано в Windows SDK. Он предоставляется для поддержки упорядочения элементов заголовка.

### <a name="example"></a>Пример

  См. пример для [CHeaderCtrl:: жетордераррай](#getorderarray).

## <a name="see-also"></a>См. также

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CImageList](../../mfc/reference/cimagelist-class.md)
