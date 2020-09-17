---
title: Класс CImageList
ms.date: 11/04/2016
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
ms.openlocfilehash: 28693aaa32ab5f4baaf773a7bac64c491d55cf78
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212401"
---
# <a name="cimagelist-class"></a>Класс CImageList

Предоставляет функциональные возможности стандартного элемента управления "список изображений" Windows.

## <a name="syntax"></a>Синтаксис

```
class CImageList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CImageList:: CImageList](#cimagelist)|Формирует объект `CImageList`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CImageList:: Add](#add)|Добавляет изображение или изображения в список изображений.|
|[CImageList:: Attach](#attach)|Присоединяет список изображений к `CImageList` объекту.|
|[CImageList:: Бегиндраг](#begindrag)|Начинает перетаскивать изображение.|
|[CImageList:: Copy](#copy)|Копирует изображение в `CImageList` объект.|
|[CImageList:: Create](#create)|Инициализирует список изображений и прикрепляет его к `CImageList` объекту.|
|[CImageList::D Елетеимажелист](#deleteimagelist)|Удаляет список изображений.|
|[CImageList::D Елететемпмап](#deletetempmap)|Вызывается обработчиком времени простоя [CWinApp](../../mfc/reference/cwinapp-class.md) для удаления любого временного `CImageList` объекта, созданного `FromHandle` .|
|[CImageList::D етач](#detach)|Отсоединяет объект списка изображений от `CImageList` объекта и возвращает маркер в список изображений.|
|[CImageList::D Ражентер](#dragenter)|Блокирует обновления во время операции перетаскивания и отображает изображение перетаскивания в указанной позиции.|
|[CImageList::D Раглеаве](#dragleave)|Разблокирует окно и скрывает изображение перетаскивания, чтобы можно было обновить окно.|
|[CImageList::D Рагмове](#dragmove)|Перемещает изображение, которое перетаскивается во время операции перетаскивания.|
|[CImageList::D Рагшовнолокк](#dragshownolock)|Показывает или скрывает изображение перетаскивания во время операции перетаскивания без блокировки окна.|
|[CImageList::D RAW](#draw)|Рисует изображение, которое перетаскивается во время операции перетаскивания.|
|[CImageList::D Равекс](#drawex)|Рисует элемент списка изображений в указанном контексте устройства. Функция использует указанный стиль рисования и смешивает изображение с указанным цветом.|
|[CImageList::D Равиндирект](#drawindirect)|Рисует изображение из списка изображений.|
|[CImageList:: Енддраг](#enddrag)|Завершает операцию перетаскивания.|
|[CImageList:: Екстрактикон](#extracticon)|Создает значок на основе изображения и маски в списке изображений.|
|[CImageList:: FromHandle](#fromhandle)|Возвращает указатель на `CImageList` объект при наличии маркера для списка изображений. Если объект `CImageList` не прикреплен к дескриптору, создается и прикрепляется временный объект `CImageList`.|
|[CImageList:: Фромхандлеперманент](#fromhandlepermanent)|Возвращает указатель на `CImageList` объект при наличии маркера для списка изображений. Если `CImageList` объект не присоединен к маркеру, возвращается значение null.|
|[CImageList:: Жетбкколор](#getbkcolor)|Извлекает текущий цвет фона для списка изображений.|
|[CImageList:: Жетдрагимаже](#getdragimage)|Возвращает временный список изображений, используемый для перетаскивания.|
|[CImageList:: Жетимажекаунт](#getimagecount)|Извлекает количество образов в списке изображений.|
|[CImageList:: Жетимажеинфо](#getimageinfo)|Извлекает сведения о изображении.|
|[CImageList:: Жетсафехандле](#getsafehandle)|Извлекает `m_hImageList` .|
|[CImageList:: Read](#read)|Считывает список изображений из архива.|
|[CImageList:: Remove](#remove)|Удаляет изображение из списка изображений.|
|[CImageList:: Replace](#replace)|Заменяет изображение в списке изображений новым изображением.|
|[CImageList:: Сетбкколор](#setbkcolor)|Задает цвет фона для списка изображений.|
|[CImageList:: Сетдрагкурсоримаже](#setdragcursorimage)|Создает новое изображение перетаскивания.|
|[CImageList:: Сетимажекаунт](#setimagecount)|Сбрасывает число образов в списке изображений.|
|[CImageList:: Сетоверлайимаже](#setoverlayimage)|Добавляет Отсчитываемый от нуля индекс изображения в список изображений, которые будут использоваться в качестве масок наложения.|
|[CImageList:: Write](#write)|Записывает список образов в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CImageList::operator ХИМАЖЕЛИСТ](#operator_himagelist)|Возвращает ХИМАЖЕЛИСТ, присоединенный к `CImageList` .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CImageList:: m_hImageList](#m_himagelist)|Маркер, содержащий список изображений, прикрепленных к этому объекту.|

## <a name="remarks"></a>Примечания

"Список изображений" — это коллекция изображений одинакового размера, на каждый из которых может ссылаться индекс, начинающийся с нуля. Списки изображений используются для эффективного управления большими наборами значков или точечных рисунков. Все изображения в списке изображений содержатся в одном расширенном точечном рисунке в формате экранного устройства. Список изображений может также включать монохромное растровое изображение, которое содержит маски, используемые для прозрачного рисования изображений (стиль значка). Интерфейс прикладного программирования (API) Microsoft Win32 предоставляет функции списка изображений, позволяющие рисовать изображения, создавать и уничтожать списки изображений, добавлять и удалять изображения, заменять изображения, объединять изображения и перетаскивать изображения.

Этот элемент управления (и, следовательно, `CImageList` класс) доступен только для программ, работающих под управлением windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Дополнительные сведения об использовании см `CImageList` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CImageList](../../mfc/using-cimagelist.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cimagelistadd"></a><a name="add"></a>CImageList:: Add

Вызовите эту функцию, чтобы добавить одно или несколько изображений или значок в список изображений.

```
int Add(
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Add(
    CBitmap* pbmImage,
    COLORREF crMask);

int Add(HICON hIcon);
```

### <a name="parameters"></a>Параметры

*пбмимаже*<br/>
Указатель на точечный рисунок, содержащий изображение или изображения. Число изображений выводится из ширины точечного рисунка.

*пбммаск*<br/>
Указатель на точечный рисунок, содержащий маску. Если в списке изображений не используется маска, этот параметр игнорируется.

*крмаск*<br/>
Цвет, используемый для создания маски. Каждый пиксел этого цвета в заданном растровом изображении изменяется на черный, а соответствующий бит в маске имеет значение 1.

*hIcon*<br/>
Маркер значка, который содержит растровое изображение и маску для нового изображения.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого нового образа в случае успеха; в противном случае — 1.

### <a name="remarks"></a>Примечания

Вы несете ответственность за освобождение маркера значка по завершении работы с ним.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>CImageList:: Attach

Вызовите эту функцию, чтобы присоединить список изображений к `CImageList` объекту.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Маркер объекта списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если вложение прошло успешно; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>CImageList:: Бегиндраг

Вызовите эту функцию, чтобы начать перетягивание изображения.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения для перетаскивания.

*псотспот*<br/>
Координаты начальной позиции перетаскивания (как правило, позиции курсора). Координаты задаются относительно верхнего левого угла изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция создает временный список изображений, который используется для перетаскивания. Изображение объединяет указанное изображение и его маску с текущим курсором. В ответ на последующие WM_MOUSEMOVE сообщения можно переместить изображение перетаскивания с помощью `DragMove` функции члена. Чтобы завершить операцию перетаскивания, можно использовать `EndDrag` функцию члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>CImageList:: CImageList

Формирует объект `CImageList`.

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>CImageList:: Copy

Эта функция члена реализует поведение функции Win32 [ImageList_Copy](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy), как описано в Windows SDK.

```
BOOL Copy(
    int iDst,
    int iSrc,
    UINT uFlags = ILCF_MOVE);

BOOL Copy(
    int iDst,
    CImageList* pSrc,
    int iSrc,
    UINT uFlags = ILCF_MOVE);
```

### <a name="parameters"></a>Параметры

*идст*<br/>
Отсчитываемый от нуля индекс изображения, которое будет использоваться в качестве назначения для операции копирования.

*исрк*<br/>
Отсчитываемый от нуля индекс изображения, используемого в качестве источника операции копирования.

*уфлагс*<br/>
Значение битового флага, указывающее тип выполняемой операции копирования. Этот параметр может принимать одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|ILCF_MOVE|Исходное изображение копируется в индекс конечного образа. Эта операция приводит к получению нескольких экземпляров заданного образа. Значение по умолчанию — ILCF_MOVE.|
|ILCF_SWAP|Координаты исходного и конечного образов находятся в списке образов.|

*pSrc*<br/>
Указатель на `CImageList` объект, являющийся целевым объектом операции копирования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>CImageList:: Create

Инициализирует список изображений и прикрепляет его к объекту [CImageList](../../mfc/reference/cimagelist-class.md) .

```
BOOL Create(
    int cx,
    int cy,
    UINT nFlags,
    int nInitial,
    int nGrow);

BOOL Create(
    UINT nBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    LPCTSTR lpszBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    CImageList& imagelist1,
    int nImage1,
    CImageList& imagelist2,
    int nImage2,
    int dx,
    int dy);

BOOL Create(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*/CX*<br/>
Размеры каждого изображения (в пикселях).

*CY*<br/>
Размеры каждого изображения (в пикселях).

*нфлагс*<br/>
Указывает тип создаваемого списка изображений. Этот параметр может быть сочетанием следующих значений, но может включать только одно из `ILC_COLOR` значений.

|Значение|Значение|
|-----------|-------------|
|ILC_COLOR|Используйте поведение по умолчанию, если не указано ни одного другого флага ILC_COLOR *. Как правило, значение по умолчанию — ILC_COLOR4; но для старых драйверов экрана значение по умолчанию — ILC_COLORDDB.|
|ILC_COLOR4|Используйте 4-разрядное (16 цветовое) подразделы DIB в качестве точечного рисунка для списка изображений.|
|ILC_COLOR8|Используйте 8-разрядный раздел DIB. Цвета, используемые для таблицы цветов, имеют те же цвета, что и палитра полутонов.|
|ILC_COLOR16|Используйте 16-разрядный (32/64k цвет) раздел DIB.|
|ILC_COLOR24|Используйте 24-разрядный раздел DIB.|
|ILC_COLOR32|Используйте 32-разрядный раздел DIB.|
|ILC_COLORDDB|Используйте зависимый от устройства точечный рисунок.|
|ILC_MASK|Использует маску. Список изображений содержит два точечных рисунка, один из которых является монохромным точечным рисунком, используемым в качестве маски. Если это значение не включено, список изображений содержит только одно растровое изображение. Дополнительные сведения о маскированных изображениях см. в разделе [Рисование изображений из списка изображений](../../mfc/drawing-images-from-an-image-list.md) .|

*нинитиал*<br/>
Число образов, изначально содержащихся в списке изображений.

*нгров*<br/>
Число образов, по которым может увеличиваться список изображений, когда системе необходимо изменить размер списка, чтобы освободить место для новых изображений. Этот параметр представляет число новых изображений, которые может содержать список изображений с измененным размером.

*нбитмапид*<br/>
Идентификаторы ресурсов растрового изображения, которые должны быть связаны со списком изображений.

*крмаск*<br/>
Цвет, используемый для создания маски. Каждый пиксел этого цвета в указанном растровом изображении изменяется на черный, а соответствующий бит в маске имеет значение 1.

*лпсзбитмапид*<br/>
Строка, содержащая идентификаторы ресурсов для изображений.

*imageList1*<br/>
Ссылка на объект `CImageList`.

*nImage1*<br/>
Индекс первого существующего изображения.

*imagelist2*<br/>
Ссылка на объект `CImageList`.

*nImage2*<br/>
Индекс второго существующего изображения.

*DX*<br/>
Смещение оси x второго изображения по отношению к первому изображению в пикселях.

*DY*<br/>
Смещение оси y второго изображения по отношению к первому изображению в пикселях.

*пимажелист*<br/>
Указатель на объект `CImageList`.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Построение создается `CImageList` в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который создает список изображений и прикрепляет его к `CImageList` объекту.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>CImageList::D Елетеимажелист

Вызовите эту функцию, чтобы удалить список изображений.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>CImageList::D Елететемпмап

Автоматически вызывается `CWinApp` обработчиком времени простоя, `DeleteTempMap` удаляет все временные `CImageList` объекты, созданные [FromHandle](#fromhandle), но не уничтожает дескрипторы ( `hImageList` ), временно связанные с `ImageList` объектами.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>CImageList::D етач

Вызовите эту функцию, чтобы отсоединить объект списка изображений от `CImageList` объекта.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Маркер объекта списка изображений.

### <a name="remarks"></a>Примечания

Эта функция возвращает маркер объекта списка изображений.

### <a name="example"></a>Пример

  См. пример для [CImageList:: Attach](#attach).

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>CImageList::D Ражентер

Во время операции перетаскивания фиксирует обновления в окне, заданном параметром *пвндлокк* , и отображает изображение перетаскивания в позиции, указанной параметром *Point*.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*пвндлокк*<br/>
Указатель на окно, которому принадлежит изображение перетаскивания.

*точки*<br/>
Расположение, в котором отображается изображение перетаскивания. Координаты задаются относительно левого верхнего угла окна (а не клиентской области).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Координаты задаются относительно левого верхнего угла окна, поэтому при указании координат необходимо компенсировать ширину элементов окна, таких как границы, заголовок и строка меню.

Если *пвндлокк* имеет значение null, эта функция рисует изображение в контексте отображения, связанном с окном рабочего стола, а координаты задаются относительно левого верхнего угла экрана.

Эта функция блокирует все остальные обновления в заданном окне во время операции перетаскивания. Если во время операции перетаскивания необходимо выполнить какие-либо действия, такие как выделение целевого объекта для операции перетаскивания, можно временно скрыть Перетаскивание изображения с помощью функции [CImageList::D раглеаве](#dragleave) .

### <a name="example"></a>Пример

  См. пример для [CImageList:: бегиндраг](#begindrag).

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>CImageList::D Раглеаве

Разблокирует окно, заданное параметром *пвндлокк* , и скрывает изображение перетаскивания, позволяя обновлять окно.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Параметры

*пвндлокк*<br/>
Указатель на окно, которому принадлежит изображение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [CImageList:: енддраг](#enddrag).

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>CImageList::D Рагмове

Вызовите эту функцию, чтобы переместить изображение, которое перетаскивается во время операции перетаскивания.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Параметры

*лутор*<br/>
Новое расположение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается в ответ на WM_MOUSEMOVE сообщение. Чтобы начать операцию перетаскивания, используйте `BeginDrag` функцию-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>CImageList::D Рагшовнолокк

Показывает или скрывает изображение перетаскивания во время операции перетаскивания без блокировки окна.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, должно ли отображаться изображение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Функция [CImageList::D ражентер](#dragenter) блокирует все обновления окна во время операции перетаскивания. Однако эта функция не блокирует окно.

## <a name="cimagelistdraw"></a><a name="draw"></a>CImageList::D RAW

Вызовите эту функцию, чтобы нарисовать изображение, которое перетаскивается во время операции перетаскивания.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на контекст целевого устройства.

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения для рисования.

*лутор*<br/>
Расположение для рисования в указанном контексте устройства.

*nStyle*<br/>
Флаг, указывающий стиль отображения. Это может быть одно или несколько из следующих значений:

|Значение|Значение|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|Рисует изображение, смешивание 25% с цветом выделения системы. Это значение не действует, если список изображений не содержит маску.|
|ILD_BLEND50, ILD_SELECTED ILD_BLEND|Рисует изображение, смешивание 50 процентов с цветом выделения системы. Это значение не действует, если список изображений не содержит маску.|
|ILD_MASK|Рисует маску.|
|ILD_NORMAL|Рисует изображение, используя цвет фона для списка изображений. Если цвет фона является CLR_NONE значением, изображение прозрачно рисуется с помощью маски.|
|ILD_TRANSPARENT|Рисует изображение прозрачно с помощью маски независимо от цвета фона.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [CImageList:: сетоверлайимаже](#setoverlayimage).

## <a name="cimagelistdrawex"></a><a name="drawex"></a>CImageList::D Равекс

Рисует элемент списка изображений в указанном контексте устройства.

```
BOOL DrawEx(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    COLORREF clrBk,
    COLORREF clrFg,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на контекст целевого устройства.

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения для рисования.

*лутор*<br/>
Расположение для рисования в указанном контексте устройства.

*SZ*<br/>
Размер части изображения для рисования относительно левого верхнего угла изображения. См. раздел *DX* и *dy* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*клрбк*<br/>
Цвет фона изображения. См. раздел *ргббк* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*клрфг*<br/>
Цвет переднего плана изображения. См. раздел *ргбфг* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*nStyle*<br/>
Флаг, указывающий стиль отображения. См. раздел *фстиле* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Функция использует указанный стиль рисования и смешивает изображение с указанным цветом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>CImageList::D Равиндирект

Вызовите эту функцию члена, чтобы нарисовать изображение из списка изображений.

```
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

BOOL DrawIndirect(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    POINT ptOrigin,
    UINT fStyle = ILD_NORMAL,
    DWORD dwRop = SRCCOPY,
    COLORREF rgbBack = CLR_DEFAULT,
    COLORREF rgbFore = CLR_DEFAULT,
    DWORD fState = ILS_NORMAL,
    DWORD Frame = 0,
    COLORREF crEffect = CLR_DEFAULT);
```

### <a name="parameters"></a>Параметры

*пимлдп*<br/>
Указатель на структуру [имажелистдравпарамс](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) , содержащую сведения об операции рисования.

*Хозяин*<br/>
Указатель на контекст целевого устройства. Этот объект [CDC](../../mfc/reference/cdc-class.md) необходимо удалить по завершении с ним.

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения, которое необходимо прорисовать.

*лутор*<br/>
Структура [точек](/windows/win32/api/windef/ns-windef-point) , содержащая координаты x и y, где будет нарисован изображение.

*SZ*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) , указывающая размер изображения для рисования.

*пторигин*<br/>
Структура [точек](/windows/win32/api/windef/ns-windef-point) , содержащая координаты x и y, указывающие верхний левый угол операции рисования относительно самого изображения. Пикселы изображения, расположенные слева от координаты x и над координатой y, не рисуются.

*фстиле*<br/>
Флаг, указывающий стиль рисования и, при необходимости, изображение оверлея. Сведения о наложенном изображении см. в разделе "Примечания". Реализация MFC по умолчанию, ILD_NORMAL, рисует изображение, используя цвет фона для списка изображений. Если цвет фона является CLR_NONE значением, изображение прозрачно рисуется с помощью маски.

Другие возможные стили описаны в элементе *фстиле* структуры [имажелистдравпарамс](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) .

*dwRop*<br/>
Значение, указывающее код точечной операции. Эти коды определяют, как данные цвета для исходного прямоугольника будут объединены с данными цвета для прямоугольника назначения, чтобы получить окончательный цвет. Реализация MFC по умолчанию СРККОПИ копирует исходный прямоугольник непосредственно в прямоугольник назначения. Этот параметр пропускается, если параметр *фстиле* не включает флаг ILD_ROP.

Другие возможные значения описаны в элементе *двроп* структуры [имажелистдравпарамс](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) .

*ргббакк*<br/>
Цвет фона изображения по умолчанию CLR_DEFAULT. Этот параметр может быть значением RGB, определенным приложением, или одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|Цвет фона по умолчанию. Изображение отображается с помощью цвета фона списка изображений.|
|CLR_NONE|Цвет фона отсутствует. Изображение прозрачно рисуется.|

*ргбфоре*<br/>
Цвет переднего плана изображения CLR_DEFAULT по умолчанию. Этот параметр может быть значением RGB, определенным приложением, или одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|Цвет переднего плана по умолчанию. Изображение отображается с использованием цвета выделения системы в качестве цвета переднего плана.|
|CLR_NONE|Нет цвета смешения. Изображение смешивается с цветом контекста целевого устройства.|

Этот параметр используется только в том случае, если *фстиле* включает флаг ILD_BLEND25 или ILD_BLEND50.

*фстате*<br/>
Флаг, указывающий состояние рисования. Этот элемент может содержать один или несколько флагов состояния списка изображений.

*Frame*<br/>
Влияет на поведение эффектов насыщенности и альфа-смешения.

При использовании с ILS_SATURATE этот элемент содержит значение, которое добавляется к каждому компоненту цвета Triplet RGB для каждого пикселя в значке.

При использовании с ILS_APLHA этот элемент содержит значение для альфа-канала. Это значение может быть от 0 до 255, при этом 0 будет полностью прозрачным, а 255 — полностью непрозрачным.

*креффект*<br/>
Значение [COLORREF](/windows/win32/gdi/colorref) , используемое для эффектов свечения и тени.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если изображение успешно рисуется; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Используйте первую версию, если хотите самостоятельно заполнить структуру Win32. Используйте вторую версию, если требуется использовать один или несколько аргументов MFC по умолчанию или не управлять структурой.

Изображение оверлея — это изображение, которое рисуется поверх основного изображения, указанного в этой функции-члене параметром *Нимаже* . Нарисуйте маску оверлея с помощью функции-члена [Draw](#draw) с индексом оверлея, заданным с помощью макроса [индекстуверлаймаск](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>CImageList:: Енддраг

Вызовите эту функцию для завершения операции перетаскивания.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Примечания

Чтобы начать операцию перетаскивания, используйте `BeginDrag` функцию-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>CImageList:: Екстрактикон

Вызовите эту функцию, чтобы создать значок на основе изображения и связанной с ним маски в списке изображений.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения.

### <a name="return-value"></a>Возвращаемое значение

Маркер значка в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Этот метод зависит от поведения макроса [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) для создания значка. Дополнительные сведения о создании и очистке значков см. в [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) макросе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>CImageList:: FromHandle

Возвращает указатель на `CImageList` объект при наличии маркера для списка изображений.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Задает список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект в случае `CImageList` успеха; в противном случае — null.

### <a name="remarks"></a>Примечания

Если объект `CImageList` не присоединен к обработчику, создается и подключается временный `CImageList` . Этот временный `CImageList` объект действителен только до тех пор, пока приложение не найдет время простоя в цикле событий, во время которого все временные объекты будут удалены.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>CImageList:: Фромхандлеперманент

Возвращает указатель на `CImageList` объект при наличии маркера для списка изображений.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Задает список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект в случае `CImageList` успеха; в противном случае — null.

### <a name="remarks"></a>Примечания

Если `CImageList` объект не присоединен к маркеру, возвращается значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>CImageList:: Жетбкколор

Вызовите эту функцию, чтобы получить текущий цвет фона для списка изображений.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB `CImageList` цвета фона объекта.

### <a name="example"></a>Пример

  См. пример для [CImageList:: сетбкколор](#setbkcolor).

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>CImageList:: Жетдрагимаже

Возвращает временный список изображений, используемый для перетаскивания.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Параметры

*лппоинт*<br/>
Адрес структуры [точек](/windows/win32/api/windef/ns-windef-point) , которая получает текущую позицию перетаскивания.

*лппоинсотспот*<br/>
Адрес `POINT` структуры, получающей смещение изображения перетаскивания относительно позиции перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на временный список изображений, используемый для перетаскивания; в противном случае значение NULL.

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>CImageList:: Жетимажекаунт

Вызовите эту функцию, чтобы получить количество изображений в списке изображений.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество образов.

### <a name="example"></a>Пример

  См. пример для [CImageList:: екстрактикон](#extracticon).

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>CImageList:: Жетимажеинфо

Вызовите эту функцию, чтобы получить сведения о изображении.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения.

*пимажеинфо*<br/>
Указатель на структуру [имажеинфо](/windows/win32/api/commctrl/ns-commctrl-imageinfo) , которая получает сведения об изображении. Сведения в этой структуре можно использовать для непосредственного управления точечными рисунками изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`IMAGEINFO`Структура содержит сведения о изображении в списке изображений.

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>CImageList:: Жетсафехандле

Вызовите эту функцию, чтобы получить `m_hImageList` элемент данных.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер для присоединенного списка изображений; в противном случае значение NULL, если объект не присоединен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>CImageList:: m_hImageList

Маркер списка изображений, прикрепленный к этому объекту.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Примечания

`m_hImageList`Элемент данных является открытой переменной типа химажелист.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>CImageList::operator ХИМАЖЕЛИСТ

Этот оператор используется для получения присоединенного маркера `CImageList` объекта.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха — обработчик списка изображений, представленный `CImageList` объектом; в противном случае — null.

### <a name="remarks"></a>Примечания

Этот оператор является оператором приведения, который поддерживает прямое использование объекта ХИМАЖЕЛИСТ.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>CImageList:: Read

Эта функция вызывается для чтения списка изображений из архива.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*парчиве*<br/>
Указатель на объект, `CArchive` из которого считывается список изображений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>CImageList:: Remove

Вызовите эту функцию, чтобы удалить изображение из объекта списка изображений.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс удаляемого изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Все элементы, следующие за *Нимаже* , теперь перемещаются в одну и ту же позиции. Например, если список изображений содержит два элемента, удаление первого элемента приведет к тому, что оставшийся элемент будет находиться в первой позиции. *Нимаже*= 0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>CImageList:: Replace

Вызовите эту функцию, чтобы заменить изображение в списке изображений новым изображением.

```
BOOL Replace(
    int nImage,
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Replace(
    int nImage,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс заменяемого изображения.

*пбмимаже*<br/>
Указатель на точечный рисунок, содержащий изображение.

*пбммаск*<br/>
Указатель на точечный рисунок, содержащий маску. Если в списке изображений не используется маска, этот параметр игнорируется.

*hIcon*<br/>
Маркер для значка, который содержит растровое изображение и маску для нового изображения.

### <a name="return-value"></a>Возвращаемое значение

Версия, возвращающая BOOL, возвращает ненулевое значение в случае успеха. в противном случае — 0.

Возвращаемая версия **`int`** возвращает отсчитываемый от нуля индекс изображения в случае успеха; в противном случае — 1.

### <a name="remarks"></a>Примечания

Вызовите эту функцию члена после вызова [сетимажекаунт](#setimagecount) , чтобы назначить новые допустимые изображения для номеров индекса изображения заполнителя.

### <a name="example"></a>Пример

  См. пример для [CImageList:: сетимажекаунт](#setimagecount).

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>CImageList:: Сетбкколор

Вызовите эту функцию, чтобы задать цвет фона для списка изображений.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*Кредит*<br/>
Цвет фона для установки. Его можно CLR_NONE. В этом случае изображения прозрачно рисуются с помощью маски.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет фона в случае успеха; в противном случае CLR_NONE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>CImageList:: Сетдрагкурсоримаже

Создает новое изображение перетаскивания, комбинируя заданный рисунок (обычно это изображение курсора мыши) с текущим изображением перетаскивания.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*ндраг*<br/>
Индекс нового изображения, которое необходимо объединить с изображением перетаскивания.

*псотспот*<br/>
Расположение активной точки в новом изображении.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Поскольку функции перетаскивания используют новый образ во время операции перетаскивания, следует использовать функцию Windows [шовкурсор](/windows/win32/api/winuser/nf-winuser-showcursor) , чтобы скрыть фактический курсор мыши после вызова метода `CImageList::SetDragCursorImage` . В противном случае система может иметь два курсора мыши в течение операции перетаскивания.

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>CImageList:: Сетимажекаунт

Вызовите эту функцию-член, чтобы сбросить количество изображений в `CImageList` объекте.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Параметры

*уневкаунт*<br/>
Значение, указывающее новое общее число образов в списке изображений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

При вызове этой функции члена для увеличения количества изображений в списке изображений вызовите метод [Replace](#replace) для каждого дополнительного изображения, чтобы назначить новые индексы допустимым изображениям. Если не назначить индексы допустимым изображениям, операции рисования, создающие новые образы, будут непредсказуемыми.

При уменьшении размера списка изображений с помощью этой функции усеченные изображения освобождаются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>CImageList:: Сетоверлайимаже

Вызовите эту функцию, чтобы добавить Отсчитываемый от нуля индекс изображения в список изображений, которые будут использоваться в качестве масок наложения.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения, используемого в качестве маски оверлея.

*новерлай*<br/>
Индекс маски оверлея, отсчитываемый от единицы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

В список можно добавить до четырех индексов.

Маска оверлея — это изображение, которое прозрачно рисуется над другим изображением. Нарисуйте маску наложения для изображения с помощью функции-члена [CImageList::D RAW](#draw) с индексом оверлея, заданным с помощью макроса индекстуверлаймаск.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>CImageList:: Write

Вызывайте эту функцию для записи объекта списка изображений в архив.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*парчиве*<br/>
Указатель на объект, `CArchive` в котором будет храниться список изображений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)
