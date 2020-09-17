---
title: Класс Кпажесетупдиалог
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 280d75c3bcacd673107fd32ecaa39953b06a77c8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214078"
---
# <a name="cpagesetupdialog-class"></a>Класс Кпажесетупдиалог

Инкапсулирует службы, предоставляемые стандартным диалоговым окном OLE "Параметры страницы" Windows с дополнительной поддержкой установки и изменения полей печати.

## <a name="syntax"></a>Синтаксис

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кпажесетупдиалог:: Кпажесетупдиалог](#cpagesetupdialog)|Формирует объект `CPageSetupDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кпажесетупдиалог:: Креатепринтердк](#createprinterdc)|Создает контекст устройства для печати.|
|[Кпажесетупдиалог::D Омодал](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[Кпажесетупдиалог:: Жетдевиценаме](#getdevicename)|Возвращает имя устройства принтера.|
|[Кпажесетупдиалог::](#getdevmode)|Возвращает текущий DEVMODE принтера.|
|[Кпажесетупдиалог:: GetDriverName](#getdrivername)|Возвращает драйвер, используемый принтером.|
|[Поля Кпажесетупдиалог:: Margin](#getmargins)|Возвращает текущие настройки полей принтера.|
|[Кпажесетупдиалог:: Жетпаперсизе](#getpapersize)|Возвращает размер бумаги принтера.|
|[Кпажесетупдиалог:: Жетпортнаме](#getportname)|Возвращает имя выходного порта.|
|[Кпажесетупдиалог:: Ондравпаже](#ondrawpage)|Вызывается платформой для отрисовки экранного изображения печатной страницы.|
|[Кпажесетупдиалог::P Редравпаже](#predrawpage)|Вызывается структурой перед отрисовкой экранного изображения печатной страницы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кпажесетупдиалог:: m_psd](#m_psd)|Структура, используемая для настройки `CPageSetupDialog` объекта.|

## <a name="remarks"></a>Примечания

Этот класс предназначен для размещения диалогового окна «Настройка печати».

Чтобы использовать `CPageSetupDialog` объект, сначала создайте объект с помощью `CPageSetupDialog` конструктора. После создания диалогового окна можно задать или изменить любые значения в `m_psd` элементе данных, чтобы инициализировать значения элементов управления диалогового окна. Структура [m_psd](#m_psd) имеет тип пажесетупдлг.

После инициализации элементов управления диалогового окна вызовите `DoModal` функцию члена, чтобы открыть диалоговое окно и позволить пользователю выбрать параметры печати. `DoModal`Возвращает значение, указывающее, выбрал пользователь кнопку ОК (ИДОК) или Отмена (ИДКАНЦЕЛ).

Если `DoModal` ВОЗВРАЩАЕТ идок, можно использовать несколько `CPageSetupDialog` функций члена или получить доступ к `m_psd` элементу данных, чтобы получить данные, введенные пользователем.

> [!NOTE]
> После закрытия диалогового окна «Общие параметры OLE-страницы» все изменения, внесенные пользователем, не будут сохранены платформой. Приложение может сохранить любые значения из этого диалогового окна в постоянное расположение, например член приложения или класса приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс.h

## <a name="cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>Кпажесетупдиалог:: Кпажесетупдиалог

Вызовите эту функцию для создания `CPageSetupDialog` объекта.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна. Значения можно комбинировать с помощью оператора побитового или. Данные величины имеют следующие значения:

- PSD_DEFAULTMINMARGINS устанавливает минимально допустимую ширину полей страницы в соответствии с минимальными размерами принтера. Этот флаг пропускается, если также указаны флаги PSD_MARGINS и PSD_MINMARGINS.

- PSD_INWININIINTLMEASURE не реализована.

- PSD_MINMARGINS заставляет систему использовать значения, указанные в элементе, `rtMinMargin` как минимально допустимую ширину для левого, верхнего, правого и нижнего полей. Система не дает пользователю вводить ширину, которая меньше указанного минимума. Если параметр PSD_MINMARGINS не указан, система устанавливает минимально допустимую ширину, разрешенную принтером.

- PSD_MARGINS активирует область элементов управления поля.

- PSD_INTHOUSANDTHSOFINCHES приводит к тому, что единицы измерения диалогового окна измеряются в 1/1000 дюйма.

- PSD_INHUNDREDTHSOFMILLIMETERS приводит к тому, что единицы измерения диалогового окна измеряются в 1/100 миллиметра.

- PSD_DISABLEMARGINS отключает элементы управления диалогового окна «поле».

- PSD_DISABLEPRINTER отключает кнопку "принтер".

- PSD_NOWARNING предотвращает отображение предупреждающего сообщения при отсутствии принтера по умолчанию.

- PSD_DISABLEORIENTATION отключает элемент управления диалогового окна «ориентация страницы».

- PSD_RETURNDEFAULT приводит `CPageSetupDialog` к возврату структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) , инициализированных для принтера системы по умолчанию без отображения диалогового окна. Предполагается, что оба `hDevNames` `hDevMode` аргумента и имеют значение null. в противном случае функция возвращает ошибку. Если системный принтер по умолчанию поддерживается старым драйвером принтера (версия до Windows 3,0), то возвращается только `hDevNames` `hDevMode` значение null.

- PSD_DISABLEPAPER отключает элемент управления "Выбор бумаги".

- PSD_SHOWHELP заставляет диалоговое окно отображать кнопку «Справка». `hwndOwner`Если указан этот флаг, член не должен иметь значение null.

- PSD_ENABLEPAGESETUPHOOK включает функцию-обработчик, указанную в `lpfnSetupHook` .

- PSD_ENABLEPAGESETUPTEMPLATE заставляет операционную систему создать диалоговое окно, используя диалоговое окно шаблон диалогового окна, определяемое `hInstance` и `lpSetupTemplateName` .

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE указывает, что `hInstance` определяет блок данных, содержащий предварительно загруженный шаблон диалогового окна. Система не учитывает, `lpSetupTemplateName` Если указан этот флаг.

- PSD_ENABLEPAGEPAINTHOOK включает функцию-обработчик, указанную в `lpfnPagePaintHook` .

- PSD_DISABLEPAGEPAINTING отключает область рисования диалогового окна.

*ппарентвнд*<br/>
Указатель на родительский элемент или владелец диалогового окна.

### <a name="remarks"></a>Примечания

Используйте функцию [DoModal](../../mfc/reference/cdialog-class.md#domodal) для вывода диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

## <a name="cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>Кпажесетупдиалог:: Креатепринтердк

Создает контекст печатающего устройства из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) .

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработайте только что созданный контекст устройства печати (DC).

## <a name="cpagesetupdialogdomodal"></a><a name="domodal"></a>Кпажесетупдиалог::D Омодал

Эта функция вызывается для отображения диалогового окна Общие параметры OLE страницы Windows и позволяет пользователю выбирать различные параметры печати, такие как поля печати, размер и ориентация бумаги, а также конечный принтер.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

ИДОК или ИДКАНЦЕЛ. Если возвращается ИДКАНЦЕЛ, вызовите функцию Windows [коммдлжекстендедеррор](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) , чтобы определить, произошла ли ошибка.

ИДОК и ИДКАНЦЕЛ — это константы, которые указывают, выбрал ли пользователь кнопку ОК или Отмена.

### <a name="remarks"></a>Примечания

Кроме того, пользователь может получить доступ к параметрам установки принтера, таким как сетевое расположение и свойства, относящиеся к выбранному принтеру.

Если требуется инициализировать различные параметры диалогового окна настройки страницы путем установки элементов `m_psd` структуры, следует сделать это перед вызовом `DoModal` и после создания объекта диалогового окна. После вызова `DoModal` вызовите другие функции члена для получения параметров или данных, вводимых пользователем, в диалоговое окно.

Если вы хотите распространить текущие параметры, введенные пользователем, выполните вызов метода [CWinApp:: селектпринтер](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция принимает сведения из `CPageSetupDialog` объекта и инициализирует и выбирает новый контроллер домена с правильными атрибутами.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Пример

  См. пример для [кпажесетупдиалог:: кпажесетупдиалог](#cpagesetupdialog).

## <a name="cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>Кпажесетупдиалог:: Жетдевиценаме

Вызовите эту функцию после, `DoModal` чтобы получить имя текущего выбранного принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя устройства, используемое `CPageSetupDialog` объектом.

## <a name="cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>Кпажесетупдиалог::

Вызовите эту функцию после вызова `DoModal` , чтобы получить сведения о контексте устройства печати `CPageSetupDialog` объекта.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , которая содержит сведения об инициализации устройства и среде драйвера печати. Необходимо разблокировать память, занятую этой структурой, с помощью функции Windows [глобалунлокк](/windows/win32/api/winbase/nf-winbase-globalunlock) , которая описана в Windows SDK.

## <a name="cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>Кпажесетупдиалог:: GetDriverName

Вызовите эту функцию после вызова [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) , чтобы получить имя драйвера принтера, определенного системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа, `CString` указывающее имя драйвера, определяемое системой.

### <a name="remarks"></a>Примечания

Используйте указатель на `CString` объект, возвращаемый в `GetDriverName` качестве значения `lpszDriverName` в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

## <a name="cpagesetupdialoggetmargins"></a><a name="getmargins"></a>Поля Кпажесетупдиалог:: Margin

Вызовите эту функцию после вызова метода, `DoModal` чтобы получить поля драйвера печатающего устройства.

```cpp
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Параметры

*лпректмаргинс*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) , описывающий поля печати для текущего выбранного принтера (в 1/1000 дюймах или 1/100 мм). Если вы не заинтересованы в этом прямоугольнике, передайте значение NULL для этого параметра.

*лпректминмаргинс*<br/>
Указатель на `RECT` структуру или `CRect` объект, описывающие минимальное поле печати для выбранного принтера (в 1/1000 дюймах или 1/100 мм). Если вы не заинтересованы в этом прямоугольнике, передайте значение NULL для этого параметра.

## <a name="cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>Кпажесетупдиалог:: Жетпаперсизе

Вызовите эту функцию, чтобы получить размер бумаги, выбранной для печати.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) , содержащий размер бумаги (в 1/1000 дюймах или 1/100 мм), выбранный для печати.

## <a name="cpagesetupdialoggetportname"></a><a name="getportname"></a>Кпажесетупдиалог:: Жетпортнаме

Вызовите эту функцию после вызова, `DoModal` чтобы получить имя текущего выбранного порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент порта принтера.

## <a name="cpagesetupdialogm_psd"></a><a name="m_psd"></a>Кпажесетупдиалог:: m_psd

Структура типа ПАЖЕСЕТУПДЛГ, члены которой хранят характеристики объекта диалогового окна.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Примечания

После создания `CPageSetupDialog` объекта можно использовать `m_psd` для установки различных аспектов диалогового окна перед вызовом `DoModal` функции-члена.

При `m_psd` непосредственном изменении элемента данных будет переопределено поведение по умолчанию.

Дополнительные сведения о структуре [пажесетупдлг](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw) см. в Windows SDK.

См. пример для [кпажесетупдиалог:: кпажесетупдиалог](#cpagesetupdialog).

## <a name="cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>Кпажесетупдиалог:: Ондравпаже

Вызывается платформой для отрисовки экранного изображения печатной страницы.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на контекст устройства принтера.

*nсообщение*<br/>
Задает сообщение, указывающее область страницы, на которой выполняется прорисовка. Может применяться один из перечисленных ниже типов.

- WM_PSD_FULLPAGERECT всю область страницы.

- WM_PSD_MINMARGINRECT текущие минимальные поля.

- WM_PSD_MARGINRECT текущие поля.

- WM_PSD_GREEKTEXTRECT содержимое страницы.

- Область WM_PSD_ENVSTAMPRECT зарезервирована для представления штампа почтовых марок.

- Область WM_PSD_YAFULLPAGERECT для представления обратного адреса. Эта область распространяется на границы области образца страницы.

*лпрект*<br/>
Указатель на объект [крект](../../atl-mfc-shared/reference/crect-class.md) или [Rect](/windows/win32/api/windef/ns-windef-rect) , содержащий координаты области рисования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обработке; в противном случае — 0.

### <a name="remarks"></a>Примечания

Это изображение затем отображается как часть диалогового окна «Общие параметры страницы OLE». Реализация по умолчанию рисует изображение страницы текста.

Переопределите эту функцию, чтобы настроить Рисование определенной области изображения или всего изображения. Это можно сделать с помощью **`switch`** инструкции с **`case`** инструкциями, которая проверяет значение *nсообщение*. Например, чтобы настроить отрисовку содержимого изображения страницы, можно использовать следующий пример кода:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Обратите внимание, что не требуется выполнять обработку каждого случая *nсообщение*. Можно выбрать обработку одного компонента изображения, нескольких компонентов изображения или всей области.

## <a name="cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>Кпажесетупдиалог::P Редравпаже

Вызывается структурой перед отрисовкой экранного изображения печатной страницы.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Параметры

*впапер*<br/>
Задает значение, указывающее размер бумаги. Это значение может быть одним из **DMPAPER_** значений, перечисленных в описании структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) .

*вфлагс*<br/>
Указывает ориентацию бумаги или конверта, а также наличие устройства с точечной матрицей или ориентации для HPPCLHPPCL (язык управления принтерами Hewlett Packard). Этот параметр может принимать одно из следующих значений:

- 0x001 бумага в альбомном режиме (матричный)

- 0x003 бумага в альбомном режиме (ориентации для HPPCLHPPCL)

- 0x005 бумага в книжной ориентации (точечная матрица)

- 0x007 бумага в книжном режиме (ориентации для HPPCLHPPCL)

- Конверт 0x00b в альбомном режиме (ориентации для HPPCLHPPCL)

- Конверт в 0x00 в книжном режиме (матрица точек)

- Конверт 0x019 в альбомной ориентации (матрица точек)

- Конверт 0x01f в книжной ориентации (матрица точек)

*ппсд*<br/>
Указатель на структуру `PAGESETUPDLG`. Дополнительные сведения о [пажесетупдлг](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)см. в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обработке; в противном случае — 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить Рисование изображения. Если вы переопределяете эту функцию и возвращаете значение TRUE, необходимо рисовать изображение целиком. Если переопределить эту функцию и вернуть значение FALSE, платформа будет рисовать все изображение по умолчанию.

## <a name="see-also"></a>См. также раздел

[Образец WORDPAD для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс Ккоммондиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
