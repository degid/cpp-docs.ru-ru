---
title: Класс CMFCRibbonMainPanel
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 0fd1cd2fec31f9da0c2bec36d08586780f4f95c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753579"
---
# <a name="cmfcribbonmainpanel-class"></a>Класс CMFCRibbonMainPanel

Реализует ленточной панели, которая отображаетприжается при нажатии кнопки [CMFCRibbonApplicationButton.](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Конструктор по умолчанию.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonMainPanel::Добавить](#add)|Добавляет элемент ленты в левое стекло панели кнопки приложения. (Переопределяет [CMFCRibbonPanel::Добавить](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Добавляет строку текста в меню списка последних файлов.|
|[CMFCRibbonMainPanel::Addtobottom](#addtobottom)|Добавляет элемент ленты в нижнюю панель панели приложения ленты.|
|[CMFCRibbonMainPanel::AddtoRight](#addtoright)|Добавляет элемент ленты к правому стеку панели кнопки приложения.|
|`CMFCRibbonMainPanel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Возвращает прямоугольник, представляющий область основной панели ленты.|
|`CMFCRibbonMainPanel::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|

## <a name="remarks"></a>Примечания

Рамочная платформа `CMFCRibbonMainPanel` отображает при открытии панели приложений. Он содержит три стекла:

- Левое стекло содержит команды, связанные с файлами, такие как **Open,** **Save,** **Print**и **Close.** Чтобы добавить команду к этой панели, позвоните [CMFCRibbonMainPanel::Добавить](#add).

- Правое стекло содержит параметры, которые изменяют команду, которую вы нажимаете в левом стеку. Например, если вы нажмете **Сохранить Как** из левого стекла, правое стекло может отображать доступные типы файлов. Чтобы добавить элемент в эту панель, позвоните [CMFCRibbonMainPanel::AddToRight](#addtoright).

- Нижняя панель содержит кнопки, которые позволяют изменить настройки приложения и выйти из программы. Чтобы добавить элемент в эту панель, позвоните [CMFCRibbonMainPanel::AddToBottom](#addtobottom).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonMainPanel.h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a>CMFCRibbonMainPanel::Добавить

Добавляет элемент ленты в левое стекло панели кнопки приложения.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
(в, вне) Указатель на элемент ленты, чтобы добавить к основной панели.

### <a name="remarks"></a>Примечания

Добавляет элемент ленты в панель. Элементы, добавленные с помощью этого метода, будут расположены в левой колонке основной панели.

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList

Добавляет строку текста в меню списка последних файлов.

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Определяет строку для добавления в последний список файлов.

*nWidth*<br/>
Определяет ширину в пикселях последней панели списка файлов.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFCRibbonMainPanel::Addtobottom

Добавляет элемент ленты в нижнюю панель панели приложения ленты.

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
(в, вне) Указатель на элемент ленты, чтобы добавить в нижней части основной панели.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFCRibbonMainPanel::AddtoRight

Добавляет элемент ленты к правому стеку панели кнопки приложения.

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
Указатель на элемент ленты, который будет добавлен в правую сторону основной панели.

*nWidth*<br/>
Определяет ширину в пикселях правой панели.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы добавить элемент ленты в правую панель. Правая панель обычно отображает последний список файлов, но здесь можно добавить любой другой элемент ленты.

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame

Возвращает прямоугольник, представляющий область основной панели ленты.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, представляющий область ленты основной панели.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
