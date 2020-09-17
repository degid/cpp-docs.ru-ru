---
title: Класс COlePropertyPage
ms.date: 11/04/2016
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
ms.openlocfilehash: 872ade08438e54098da730012f98cdd906483887
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753792"
---
# <a name="colepropertypage-class"></a>Класс COlePropertyPage

Используется для отображения свойств пользовательского элемента управления в графическом интерфейсе подобно диалоговому окну.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Формирует объект `COlePropertyPage`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Указывает, изменил ли пользователь значение в элементе управления.|
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Возвращает массив объектов, редактируемых страницей свойств.|
|[COlePropertyPage::GetPageSite](#getpagesite)|Возвращает указатель на `IPropertyPageSite` интерфейс страницы свойств.|
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Определяет, какие элементы управления не включат кнопку Apply.|
|[COlePropertyPage::Ismodified](#ismodified)|Указывает, изменил ли пользователь страницу свойств.|
|[COlePropertyPage::ItProperty](#oneditproperty)|Вызывается по системе, когда пользователь отослал свойство.|
|[ColePropertyPage::Help](#onhelp)|Вызывается по системе, когда пользователь вызывает помощь.|
|[COlePropertyPage::ItDialog](#oninitdialog)|Вызывается по системе, когда страница свойств инициализирована.|
|[COlePropertyPage::OnobjectsChanged](#onobjectschanged)|Вызывается по системе, когда другой элемент управления OLE, с новыми свойствами, выбран.|
|[ColepropertyPage::OnsetPagesite](#onsetpagesite)|Вызывается по системе, когда рамка свойств предоставляет сайт страницы.|
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Устанавливает флаг, указывающий, изменил ли пользователь значение в элементе управления.|
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Устанавливает диалоговый ресурс страницы свойств.|
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Устанавливает краткий текст справки страницы свойств, название файла справки и контекст справки.|
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Устанавливает сядек, указывающий на то, изменил ли пользователь страницу свойств.|
|[COlePropertyPage::SetPageName](#setpagename)|Устанавливает имя страницы свойства (подпись).|

## <a name="remarks"></a>Примечания

Например, страница свойств может включать элемент управления отсеивания, который позволяет пользователю просматривать и изменять свойство подписи элемента управления.

Каждое пользовательское свойство управления акциями или акциями может иметь элемент управления диалогом, который позволяет пользователю элемента управления просматривать текущую стоимость свойства и при необходимости изменять это значение.

Для получения дополнительной `COlePropertyPage`информации об использовании, см. [ActiveX Controls: Property Pages](../../mfc/mfc-activex-controls-property-pages.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="colepropertypagecolepropertypage"></a><a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage

Формирует объект `COlePropertyPage`.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>Параметры

*idDlg*<br/>
Идентификатор ресурсов шаблона диалогов.

*idCaption*<br/>
Идентификатор ресурса подписи страницы свойства.

### <a name="remarks"></a>Примечания

При реализации `COlePropertyPage`подкласса конструктор подкласса должен использовать `COlePropertyPage` конструктор для определения ресурса диалог-шаблона, на котором основана страница свойств, и ресурс строки, содержащий ее подпись.

## <a name="colepropertypagegetcontrolstatus"></a><a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus

Определяет, изменял ли пользователь значение управления страницей свойств с помощью заданного идентификатора ресурса.

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса управления страницей свойств.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если контрольное значение было изменено; в противном случае FALSE.

## <a name="colepropertypagegetobjectarray"></a><a name="getobjectarray"></a>COlePropertyPage::GetObjectArray

Возвращает массив объектов, редактируемых страницей свойств.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>Параметры

*pnObjects*<br/>
Указатель на неподписанный длинный целый ряд, который получит количество объектов, редактируемых страницей.

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `IDispatch` указателей, которые используются для доступа к свойствам каждого элемента управления на странице свойств. Абонент не должен выпускать эти указатели интерфейса.

### <a name="remarks"></a>Примечания

Каждый объект страницы свойств поддерживает массив `IDispatch` указателей на интерфейсы объектов, редактируемых страницей. Эта функция устанавливает аргумент *pnObjects* в число элементов в этом массиве и возвращает указатель к первому элементу массива.

## <a name="colepropertypagegetpagesite"></a><a name="getpagesite"></a>COlePropertyPage::GetPageSite

Получает указатель на `IPropertyPageSite` интерфейс страницы свойств.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IPropertyPageSite` интерфейс страницы свойств.

### <a name="remarks"></a>Примечания

Элементы управления и контейнеры сотрудничают, чтобы пользователи могли просматривать и отсваговать свойства управления. Элемент управления предоставляет страницы свойств, каждая из которых является объектом OLE, который позволяет пользователю отсеивать соответствующий набор свойств. Контейнер предоставляет рамку свойств, отображая страницы свойств. Для каждой страницы в кадре свойств `IPropertyPageSite` содержится сайт страницы, поддерживающий интерфейс.

## <a name="colepropertypageignoreapply"></a><a name="ignoreapply"></a>COlePropertyPage::IgnoreApply

Определяет, какие элементы управления не включат кнопку Apply.

```cpp
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления, который необходимо игнорировать.

### <a name="remarks"></a>Примечания

Кнопка применить страницы свойств включена только при изменении значений элементов управления страницой свойств. Используйте эту функцию, чтобы указать элементы управления, которые не приводят к включению кнопки Apply при изменении их значений.

## <a name="colepropertypageismodified"></a><a name="ismodified"></a>COlePropertyPage::Ismodified

Определяет, изменил ли пользователь какие-либо значения на странице свойств.

```
BOOL IsModified();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если страница свойства была изменена.

## <a name="colepropertypageoneditproperty"></a><a name="oneditproperty"></a>COlePropertyPage::ItProperty

Платформа вызывает эту функцию при редактировании определенного свойства.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Отправка идентификатора редактируемого свойства.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает FALSE. Переопределения этой функции должны вернуть TRUE.

### <a name="remarks"></a>Примечания

Вы можете переопределить его, чтобы установить фокус на соответствующий элемент управления на странице. Реализация по умолчанию ничего не делает и возвращает FALSE.

## <a name="colepropertypageonhelp"></a><a name="onhelp"></a>ColePropertyPage::Help

Платформа вызывает эту функцию, когда пользователь запрашивает онлайн-справку.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>Параметры

*lpszHelpDir*<br/>
Каталог, содержащий файл справки страницы свойств.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает FALSE.

### <a name="remarks"></a>Примечания

Переопределить его, если ваша страница свойств должна выполнить какие-либо специальные действия, когда пользователь получает доступ к помощи. Реализация по умолчанию ничего не делает и возвращает FALSE, который поручает инфраструктуре вызывать WinHelp.

## <a name="colepropertypageoninitdialog"></a><a name="oninitdialog"></a>COlePropertyPage::ItDialog

Платформа вызывает эту функцию при инициализании диалога страницы свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает FALSE.

### <a name="remarks"></a>Примечания

Переопределить его, если требуется какое-либо специальное действие, когда диалог инициализируется. Выполнение по `CDialog::OnInitDialog` умолчанию вызывает и возвращает FALSE.

## <a name="colepropertypageonobjectschanged"></a><a name="onobjectschanged"></a>COlePropertyPage::OnobjectsChanged

Вызывается по системе, когда другой элемент управления OLE, с новыми свойствами, выбран.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>Примечания

При просмотре свойств управления OLE в среде разработчика используется безрежимный диалоговый ящик для отображения страниц свойств. При выборе другого элемента управления для нового набора свойств должен отображаться другой набор страниц свойств. Платформа вызывает эту функцию для уведомления страницы свойств изменения.

Переопределить эту функцию, чтобы получать уведомления об этом действии и выполнять любые специальные действия.

## <a name="colepropertypageonsetpagesite"></a><a name="onsetpagesite"></a>ColepropertyPage::OnsetPagesite

Платформа вызывает эту функцию, когда рамка свойств предоставляет страницу страницы свойств.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию загружает заголовок страницы и пытается определить размер страницы из ресурса диалога. Переопределить эту функцию, если ваша страница свойств требует каких-либо дальнейших действий; переопределение должно вызывать реализацию базового класса.

## <a name="colepropertypagesetcontrolstatus"></a><a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus

Изменяет статус элемента управления страницей свойств.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Содержит идентификатор элемента управления страницей свойств.

*bDirty*<br/>
Устраняет, было ли изменено поле страницы свойств. Установите в ИСТИННО, если поле было изменено, FALSE, если оно не было изменено.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанный элемент управления был установлен; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Если состояние элемента управления страницей свойств является грязным, когда страница свойств закрыта или выбрана кнопка Apply, свойство элемента управления будет обновлено с соответствующим значением.

## <a name="colepropertypagesetdialogresource"></a><a name="setdialogresource"></a>COlePropertyPage::SetDialogResource

Устанавливает диалоговый ресурс страницы свойств.

```cpp
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>Параметры

*hDialog*<br/>
Обработка к диалоговому ресурсу страницы свойств.

## <a name="colepropertypagesethelpinfo"></a><a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo

Укажите информацию о наборе инструментов, имя файла справки и контекст справки для страницы свойств.

```cpp
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>Параметры

*lpszDocString*<br/>
Строка, содержащая краткую справочную информацию для отображения в строке состояния или другом месте.

*lpszHelpFile*<br/>
Имя файла справки страницы свойства.

*dwHelpКонтекст*<br/>
Справка контекст для страницы свойств.

## <a name="colepropertypagesetmodifiedflag"></a><a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag

Указывает, изменил ли пользователь страницу свойств.

```cpp
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bИзменено*<br/>
Упоняет новое значение измененного флага страницы свойств.

## <a name="colepropertypagesetpagename"></a><a name="setpagename"></a>COlePropertyPage::SetPageName

Устанавливает имя страницы свойства, которое обычно отображается в кадре свойства на вкладке страницы.

```cpp
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>Параметры

*lpszPageName*<br/>
Указатель на строку, содержащую имя страницы свойства.

## <a name="see-also"></a>См. также раздел

[MFC Образец CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
