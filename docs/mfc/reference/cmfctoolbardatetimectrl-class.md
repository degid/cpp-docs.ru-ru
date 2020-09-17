---
title: Класс CMFCToolBarDateTimeCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: 9aebd55f19a6687554d8d8378ef84ed5932025a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372180"
---
# <a name="cmfctoolbardatetimectrl-class"></a>Класс CMFCToolBarDateTimeCtrl

Кнопка панели инструментов, содержащая управление сборщиком даты и времени.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Формирует объект `CMFCToolBarDateTimeCtrl`.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Уточняется, может ли пользователь растягивать кнопку во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl:CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов на текущую кнопку. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Зарезервировано для последующего использования.|
|[CMFCToolBarButton::ExporttoMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Копирует текст из кнопки панели инструментов в меню.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCToolBarDateTimeCtrl:GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении с указанным идентификатором команды.|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Возвращает указатель на контроль насборщика даты и времени.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Извлекает ручку окна, связанную с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Получает выбранное время от управления сборщиком даты и времени и помещает его в указанную структуру [SYSTEMTIME.](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Возвращает выбранное время из кнопки управления сборщиком времени с указанным идентификатором команды.|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Определяет, отображается ли граница кнопки при выборе кнопки пользователем. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl:NotifyCommand](#notifycommand)|Уточняется, обрабатывает ли кнопка [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddTo CustomizePage](#onaddtocustomizepage)|Вызывается по фреймворку при добавлении кнопки в поле **настраиваемых** диалогов. (Переопределяет [CMFCToolBarButton::OnAddTo CustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Вызывается фреймворком для расчета размера кнопки для заданного контекста устройства и состояния стыковки. (Переопределяет [CMFCToolBarButton::OncalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Вызывается по системе, когда пользователь нажимает на элемент управления. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl:OnCtlColor](#onctlcolor)|Вызывается по системе, когда панель родительских инструментов обрабатывает WM_CTLCOLOR сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Вызывается в рамках, чтобы нарисовать кнопку с помощью указанных стилей и опций. (Переопределяет [CMFCToolBarButton::Ondraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Вызывается фреймворком, чтобы нарисовать кнопку в панели **команд** в поле **настраивания** диалогов. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается рамками, когда глобальный шрифт изменился. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Вызывается по фреймворку при движении родительской панели инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl:OnShow](#onshow)|Вызывается по фрейму, когда кнопка становится видимой или невидимой. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Вызывается в фреймворке, когда панель родительских инструментов изменяет свой размер или положение, и это изменение приводит к изменению размера кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Вызывается по фреймворку, когда панель родительских инструментов обновляет свой текст инструментария. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Читает этот объект из архива или пишет его в архив,( Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Устанавливает стиль кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl:SetTime](#settime)|Устанавливает время и дату управления сборщиком времени.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Устанавливает время и дату во всех случаях управления сборщиком времени, которые имеют определенный идентификатор команды.|

## <a name="remarks"></a>Примечания

Например, как использовать управление сборщиком дат и времени, см. Для получения информации о том, как добавить кнопки управления в панели инструментов, [см.](../../mfc/walkthrough-putting-controls-on-toolbars.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbardatetimectrl.h

## <a name="cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched

Уточняется, может ли пользователь растягивать кнопку во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает TRUE.

### <a name="remarks"></a>Примечания

По умолчанию фреймворк не позволяет пользователю растягивать кнопку панели инструментов во время настройки. Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растягивать кнопку панели инструментов даты и времени во время настройки.

## <a name="cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl

Создает и инициализирует объект [CMFCToolBarDateTimeCtrl.](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор управления.

*iImage*<br/>
(в) Индекс изображения в `CMFCToolBarImages` объекте панели инструментов.

*dwStyle*<br/>
(в) Стиль `CMFCToolBarDateTimeCtrlImpl` окна, который создается, когда пользователь нажимает на кнопку.

*iWidth*<br/>
(в) Ширина элемента управления, в пикселях.

### <a name="remarks"></a>Примечания

Этот объект инициализирован к дате и времени системы. Стиль окна внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта включает в себя параметр *dwStyle* и WS_CHILD и WS_VISIBLE стили. Вы не можете изменить `CMFCToolBarDateTimeCtrl::SetStyle`эти стили с помощью . Используйте `SetStyle` для изменения `CMFCToolBarDateTimeCtrl` стиля управления.

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCToolBarDateTimeCtrl` построить объект класса. Этот фрагмент кода является частью [образца времени выборки тайма панели инструментов.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

## <a name="cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>CMFCToolBarDateTimeCtrl:CopyFrom

Копирует свойства другой кнопки панели инструментов на текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Ссылка на кнопку исходного кода, из которой можно скопировать.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен быть `CMFCToolBarDateTimeCtrl`типа .

## <a name="cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolbarDateTimectrl::ExporttoMenuButton

Копирует текст из кнопки панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*менюButton*<br/>
(в) Ссылка на кнопку целевого меню.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает TRUE.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) путем загрузки ресурса строки, связанного с идентификатором команды управления. Для получения дополнительной информации о строке ресурсов, [см. Cstringt:LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

## <a name="cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>CMFCToolBarDateTimeCtrl:GetByCmd

Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении с указанным идентификатором команды.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды кнопки для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarDateTimeCtrl` объект в приложении, который имеет указанный `CMFCToolBarDateTimeCtrl` идентификатор команды, или NULL, если у объектов нет указанного идентификатора команды.

### <a name="remarks"></a>Примечания

Этот общий метод утилиты используется такими методами, как [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) и [CMFCToolBarDateTimeCtrl::GetTimeAll,](#gettimeall) чтобы установить или получить время и дату всех экземпляров управления сборщиком времени, которые имеют указанный идентификатор команды.

## <a name="cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

Возвращает указатель на контроль насборщика даты и времени.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дату и время управления сборщика; или NULL, если элемент управления не существует.

### <a name="remarks"></a>Примечания

Класс `CMFCToolBarDateTimeCtrl` инициализирует член `m_pWndDateTime` данных `CMFCToolBarDateTimeCtrl` при вставке объекта в панель инструментов.

## <a name="cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd

Извлекает ручку окна, связанную с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка окна, связанная с кнопкой панели инструментов даты и времени.

### <a name="remarks"></a>Примечания

Этот метод перекрывает [метод CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод.

## <a name="cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime

Получает выбранное время от связанного управления сборщиком даты и времени и помещает его в указанную структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Параметры

*timeDest*<br/>
(ваут) В первой перегрузке объект [класса COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) который будет получать информацию о времени системы. Во второй перегрузке объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) который будет получать информацию о времени системы.

*pTimeDest*<br/>
(ваут) Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения информации о времени системы. Не должно быть NULL.

### <a name="return-value"></a>Возвращаемое значение

При первой перегрузке, ненулевой, если время успешно записано на объект [класса COleDateTime;](../../atl-mfc-shared/reference/coledatetime-class.md) в противном случае 0. Во втором и третьем перегрузках значение возврата является DWORD, равным члену dwFlag, установленного в структуре [NMDATETIMECHANGE.](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange)

### <a name="remarks"></a>Примечания

Метод устанавливает член dwFlags структуры [nMDATETIME,](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) чтобы указать, устанавливается ли дата и время сборщика на дату и время. Если значение равняется GDT_NONE, элемент `no date` управления устанавливается в статус и использует DTS_SHOWNONE стиле. Если возврат номинал равняется GDT_VALID, время системы успешно хранится в месте назначения.

## <a name="cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll

Возвращает время, выбранное пользователем, из кнопки управления тайм-сборщиком с указанным идентификатором команды.

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Упоньте идентификатор команды кнопки панели инструментов.

*timeDest*<br/>
(ваут) В первой перегрузке объект [класса COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) который будет получать информацию о времени системы. Во второй перегрузке объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) который будет получать информацию о времени системы.

*pTimeDest*<br/>
(ваут) Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения информации о времени системы. Не должно быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Если фреймворк не может найти кнопку панели инструментов, которая соответствует *iiCmd*команды, значение возврата равняется нулю в первой перегрузке, а GDT_NONE в других перегрузках. При обнаружении кнопки панели инструментов значение возврата такое же, как и значение возврата от вызова к [CMFCToolBarDateTimeCtrl::GetTime](#gettime) на этой кнопке. При обнаружении кнопки может произойти значение возврата нуля или `GetTime` GDT_NONE, что указывает на то, что вызов не вернул действительную дату по какой-либо другой причине.

### <a name="remarks"></a>Примечания

Этот метод ищет кнопку панели инструментов с указанным идентификатором команды и вызывает [CMFCToolBarDateTimeCtrl::GetTime](#gettime) метод на этой кнопке.

## <a name="cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder

Определяет, отображается ли граница кнопки при выборе кнопки пользователем.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка отображает свою границу при выборе; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает ненулевое значение, если элемент управления виден.

## <a name="cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarDateTimeCtrl:NotifyCommand

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

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::NotifyCommand)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)путем обработки [уведомления DTN_DATETIMECHANGE.](/windows/win32/Controls/dtn-datetimechange) Он обновляет внутренний статус времени и `CMFCToolBarDateTimeCtrl` обновляет временное свойство всех объектов с одинаковым идентификатором команды.

## <a name="cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddTo CustomizePage

Вызывается по фреймворку при добавлении кнопки в поле **настраиваемых** диалогов.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), путем копирования свойств с первого дня и времени управления в любой панели инструментов, которая имеет тот же идентификатор команды, как этот объект. Этот метод ничего не делает, если ни одна панель инструментов не имеет управления датой и временем, который имеет тот же идентификатор команды, что и этот объект.

Для получения дополнительной информации о **настраиваемый** диалоговый ящик, [см.](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)

## <a name="cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd

Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::OnChangeParentWnd)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)путем воссоздания внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

## <a name="cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick

Вызывается по системе, когда пользователь нажимает на элемент управления.

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

Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnClick,](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)вернув `CMFCToolBarDateTimeCtrlImpl` ненулевое значение, если внутренний объект виден.

