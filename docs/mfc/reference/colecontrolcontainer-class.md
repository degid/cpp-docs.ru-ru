---
title: Класс Колеконтролконтаинер
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: 2c2c97090fc8255c06e1678a377fe2dcc968ffd2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214117"
---
# <a name="colecontrolcontainer-class"></a>Класс Колеконтролконтаинер

Играет роль контейнера для элементов управления ActiveX.

## <a name="syntax"></a>Синтаксис

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Колеконтролконтаинер:: Колеконтролконтаинер](#colecontrolcontainer)|Формирует объект `COleControlContainer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Колеконтролконтаинер:: Аттачконтролсите](#attachcontrolsite)|Создает узел элемента управления, размещенный в контейнере.|
|[Колеконтролконтаинер:: Броадкастамбиентпропертичанже](#broadcastambientpropertychange)|Информирует все размещенные элементы управления об изменении внешнего свойства.|
|[Колеконтролконтаинер:: Чеккдлгбуттон](#checkdlgbutton)|Изменяет указанный элемент управления "Кнопка".|
|[Колеконтролконтаинер:: Чеккрадиобуттон](#checkradiobutton)|Выбирает указанный переключатель группы.|
|[Колеконтролконтаинер:: CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|
|[Колеконтролконтаинер:: Креатеолефонт](#createolefont)|Создает шрифт OLE.|
|[Колеконтролконтаинер:: FindItem](#finditem)|Возвращает пользовательский сайт указанного элемента управления.|
|[Колеконтролконтаинер:: Фризеаллевентс](#freezeallevents)|Определяет, принимает ли сайт управления события.|
|[Колеконтролконтаинер:: Жетамбиентпроп](#getambientprop)|Извлекает указанное внешнее свойство.|
|[Колеконтролконтаинер:: Жетдлгитем](#getdlgitem)|Извлекает указанный элемент управления диалогового окна.|
|[Колеконтролконтаинер:: Жетдлгитеминт](#getdlgitemint)|Извлекает значение указанного элемента управления диалогового окна.|
|[Колеконтролконтаинер:: Жетдлгитемтекст](#getdlgitemtext)|Извлекает заголовок указанного элемента управления диалогового окна.|
|[Колеконтролконтаинер:: Хандлесетфокус](#handlesetfocus)|Определяет, обрабатывает ли контейнер WM_SETFOCUS сообщения.|
|[Колеконтролконтаинер:: Хандлевиндовлессмессаже](#handlewindowlessmessage)|Обрабатывает сообщения, отправляемые в безоконный элемент управления.|
|[Колеконтролконтаинер:: Исдлгбуттончеккед](#isdlgbuttonchecked)|Определяет состояние указанной кнопки.|
|[Колеконтролконтаинер:: onpain](#onpaint)|Вызывается для перерисовки части контейнера.|
|[Колеконтролконтаинер:: Онуиактивате](#onuiactivate)|Вызывается, когда элемент управления активируется на месте.|
|[Колеконтролконтаинер:: Онуидеактивате](#onuideactivate)|Вызывается, когда элемент управления собирается деактивироваться.|
|[Колеконтролконтаинер:: Скроллчилдрен](#scrollchildren)|Вызывается структурой при получении сообщений прокрутки из дочернего окна.|
|[Колеконтролконтаинер:: Сенддлгитеммессаже](#senddlgitemmessage)|Отправляет сообщение указанному элементу управления.|
|[Колеконтролконтаинер:: Сетдлгитеминт](#setdlgitemint)|Задает значение указанного элемента управления.|
|[Колеконтролконтаинер:: Сетдлгитемтекст](#setdlgitemtext)|Задает текст указанного элемента управления.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Колеконтролконтаинер:: m_crBack](#m_crback)|Цвет фона контейнера.|
|[Колеконтролконтаинер:: m_crFore](#m_crfore)|Цвет переднего плана контейнера.|
|[Колеконтролконтаинер:: m_listSitesOrWnds](#m_listsitesorwnds)|Список поддерживаемых сайтов элементов управления.|
|[Колеконтролконтаинер:: m_nWindowlessControls](#m_nwindowlesscontrols)|Количество размещенных элементов управления без окон.|
|[Колеконтролконтаинер:: m_pOleFont](#m_polefont)|Указатель на шрифт OLE сайта пользовательского элемента управления.|
|[Колеконтролконтаинер:: m_pSiteCapture](#m_psitecapture)|Указатель на сайт управления записью.|
|[Колеконтролконтаинер:: m_pSiteFocus](#m_psitefocus)|Указатель на элемент управления, который в данный момент имеет фокус ввода.|
|[Колеконтролконтаинер:: m_pSiteUIActive](#m_psiteuiactive)|Указатель на элемент управления, который в настоящее время активирован на месте.|
|[Колеконтролконтаинер:: m_pWnd](#m_pwnd)|Указатель на окно, реализующее контейнер элемента управления.|
|[Колеконтролконтаинер:: m_siteMap](#m_sitemap)|Схема узла.|

## <a name="remarks"></a>Примечания

Это делается за счет поддержки одного или нескольких сайтов элементов управления ActiveX (реализованных `COleControlSite` ). `COleControlContainer`полностью реализует интерфейсы [иолеинплацефраме](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe) и [иолеконтаинер](/windows/win32/api/oleidl/nn-oleidl-iolecontainer) , позволяя содержащимся элементам управления ActiveX выполнять свои квалификации как элементы на месте.

Как правило, этот класс используется вместе с `COccManager` и `COleControlSite` для реализации пользовательского контейнера элемента управления ActiveX с пользовательскими сайтами для одного или нескольких элементов управления ActiveX.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Требования

**Заголовок:** афксокк.h

## <a name="colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>Колеконтролконтаинер:: Аттачконтролсите

Вызывается платформой для создания и подключения сайта элемента управления.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на объект `CWnd`.

*нидк*<br/>
Идентификатор присоединяемого элемента управления.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если вы хотите настроить этот процесс.

> [!NOTE]
> Используйте первую форму этой функции при статической компоновке с библиотекой MFC. Используйте вторую форму, если вы динамически связываетесь с библиотекой MFC.

## <a name="colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>Колеконтролконтаинер:: Броадкастамбиентпропертичанже

Информирует все размещенные элементы управления об изменении внешнего свойства.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации изменяемого свойства окружения.

### <a name="remarks"></a>Примечания

Эта функция вызывается платформой, когда свойство окружения изменило значение. Переопределите эту функцию, чтобы настроить это поведение.

## <a name="colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>Колеконтролконтаинер:: Чеккдлгбуттон

Изменяет текущее состояние кнопки.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Параметры

*нидбуттон*<br/>
Идентификатор изменяемой кнопки.

*nДополнительные*<br/>
Задает состояние кнопки. Может применяться один из перечисленных ниже типов.

- BST_CHECKED Устанавливает состояние кнопки "установлен".

- BST_INDETERMINATE задает состояние кнопки серым цветом, что указывает на неопределенное состояние. Используйте это значение только в том случае, если кнопка имеет стиль BS_3STATE или BS_AUTO3STATE.

- BST_UNCHECKED устанавливает состояние кнопки "Очистка".

## <a name="colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>Колеконтролконтаинер:: Чеккрадиобуттон

Выбирает указанный переключатель в группе и удаляет оставшиеся кнопки в группе.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Параметры

*нидфирстбуттон*<br/>
Задает идентификатор первого переключателя в группе.

*нидластбуттон*<br/>
Задает идентификатор последнего переключателя в группе.

*нидчеккбуттон*<br/>
Задает идентификатор переключателя для проверки.

## <a name="colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>Колеконтролконтаинер:: Колеконтролконтаинер

Формирует объект `COleControlContainer`.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на родительское окно контейнера элемента управления.

### <a name="remarks"></a>Примечания

После успешного создания объекта добавьте пользовательский сайт элемента управления с вызовом `AttachControlSite` .

## <a name="colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>Колеконтролконтаинер:: CreateControl

Создает элемент управления ActiveX, размещенный на указанном `COleControlSite` объекте.

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>Параметры

*пвндктрл*<br/>
Указатель на объект окна, представляющий элемент управления.

*этому*<br/>
Уникальный идентификатор класса элемента управления.

*лпсзвиндовнаме*<br/>
Указатель на текст, отображаемый в элементе управления. Задает значение свойства Caption или Text элемента управления (если оно имеется). Если значение равно NULL, свойство Caption или Text элемента управления не изменяется.

*двстиле*<br/>
Стили Windows. Доступные стили перечислены в разделе **"Примечания** ".

*rect*<br/>
Задает размер и расположение элемента управления. Это может быть либо `CRect` объект, либо `RECT` структура.

*nID*<br/>
Указывает идентификатор дочернего окна элемента управления.

*пперсист*<br/>
Указатель на объект, `CFile` содержащий постоянное состояние для элемента управления. Значение по умолчанию равно NULL, что означает, что элемент управления инициализируется без восстановления состояния из постоянного хранилища. Если значение не равно NULL, это должен быть указатель на `CFile` производный объект, содержащий постоянные данные элемента управления, в виде потока или хранилища. Эти данные могли быть сохранены в предыдущей активации клиента. Объект `CFile` может содержать другие данные, но его указатель для чтения и записи должен быть установлен на первый байт постоянных данных во время вызова `CreateControl` .

*бстораже*<br/>
Указывает, должны ли данные в *пперсист* интерпретироваться как `IStorage` данные или `IStream` . Если данные в *пперсист* являются хранилищем, *бстораже* должно иметь значение true. Если данные в *пперсист* являются потоком, *бстораже* должен иметь значение false. Значение по умолчанию — FALSE.

*бстрликкэй*<br/>
Необязательные данные лицензионного ключа. Эти данные необходимы только для создания элементов управления, требующих лицензионного ключа во время выполнения. Если элемент управления поддерживает лицензирование, необходимо предоставить лицензионный ключ, чтобы создать элемент управления для выполнения. Значение по умолчанию — NULL.

*ппневсите*<br/>
Указатель на существующий узел элемента управления, на котором будет размещен создаваемый элемент управления. Значение по умолчанию равно NULL, что означает, что новый узел элемента управления будет автоматически создан и присоединен к новому элементу управления.

*PowerPoint*<br/>
Указатель на `POINT` структуру, содержащую левый верхний угол элемента управления. Размер элемента управления определяется значением *псизе*. Значения *PPT* и *псизе* являются необязательным методом указания размера и расположения элемента управления.

*псизе*<br/>
Указатель на `SIZE` структуру, которая содержит размер элемента управления. Левый верхний угол определяется значением *PPT*. Значения *PPT* и *псизе* являются необязательным методом указания размера и расположения элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Поддерживается только подмножество флагов Windows *двстиле* `CreateControl` :

- WS_VISIBLE создает окно, которое изначально видимо. Требуется, если необходимо, чтобы элемент управления был видимым немедленно, например обычным окнам.

- WS_DISABLED создает окно, которое изначально отключено. Отключенное окно не может принимать входные данные от пользователя. Может быть задан, если элемент управления имеет свойство Enabled.

- WS_BORDER создает окно с тонкой линией. Может быть задан, если элемент управления имеет свойство BorderStyle.

- WS_GROUP задает первый элемент управления группы элементов управления. Пользователь может изменить фокус клавиатуры с одного элемента управления в группе на следующий с помощью клавиш направления. Все элементы управления, определенные с WS_GROUP стилем после первого элемента управления, принадлежат к одной группе. Следующий элемент управления с стилем WS_GROUP завершает группу и запускает следующую группу.

- WS_TABSTOP указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. При нажатии клавиши TAB фокус клавиатуры меняется на следующий элемент управления стиля WS_TABSTOP.

Используйте вторую перегрузку для создания элементов управления размером по умолчанию.

## <a name="colecontrolcontainercreateolefont"></a><a name="createolefont"></a>Колеконтролконтаинер:: Креатеолефонт

Создает шрифт OLE.

```cpp
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
Указатель на шрифт, используемый контейнером элемента управления.

## <a name="colecontrolcontainerfinditem"></a><a name="finditem"></a>Колеконтролконтаинер:: FindItem

Находит пользовательский сайт, на котором размещен указанный элемент.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор найденного элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на пользовательский сайт указанного элемента.

## <a name="colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>Колеконтролконтаинер:: Фризеаллевентс

Определяет, будет ли контейнер игнорировать события от вложенных сайтов элементов управления или принимать их.

```cpp
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Параметры

*бфризе*<br/>
Ненулевое значение, если события будут обработаны; в противном случае — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Элементу управления не требуется прекращать срабатывание событий, если это запрошено контейнером элемента управления. Он может продолжать обработку, но все последующие события будут игнорироваться контейнером элемента управления.

## <a name="colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>Колеконтролконтаинер:: Жетамбиентпроп

Извлекает значение указанного внешнего свойства.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Параметры

*псите*<br/>
Указатель на сайт элемента управления, из которого будет получено внешнее свойство.

*DISPID*<br/>
Идентификатор диспетчеризации требуемого внешнего свойства.

*пварресулт*<br/>
Указатель на значение свойства окружения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>Колеконтролконтаинер:: Жетдлгитем

Извлекает указатель на указанный элемент управления или дочернее окно в диалоговом окне или другом окне.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор извлекаемого элемента диалогового окна.

*фвнд*<br/>
Указатель на маркер объекта окна указанного диалогового элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно диалогового элемента.

## <a name="colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>Колеконтролконтаинер:: Жетдлгитеминт

Возвращает значение переведенного текста данного элемента управления.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*лптранс*<br/>
Указатель на логическую переменную, которая получает значение успешного или неуспешного выполнения функции (значение TRUE указывает на успешное выполнение, FALSE — на ошибку).

*бсигнед*<br/>
Указывает, должна ли функция проверять текст на наличие знака "минус" в начале и возвращать целочисленное значение со знаком, если оно найдено. Если параметр *бсигнед* имеет значение true, то при указании значения, которое должно быть извлечено, будет использоваться целое число со знаком, приведенное к **`int`** типу значение. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха переменная, на которую указывает *лптранс* , имеет значение true, а возвращаемое значение является переведенным значением текста элемента управления.

Если функция завершается ошибкой, переменная, на которую указывает *лптранс* , устанавливается в значение false, а возвращаемое значение равно нулю. Обратите внимание, что, поскольку ноль является возможным преобразованным значением, возвращаемое значение, равное нулю, само по себе не указывает на сбой.

Если *лптранс* имеет значение null, функция не возвращает сведения об успехе или неудаче.

### <a name="remarks"></a>Примечания

Функция преобразует полученный текст, удаляя лишние пробелы в начале текста, а затем преобразуя десятичные цифры. Функция прекращает трансляцию при достижении конца текста или при обнаружении нечислового символа.

Эта функция возвращает нуль, если переведенное значение больше INT_MAX (для чисел со знаком) или UINT_MAX (для чисел без знака).

## <a name="colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>Колеконтролконтаинер:: Жетдлгитемтекст

Извлекает текст заданного элемента управления.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*lpStr*<br/>
Указатель на текст элемента управления.

*нмакскаунт*<br/>
Задает максимальную длину строки в символах, которая должна быть скопирована в буфер, на который указывает *LPSTR*. Если длина строки превышает ограничение, строка усекается.

### <a name="return-value"></a>Возвращаемое значение

Если функция завершается удачно, возвращаемое значение указывает количество символов, копируемых в буфер, не включая завершающий символ null.

Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## <a name="colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>Колеконтролконтаинер:: Хандлесетфокус

Определяет, обрабатывает ли контейнер WM_SETFOCUS сообщения.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если контейнер обрабатывает WM_SETFOCUS сообщения; в противном случае — ноль.

## <a name="colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>Колеконтролконтаинер:: Хандлевиндовлессмессаже

Обрабатывает сообщения окна для безоконных элементов управления.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор сообщения окна, предоставляемого Windows.

*wParam*<br/>
Параметр сообщения; предоставляется Windows. Указывает дополнительные сведения, относящиеся к конкретному сообщению. Содержимое этого параметра зависит от значения параметра *Message* .

*lParam*<br/>
Параметр сообщения; предоставляется Windows. Указывает дополнительные сведения, относящиеся к конкретному сообщению. Содержимое этого параметра зависит от значения параметра *Message* .

*плресулт*<br/>
Код результата Windows. Указывает результат обработки сообщения и зависит от отправленного сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить обработку безоконных сообщений управления.

## <a name="colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>Колеконтролконтаинер:: Исдлгбуттончеккед

Определяет состояние указанной кнопки.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Параметры

*нидбуттон*<br/>
Идентификатор элемента управления "Кнопка".

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение из кнопки, созданной с помощью BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON или стиля BS_3STATE. Может применяться один из перечисленных ниже типов.

- Выбрана кнопка BST_CHECKED.

- BST_INDETERMINATE кнопка является серым, что указывает на неопределенное состояние (применяется только в том случае, если у кнопки есть BS_3STATE или BS_AUTO3STATE стиль).

- Кнопка BST_UNCHECKED сброшена.

### <a name="remarks"></a>Примечания

Если кнопка является элементом управления с тремя состояниями, функция-член определяет, является ли она недоступной, установленной или ни одной.

## <a name="colecontrolcontainerm_crback"></a><a name="m_crback"></a>Колеконтролконтаинер:: m_crBack

Цвет фона контейнера.

```
COLORREF m_crBack;
```

## <a name="colecontrolcontainerm_crfore"></a><a name="m_crfore"></a>Колеконтролконтаинер:: m_crFore

Цвет переднего плана контейнера.

```
COLORREF m_crFore;
```

## <a name="colecontrolcontainerm_listsitesorwnds"></a><a name="m_listsitesorwnds"></a>Колеконтролконтаинер:: m_listSitesOrWnds

Список узлов элементов управления, размещенных в контейнере.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

## <a name="colecontrolcontainerm_nwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>Колеконтролконтаинер:: m_nWindowlessControls

Число безоконных элементов управления, размещаемых контейнером элементов управления.

```
int m_nWindowlessControls;
```

## <a name="colecontrolcontainerm_polefont"></a><a name="m_polefont"></a>Колеконтролконтаинер:: m_pOleFont

Указатель на шрифт OLE сайта пользовательского элемента управления.

```
LPFONTDISP m_pOleFont;
```

## <a name="colecontrolcontainerm_psitecapture"></a><a name="m_psitecapture"></a>Колеконтролконтаинер:: m_pSiteCapture

Указатель на сайт управления записью.

```
COleControlSite* m_pSiteCapture;
```

## <a name="colecontrolcontainerm_psitefocus"></a><a name="m_psitefocus"></a>Колеконтролконтаинер:: m_pSiteFocus

Указатель на сайт управления, на котором в данный момент находится фокус ввода.

```
COleControlSite* m_pSiteFocus;
```

## <a name="colecontrolcontainerm_psiteuiactive"></a><a name="m_psiteuiactive"></a>Колеконтролконтаинер:: m_pSiteUIActive

Указатель на узел элемента управления, который активирован на месте.

```
COleControlSite* m_pSiteUIActive;
```

## <a name="colecontrolcontainerm_pwnd"></a><a name="m_pwnd"></a>Колеконтролконтаинер:: m_pWnd

Указатель на объект окна, связанный с контейнером.

```
CWnd* m_pWnd;
```

## <a name="colecontrolcontainerm_sitemap"></a><a name="m_sitemap"></a>Колеконтролконтаинер:: m_siteMap

Схема узла.

```
CMapPtrToPtr m_siteMap;
```

## <a name="colecontrolcontaineronpaint"></a><a name="onpaint"></a>Колеконтролконтаинер:: onpain

Вызывается платформой для обработки запросов WM_PAINT.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на контекст устройства, используемый контейнером.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение было обработано; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить процесс рисования.

## <a name="colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>Колеконтролконтаинер:: Онуиактивате

Вызывается структурой, когда узел элемента управления, на который указывает *псите*, будет активирован на месте.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Параметры

*псите*<br/>
Указатель на узел элемента управления, который должен быть активирован на месте.

### <a name="remarks"></a>Примечания

Активация на месте означает, что главное меню контейнера заменяется составным меню на месте.

## <a name="colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>Колеконтролконтаинер:: Онуидеактивате

Вызывается структурой, когда узел элемента управления, на который указывает *псите*, будет деактивирован.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Параметры

*псите*<br/>
Указатель на сайт элемента управления, который необходимо отключить.

### <a name="remarks"></a>Примечания

При получении этого уведомления контейнер должен переустановить пользовательский интерфейс и захватить фокус.

## <a name="colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>Колеконтролконтаинер:: Скроллчилдрен

Вызывается структурой при получении сообщений прокрутки из дочернего окна.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Параметры

*DX*<br/>
Объем (в пикселях) прокрутки вдоль оси x.

*DY*<br/>
Объем (в пикселях) прокрутки вдоль оси y.

## <a name="colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>Колеконтролконтаинер:: Сенддлгитеммессаже

Отправляет сообщение указанному элементу управления.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Задает идентификатор элемента управления, который получает сообщение.

*message*<br/>
Указывает отправляемое сообщение.

*wParam*<br/>
Указывает дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
Указывает дополнительные сведения, относящиеся к конкретному сообщению.

## <a name="colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>Колеконтролконтаинер:: Сетдлгитеминт

Задает текст элемента управления в диалоговом окне в виде строкового представления указанного целочисленного значения.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*Nзначение*<br/>
Отображаемое целочисленное значение.

*бсигнед*<br/>
Указывает, является ли параметр *nзначение* знаком или без знака. Если этот параметр имеет значение TRUE, *nзначение* подписывается. Если этот параметр имеет значение TRUE, а *nзначение* меньше нуля, то перед первой цифрой в строке ставится знак минус. Если этот параметр имеет значение FALSE, *nзначение* не имеет знака.

## <a name="colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>Колеконтролконтаинер:: Сетдлгитемтекст

Задает текст указанного элемента управления, используя текст, содержащийся в *лпсзстринг*.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*лпсзстринг*<br/>
Указатель на текст элемента управления.

## <a name="see-also"></a>См. также раздел

[Класс от CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Колеконтролсите](../../mfc/reference/colecontrolsite-class.md)<br/>
[Класс Коккманажер](../../mfc/reference/coccmanager-class.md)
