---
title: Класс Ккомконтролбасе
ms.date: 11/04/2016
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 6baaad9e3eae077b0ec460ba4e881508245bb894
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224322"
---
# <a name="ccomcontrolbase-class"></a>Класс Ккомконтролбасе

Этот класс предоставляет методы для создания элементов управления ATL и управления ими.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[Ккомконтролбасе:: Аппеаранцетипе](#appearancetype)|Переопределите, имеет ли `m_nAppearance` свойство фондовой биржи тип **`short`** .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ккомконтролбасе:: Ккомконтролбасе](#ccomcontrolbase)|Конструктор.|
|[Ккомконтролбасе:: ~ Ккомконтролбасе](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккомконтролбасе:: Контролкуеринтерфаце](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[Ккомконтролбасе::D Оесвербактивате](#doesverbactivate)|Проверяет, что параметр *иверб* , используемый, `IOleObjectImpl::DoVerb` либо активирует пользовательский интерфейс элемента управления (*иверб* равно OLEIVERB_UIACTIVATE), определяет действие, выполняемое, когда пользователь дважды щелкает элемент управления (*иверб* равно OLEIVERB_PRIMARY), отображает элемент управления (*иверб* равен OLEIVERB_SHOW) или активирует элемент управления (*иверб* равно OLEIVERB_INPLACEACTIVATE).|
|[Ккомконтролбасе::D Оесвербуиактивате](#doesverbuiactivate)|Проверяет, что параметр *иверб* , используемый, `IOleObjectImpl::DoVerb` вызывает в пользовательском интерфейсе элемента управления активацию и возвращает значение true.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Отображает страницы свойств элемента управления.|
|[Ккомконтролбасе:: Фиревиевчанже](#fireviewchange)|Вызовите этот метод, чтобы сообщить контейнеру о необходимости перерисовки элемента управления или уведомить зарегистрированные приемники уведомлений о том, что представление элемента управления изменилось.|
|[Ккомконтролбасе:: Жетамбиентаппеаранце](#getambientappearance)|Извлекает DISPID_AMBIENT_APPEARANCE, текущий параметр внешнего вида для элемента управления: 0 для Flat и 1 для 3D.|
|[Ккомконтролбасе:: Жетамбиентаутоклип](#getambientautoclip)|Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматическое обрезание области просмотра элемента управления.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружения для всех элементов управления, определенных контейнером.|
|[Ккомконтролбасе:: Жетамбиентчарсет](#getambientcharset)|Извлекает DISPID_AMBIENT_CHARSET, набор внешних символов для всех элементов управления, определенных контейнером.|
|[Ккомконтролбасе:: Жетамбиенткодепаже](#getambientcodepage)|Извлекает DISPID_AMBIENT_CODEPAGE, набор внешних символов для всех элементов управления, определенных контейнером.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который имеет значение TRUE, если контейнер пометил элемент управления на этом сайте как кнопку по умолчанию, и поэтому элемент управления "Кнопка" должен рисовать себя с помощью более толстой рамки.|
|[Ккомконтролбасе:: Жетамбиентдисплайнаме](#getambientdisplayname)|Извлекает DISPID_AMBIENT_DISPLAYNAME — имя, которое контейнер предоставил элементу управления.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Извлекает указатель на внешний `IFont` интерфейс контейнера.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Извлекает указатель на `IFontDisp` интерфейс диспетчеризации контейнера.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Извлекает DISPID_AMBIENT_FORECOLOR, цвет переднего плана окружения для всех элементов управления, определенных контейнером.|
|[Ккомконтролбасе:: Жетамбиентлокалеид](#getambientlocaleid)|Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемого контейнером.|
|[Ккомконтролбасе:: Жетамбиентмессажерефлект](#getambientmessagereflect)|Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет ли контейнер получать сообщения окна (например, WM_DRAWITEM) как события.|
|[Ккомконтролбасе:: Жетамбиентпалетте](#getambientpalette)|Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к ХПАЛЕТТЕ контейнера.|
|[Ккомконтролбасе:: Жетамбиентпроперти](#getambientproperty)|Извлекает свойство контейнера, заданное по *идентификатору*.|
|[Ккомконтролбасе:: Жетамбиентригхттолефт](#getambientrighttoleft)|Возвращает DISPID_AMBIENT_RIGHTTOLEFT, направление отображения содержимого контейнером.|
|[Ккомконтролбасе:: Жетамбиентскалеунитс](#getambientscaleunits)|Извлекает DISPID_AMBIENT_SCALEUNITS, окружающие элементы контейнера (например, дюймы или сантиметры) для отображения меток.|
|[Ккомконтролбасе:: Жетамбиентшовграбхандлес](#getambientshowgrabhandles)|Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, разрешает ли контейнер элемент управления отображать дескрипторы захвата для самого себя, если он активен.|
|[Ккомконтролбасе:: Жетамбиентшовхатчинг](#getambientshowhatching)|Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, позволяет ли контейнер отображать элемент управления с штриховым узором, если пользовательский интерфейс активен.|
|[Ккомконтролбасе:: Жетамбиентсуппортсмнемоникс](#getambientsupportsmnemonics)|Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер сочетания клавиш.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Извлекает DISPID_AMBIENT_TEXTALIGN, выравнивание текста, предпочитаемое контейнером: 0 для общего выравнивания (числа справа, слева направо), 1 для выравнивания по левому краю, 2 для выравнивания по центру и 3 для выравнивания по правому краю.|
|[Ккомконтролбасе:: Жетамбиенттоптоботтом](#getambienttoptobottom)|Возвращает DISPID_AMBIENT_TOPTOBOTTOM, направление отображения содержимого контейнером.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, желает ли контейнер элемент управления реагировать на действия пользовательского интерфейса.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, находится ли контейнер в режиме выполнения (TRUE) или режиме конструктора (FALSE).|
|[Ккомконтролбасе:: IsDirty](#getdirty)|Возвращает значение элемента данных `m_bRequiresSave` .|
|[Ккомконтролбасе:: Жетзуминфо](#getzoominfo)|Получает значения x и y числителя и знаменатель коэффициента масштабирования для элемента управления, активированного для редактирования на месте.|
|[Ккомконтролбасе:: Инплацеактивате](#inplaceactivate)|Заставляет элемент управления переходить из неактивного состояния в любое состояние, которое указывает команда в *иверб* .|
|[Ккомконтролбасе:: Интерналжетсите](#internalgetsite)|Вызовите этот метод, чтобы запросить на сайте элемента управления указатель на идентифицированный интерфейс.|
|[Ккомконтролбасе:: OnDraw](#ondraw)|Переопределите этот метод для рисования элемента управления.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|По умолчанию `OnDrawAdvanced` подготавливает Нормализованный контекст устройства для рисования, а затем вызывает метод класса элемента управления `OnDraw` .|
|[Ккомконтролбасе:: Онкиллфокус](#onkillfocus)|Проверяет, что элемент управления находится в активном состоянии и имеет допустимый сайт управления, а затем информирует контейнер о потере фокуса элементом управления.|
|[Ккомконтролбасе:: Онмаусеактивате](#onmouseactivate)|Проверяет, что пользовательский интерфейс находится в пользовательском режиме, а затем активирует элемент управления.|
|[Ккомконтролбасе:: onpain](#onpaint)|Подготавливает контейнер для рисования, получает клиентскую область элемента управления, а затем вызывает метод класса элемента управления `OnDraw` .|
|[Ккомконтролбасе:: OnSetFocus](#onsetfocus)|Проверяет, что элемент управления активен и имеет допустимый сайт управления, а затем сообщает контейнеру, что элемент управления получил фокус.|
|[Ккомконтролбасе::P Ретранслатеакцелератор](#pretranslateaccelerator)|Переопределите этот метод, чтобы предоставить собственные обработчики сочетаний клавиш.|
|[Ккомконтролбасе:: Сендонклосе](#sendonclose)|Уведомляет все приемники рекомендаций, зарегистрированные с помощью держателя уведомления о закрытии элемента управления.|
|[Ккомконтролбасе:: Сендондатачанже](#sendondatachange)|Уведомляет все приемники уведомлений, зарегистрированные с помощью держателя рекомендаций, что данные элемента управления изменились.|
|[Ккомконтролбасе:: Сендонренаме](#sendonrename)|Уведомляет все приемники уведомлений, зарегистрированные с помощью держателя уведомления о том, что у элемента управления есть новый моникер.|
|[Ккомконтролбасе:: Сендонсаве](#sendonsave)|Уведомляет все приемники рекомендаций, зарегистрированные с помощью держателя уведомления о том, что элемент управления сохранен.|
|[Ккомконтролбасе:: Сендонвиевчанже](#sendonviewchange)|Уведомляет все зарегистрированные приемники уведомлений о том, что представление элемента управления изменилось.|
|[Ккомконтролбасе:: Сетконтролфокус](#setcontrolfocus)|Устанавливает или удаляет фокус клавиатуры в элементе управления или из него.|
|[Ккомконтролбасе:: Сетдирти](#setdirty)|Задает для элемента данных `m_bRequiresSave` значение в *бдирти*.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Ккомконтролбасе:: m_bAutoSize](#m_bautosize)|Флаг, указывающий, что элемент управления не может быть другим размером.|
|[Ккомконтролбасе:: m_bDrawFromNatural](#m_bdrawfromnatural)|Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` должен задавать размер элемента управления от, `m_sizeNatural` а не от `m_sizeExtent` .|
|[Ккомконтролбасе:: m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Флаг, указывающий, что `IDataObjectImpl::GetData` при рисовании следует использовать единицы HIMETRIC и not pixels.|
|[Ккомконтролбасе:: m_bInPlaceActive](#m_binplaceactive)|Флаг, указывающий, что элемент управления активен в режиме "в наличии".|
|[Ккомконтролбасе:: m_bInPlaceSiteEx](#m_binplacesiteex)|Флаг, указывающий, что контейнер поддерживает `IOleInPlaceSiteEx` функции элементов управления интерфейса и OCX96, такие как бесоконные и мерцания.|
|[Ккомконтролбасе:: m_bNegotiatedWnd](#m_bnegotiatedwnd)|Флаг, указывающий, согласовывается ли элемент управления с контейнером о поддержке функций управления OCX96 (например, безмерцания и безоконное управление), а также о том, является ли элемент управления оконным или безоконным.|
|[Ккомконтролбасе:: m_bRecomposeOnResize](#m_brecomposeonresize)|Флаг, указывающий, что элемент управления желает повторно составлять свою презентацию, когда контейнер изменяет отображаемый размер элемента управления.|
|[Ккомконтролбасе:: m_bRequiresSave](#m_brequiressave)|Флаг, указывающий, что элемент управления изменился со времени последнего сохранения.|
|[Ккомконтролбасе:: m_bResizeNatural](#m_bresizenatural)|Флаг, указывающий, что элемент управления хочет изменить размер своего естественного экстента (его немасштабируемый физический размер), когда контейнер изменяет отображаемый размер элемента управления.|
|[Ккомконтролбасе:: m_bUIActive](#m_buiactive)|Флаг, указывающий пользовательский интерфейс элемента управления, например меню и панели инструментов, является активным.|
|[Ккомконтролбасе:: m_bUsingWindowRgn](#m_busingwindowrgn)|Флаг, указывающий, что элемент управления использует область окна, предоставляемую контейнером.|
|[Ккомконтролбасе:: m_bWasOnceWindowless](#m_bwasoncewindowless)|Флаг, указывающий, что элемент управления безоконный, но может быть и не может быть безоконным.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Флаг, указывающий, что элемент управления должен быть оконным, даже если контейнер поддерживает безоконные элементы управления.|
|[Ккомконтролбасе:: m_bWndLess](#m_bwndless)|Флаг, указывающий, что элемент управления не является окном.|
|[Ккомконтролбасе:: m_hWndCD](#m_hwndcd)|Содержит ссылку на маркер окна, связанный с элементом управления.|
|[Ккомконтролбасе:: m_nFreezeEvents](#m_nfreezeevents)|Количество зафиксированных событий контейнера (отклоненных для принятия событий) без промежуточного разморозки событий (прием событий).|
|[Ккомконтролбасе:: m_rcPos](#m_rcpos)|Расположение в пикселях элемента управления, выраженное в координатах контейнера.|
|[Ккомконтролбасе:: m_sizeExtent](#m_sizeextent)|Область элемента управления в единицах HIMETRIC (каждая единица — 0,01 миллиметра) для конкретного дисплея.|
|[Ккомконтролбасе:: m_sizeNatural](#m_sizenatural)|Физический размер элемента управления в единицах HIMETRIC (каждая единица — 0,01 миллиметра).|
|[Ккомконтролбасе:: m_spAdviseSink](#m_spadvisesink)|Прямой указатель на вспомогательное соединение в контейнере ( [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink)контейнера).|
|[Ккомконтролбасе:: m_spAmbientDispatch](#m_spambientdispatch)|`CComDispatchDriver`Объект, позволяющий извлекать и задавать свойства контейнера с помощью `IDispatch` указателя.|
|[Ккомконтролбасе:: m_spClientSite](#m_spclientsite)|Указатель на клиентский сайт элемента управления в контейнере.|
|[Ккомконтролбасе:: m_spDataAdviseHolder](#m_spdataadviseholder)|Предоставляет стандартные средства для хранения вспомогательных соединений между объектами данных и приемниками уведомлений.|
|[Ккомконтролбасе:: m_spInPlaceSite](#m_spinplacesite)|Указатель на указатель интерфейса [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [иолеинплацеситикс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)или [иолеинплацеситевиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) контейнера.|
|[Ккомконтролбасе:: m_spOleAdviseHolder](#m_spoleadviseholder)|Предоставляет стандартную реализацию способа хранения вспомогательных соединений.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для создания элементов управления ATL и управления ими. [Класс ккомконтрол](../../atl/reference/ccomcontrol-class.md) является производным от `CComControlBase` . При создании стандартного элемента управления или элемента управления DHTML с помощью мастера элементов управления ATL мастер автоматически создает производный класс от `CComControlBase` .

Дополнительные сведения о создании элемента управления см. в [руководстве по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проектов ATL см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлктл.h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a>Ккомконтролбасе:: Аппеаранцетипе

Переопределите, имеет ли `m_nAppearance` свойство фондовой биржи тип **`short`** .

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Примечания

Мастер элементов управления ATL добавляет `m_nAppearance` свойство акции типа Short. Переопределите, `AppearanceType` Если используется другой тип данных.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a>Ккомконтролбасе:: Ккомконтролбасе

Конструктор.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Маркер окна, связанного с элементом управления.

### <a name="remarks"></a>Примечания

Инициализирует размер элемента управления равным 5080X5080 единицам HIMETRIC (2 "x2") и инициализирует `CComControlBase` значения NULL или false для элементов данных.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a>Ккомконтролбасе:: ~ Ккомконтролбасе

Деструктор

```
~CComControlBase();
```

### <a name="remarks"></a>Примечания

Если элемент управления является оконным, `~CComControlBase` удаляет его, вызывая [дестройвиндов](/windows/win32/api/winuser/nf-winuser-destroywindow).

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a>Ккомконтролбасе:: Контролкуеринтерфаце

Извлекает указатель на запрошенный интерфейс.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
Идентификатор GUID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый по *IID*, или значение null, если интерфейс не найден.

### <a name="remarks"></a>Примечания

Обрабатывает только интерфейсы в таблице-сопоставлении COM.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a>Ккомконтролбасе::D Оесвербактивате

Проверяет, что параметр *иверб* , используемый, `IOleObjectImpl::DoVerb` либо активирует пользовательский интерфейс элемента управления (*иверб* равно OLEIVERB_UIACTIVATE), определяет действие, выполняемое, когда пользователь дважды щелкает элемент управления (*иверб* равно OLEIVERB_PRIMARY), отображает элемент управления (*иверб* равен OLEIVERB_SHOW) или активирует элемент управления (*иверб* равно OLEIVERB_INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Значение, указывающее действие, выполняемое `DoVerb` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если *иверб* равно OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE; в противном случае возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно переопределить, чтобы определить собственную команду активации.

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a>Ккомконтролбасе::D Оесвербуиактивате

Проверяет, что параметр *иверб* , используемый, `IOleObjectImpl::DoVerb` вызывает в пользовательском интерфейсе элемента управления активацию и возвращает значение true.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Значение, указывающее действие, выполняемое `DoVerb` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если *иверб* равно OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE. В противном случае метод возвращает значение FALSE.

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a>Ккомконтролбасе::D Овербпропертиес

Отображает страницы свойств элемента управления.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
Зарезервировано.

*хвндпарент*<br/>
Маркер окна, содержащего элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a>Ккомконтролбасе:: Фиревиевчанже

Вызовите этот метод, чтобы сообщить контейнеру о необходимости перерисовки элемента управления или уведомить зарегистрированные приемники уведомлений о том, что представление элемента управления изменилось.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если элемент управления активен (элемент данных класса элемента управления [ккомконтролбасе:: m_bInPlaceActive](#m_binplaceactive) имеет значение true), уведомляет контейнер о необходимости перерисовки всего элемента управления. Если элемент управления неактивен, уведомляет зарегистрированные приемники уведомлений элемента управления (через элемент данных класса элемента управления [ккомконтролбасе:: m_spAdviseSink](#m_spadvisesink)) об изменении представления элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a>Ккомконтролбасе:: Жетамбиентаппеаранце

Извлекает DISPID_AMBIENT_APPEARANCE, текущий параметр внешнего вида для элемента управления: 0 для Flat и 1 для 3D.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Параметры

*наппеаранце*<br/>
DISPID_AMBIENT_APPEARANCE свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a>Ккомконтролбасе:: Жетамбиентаутоклип

Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматическое обрезание области просмотра элемента управления.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Параметры

*баутоклип*<br/>
DISPID_AMBIENT_AUTOCLIP свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a>Ккомконтролбасе:: Жетамбиентбаккколор

Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружения для всех элементов управления, определенных контейнером.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Параметры

*BackColor*<br/>
DISPID_AMBIENT_BACKCOLOR свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a>Ккомконтролбасе:: Жетамбиентчарсет

Извлекает DISPID_AMBIENT_CHARSET, набор внешних символов для всех элементов управления, определенных контейнером.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Параметры

*бстрчарсет*<br/>
DISPID_AMBIENT_CHARSET свойства.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a>Ккомконтролбасе:: Жетамбиенткодепаже

Извлекает DISPID_AMBIENT_CODEPAGE, страницу кода окружения для всех элементов управления, определенных контейнером.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Параметры

*улкодепаже*<br/>
DISPID_AMBIENT_CODEPAGE свойства.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a>Ккомконтролбасе:: Жетамбиентдисплайасдефаулт

Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который имеет значение TRUE, если контейнер пометил элемент управления на этом сайте как кнопку по умолчанию, и поэтому элемент управления "Кнопка" должен рисовать себя с помощью более толстой рамки.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*бдисплайасдефаулт*<br/>
DISPID_AMBIENT_DISPLAYASDEFAULT свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a>Ккомконтролбасе:: Жетамбиентдисплайнаме

Извлекает DISPID_AMBIENT_DISPLAYNAME — имя, которое контейнер предоставил элементу управления.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Параметры

*бстрдисплайнаме*<br/>
DISPID_AMBIENT_DISPLAYNAME свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a>Ккомконтролбасе:: Жетамбиентфонт

Извлекает указатель на внешний `IFont` интерфейс контейнера.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Параметры

*ппфонт*<br/>
Указатель на интерфейс внешнего [IFont](/windows/win32/api/ocidl/nn-ocidl-ifont) контейнера.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если свойство имеет значение NULL, указатель имеет значение NULL. Если указатель не равен NULL, вызывающий объект должен освободить указатель.

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a>Ккомконтролбасе:: Жетамбиентфонтдисп

Извлекает указатель на `IFontDisp` интерфейс диспетчеризации контейнера.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Параметры

*ппфонт*<br/>
Указатель на интерфейс диспетчеризации внешнего [IFontDispа](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) контейнера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Если свойство имеет значение NULL, указатель имеет значение NULL. Если указатель не равен NULL, вызывающий объект должен освободить указатель.

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a>Ккомконтролбасе:: Жетамбиентфореколор

Извлекает DISPID_AMBIENT_FORECOLOR, цвет переднего плана окружения для всех элементов управления, определенных контейнером.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Параметры

*ForeColor*<br/>
DISPID_AMBIENT_FORECOLOR свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a>Ккомконтролбасе:: Жетамбиентлокалеид

Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемого контейнером.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
DISPID_AMBIENT_LOCALEID свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Элемент управления может использовать этот идентификатор для адаптации пользовательского интерфейса к различным языкам.

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a>Ккомконтролбасе:: Жетамбиентмессажерефлект

Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет ли контейнер получать сообщения окон (например, `WM_DRAWITEM` ) как события.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Параметры

*бмессажерефлект*<br/>
DISPID_AMBIENT_MESSAGEREFLECT свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a>Ккомконтролбасе:: Жетамбиентпалетте

Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к ХПАЛЕТТЕ контейнера.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Параметры

*хпалетте*<br/>
DISPID_AMBIENT_PALETTE свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a>Ккомконтролбасе:: Жетамбиентпроперти

Извлекает свойство контейнера, заданное параметром *DISPID*.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор извлекаемого свойства контейнера.

*var*<br/>
Переменная для получения свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Библиотека ATL предоставила набор вспомогательных функций для получения конкретных свойств, например [ккомконтролбасе:: жетамбиентбаккколор](#getambientbackcolor). Если подходящий метод недоступен, используйте `GetAmbientProperty` .

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a>Ккомконтролбасе:: Жетамбиентригхттолефт

Возвращает DISPID_AMBIENT_RIGHTTOLEFT, направление отображения содержимого контейнером.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Параметры

*бригхттолефт*<br/>
DISPID_AMBIENT_RIGHTTOLEFT свойства. Задайте значение TRUE, если содержимое отображается справа налево, и FALSE, если оно отображается слева направо.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a>Ккомконтролбасе:: Жетамбиентскалеунитс

Извлекает DISPID_AMBIENT_SCALEUNITS, окружающие элементы контейнера (например, дюймы или сантиметры) для отображения меток.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Параметры

*бстрскалеунитс*<br/>
DISPID_AMBIENT_SCALEUNITS свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a>Ккомконтролбасе:: Жетамбиентшовграбхандлес

Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, разрешает ли контейнер элемент управления отображать дескрипторы захвата для самого себя, если он активен.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Параметры

*бшовграбхандлес*<br/>
DISPID_AMBIENT_SHOWGRABHANDLES свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a>Ккомконтролбасе:: Жетамбиентшовхатчинг

Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, позволяет ли контейнер отображать элемент управления с штриховым узором, когда активен пользовательский интерфейс элемента управления.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Параметры

*бшовхатчинг*<br/>
DISPID_AMBIENT_SHOWHATCHING свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a>Ккомконтролбасе:: Жетамбиентсуппортсмнемоникс

Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер сочетания клавиш.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Параметры

*бсуппортсмнемоникс*<br/>
DISPID_AMBIENT_SUPPORTSMNEMONICS свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a>Ккомконтролбасе:: Жетамбиенттексталигн

Извлекает DISPID_AMBIENT_TEXTALIGN, выравнивание текста, предпочитаемое контейнером: 0 для общего выравнивания (числа справа, слева направо), 1 для выравнивания по левому краю, 2 для выравнивания по центру и 3 для выравнивания по правому краю.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Параметры

*нтексталигн*<br/>
DISPID_AMBIENT_TEXTALIGN свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a>Ккомконтролбасе:: Жетамбиенттоптоботтом

Возвращает DISPID_AMBIENT_TOPTOBOTTOM, направление отображения содержимого контейнером.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Параметры

*бтоптоботтом*<br/>
DISPID_AMBIENT_TOPTOBOTTOM свойства. Задайте значение TRUE, если текст отображается сверху вниз, значение FALSE, если оно отображается снизу вверх.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a>Ккомконтролбасе:: Жетамбиентуидеад

Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, желает ли контейнер элемент управления реагировать на действия пользовательского интерфейса.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Параметры

*буидеад*<br/>
DISPID_AMBIENT_UIDEAD свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если значение равно TRUE, элемент управления не должен отвечать. Этот флаг применяется независимо от флага DISPID_AMBIENT_USERMODE. См. раздел [ккомконтролбасе:: жетамбиентусермоде](#getambientusermode).

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a>Ккомконтролбасе:: Жетамбиентусермоде

Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, находится ли контейнер в режиме выполнения (TRUE) или режиме конструктора (FALSE).

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Параметры

*бусермоде*<br/>
DISPID_AMBIENT_USERMODE свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a>Ккомконтролбасе:: IsDirty

Возвращает значение элемента данных `m_bRequiresSave` .

```
BOOL GetDirty();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [m_bRequiresSave](#m_brequiressave)элементов данных.

### <a name="remarks"></a>Примечания

Это значение задается с помощью [ккомконтролбасе:: сетдирти](#setdirty).

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a>Ккомконтролбасе:: Жетзуминфо

Получает значения x и y числителя и знаменатель коэффициента масштабирования для элемента управления, активированного для редактирования на месте.

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Di*<br/>
Структура, которая будет содержать числитель и знаменатель коэффициента масштабирования. Дополнительные сведения см. в разделе [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).

### <a name="remarks"></a>Примечания

Коэффициент масштабирования — это доля естественного размера элемента управления в его текущем экстенте.

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a>Ккомконтролбасе:: Инплацеактивате

Заставляет элемент управления переходить из неактивного состояния в любое состояние, которое указывает команда в *иверб* .

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Значение, указывающее действие, выполняемое [иолеобжектимпл::D оверб](../../atl/reference/ioleobjectimpl-class.md#doverb).

*пркпосрект*<br/>
Указатель на позицию элемента управления на месте.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Перед активацией этот метод проверяет наличие клиентского сайта у элемента управления, проверяет, какая часть элемента управления является видимой, и получает расположение элемента управления в родительском окне. После активации элемента управления этот метод активирует пользовательский интерфейс элемента управления и сообщает контейнеру, что элемент управления должен быть видимым.

Этот метод также извлекает `IOleInPlaceSite` `IOleInPlaceSiteEx` указатель интерфейса, или `IOleInPlaceSiteWindowless` для элемента управления и сохраняет его в элемент данных класса элемента управления [ккомконтролбасе:: m_spInPlaceSite](#m_spinplacesite). Члены данных класса элемента управления [ккомконтролбасе:: m_bInPlaceSiteEx](#m_binplacesiteex), [ккомконтролбасе:: m_bWndLess](#m_bwndless), [Ккомконтролбасе:: m_bWasOnceWindowless](#m_bwasoncewindowless)и [ккомконтролбасе:: m_bNegotiatedWnd](#m_bnegotiatedwnd) имеют соответствующее значение true.

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a>Ккомконтролбасе:: Интерналжетсите

Вызовите этот метод, чтобы запросить на сайте элемента управления указатель на идентифицированный интерфейс.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор IID указателя интерфейса, который должен возвращаться в *ппунксите*.

*ппунксите*<br/>
Адрес переменной указателя, получающей указатель интерфейса, запрошенный в *riid*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Если сайт поддерживает интерфейс, запрошенный в *riid*, указатель возвращается с помощью *ппунксите*. В противном случае *ппунксите* имеет значение null.

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a>Ккомконтролбасе:: m_bAutoSize

Флаг, указывающий, что элемент управления не может быть другим размером.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Примечания

Этот флаг проверяется `IOleObjectImpl::SetExtent` и, если значение true, функция возвращает E_FAIL.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

При добавлении параметра **Авторазмер** на вкладке [Свойства акции](../../atl/reference/stock-properties-atl-control-wizard.md) мастера элементов управления ATL мастер автоматически создает этот элемент данных в классе элемента управления, создает методы Where и Get для свойства и поддерживает [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) для автоматического уведомления контейнера при изменении свойства.

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a>Ккомконтролбасе:: m_bDrawFromNatural

Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` должен задавать размер элемента управления от, `m_sizeNatural` а не от `m_sizeExtent` .

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a>Ккомконтролбасе:: m_bDrawGetDataInHimetric

Флаг, указывающий, что `IDataObjectImpl::GetData` при рисовании следует использовать единицы HIMETRIC и not pixels.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Примечания

Каждая логическая единица HIMETRIC — 0,01 миллиметра.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a>Ккомконтролбасе:: m_bInPlaceActive

Флаг, указывающий, что элемент управления активен в режиме "в наличии".

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Примечания

Это означает, что элемент управления является видимым и его окно (если оно есть) отображается, но его меню и панели инструментов могут быть неактивными. `m_bUIActive`Флаг указывает, что пользовательский интерфейс элемента управления, например меню, также является активным.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a>Ккомконтролбасе:: m_bInPlaceSiteEx

Флаг, указывающий, что контейнер поддерживает `IOleInPlaceSiteEx` функции элементов управления интерфейса и OCX96, такие как бесоконные и мерцания.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Элемент данных `m_spInPlaceSite` указывает на интерфейс [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [иолеинплацеситикс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)или [иолеинплацеситевиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) в зависимости от значения `m_bWndLess` `m_bInPlaceSiteEx` флагов и. (Элемент данных `m_bNegotiatedWnd` должен иметь значение true, `m_spInPlaceSite` чтобы указатель был допустимым.)

Если `m_bWndLess` имеет значение false и `m_bInPlaceSiteEx` имеет значение true, `m_spInPlaceSite` то является `IOleInPlaceSiteEx` указателем интерфейса. См. [m_spInPlaceSite](#m_spinplacesite) для таблицы, показывающей связь между тремя элементами данных.

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a>Ккомконтролбасе:: m_bNegotiatedWnd

Флаг, указывающий, согласовывается ли элемент управления с контейнером о поддержке функций управления OCX96 (например, безмерцания и безоконное управление), а также о том, является ли элемент управления оконным или безоконным.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

`m_bNegotiatedWnd` `m_spInPlaceSite` Чтобы указатель был допустимым, флаг должен иметь значение true.

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a>Ккомконтролбасе:: m_bRecomposeOnResize

Флаг, указывающий, что элемент управления желает повторно составлять свою презентацию, когда контейнер изменяет отображаемый размер элемента управления.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Этот флаг проверяется с помощью [иолеобжектимпл:: сетекстент](../../atl/reference/ioleobjectimpl-class.md#setextent) и, если значение true, `SetExtent` уведомляет контейнер об изменениях представления. Если этот флаг установлен, также должен быть установлен бит OLEMISC_RECOMPOSEONRESIZE в перечислении [олемиск](/windows/win32/api/oleidl/ne-oleidl-olemisc) .

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a>Ккомконтролбасе:: m_bRequiresSave

Флаг, указывающий, что элемент управления изменился со времени последнего сохранения.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Примечания

Значение `m_bRequiresSave` можно задать с помощью [ккомконтролбасе:: сетдирти](#setdirty) и получить с помощью [ккомконтролбасе:: IsDirty](#getdirty).

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a>Ккомконтролбасе:: m_bResizeNatural

Флаг, указывающий, что элемент управления хочет изменить размер своего естественного экстента (его немасштабируемый физический размер), когда контейнер изменяет отображаемый размер элемента управления.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Примечания

Этот флаг проверяется `IOleObjectImpl::SetExtent` и, если значение true, то размер, переданный в, `SetExtent` назначается `m_sizeNatural` .

Размер, переданный в `SetExtent` , всегда присваивается `m_sizeExtent` , независимо от значения `m_bResizeNatural` .

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a>Ккомконтролбасе:: m_bUIActive

Флаг, указывающий пользовательский интерфейс элемента управления, например меню и панели инструментов, является активным.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Примечания

`m_bInPlaceActive`Флаг указывает, что элемент управления активен, но его пользовательский интерфейс активен.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a>Ккомконтролбасе:: m_bUsingWindowRgn

Флаг, указывающий, что элемент управления использует область окна, предоставляемую контейнером.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a>Ккомконтролбасе:: m_bWasOnceWindowless

Флаг, указывающий, что элемент управления безоконный, но может быть и не может быть безоконным.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a>Ккомконтролбасе:: m_bWindowOnly

Флаг, указывающий, что элемент управления должен быть оконным, даже если контейнер поддерживает безоконные элементы управления.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a>Ккомконтролбасе:: m_bWndLess

Флаг, указывающий, что элемент управления не является окном.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Элемент данных `m_spInPlaceSite` указывает на интерфейс [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [иолеинплацеситикс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)или [иолеинплацеситевиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) в зависимости от значений `m_bWndLess` флагов и [ккомконтролбасе:: m_bInPlaceSiteEx](#m_binplacesiteex) . (Элемент данных [ккомконтролбасе:: m_bNegotiatedWnd](#m_bnegotiatedwnd) должен иметь значение true, чтобы указатель [ккомконтролбасе:: m_spInPlaceSite](#m_spinplacesite) был допустимым.)

Если `m_bWndLess` имеет значение true, `m_spInPlaceSite` то является `IOleInPlaceSiteWindowless` указателем интерфейса. См. раздел [ккомконтролбасе:: m_spInPlaceSite](#m_spinplacesite) для таблицы, показывающей полную связь между этими элементами данных.

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a>Ккомконтролбасе:: m_hWndCD

Содержит ссылку на маркер окна, связанный с элементом управления.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a>Ккомконтролбасе:: m_nFreezeEvents

Количество зафиксированных событий контейнера (отклоненных для принятия событий) без промежуточного разморозки событий (прием событий).

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a>Ккомконтролбасе:: m_rcPos

Расположение в пикселях элемента управления, выраженное в координатах контейнера.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a>Ккомконтролбасе:: m_sizeExtent

Область элемента управления в единицах HIMETRIC (каждая единица — 0,01 миллиметра) для конкретного дисплея.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Этот размер масштабируется по экрану. Физический размер элемента управления указан в элементе `m_sizeNatural` данных и является фиксированным.

Размер можно преобразовать в пиксели с помощью глобальной функции [атлхиметриктопиксел](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a>Ккомконтролбасе:: m_sizeNatural

Физический размер элемента управления в единицах HIMETRIC (каждая единица — 0,01 миллиметра).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Этот размер фиксирован, а размер в `m_sizeExtent` масштабируется по экрану.

Размер можно преобразовать в пиксели с помощью глобальной функции [атлхиметриктопиксел](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a>Ккомконтролбасе:: m_spAdviseSink

Прямой указатель на вспомогательное соединение в контейнере ( [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink)контейнера).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a>Ккомконтролбасе:: m_spAmbientDispatch

`CComDispatchDriver`Объект, позволяющий извлекать и задавать свойства объекта с помощью `IDispatch` указателя.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a>Ккомконтролбасе:: m_spClientSite

Указатель на клиентский сайт элемента управления в контейнере.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a>Ккомконтролбасе:: m_spDataAdviseHolder

Предоставляет стандартные средства для хранения вспомогательных соединений между объектами данных и приемниками уведомлений.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Объект данных — это элемент управления, который может передавать данные и реализующий интерфейс [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject), методы которого определяют формат и носитель передачи данных.

Интерфейс `m_spDataAdviseHolder` реализует методы [idataobject::D advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) и [IDataObject::D](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) , чтобы устанавливать и удалять рекомендации по подключениям к контейнеру. Контейнер элемента управления должен реализовывать приемник уведомлений, поддерживая интерфейс [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink) .

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a>Ккомконтролбасе:: m_spInPlaceSite

Указатель на указатель интерфейса [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [иолеинплацеситикс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)или [иолеинплацеситевиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) контейнера.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

`m_spInPlaceSite`Указатель допустим, только если флаг [m_bNegotiatedWnd](#m_bnegotiatedwnd) имеет значение true.

В следующей таблице показано, как `m_spInPlaceSite` тип указателя зависит от [m_bWndLess](#m_bwndless) и [m_bInPlaceSiteEx](#m_binplacesiteex) флаги члена данных:

|Тип m_spInPlaceSite|m_bWndLess значение|m_bInPlaceSiteEx значение|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE или FALSE|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a>Ккомконтролбасе:: m_spOleAdviseHolder

Предоставляет стандартную реализацию способа хранения вспомогательных соединений.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Чтобы использовать этот элемент данных в классе элемента управления, необходимо объявить его как элемент данных в классе элемента управления. Класс элемента управления не будет наследовать этот член данных от базового класса, так как он объявлен в объединении в базовом классе.

Интерфейс `m_spOleAdviseHolder` реализует методы [иолеобжект:: Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) и [иолеобжект:: unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) для установки и удаления вспомогательных соединений с контейнером. Контейнер элемента управления должен реализовывать приемник уведомлений, поддерживая интерфейс [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink) .

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a>Ккомконтролбасе:: OnDraw

Переопределите этот метод для рисования элемента управления.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Di*<br/>
Ссылка на структуру [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) , которая содержит сведения о рисовании, такие как аспект рисования, границы элемента управления и способ оптимизации рисунка.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

По умолчанию `OnDraw` удаляет или восстанавливает контекст устройства или не выполняет никаких действий в зависимости от флагов, установленных в [ккомконтролбасе:: ондравадванцед](#ondrawadvanced).

`OnDraw`Метод автоматически добавляется в класс элемента управления при создании элемента управления с помощью мастера элементов управления ATL. По умолчанию мастер `OnDraw` рисует прямоугольник с меткой "ATL 8,0".

### <a name="example"></a>Пример

См. пример для [ккомконтролбасе:: жетамбиентаппеаранце](#getambientappearance).

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a>Ккомконтролбасе:: Ондравадванцед

По умолчанию `OnDrawAdvanced` подготавливает Нормализованный контекст устройства для рисования, а затем вызывает метод класса элемента управления `OnDraw` .

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Di*<br/>
Ссылка на структуру [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) , которая содержит сведения о рисовании, такие как аспект рисования, границы элемента управления и способ оптимизации рисунка.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если хотите принять контекст устройства, переданный контейнером, без нормализации.

Дополнительные сведения см. в разделе [ккомконтролбасе:: OnDraw](#ondraw) .

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a>Ккомконтролбасе:: Онкиллфокус

Проверяет, что элемент управления находится в активном состоянии и имеет допустимый сайт управления, а затем информирует контейнер о потере фокуса элементом управления.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*нмсг*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*бхандлед*<br/>
Флаг, указывающий, успешно ли обработано сообщение окна. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a>Ккомконтролбасе:: Онмаусеактивате

Проверяет, что пользовательский интерфейс находится в пользовательском режиме, а затем активирует элемент управления.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*нмсг*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*бхандлед*<br/>
Флаг, указывающий, успешно ли обработано сообщение окна. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a>Ккомконтролбасе:: onpain

Подготавливает контейнер для рисования, получает клиентскую область элемента управления, а затем вызывает метод класса элемента управления `OnDrawAdvanced` .

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Параметры

*нмсг*<br/>
Зарезервировано.

*wParam*<br/>
Существующий HDC.

*lParam*<br/>
Зарезервировано.

*lResult*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение 0.

### <a name="remarks"></a>Примечания

Если *wParam* не равен null, `OnPaint` предполагает, что он содержит допустимый HDC и использует его вместо [ккомконтролбасе:: m_hWndCD](#m_hwndcd).

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a>Ккомконтролбасе:: OnSetFocus

Проверяет, что элемент управления активен и имеет допустимый сайт управления, а затем сообщает контейнеру, что элемент управления получил фокус.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*нмсг*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*бхандлед*<br/>
Флаг, указывающий, успешно ли обработано сообщение окна. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

### <a name="remarks"></a>Примечания

Отправляет уведомление в контейнер, который элемент управления получил фокус.

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a>Ккомконтролбасе::P Ретранслатеакцелератор

Переопределите этот метод, чтобы предоставить собственные обработчики сочетаний клавиш.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
Зарезервировано.

*хрет*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

По умолчанию возвращает значение FALSE.

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a>Ккомконтролбасе:: Сендонклосе

Уведомляет все приемники рекомендаций, зарегистрированные с помощью держателя уведомления о закрытии элемента управления.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Отправляет уведомление о том, что элемент управления закрыл свои приемники рекомендаций.

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a>Ккомконтролбасе:: Сендондатачанже

Уведомляет все приемники уведомлений, зарегистрированные с помощью держателя рекомендаций, что данные элемента управления изменились.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Параметры

*адвф*<br/>
Флаги advise, указывающие, как выполняется вызов [иадвисесинк:: ондатачанже](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) . Значения из перечисления [адвф](/windows/win32/api/objidl/ne-objidl-advf) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a>Ккомконтролбасе:: Сендонренаме

Уведомляет все приемники уведомлений, зарегистрированные с помощью держателя уведомления о том, что у элемента управления есть новый моникер.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Параметры

*парн*<br/>
Указатель на новый моникер элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Отправляет уведомление об изменении моникера для элемента управления.

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a>Ккомконтролбасе:: Сендонсаве

Уведомляет все приемники рекомендаций, зарегистрированные с помощью держателя уведомления о том, что элемент управления сохранен.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Отправляет уведомление о том, что элемент управления только что сохранил свои данные.

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a>Ккомконтролбасе:: Сендонвиевчанже

Уведомляет все зарегистрированные приемники уведомлений о том, что представление элемента управления изменилось.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Параметры

*дваспект*<br/>
Аспект или представление элемента управления.

*линдекс*<br/>
Часть представления, которое изменилось. Допустимо только-1.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

`SendOnViewChange`вызывает [иадвисесинк:: онвиевчанже](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange). Единственным значением параметра *Линдекс* , которое в настоящее время поддерживается, является-1, что означает, что все представление является интересным.

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a>Ккомконтролбасе:: Сетконтролфокус

Устанавливает или удаляет фокус клавиатуры в элементе управления или из него.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Параметры

*бграб*<br/>
Если значение — TRUE, устанавливает фокус клавиатуры на вызывающий элемент управления. Если значение равно FALSE, удаляет фокус клавиатуры из вызывающего элемента управления при условии, что он имеет фокус.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент управления успешно получает фокус; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Для оконного элемента управления вызывается функция [SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus) Windows API. Для элемента управления без окон вызывается [иолеинплацеситевиндовлесс:: SetFocus](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) . С помощью этого вызова элемент управления без окон получает фокус клавиатуры и может реагировать на сообщения окна.

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a>Ккомконтролбасе:: Сетдирти

Задает для элемента данных `m_bRequiresSave` значение в *бдирти*.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*бдирти*<br/>
Значение элемента данных [ккомконтролбасе:: m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Примечания

`SetDirty(TRUE)`следует вызывать, чтобы отметить, что элемент управления изменился со времени последнего сохранения. Значение `m_bRequiresSave` извлекается с помощью [ккомконтролбасе::](#getdirty)IsDirty.

## <a name="see-also"></a>См. также статью

[Класс Ккомконтрол](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