## <a name="cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl:OnCtlColor

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

Ручка к глобальной кисти, которую используется фреймворком для нарисования фона кнопки.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), установив текст и фоновые цвета предоставленного контекста устройства на глобальный текст и фоновые цвета, соответственно.

Для получения дополнительной информации о глобальных опциях, доступных для вашего приложения, с [AFX_GLOBAL_DATAм.](../../mfc/reference/afx-global-data-structure.md)

## <a name="cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged

Вызывается рамками, когда глобальный шрифт изменился.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта управления на глобальный шрифт.

Для получения дополнительной информации о глобальных опциях, доступных для вашего приложения, с [AFX_GLOBAL_DATAм.](../../mfc/reference/afx-global-data-structure.md)

## <a name="cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove

Вызывается по фреймворку при движении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию [(CMFCToolBarButton::OnMove)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)путем обновления положения внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

## <a name="cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>CMFCToolBarDateTimeCtrl:OnShow

Вызывается по фрейму, когда кнопка становится видимой или невидимой.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) Определяет, видна ли кнопка. Если этот параметр является правдой, кнопка видна. В противном случае кнопка не видна.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) путем отображения кнопки, если *bShow* является правдой. В противном случае этот метод скрывает кнопку.

## <a name="cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>CMFCToolBarDateTimeCtrl:OnSize

