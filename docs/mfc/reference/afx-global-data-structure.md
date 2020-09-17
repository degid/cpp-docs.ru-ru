---
title: AFX_GLOBAL_DATA - структура
ms.date: 11/04/2016
f1_keywords:
- AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::CleanUp
- AFXGLOBALS/AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawParentBackground
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawTextOnGlass
- AFXGLOBALS/AFX_GLOBAL_DATA::ExcludeTag
- AFXGLOBALS/AFX_GLOBAL_DATA::GetColor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetDirect2dFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetHandCursor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList3
- AFXGLOBALS/AFX_GLOBAL_DATA::GetNonClientMetrics
- AFXGLOBALS/AFX_GLOBAL_DATA::GetShellAutohideBars
- AFXGLOBALS/AFX_GLOBAL_DATA::GetTextHeight
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWICFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWriteFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::InitD2D
- AFXGLOBALS/AFX_GLOBAL_DATA::Is32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::IsDwmCompositionEnabled
- AFXGLOBALS/AFX_GLOBAL_DATA::IsHighContrastMode
- AFXGLOBALS/AFX_GLOBAL_DATA::OnSettingChange
- AFXGLOBALS/AFX_GLOBAL_DATA::RegisterWindowClass
- AFXGLOBALS/AFX_GLOBAL_DATA::ReleaseTaskBarRefs
- AFXGLOBALS/AFX_GLOBAL_DATA::Resume
- AFXGLOBALS/AFX_GLOBAL_DATA::SetLayeredAttrib
- AFXGLOBALS/AFX_GLOBAL_DATA::SetMenuFont
- AFXGLOBALS/AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateFonts
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateSysColors
- AFXGLOBALS/AFX_GLOBAL_DATA::EnableAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsWindows7
- AFXGLOBALS/AFX_GLOBAL_DATA::clrActiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::clrInactiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseSystemFont
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurHand
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretch
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretchVert
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hiconTool
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
ms.openlocfilehash: 0361d535a31526c5f7b79fdd4eab046dad0435cc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752875"
---
# <a name="afx_global_data-structure"></a>AFX_GLOBAL_DATA - структура

Структура `AFX_GLOBAL_DATA` содержит поля и методы, используемые для управления платформой или настройки внешнего вида и поведения приложения.

