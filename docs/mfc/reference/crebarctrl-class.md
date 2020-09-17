---
title: Класс CReBarCtrl
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: 872d577c2272939a6bf7ed1e3069cda426083e3f
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561899"
---
# <a name="crebarctrl-class"></a>Класс CReBarCtrl

Инкапсулирует функциональность элемента управления "главная панель ", который представляет собой контейнер для дочернего окна.

## <a name="syntax"></a>Синтаксис

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CReBarCtrl:: CReBarCtrl](#crebarctrl)|Формирует объект `CReBarCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CReBarCtrl:: Бегиндраг](#begindrag)|Помещает элемент управления главной панели в режим перетаскивания.|
|[CReBarCtrl:: Create](#create)|Создает элемент управления "Главная панель" и прикрепляет его к `CReBarCtrl` объекту.|
|[CReBarCtrl:: Креатикс](#createex)|Создает элемент управления "Главная панель" с указанными расширенными стилями Windows и прикрепляет его к `CReBarCtrl` объекту.|
|[CReBarCtrl::D Елетебанд](#deleteband)|Удаляет полосу из элемента управления главной панели.|
|[CReBarCtrl::D Рагмове](#dragmove)|Обновляет точку перетаскивания в элементе управления "Главная панель" после вызова `BeginDrag` .|
|[CReBarCtrl:: Енддраг](#enddrag)|Прерывает операцию перетаскивания элемента управления главной панели.|
|[CReBarCtrl:: Жетбандбордерс](#getbandborders)|Извлекает границы полосы.|
|[CReBarCtrl:: Жетбандкаунт](#getbandcount)|Возвращает число диапазонов, находящихся в данный момент в элементе управления "Главная панель".|
|[CReBarCtrl:: Жетбандинфо](#getbandinfo)|Извлекает сведения о заданной полосе в элементе управления "Главная панель".|
|[CReBarCtrl:: Жетбандмаргинс](#getbandmargins)|Извлекает поля полосы.|
|[CReBarCtrl:: Жетбархеигхт](#getbarheight)|Извлекает высоту элемента управления главной панели.|
|[CReBarCtrl:: Жетбаринфо](#getbarinfo)|Извлекает сведения об элементе управления "Главная панель" и используемом в нем списке изображений.|
|[CReBarCtrl:: Жетбкколор](#getbkcolor)|Возвращает цвет фона элемента управления главной панели по умолчанию.|
|[CReBarCtrl:: Жетколорсчеме](#getcolorscheme)|Извлекает структуру [колорсчеме](/windows/win32/api/commctrl/ns-commctrl-colorscheme) , связанную с элементом управления главной панели.|
|[CReBarCtrl:: Жетдроптаржет](#getdroptarget)|Извлекает указатель интерфейса элемента управления главной панели `IDropTarget` .|
|[CReBarCtrl:: Жетекстендедстиле](#getextendedstyle)|Возвращает расширенный стиль текущего элемента управления главной панели.|
|[CReBarCtrl::/ImageList](#getimagelist)|Извлекает список изображений, связанных с элементом управления главной панели.|
|[CReBarCtrl:: "Palette"](#getpalette)|Извлекает текущую палитру элемента управления "Главная панель".|
|[CReBarCtrl:: коrect](#getrect)|Извлекает ограничивающий прямоугольник для заданной полосы в элементе управления "Главная панель".|
|[CReBarCtrl:: RowCount](#getrowcount)|Возвращает количество строк полос в элементе управления "Главная панель".|
|[CReBarCtrl:: Жетровхеигхт](#getrowheight)|Получает высоту указанной строки в элементе управления "Главная панель".|
|[CReBarCtrl:: Жеттекстколор](#gettextcolor)|Извлекает цвет текста по умолчанию элемента управления главной панели.|
|[CReBarCtrl:: подсказки](#gettooltips)|Извлекает маркер любого элемента управления "Подсказка", связанного с элементом управления "Главная панель".|
|[CReBarCtrl:: HitTest](#hittest)|Определяет, какая часть полосы элементов управления находится в заданной точке экрана, если в этой точке существует полоса главной панели.|
|[CReBarCtrl:: Идтоиндекс](#idtoindex)|Преобразует идентификатор диапазона (ID) в индекс диапазона в элементе управления главной панели.|
|[CReBarCtrl:: Инсертбанд](#insertband)|Вставляет новый полосу в элемент управления главной панели.|
|[CReBarCtrl:: Максимизебанд](#maximizeband)|Изменяет размер полосы в элементе управления "Главная панель" до его самого крупного размера.|
|[CReBarCtrl:: Минимизебанд](#minimizeband)|Изменяет размер полосы в элементе управления "Главная панель" до наименьшего размера.|
|[CReBarCtrl:: Мовебанд](#moveband)|Перемещает диапазон из одного индекса в другой.|
|[CReBarCtrl::P Ушчеврон](#pushchevron)|Программно отправляет Шеврон.|
|[CReBarCtrl:: Ресторебанд](#restoreband)|Изменяет размер полосы в элементе управления "Главная панель" до его идеального размера.|
|[CReBarCtrl:: Сетбандинфо](#setbandinfo)|Задает характеристики существующей полосы в элементе управления "Главная панель".|
|[CReBarCtrl:: Сетбандвидс](#setbandwidth)|Задает ширину указанной закрепленной полосы в текущем элементе управления главной панели.|
|[CReBarCtrl:: Сетбаринфо](#setbarinfo)|Задает характеристики элемента управления главной панели.|
|[CReBarCtrl:: Сетбкколор](#setbkcolor)|Задает цвет фона элемента управления главной панели по умолчанию.|
|[CReBarCtrl:: Сетколорсчеме](#setcolorscheme)|Задает цветовую схему для кнопок в элементе управления "Главная панель".|
|[CReBarCtrl:: Сетекстендедстиле](#setextendedstyle)|Задает расширенные стили для текущего элемента управления главной панели.|
|[CReBarCtrl:: Сетимажелист](#setimagelist)|Задает список изображений элемента управления "Главная панель".|
|[CReBarCtrl:: Сетовнер](#setowner)|Задает окно владельца элемента управления главной панели.|
|[CReBarCtrl:: Сетпалетте](#setpalette)|Задает текущую палитру элемента управления главной панели.|
|[CReBarCtrl:: Сеттекстколор](#settextcolor)|Задает цвет текста по умолчанию для элемента управления главной панели.|
|[CReBarCtrl:: Сеттултипс](#settooltips)|Связывает элемент управления «подсказка» с элементом управления главной панели.|
|[CReBarCtrl:: SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления главной панели.|
|[CReBarCtrl:: Шовбанд](#showband)|Показывает или скрывает заданную полосу в элементе управления "Главная панель".|
|[CReBarCtrl:: Сизеторект](#sizetorect)|Подмещает элемент управления "Главная панель" к указанному прямоугольнику.|

## <a name="remarks"></a>Примечания

Приложение, в котором находится элемент управления "Главная панель", назначает дочернее окно, содержащееся в элементе управления "Главная панель", в полосу главной панели. Дочернее окно обычно является еще одним распространенным элементом управления.

Элементы управления "Главная панель" содержат одну или несколько полос. Каждая полоса может содержать сочетание полосы захвата, точечного рисунка, метки текста и дочернего окна. Полоса может содержать только один из этих элементов.

Элемент управления "Главная панель" может отображать дочернее окно над заданным фоновым рисунком. Размер всех панелей управления главной панели можно изменять, за исключением тех, которые используют стиль RBBS_FIXEDSIZE. При перемещении или изменении размера полосы управления главной панелью элемент управления главной панели управляет размером и положением дочернего окна, назначенного этому диапазону. Чтобы изменить порядок полос в элементе управления, щелкните и перетащите полосу захвата диапазона.

На следующем рисунке показан элемент управления "Главная панель" с тремя полосами:

- Полоса 0 содержит плоский, прозрачный элемент управления ToolBar.

- Панель 1 содержит как прозрачные стандартные, так и прозрачные кнопки раскрывающегося списка.

- Полоса 2 содержит поле со списком и четыре стандартные кнопки.

   ![Пример меню "Главная панель"](../../mfc/reference/media/vc4scc1.gif "Пример меню "Главная панель"")

## <a name="rebar-control"></a>Элемент управления главной панели

Поддержка элементов управления главной панели:

- Списки изображений.

- Обработка сообщений.

- Пользовательские функции рисования.

- Разнообразные стили элементов управления в дополнение к стандартным стилям окна. Список этих стилей см. в разделе [стили элементов управления главной панели](/windows/win32/Controls/rebar-control-styles) в Windows SDK.

Дополнительные сведения см. [в разделе Использование CReBarCtrl](../../mfc/using-crebarctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a> CReBarCtrl:: Бегиндраг

Реализует поведение [RB_BEGINDRAG](/windows/win32/Controls/rb-begindrag)сообщения Win32, как описано в Windows SDK.

```cpp
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона, на который будет влиять операция перетаскивания.

*двпос*<br/>
Значение типа DWORD, содержащее начальные координаты мыши. Горизонтальная координата содержится в ЛОВОРД, а вертикальная координата содержится в HIWORD. Если передать (DWORD) значение 1, элемент управления "Главная панель" будет использовать расположение мыши во время последнего вызова потока элемента управления `GetMessage` или `PeekMessage` .

## <a name="crebarctrlcreate"></a><a name="create"></a> CReBarCtrl:: Create

Создает элемент управления "Главная панель" и прикрепляет его к `CReBarCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает сочетание стилей элементов управления главной панели, применяемых к элементу управления. Список поддерживаемых стилей см. в разделе [стили элементов управления главной панели](/windows/win32/Controls/rebar-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на объект [крект](../../atl-mfc-shared/reference/crect-class.md) или структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая является положением и размером элемента управления главной панели.

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления главной панели. Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления главной панели.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае — 0.

### <a name="remarks"></a>Примечания

Создайте элемент управления "Главная панель" в два этапа:

1. Вызовите [CReBarCtrl](#crebarctrl) для создания `CReBarCtrl` объекта.

1. Вызовите эту функцию члена, которая создает элемент управления "Главная панель Windows" и присоединяет ее к `CReBarCtrl` объекту.

При вызове метода `Create` инициализируются стандартные элементы управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a> CReBarCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CReBarCtrl` объектом.

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
Задает сочетание стилей элементов управления главной панели, применяемых к элементу управления. Список поддерживаемых стилей см. в разделе [стили элементов управления главной панели](/windows/win32/Controls/rebar-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные стили Windows, заданные **WS_EX_** в расширенном стиле Windows.

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a> CReBarCtrl:: CReBarCtrl

Создает объект `CReBarCtrl`.

```
CReBarCtrl();
```

### <a name="example"></a>Пример

  См. пример для [CReBarCtrl:: Create](#create).

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a> CReBarCtrl::D Елетебанд

Реализует поведение [RB_DELETEBAND](/windows/win32/Controls/rb-deleteband)сообщения Win32, как описано в Windows SDK.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс удаляемого диапазона.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если полоса успешно удалена; в противном случае — ноль.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a> CReBarCtrl::D Рагмове

Реализует поведение [RB_DRAGMOVE](/windows/win32/Controls/rb-dragmove)сообщения Win32, как описано в Windows SDK.

```cpp
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Параметры

*двпос*<br/>
Значение типа DWORD, содержащее новые координаты мыши. Горизонтальная координата содержится в ЛОВОРД, а вертикальная координата содержится в HIWORD. Если передать (DWORD) значение 1, элемент управления "Главная панель" будет использовать расположение мыши во время последнего вызова потока элемента управления `GetMessage` или `PeekMessage` .

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a> CReBarCtrl:: Енддраг

Реализует поведение [RB_ENDDRAG](/windows/win32/Controls/rb-enddrag)сообщения Win32, как описано в Windows SDK.

```cpp
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a> CReBarCtrl:: Жетбандбордерс

Реализует поведение [RB_GETBANDBORDERS](/windows/win32/Controls/rb-getbandborders)сообщения Win32, как описано в Windows SDK.

```cpp
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона, для которого будут извлечены границы.

*PRC*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая будет принимать границы полосы. Если элемент управления "Главная панель" имеет стиль RBS_BANDBORDERS, каждый элемент этой структуры получит количество пикселей на соответствующей стороне полосы, составляющее границу. Если элемент управления "Главная панель" не имеет стиля RBS_BANDBORDERS, только левый член этой структуры получает действительную информацию. Описание стилей элементов управления главной панели см. в разделе [стили элементов управления главной](/windows/win32/Controls/rebar-control-styles) панели в Windows SDK.

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a> CReBarCtrl:: Жетбандкаунт

Реализует поведение [RB_GETBANDCOUNT](/windows/win32/Controls/rb-getbandcount)сообщения Win32, как описано в Windows SDK.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число диапазонов, назначенных элементу управления.

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a> CReBarCtrl:: Жетбандинфо

Реализует поведение сообщения Win32 [RB_GETBANDINFO](/windows/win32/Controls/rb-getbandinfo) , как описано в Windows SDK.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона, для которого будут извлечены сведения.

*прбби*<br/>
Указатель на структуру [ребарбандинфо](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) для получения сведений о диапазоне. Необходимо установить `cbSize` член этой структуры в значение `sizeof(REBARBANDINFO)` и задать `fMask` элементы, которые необходимо получить, перед отправкой этого сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a> CReBarCtrl:: Жетбандмаргинс

Извлекает поля полосы.

```cpp
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Параметры

*пмаргинс*<br/>
Указатель на структуру [полей](/windows/win32/api/uxtheme/ns-uxtheme-margins), которая будет принимать информацию.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) сообщения, как описано в Windows SDK.

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a> CReBarCtrl:: Жетбархеигхт

Извлекает высоту строки главной панели.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее высоту элемента управления в пикселях.

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a> CReBarCtrl:: Жетбаринфо

Реализует поведение [RB_GETBARINFO](/windows/win32/Controls/rb-getbarinfo)сообщения Win32, как описано в Windows SDK.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Параметры

*прби*<br/>
Указатель на структуру [ребаринфо](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , которая будет принимать сведения об элементе управления главной панели. *cbSize* `sizeof(REBARINFO)` Перед отправкой этого сообщения необходимо задать для элемента кбсизе этой структуры значение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a> CReBarCtrl:: Жетбкколор

Реализует поведение [RB_GETBKCOLOR](/windows/win32/Controls/rb-getbkcolor)сообщения Win32, как описано в Windows SDK.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее текущий цвет фона по умолчанию.

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a> CReBarCtrl:: Жетколорсчеме

Извлекает структуру [колорсчеме](/windows/win32/api/commctrl/ns-commctrl-colorscheme) для элемента управления главной панели.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Параметры

*LPC*<br/>
Указатель на структуру [колорсчеме](/windows/win32/api/commctrl/ns-commctrl-colorscheme) , как описано в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

`COLORSCHEME`Структура включает цвет выделения кнопки и цвет тени для кнопки.

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a> CReBarCtrl:: Жетдроптаржет

Реализует поведение [RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget)сообщения Win32, как описано в Windows SDK.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) .

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a> CReBarCtrl:: Жетекстендедстиле

Возвращает расширенные стили текущего элемента управления главной панели.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Побитовое сочетание (или) флагов, указывающих на расширенные стили. Возможные флаги: RBS_EX_SPLITTER и RBS_EX_TRANSPARENT. Дополнительные сведения см. в описании параметра *двмаск* метода [CReBarCtrl:: сетекстендедстиле](#setextendedstyle) .

### <a name="remarks"></a>Примечания

Этот метод отправляет [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) сообщение, описанное в Windows SDK.

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a> CReBarCtrl::/ImageList

Возвращает `CImageList` объект, связанный с элементом управления "Главная панель".

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) . Возвращает значение NULL, если для элемента управления не задан список изображений.

### <a name="remarks"></a>Примечания

Эта функция члена использует сведения о размере и маске, хранящиеся в структуре [ребаринфо](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , как описано в Windows SDK.

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a> CReBarCtrl:: "Palette"

Извлекает текущую палитру элемента управления "Главная панель".

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [кпалетте](../../mfc/reference/cpalette-class.md) , указывающий текущую палитру элемента управления главной панели.

### <a name="remarks"></a>Примечания

Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не хпалетте.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a> CReBarCtrl:: коrect

Реализует поведение [RB_GETRECT](/windows/win32/Controls/rb-getrect)сообщения Win32, как описано в Windows SDK.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс полосы в элементе управления главной панели.

*PRC*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая будет принимать границы полосы-панели.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a> CReBarCtrl:: RowCount

Реализует поведение [RB_GETROWCOUNT](/windows/win32/Controls/rb-getrowcount)сообщения Win32, как описано в Windows SDK.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение UINT, представляющее количество строк полос в элементе управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a> CReBarCtrl:: Жетровхеигхт

Реализует поведение [RB_GETROWHEIGHT](/windows/win32/Controls/rb-getrowheight)сообщения Win32, как описано в Windows SDK.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Параметры

*уров*<br/>
Отсчитываемый от нуля индекс диапазона, для которого будет извлечена высота.

### <a name="return-value"></a>Возвращаемое значение

Значение UINT, представляющее высоту строки в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a> CReBarCtrl:: Жеттекстколор

Реализует поведение [RB_GETTEXTCOLOR](/windows/win32/Controls/rb-gettextcolor)сообщения Win32, как описано в Windows SDK.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее текущий цвет текста по умолчанию.

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a> CReBarCtrl:: подсказки

Реализует поведение [RB_GETTOOLTIPS](/windows/win32/Controls/rb-gettooltips)сообщения Win32, как описано в Windows SDK.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) .

### <a name="remarks"></a>Примечания

Обратите внимание, что реализация MFC `GetToolTips` возвращает указатель на `CToolTipCtrl` , а не на HWND.

## <a name="crebarctrlhittest"></a><a name="hittest"></a> CReBarCtrl:: HitTest

Реализует поведение [RB_HITTEST](/windows/win32/Controls/rb-hittest)сообщения Win32, как описано в Windows SDK.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Параметры

*прбхт*<br/>
Указатель на структуру [рбхиттестинфо](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo) . Перед отправкой сообщения `pt` член этой структуры должен быть инициализирован в точке, которая будет протестирована в клиентских координатах.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс полосы в заданной точке или-1, если полоса элементов не была в точке.

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a> CReBarCtrl:: Идтоиндекс

Реализует поведение [RB_IDTOINDEX](/windows/win32/controls/rb-idtoindex)сообщения Win32, как описано в Windows SDK.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Параметры

*убандид*<br/>
Определяемый приложением идентификатор указанной полосы, переданный в `wID` элемент структуры [ребарбандинфо](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) при вставке полосы.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс полосы, если он был успешным, или значение-1 в противном случае. Если существуют дублирующиеся индексы полосы, возвращается первый из них.

## <a name="crebarctrlinsertband"></a><a name="insertband"></a> CReBarCtrl:: Инсертбанд

Реализует поведение [RB_INSERTBAND](/windows/win32/Controls/rb-insertband)сообщения Win32, как описано в Windows SDK.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Параметры

*уиндекс*<br/>
Отсчитываемый от нуля индекс расположения, в которое будет вставлен полоса. Если задать для этого параметра значение-1, элемент управления добавит новую полосу в последнее расположение.

*прбби*<br/>
Указатель на структуру [ребарбандинфо](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , определяющую полосу для вставки. *cbSize* `sizeof(REBARBANDINFO)` Перед вызовом этой функции необходимо задать для элемента кбсизе этой структуры значение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a> CReBarCtrl:: Максимизебанд

Изменяет размер полосы в элементе управления "Главная панель" до его самого крупного размера.

```cpp
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона, который необходимо развернуть.

### <a name="remarks"></a>Примечания

Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) с параметром, равным `fIdeal` 0, как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a> CReBarCtrl:: Минимизебанд

Изменяет размер полосы в элементе управления "Главная панель" до наименьшего размера.

```cpp
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс полосы, которая должна быть уменьшена.

### <a name="remarks"></a>Примечания

Реализует поведение [RB_MINIMIZEBAND](/windows/win32/Controls/rb-minimizeband)сообщения Win32, как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a> CReBarCtrl:: Мовебанд

Реализует поведение [RB_MOVEBAND](/windows/win32/Controls/rb-moveband)сообщения Win32, как описано в Windows SDK.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Параметры

*уфром*<br/>
Отсчитываемый от нуля индекс перемещаемого диапазона.

*втоматическое*<br/>
Отсчитываемый от нуля индекс новой позиции полосы. Значение этого параметра не должно превышать число полос минус единица. Чтобы получить количество полос, вызовите [жетбандкаунт](#getbandcount).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a> CReBarCtrl::P Ушчеврон

Реализует поведение [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron)сообщения Win32, как описано в Windows SDK.

```cpp
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс полосы, Шеврон которого должен быть отправлен.

*лаппвалуе*<br/>
Определенное приложением 32-разрядное значение. См. раздел *лаппвалуе* в [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) в Windows SDK.

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a> CReBarCtrl:: Ресторебанд

Изменяет размер полосы в элементе управления "Главная панель" до его идеального размера.

```cpp
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона, который необходимо развернуть.

### <a name="remarks"></a>Примечания

Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) с параметром, равным `fIdeal` 1, как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a> CReBarCtrl:: Сетбандинфо

Реализует поведение [RB_SETBANDINFO](/windows/win32/Controls/rb-setbandinfo)сообщения Win32, как описано в Windows SDK.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс диапазона для получения новых параметров.

*прбби*<br/>
Указатель на структуру [ребарбандинфо](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , определяющую полосу для вставки. `cbSize` `sizeof(REBARBANDINFO)` Перед отправкой этого сообщения необходимо задать член этой структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a> CReBarCtrl:: Сетбандвидс

Задает ширину указанной закрепленной полосы в текущем элементе управления главной панели.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

*убанд*\
окне Отсчитываемый от нуля индекс полосы главной панели.

*кксвидс*\
окне Новая ширина панели элементов управления (в пикселях).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_rebar` которая используется для доступа к текущему элементу управления главной панели. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Пример

В следующем примере кода каждая панель главной панели задается одинаковой ширины.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a> CReBarCtrl:: Сетбаринфо

Реализует поведение [RB_SETBARINFO](/windows/win32/Controls/rb-setbarinfo)сообщения Win32, как описано в Windows SDK.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Параметры

*прби*<br/>
Указатель на структуру [ребаринфо](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , содержащую данные, которые необходимо задать. `cbSize` `sizeof(REBARINFO)` Перед отправкой этого сообщения необходимо задать член этой структуры

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a> CReBarCtrl:: Сетбкколор

Реализует поведение [RB_SETBKCOLOR](/windows/win32/Controls/rb-setbkcolor)сообщения Win32, как описано в Windows SDK.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*среду*<br/>
Значение COLORREF, представляющее новый цвет фона по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , представляющее предыдущий цвет фона по умолчанию.

### <a name="remarks"></a>Примечания

Дополнительные сведения о том, когда следует задавать цвет фона, и о том, как задать значение по умолчанию, см. в этом разделе.

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a> CReBarCtrl:: Сетколорсчеме

Задает цветовую схему для кнопок в элементе управления "Главная панель".

```cpp
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Параметры

*LPC*<br/>
Указатель на структуру [колорсчеме](/windows/win32/api/commctrl/ns-commctrl-colorscheme) , как описано в Windows SDK.

### <a name="remarks"></a>Примечания

`COLORSCHEME`Структура включает как цвет выделения кнопки, так и цвет тени кнопки.

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a> CReBarCtrl:: Сетекстендедстиле

Задает расширенные стили для текущего элемента управления главной панели.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Параметры

*двмаск*\
окне Побитовое сочетание (или) флагов, указывающих, какие флаги в параметре *двстиликс* применяются. Используйте одно или несколько из следующих значений:

- `RBS_EX_SPLITTER`: По умолчанию отображение разделителя в нижней части в горизонтальном режиме и справа в вертикальном режиме.
- `RBS_EX_TRANSPARENT`: Пересылка [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) сообщения родительскому окну.

*двстиликс*\
окне Побитовое сочетание (или) флагов, определяющих применяемые стили. Чтобы задать стиль, укажите тот же флаг, который используется в параметре *двмаск* . Чтобы сбросить стиль, укажите двоичный нуль.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий расширенный стиль.

### <a name="remarks"></a>Примечания

Этот метод отправляет [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) сообщение, описанное в Windows SDK.

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a> CReBarCtrl:: Сетимажелист

Назначает список изображений элементу управления главной панели.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*пимажелист*<br/>
Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий список изображений, назначаемый элементу управления главной панели.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlsetowner"></a><a name="setowner"></a> CReBarCtrl:: Сетовнер

Реализует поведение [RB_SETPARENT](/windows/win32/Controls/rb-setparent)сообщения Win32, как описано в Windows SDK.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на объект, `CWnd` заданный в качестве владельца элемента управления главной панели.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является текущим владельцем элемента управления "Главная панель".

### <a name="remarks"></a>Примечания

Обратите внимание, что эта функция члена использует указатели на `CWnd` объекты как для текущего, так и для выбранного владельца элемента управления главной панели, а не для обработки в Windows.

> [!NOTE]
> Эта функция члена не изменяет фактический родительский элемент, заданный при создании элемента управления; Вместо этого он отправляет сообщения уведомления в указанное вами окно.

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a> CReBarCtrl:: Сетпалетте

Реализует поведение [RB_SETPALETTE](/windows/win32/Controls/rb-setpalette)сообщения Win32, как описано в Windows SDK.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Параметры

*хпал*<br/>
Объект ХПАЛЕТТЕ, указывающий новую палитру, которую будет использовать элемент управления "Главная панель".

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [кпалетте](../../mfc/reference/cpalette-class.md) , указывающий предыдущую палитру элемента управления главной панели.

### <a name="remarks"></a>Примечания

Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не хпалетте.

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a> CReBarCtrl:: Сеттекстколор

Реализует поведение [RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor)сообщения Win32, как описано в Windows SDK.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*среду*<br/>
Значение COLORREF, представляющее новый цвет текста в `CReBarCtrl` объекте.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , представляющее предыдущий цвет текста, связанный с `CReBarCtrl` объектом.

### <a name="remarks"></a>Примечания

Он предоставляется для поддержки гибкости цвета текста в элементе управления "Главная панель".

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a> CReBarCtrl:: Сеттултипс

Связывает элемент управления «подсказка» с элементом управления главной панели.

```cpp
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Параметры

*птултип*<br/>
Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

### <a name="remarks"></a>Примечания

После завершения этого действия `CToolTipCtrl` объект необходимо уничтожить.

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a> CReBarCtrl:: SetWindowTheme

Задает визуальный стиль элемента управления главной панели.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*псзсубаппнаме*<br/>
Указатель на строку в Юникоде, содержащую стиль визуального элемента главной панели, который необходимо задать.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не используется.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) сообщения, как описано в Windows SDK.

## <a name="crebarctrlshowband"></a><a name="showband"></a> CReBarCtrl:: Шовбанд

Реализует поведение [RB_SHOWBAND](/windows/win32/Controls/rb-showband)сообщения Win32, как описано в Windows SDK.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Параметры

*убанд*<br/>
Отсчитываемый от нуля индекс полосы в элементе управления главной панели.

*фшов*<br/>
Указывает, следует ли отображать или скрывать полосу. Если это значение равно TRUE, будет отображаться полоса. В противном случае полоса будет скрыта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a> CReBarCtrl:: Сизеторект

Реализует поведение [RB_SIZETORECT](/windows/win32/Controls/rb-sizetorect)сообщения Win32, как описано в Windows SDK.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылка на объект [крект](../../atl-mfc-shared/reference/crect-class.md) , указывающий прямоугольник, до которого должен быть изменен размер элемента управления "Главная панель".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Обратите внимание, что эта функция-член использует в `CRect` качестве параметра объект, а не `RECT` структуру.

## <a name="see-also"></a>См. также

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