Вызывается в фреймворке, когда панель родительских инструментов изменяет свой размер или положение, и это изменение приводит к изменению размера кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*iSize*<br/>
(в) Новая ширина кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию [(CMFCToolBarButton::OnSize)](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)путем обновления размера и положения внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

## <a name="cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip

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
(в) Родительское окно.

*iButtonIndex*<br/>
(в) Индекс кнопки с нулевым уровнем в коллекции родительских кнопок.

*wndToolTip*<br/>
(в) Элемент управления, отображаемого текстом tooltip.

*Ул*<br/>
(ваут) Объект, `CString` который получает обновленный текст tooltip.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод обновляет текст инструментария; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) путем отображения текста инструментария, который связан с кнопкой. Если кнопка не пристыкована горизонтально, этот метод ничего не делает и возвращает FALSE.

## <a name="cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>CMFCToolBarDateTimeCtrl:SetTime

Устанавливает время и дату управления сборщиком времени.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Параметры

*времяНовые*<br/>
(в) В первой версии ссылка на объект [класса COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий время, к которому будет установлен элемент управления. Во второй версии указатель на объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий время, к которому будет установлен элемент управления.

*pTimeNew*<br/>
(в) Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую время, к которому будет установлен элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Устанавливает время в контроле сборщика даты и времени, позвонив [в CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).

## <a name="cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll

Устанавливает время и дату во всех случаях управления сборщиком времени, которые имеют определенный идентификатор команды.

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Упоньте идентификатор команды кнопки панели инструментов.

*времяНовые*<br/>
(в) В первой версии объект [класса COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий время, к которому будет установлен элемент управления. Во второй версии указатель на объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий время, к которому будет установлен элемент управления.

*pTimeNew*<br/>
(в) Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую время, к которому будет установлен элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Ищет кнопку панели инструментов с указанным идентификатором команды и устанавливает время в управлении сборщиком даты и времени, позвонив [по телефону CMFCToolBarDateTimeCtrl::SetTime](#settime).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