## <a name="syntax"></a>Синтаксис

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Создает структуру `AFX_GLOBAL_DATA` .|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[AFX_GLOBAL_DATA::CleanUp](#cleanup)|Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.|
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.|
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Рисует фон родительского объекта элемента управления в заданной области.|
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Рисует заданный текст в визуальном стиле указанной темы.|
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Удаляет заданную пару тегов XML из указанного буфера.|
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Получает текущий цвет из указанного элемента пользовательского интерфейса.|
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Получает указатель на интерфейс `ID2D1Factory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Извлекает стандартный курсор в виде руки, идентификатор которого равен `IDC_HAND`.|
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList.|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList3.|
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|Получает метрики, связанные с неклиентской областью несвернутого окна.|
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Определяет положения автоматически скрываемых панелей оболочки.|
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Получает высоту символов текста в текущем шрифте.|
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Получает указатель на интерфейс `IWICImagingFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Получает указатель на интерфейс `IDWriteFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|
|[AFX_GLOBAL_DATA::InitD2D](#initd2d)|Инициализирует фабрики `D2D`, `DirectWrite`и `WIC` . Данный метод следует вызывать до инициализации основного окна.|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Указывает, поддерживаются ли стандартные 32-разрядные значки.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Определяет, был ли инициализирован `D2D` .|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) Windows.|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Указывает, отображаются ли сейчас изображения с высокой контрастностью.|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Регистрирует указанный класс окна MFC.|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|Освобождает интерфейсы, полученные через методы GetITaskbarList и GetITaskbarList3.|
|[AFX_GLOBAL_DATA::Resume](#resume)|Повторно инициализирует внутренние указатели функции, которые обращаются к методам, поддерживающим [темы и стили оформления](/windows/win32/Controls/visual-styles-overview)Windows.|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) Windows.|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Создает указанный логический шрифт.|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Повторно инициализирует логические шрифты, используемые платформой.|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Включает или отключает поддержку Microsoft Active Accessibility. Active Accessibility предлагает надежные методы для предоставления информации об элементах пользовательского интерфейса.|
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Указывает, включена ли поддержка Microsoft Active Accessibility.|
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|Указывает, поддерживает ли операционная система многослойные окна.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Указывает, поддерживает ли текущая операционная система альфа-смешение.|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Указывает, выполняется ли приложение в ОС Windows 7 или более поздней версии.|
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Задает цвет градиента для активного заголовка. Обычно используется для закрепляемых панелей.|
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Задает цвет градиента для неактивного заголовка. Обычно используется для закрепляемых панелей.|
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.|
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|Сохраняет дескриптор курсора в виде ладони.|
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Сохраняет дескриптор для курсора растяжения по горизонтали.|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Сохраняет дескриптор для курсора растяжения по вертикали.|
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Сохраняет дескриптор для значка средства.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Указывает смещение от самой левой автоматически скрываемой панели инструментов до левой части панели стыковки.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Указывает интервал между автоматически скрываемыми панелями инструментов.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в закрепленном состоянии.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в плавающем состоянии.|

### <a name="remarks"></a>Примечания

Большинство данных в структуре `AFX_GLOBAL_DATA` инициализируется при запуске приложения.

### <a name="inheritance-hierarchy"></a>Иерархия наследования

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>Требования

**Заголовок:** afxglobals.h

## <a name="afx_global_databisosalphablendingsupport"></a><a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

Указывает, поддерживает ли операционная система альфа-смешивание.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Примечания

TRUE указывает на альфа-смешивание поддерживается; в противном случае, FALSE.

## <a name="afx_global_datacleanup"></a><a name="cleanup"></a>AFX_GLOBAL_DATA::Очистка

Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.

```cpp
void CleanUp();
```

## <a name="afx_global_datad2d1makerotatematrix"></a><a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1MakeRotateMatrix

Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>Параметры

*angle*<br/>
Угол поворота по часовой стрелке в градусах.

*Центр*<br/>
Точка, о которой вращаться.

*Матрица*<br/>
Когда этот метод возвращается, содержит новое преобразование вращения. Для этого параметра необходимо выделить хранилище.

### <a name="return-value"></a>Возвращаемое значение

Возвраты S_OK в случае успеха или значение ошибки в противном случае.

## <a name="afx_global_datadrawparentbackground"></a><a name="drawparentbackground"></a>AFX_GLOBAL_DATA::DrawParentBackground

Рисует фон родительского объекта элемента управления в заданной области.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на окно управления.

*pDC*<br/>
(в) Указатель на контекст устройства.

*lpRect*<br/>
(в) Указатель на прямоугольник, который граничит с областью для рисования. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="afx_global_datadrawtextonglass"></a><a name="drawtextonglass"></a>AFX_GLOBAL_DATA::DrawTextonGlass

Рисует заданный текст в визуальном стиле указанной темы.

```
BOOL DrawTextOnGlass(
    HTHEME hTheme,
    CDC* pDC,
    int iPartId,
    int iStateId,
    CString strText,
    CRect rect,
    DWORD dwFlags,
    int nGlowSize = 0,
    COLORREF clrText = (COLORREF)-1);
```

### <a name="parameters"></a>Параметры

*hТема*<br/>
(в) Обработка данных темы окна, или NULL. Платформа использует указанную тему для рисования текста, если этот параметр не является НУИЛ и темы поддерживаются. В противном случае платформа не использует тему для рисования текста.

Используйте метод [OpenThemeData](/windows/win32/api/uxtheme/nf-uxtheme-openthemedata) для создания HTHEME.

*pDC*<br/>
(в) Указатель на контекст устройства.

*iPartId*<br/>
(в) Контрольная часть, которая имеет желаемый вид текста. Дополнительные сведения см. в столбце "Части" в таблице [Части и состояния](/windows/win32/controls/parts-and-states). Если это значение равно 0, текст рисуется с помощью шрифта по умолчанию или шрифта, выбранного в контексте устройства.

*iStateId*<br/>
(в) Состояние управления, которое имеет желаемый вид текста. Дополнительные сведения см. в столбце "Состояния" в таблице [Части и состояния](/windows/win32/controls/parts-and-states).

*strText*<br/>
(в) Текст нарисовать.

*rect*<br/>
(в) Граница области, в которой нарисован указанный текст.

*dwFlags*<br/>
(в) Битовая комбинация (ИЛИ) флагов, определяющих порядок нарисования указанного текста.

Если параметр *hTheme* `NULL` или если темы не поддерживаются и не включены, параметр *nFormat* [метода CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) описывает действительные флаги. Если темы поддерживаются, параметр *dwFlags* метода [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) описывает действительные флаги.

*nGlowSize*<br/>
(в) Размер эффекта свечения, нарисованного на фоне перед рисованием указанного текста. Значение по умолчанию — 0.

*clrText*<br/>
(в) Цвет, в котором нарисован указанный текст. Значением по умолчанию является цвет по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если тема используется для рисования указанного текста; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Тема определяет визуальный стиль приложения. Тема не используется для рисования текста, если параметр *hTheme* является NULL, или если метод [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) не поддерживается, или если композиция [Desktop Window Manager](/windows/win32/dwm/dwm-overview) (DWM) отключена.

## <a name="afx_global_dataenableaccessibilitysupport"></a><a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA::EnableAccessibilitySupport

Включает или отключает поддержку Microsoft Active Accessibility.

```cpp
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для обеспечения поддержки доступности; FALSE для отторжать поддержку доступности. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Active Accessibility — это технология, основанная на COM, которая улучшает работу программ и операционной системы Windows вместе с вспомогательными технологическими продуктами. Он предоставляет надежные методы для раскрытия информации об элементах пользовательского интерфейса. Однако теперь доступна новая модель доступности под названием Microsoft UI Automation. Для сравнения двух технологий см. [UI Automation и Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).

Используйте [метод AFX_GLOBAL_DATA::IsAccessibilitySupport,](#isaccessibilitysupport) чтобы определить, включена ли поддержка активной доступности Майкрософт.

## <a name="afx_global_dataexcludetag"></a><a name="excludetag"></a>AFX_GLOBAL_DATA::ExcludeTag

Удаляет заданную пару тегов XML из указанного буфера.

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>Параметры

*strBuffer*<br/>
(в) Буфер текста.

*lpszTag*<br/>
(в) Название пары открытия и закрытия XML тегов.

*strTag*<br/>
(ваут) Когда этот метод возвращается, параметр *strTag* содержит текст, который находится между открытием и закрытием меток XML, которые названы параметром *lpszTag.* Любое ведущее или захудающее белое пространство обрезается из результата.

*bIsCharsList*<br/>
(в) TRUE для преобразования символов побега в параметре *strTag* в фактические символы побега; FALSE не выполнять преобразование. Значение по умолчанию FALSE. Дополнительные сведения см. в подразделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Пара тегов XML состоит из именованных тегов открытия и закрытия, указывающих начало и конец запуска текста в указанном буфере. Параметр *strBuffer* определяет буфер, а параметр *lpszTag* определяет название меток XML.

Используйте символы в следующей таблице, чтобы кодировать набор символов побега в указанном буфере. Укажите TRUE для параметра *bIsCharsList* для преобразования символов в *параметре strTag* в фактические символы побега. В следующей таблице используется [_T()](../../c-runtime-library/data-type-mappings.md) макрос для указания строк символа и избежания символов.

|Символ|Escape-символ|
|------------|----------------------|
|_T ("\\t")|_T ("t")|
|_T ("N")\\|_T ("N")|
|_T ("Зр")\\|_T ("Зр")|
|_T ("Б")\\|_T («Б»)|
|_T ("LT")|_T (")\<|
|_T ("GT")|_T (">")|
|_T ("AMP")|_T ("&")|

## <a name="afx_global_datagetcolor"></a><a name="getcolor"></a>AFX_GLOBAL_DATA::GetColor

Получает текущий цвет из указанного элемента пользовательского интерфейса.

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>Параметры

*nЦвет*<br/>
(в) Значение, опознавающее элемент пользовательского интерфейса, цвет которого извлекается. Список допустимых значений *nIndex* см. [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor)

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB указанного элемента пользовательского интерфейса. Дополнительные сведения см. в подразделе "Примечания".

### <a name="remarks"></a>Примечания

Если параметр *nColor* находится вне диапазона, значение возврата равно нулю. Поскольку ноль также является допустимое значениеR, вы не можете использовать этот метод, чтобы определить, поддерживается ли цвет системы текущей операционной системой. Вместо этого используйте метод [GetSysColorBrush,](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush) который возвращает NULL, если цвет не поддерживается.

## <a name="afx_global_datagetdirect2dfactory"></a><a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA::GetDirect2dFactory

Возвращает указатель на интерфейс ID2D1Factory, который хранится в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Factory, если создание фабрики удается, или NULL, если создание не удается или текущая оперативная система не имеют поддержки D2D.

## <a name="afx_global_datagethandcursor"></a><a name="gethandcursor"></a>AFX_GLOBAL_DATA::GetHandCursor

Извлекает предопределенный курсор, напоминающий руку и идентификатор которого находится IDC_HAND.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка ручного курсора.

## <a name="afx_global_datagetnonclientmetrics"></a><a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA:GetNonClientMetrics

Получает метрики, связанные с неклиентской областью несвернутого окна.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>Параметры

*Информация*<br/>
(в, вне) Структура [NONCLIENTMETRICS,](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw) содержащая масштабируемые метрики, связанные с областью неклиента неснимированного окна.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае, FALSE.

## <a name="afx_global_datagettextheight"></a><a name="gettextheight"></a>AFX_GLOBAL_DATA::GetTextHeight

Получает высоту символов текста в текущем шрифте.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*bHorz*<br/>
(в) TRUE для получения высоты символов, когда текст работает горизонтально; FALSE для получения высоты символов, когда текст работает вертикально. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Высота текущего шрифта, который измеряется от его восходящего до его спуска.

## <a name="afx_global_datagetwicfactory"></a><a name="getwicfactory"></a>AFX_GLOBAL_DATA::GetWICFactory

Возвращает указатель на интерфейс IWICImagingFactory, который хранится в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IWICImagingFactory, если создание фабрики удается, или NULL, если создание не удается или текущая система операции не имеют поддержки WIC.

## <a name="afx_global_datagetwritefactory"></a><a name="getwritefactory"></a>AFX_GLOBAL_DATA::GetWriteFactory

Возвращает указатель на интерфейс IDWriteFactory, который хранится в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteFactory, если создание фабрики удается, или NULL, если создание не удается или текущая система операции не имеют поддержки DirectWrite.

## <a name="afx_global_datainitd2d"></a><a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D

Инициализирует D2D, DirectWrite и WIC заводы. Данный метод следует вызывать до инициализации основного окна.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Параметры

*d2dFactoryType*<br/>
Модель резьбы фабрики D2D и ресурсы, которые она создает.

*writeFactoryType*<br/>
Значение, описавававальное ли объект фабрики записи, будет общим или изолированным

### <a name="return-value"></a>Возвращаемое значение

Возвращает правда, если заводы были intilalizrd, FALSE - в противном случае

## <a name="afx_global_datais32biticons"></a><a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32BitIcons

Указывает, поддерживаются ли стандартные 32-разрядные значки.

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если поддерживаются предопределенные 32-битные значки; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает TRUE, если фреймворк поддерживает 32-разрядные встроенные значки, и если операционная система поддерживает 16 битов на пиксель или более, и если изображения не отображаются с высоким контрастом.

## <a name="afx_global_dataisaccessibilitysupport"></a><a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA::IsAccessibilitySupport

Указывает, включена ли поддержка Microsoft Active Accessibility.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если поддержка доступности включена; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Microsoft Active Accessibility была более ранним решением для обеспечения доступности приложений. Microsoft UI Automation — это новая модель доступности для Microsoft Windows, предназначенная для удовлетворения потребностей вспомогательных технологических продуктов и автоматизированных инструментов тестирования.

Используйте [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) метод для включения или отключить поддержку Active Accessibility.

## <a name="afx_global_dataisd2dinitialized"></a><a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2D Initialized

Определяет, был ли D2D инициализирован

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если D2D был инициализирован; в противном случае FALSE.

## <a name="afx_global_dataisdwmcompositionenabled"></a><a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA::IsDwmComposition

Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) Windows.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если включена композиция [Desktop Window Manager](/windows/win32/dwm/dwm-overview) (DWM); в противном случае, FALSE.

## <a name="afx_global_dataishighcontrastmode"></a><a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA::IsHighContrastMode

Указывает, отображаются ли сейчас изображения с высокой контрастностью.

```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если изображения в настоящее время отображаются в черном или белом режиме высокой контрастности; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

В режиме черного высокого контраста края, обращенные к свету, белые, а фон черный. В белом режиме высокой контрастности края, обращенные к свету, черные, а фон белый.

## <a name="afx_global_dataiswindowslayersupportavailable"></a><a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA::IsWindowsLayerПоддержкаДоступна

Указывает, поддерживает ли операционная система многослойные окна.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если слоистые окна поддерживаются; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Если слоистые окна поддерживаются, умные маркеры *стыковки* используют многослойные окна.

## <a name="afx_global_datam_busebuiltin32biticons"></a><a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Примечания

TRUE указывает, что в фреймворке используются 32-битные цветные иконки; FALSE указывает значки с более низким разрешением. Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член к TRUE.

Этот участник должен быть настроен при запуске приложения.

## <a name="afx_global_datam_busesystemfont"></a><a name="m_busesystemfont"></a>AFX_GLOBAL_DATA::m_bUseSystemFont

Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Примечания

TRUE указывает на использование системного шрифта; в противном случае, FALSE. Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член на FALSE.

Тестирование этого участника — не единственный способ для платформы определить шрифт для использования. Метод `AFX_GLOBAL_DATA::UpdateFonts` также тестирует по умолчанию и альтернативные шрифты, чтобы определить, какие визуальные стили доступны для применения к меню, панели инструментов и ленты.

## <a name="afx_global_datam_hcurhand"></a><a name="m_hcurhand"></a>AFX_GLOBAL_DATA::m_hcurHand

Сохраняет дескриптор курсора в виде ладони.

```
HCURSOR m_hcurHand;
```

## <a name="afx_global_datam_hcurstretch"></a><a name="m_hcurstretch"></a>AFX_GLOBAL_DATA::m_hcurStretch

Сохраняет дескриптор для курсора растяжения по горизонтали.

```
HCURSOR m_hcurStretch;
```

## <a name="afx_global_datam_hcurstretchvert"></a><a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA::m_hcurStretchVert

Сохраняет дескриптор для курсора растяжения по вертикали.

```
HCURSOR m_hcurStretchVert;
```

## <a name="afx_global_datam_hicontool"></a><a name="m_hicontool"></a>AFX_GLOBAL_DATA::m_hiconTool

Сохраняет дескриптор для значка средства.

```
HICON m_hiconTool;
```

## <a name="afx_global_datam_nautohidetoolbarmargin"></a><a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin

Определяет смещение от левой панели инструментов автохидов к левой стороне док-бара.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Примечания

Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член до 4 пикселей.

## <a name="afx_global_datam_nautohidetoolbarspacing"></a><a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

Указывает интервал между автоматически скрываемыми панелями инструментов.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Примечания

Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член до 14 пикселей.

## <a name="afx_global_datam_ndragframethicknessdock"></a><a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Определяет толщину рамы перетаскивания, которая используется для обозначения пристыкованного состояния.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Примечания

Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член до 3 пикселей.

## <a name="afx_global_datam_ndragframethicknessfloat"></a><a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

Определяет толщину рамы перетаскивания, которая используется для обозначения плавающего состояния.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Примечания

Конструктор `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` инициализирует этот член до 4 пикселей.

## <a name="afx_global_dataonsettingchange"></a><a name="onsettingchange"></a>AFX_GLOBAL_DATA::OnsettingChange

Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.

```cpp
void OnSettingChange();
```

### <a name="remarks"></a>Примечания

Этот метод устанавливает переменные фреймворка в состояние определенных атрибутов рабочего стола пользователя. Этот метод определяет текущее состояние анимации меню, увядания меню и функции автохидов панели задач.

## <a name="afx_global_dataregisterwindowclass"></a><a name="registerwindowclass"></a>AFX_GLOBAL_DATA:RegisterWindowClass

Регистрирует указанный класс окна MFC.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>Параметры

*lpszClassNamePrefix*<br/>
(в) Название класса окон для регистрации.

### <a name="return-value"></a>Возвращаемое значение

Квалифицированное название зарегистрированного класса, если этот метод удается; в противном случае [исключение ресурса](exception-processing.md#afxthrowresourceexception).

### <a name="remarks"></a>Примечания

Значение возврата представляет собой список параметра *lpszClassNamePrefix* и гексадецимного текстовых представления дейков текущего экземпляра приложения; курсор приложения, который является курсором стрелки, идентификатор которого является IDC_ARROW; и фоновая кисть. Для получения дополнительной информации о регистрации классов окон MFC [см.](../../mfc/reference/application-information-and-management.md#afxregisterclass)

## <a name="afx_global_dataresume"></a><a name="resume"></a>AFX_GLOBAL_DATA::Resume

Повторно инициализирует внутренние указатели функции, которые обращаются к методам, поддерживающим темы и стили оформления Windows.

```
BOOL Resume();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае, FALSE. В режиме отладки этот метод утверждает, что этот метод не удался.

### <a name="remarks"></a>Примечания

Этот метод вызывается, когда фреймворк получает [WM_POWERBROADCAST](/windows/win32/Power/wm-powerbroadcast) сообщение.

## <a name="afx_global_datasetlayeredattrib"></a><a name="setlayeredattrib"></a>AFX_GLOBAL_DATA::SetlayeredAttrib

Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) Windows.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к многослойной окне.

*crKey*<br/>
(в) Ключ цвета прозрачности, который используется [диспетчером окна рабочего стола](/windows/win32/dwm/dwm-overview) для составления многослойного окна.

*bAlpha*<br/>
(в) Альфа-значение, используемое для описания непрозрачности многослойного окна.

*dwFlags*<br/>
(в) Битовая комбинация (ИЛИ) флагов, определяющих параметры какого метода для использования. Укажите LWA_COLORKEY использовать параметр *crKey* в качестве цвета прозрачности. Укажите LWA_ALPHA использовать параметр *bAlpha* для определения непрозрачности многослойного окна.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае, FALSE.

## <a name="afx_global_datasetmenufont"></a><a name="setmenufont"></a>AFX_GLOBAL_DATA::SetMenuFont

Создает указанный логический шрифт.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
(в) Указатель на структуру, содержащую атрибуты шрифта.

*bHorz*<br/>
(в) TRUE указать, что текст работает горизонтально; FALSE указать, что текст работает вертикально.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае, FALSE. В режиме отладки этот метод утверждает, что этот метод не удался.

### <a name="remarks"></a>Примечания

Этот метод создает горизонтальный обычный шрифт, подчеркнутый шрифт и жирный шрифт, который используется в элементах меню по умолчанию. Этот метод дополнительно создает обычный вертикальный шрифт. Для получения дополнительной информации о логических шрифтов, [см. CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).

## <a name="afx_global_dataupdatefonts"></a><a name="updatefonts"></a>AFX_GLOBAL_DATA:UpdateФоны

Повторно инициализирует логические шрифты, используемые платформой.

```cpp
void UpdateFonts();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации `CFont::CreateFontIndirect`о логических шрифтов, см.

## <a name="afx_global_dataupdatesyscolors"></a><a name="updatesyscolors"></a>AFX_GLOBAL_DATA:UpdateSysColors

Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.

```cpp
void UpdateSysColors();
```

## <a name="afx_global_databiswindows7"></a><a name="biswindows7"></a>AFX_GLOBAL_DATA::bIsWindows7

Указывает, выполняется ли приложение под Windows 7 или выше.

```
BOOL bIsWindows7;
```

## <a name="afx_global_dataclractivecaptiongradient"></a><a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA:clrActiveCaptionGradient

Определяет градиентный цвет активного заголовка. Обычно используется для закрепляемых панелей.

```
COLORREF clrActiveCaptionGradient;
```

## <a name="afx_global_dataclrinactivecaptiongradient"></a><a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA:clrInactivecaptionGradient

Определяет градиентный цвет неактивной подписи. Обычно используется для закрепляемых панелей.

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="afx_global_datagetitaskbarlist"></a><a name="getitaskbarlist"></a>AFX_GLOBAL_DATA:GetITaskbarList

Создает и хранит в глобальных данных указатель на `ITaskBarList` интерфейс.

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `ITaskbarList` интерфейс, если создание объекта списка панели задач удается; NULL, если создание не удается или если текущая система операции меньше, чем Windows 7.

## <a name="afx_global_datagetitaskbarlist3"></a><a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA:GetITaskbarList3

Создает и хранит в глобальных данных указатель на `ITaskBarList3` интерфейс.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `ITaskbarList3` интерфейс, если создание объекта списка панели задач удается; NULL, если создание не удается или если текущая система операции меньше, чем Windows 7.

## <a name="afx_global_datagetshellautohidebars"></a><a name="getshellautohidebars"></a>AFX_GLOBAL_DATA::GetShellAutohideBars

Определяет положения автоматически скрываемых панелей оболочки.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Возвращаемое значение

Значение с закодированными флагами, указывающими позиции баров автоматического укрытия. Он может сочетать в себе следующие значения: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.

## <a name="afx_global_datareleasetaskbarrefs"></a><a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA::ReleaseTaskBarRefs

Выпускает интерфейсы, полученные с помощью `GetITaskbarList` и `GetITaskbarList3` методы.

```cpp
void ReleaseTaskBarRefs();
```

## <a name="afx_global_datashellcreateitemfromparsingname"></a><a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA::ShellCreateItemFromParsingName

Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
(в) Указатель на имя дисплея.

*Pbc*<br/>
Указатель на контекст связывания, который контролирует операцию разбора.

*riid*<br/>
Ссылка на идентификатор интерфейса.

*Ppv*<br/>
(ваут) Когда эта функция возвращается, содержит указатель интерфейса, запрошенный в *riid*. Это, как `IShellItem` `IShellItem2`правило, или .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха; значение ошибки в противном случае.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../hierarchy-chart.md)<br/>
[Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Части и состояния](/windows/win32/controls/parts-and-states)<br/>
[CDC::DrawText](cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[диспетчера окон рабочего стола](/windows/win32/dwm/dwm-overview)<br/>
[Включение и контроль композиции DWM](/windows/win32/dwm/composition-ovw)<br/>
[Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[Функция GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor)<br/>
[GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[Структура NONCLIENTMETRICS](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)
