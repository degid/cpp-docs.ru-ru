---
title: Класс COleDocument
ms.date: 11/04/2016
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
ms.openlocfilehash: 1500035cb8be3036678090918154829aace48d2f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753872"
---
# <a name="coledocument-class"></a>Класс COleDocument

Базовый класс для документов OLE, которые поддерживают визуальное редактирование.

## <a name="syntax"></a>Синтаксис

```
class COleDocument : public CDocument
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|Формирует объект `COleDocument`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|Добавляет элемент в список элементов, хранятих в документе.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Устанавливает устройство с печатной целью для всех клиентских элементов в документе.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Вызывает хранение документов с помощью формата файла СТРУКТУРИРОВАНного хранения OL.|
|[ColeDocument::GetinPlaceActiveitem](#getinplaceactiveitem)|Возвращает элемент OLE, который в настоящее время находится на месте активного.|
|[ColeDocument::GetNextClientItem](#getnextclientitem)|Получает следующий элемент клиента для итерации.|
|[COleDocument::GetNextItem](#getnextitem)|Получает следующий элемент документа для итерации.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|Получает следующий элемент сервера для итерации.|
|[ColeDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Возвращает основной выбранный элемент OLE в документе.|
|[COleDocument::GetStartPosition](#getstartposition)|Получает исходное положение, чтобы начать итерацию.|
|[ColeDocument::HasblankItems](#hasblankitems)|Проверки на наличие пустых элементов в документе.|
|[COleDocument::OnshowViews](#onshowviews)|Вызывается, когда документ становится видимым или невидимым.|
|[ColeDocument::RemoveItem](#removeitem)|Удаляет элемент из списка элементов, хранятих в документе.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Отметив документ как измененный, если какие-либо из содержащихся элементов OLE были изменены.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[COleDocument::ItChangeIcon](#oneditchangeicon)|Обработка событий в команде меню «Изменение значков».|
|[COleDocument::It-Преобразование](#oneditconvert)|Обрабатывает преобразование встроенного или связанного объекта из одного типа в другой.|
|[COleDocument::ItСсылки](#oneditlinks)|Обработка событий в команде Ссылки в меню Edit.|
|[COleDocument::OnFileSendMail](#onfilesendmail)|Отправляет почтовое сообщение с приложеным документом.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Вызывается системой для обновления системы управления иного использования для опции меню «Изменение/Изменение значки».|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Вызывается в рамках для обновления утилиты управления ими для опции меню Edit/Links.|
|[COleDocument::OnupdateObjectVerbMenu](#onupdateobjectverbmenu)|Вызывается рамкой для обновления опции управления управления командой для опции меню *Edit/ObjectName* и подменю Verb, доступ к которым из Edit/ *ObjectName.*|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Вызывается в рамках для обновления утилиты управления ими для опции специального меню Paste.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Вызывается в рамках для обновления утилиты управления ими для опции меню пасты.|

## <a name="remarks"></a>Примечания

`COleDocument`является производным от `CDocument`, который позволяет вашим приложениям OLE использовать архитектуру документа/просмотра, предоставленную библиотекой класса Microsoft Foundation.

`COleDocument`рассматривает документ как набор объектов [CDocItem](../../mfc/reference/cdocitem-class.md) для обработки элементов OLE. Как контейнерные, так и серверные приложения требуют такой архитектуры, поскольку их документы должны содержать элементы OLE. Классы [COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem,](../../mfc/reference/coleclientitem-class.md) `CDocItem`полученные из, управляют взаимодействиями между приложениями и элементами OLE.

Если вы пишете простое контейнерное `COleDocument`приложение, извлеките класс документов из. Если вы пишете контейнерное приложение, которое поддерживает ссылки на встроенные элементы, содержащиеся в его документах, получите класс документов из [COleLinkingDoc.](../../mfc/reference/colelinkingdoc-class.md) Если вы пишете серверное приложение или комбинированный контейнер/сервер, получите класс документов из [COleServerDoc.](../../mfc/reference/coleserverdoc-class.md) `COleLinkingDoc`и `COleServerDoc` являются производными от `COleDocument`, так `COleDocument` что `CDocument`эти классы наследуют все услуги, доступные в и .

Для `COleDocument`использования, получить класс из него и добавить функциональность для управления не-OLE данных приложения, а также встроенные или связанные элементы. Если вы `CDocItem`определяете классы, полученные для хранения родных данных `COleDocument` приложения, можно использовать реализацию по умолчанию, определяемую для хранения данных OLE и non-OLE. Вы также можете создать свои собственные структуры данных для хранения данных, не относясь к OLE, отдельно от элементов OLE. Для получения дополнительной [информации,](../../mfc/containers-compound-files.md)см.

`CDocument`поддерживает отправку документа по почте, если поддержка почты (MAPI) присутствует. `COleDocument`обновил [OnFileSendMail](#onfilesendmail) для правильной обработки сложных документов. Для получения дополнительной информации смотрите статьи [MAPI](../../mfc/mapi.md) и [MAPI Поддержки в MFC](../../mfc/mapi-support-in-mfc.md)..

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem

Вызовите эту функцию, чтобы добавить элемент в документ.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на добавленный элемент документа.

### <a name="remarks"></a>Примечания

Вам не нужно вызывать эту функцию явно, `COleClientItem` когда `COleServerItem` она называется или конструктор, который принимает указатель на документ.

## <a name="coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice

Вызовите эту функцию, чтобы изменить устройство для печати-целевой для всех встроенных элементов [COleClientItem](../../mfc/reference/coleclientitem-class.md) в контейнерном документе приложения.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Параметры

*ptd*<br/>
Указатель на `DVTARGETDEVICE` структуру данных, содержащую информацию о новом устройстве с целью печати. Может иметь значение NULL.

*Ppd*<br/>
Указатель на `PRINTDLG` структуру данных, содержащую информацию о новом устройстве с целью печати. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обновляет устройство, предназначенное для печати, для всех элементов, но не обновляет кэш презентации для этих элементов. Чтобы обновить кэш презентации для элемента, позвоните [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).

Аргументы к этой функции содержат информацию, которую OLE использует для идентификации целевого устройства. Структура [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) содержит информацию, которую Windows использует для инициализации общего диалогового окна печати. После того, как пользователь закрывает диалоговую будку, Windows возвращает информацию о выборе пользователя в этой структуре. Членом `m_pd` объекта [CPrintDialog](../../mfc/reference/cprintdialog-class.md) является `PRINTDLG` структура.

Для получения дополнительной [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) информации см.

Для получения дополнительной [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) информации см.

## <a name="coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument

Формирует объект `COleDocument`.

```
COleDocument();
```

## <a name="coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile

Позвоните в эту функцию, если вы хотите сохранить документ с помощью формата соединения файла.

```cpp
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Определяет, включена ли или отключена поддержка составных файлов.

### <a name="remarks"></a>Примечания

Это также называется структурированным хранилищем. Обычно эту функцию вы называете `COleDocument`от конструктора вашего класса, полученного. Для получения дополнительной информации о [Containers: Compound Files](../../mfc/containers-compound-files.md)сложных документов, см.

Если вы не позвоните по этой функции участника, документы будут храниться в неструктурированном ("плоском") формате файла.

После включения или отключения поддержки файла или отключения документа настройка не должна изменяться в течение всего срока службы документа.

## <a name="coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>ColeDocument::GetinPlaceActiveitem

Вызовите эту функцию, чтобы получить элемент OLE, который в настоящее время активирован на месте в окне кадра, содержащий представление, *идентифицированное pWnd.*

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, отображаев контейнерное документ.

### <a name="return-value"></a>Возвращаемое значение

Указатель на один, на месте активного элемента OLE; NULL, если в настоящее время нет элемента OLE в состоянии "на месте активного".

## <a name="coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>ColeDocument::GetNextClientItem

Позвоните в эту функцию неоднократно, чтобы получить доступ к каждому из элементов клиента в документе.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение POSITION, установленное предыдущим `GetNextClientItem`вызовом; начальное значение возвращается `GetStartPosition` функцией участника.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент клиента в документе, или NULL, если больше нет клиентских элементов.

### <a name="remarks"></a>Примечания

После каждого вызова значение *pos* устанавливается для следующего элемента в документе, который может быть или не быть элементом клиента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

## <a name="coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem

Повторное вызов этой функции для доступа к каждому из элементов в документе.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение POSITION, установленное предыдущим `GetNextItem`вызовом; начальное значение возвращается `GetStartPosition` функцией участника.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент документа в указанном положении.

### <a name="remarks"></a>Примечания

После каждого вызова значение *pos* устанавливается к значению POSITION следующего элемента в документе. Если извлеченный элемент является последним элементом в документе, новое значение *pos* является NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

## <a name="coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem

Повторно ели вызов этой функции, чтобы получить доступ к каждому из элементов сервера в документе.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение POSITION, установленное предыдущим `GetNextServerItem`вызовом; начальное значение возвращается `GetStartPosition` функцией участника.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент сервера в документе, или NULL, если больше нет элементов сервера.

### <a name="remarks"></a>Примечания

После каждого вызова значение *pos* устанавливается для следующего элемента в документе, который может быть или не быть элементом сервера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

## <a name="coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>ColeDocument::GetPrimarySelectedItem

Вызывается в рамках для извлечения выбранного в настоящее время элемента OLE в указанном представлении.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указатель на объект активного представления, отображающий документ.

### <a name="return-value"></a>Возвращаемое значение

Указатель на один, выбранный элемент OLE; NULL, если не выбраны элементы OLE или если выбрано более одного элемента.

### <a name="remarks"></a>Примечания

Реализация по умолчанию выполняет поиск по списку содержащихся элементов OLE для одного выбранного элемента и возвращает указатель на него. Если нет выбранного элемента, или если выбрано более одного элемента, функция возвращает NULL. Для работы `CView::IsSelected` этой функции необходимо переопределить функцию участника в классе представления. Переопределить эту функцию, если у вас есть свой собственный метод хранения, содержащихся ole элементов.

## <a name="coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition

Позвоните в эту функцию, чтобы получить положение первого элемента в документе.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для начала итерации через элементы документа; NULL, если документ не имеет элементов.

### <a name="remarks"></a>Примечания

Передайте значение, `GetNextItem` `GetNextClientItem`возвращенное в, или `GetNextServerItem`.

## <a name="coledocumenthasblankitems"></a><a name="hasblankitems"></a>ColeDocument::HasblankItems

Позвоните в эту функцию, чтобы определить, содержит ли документ какие-либо пустые элементы.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если документ содержит какие-либо пустые элементы; в противном случае 0.

### <a name="remarks"></a>Примечания

Пустой элемент — это тот, прямоугольник которого пуст.

## <a name="coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::ItChangeIcon

Отображает диалоговую коробку ICON Change Icon и изменяет значок, представляющий выбранный в настоящее время элемент OLE, на значок, выбранный пользователем в диалоговом поле.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Примечания

`OnEditChangeIcon`создает и `COleChangeIconDialog` запускает диалоговую коробку «Изменение значка».

## <a name="coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::It-Преобразование

Отображает диалоговую коробку OLE Convert и преобразует или активирует выбранный в настоящее время элемент OLE в соответствии с выбором пользователя в диалоговом поле.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Примечания

`OnEditConvert`создает и `COleConvertDialog` запускает диалоговую коробку Convert.

Примером преобразования является преобразование документа Microsoft Word в документ WordPad.

## <a name="coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::ItСсылки

Отображает диалоговую коробку OLE Edit/Links.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Примечания

`OnEditLinks`создает и `COleLinksDialog` запускает диалоговое окно Ссылки, которое позволяет пользователю изменять связанные объекты.

## <a name="coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail

Отправляет сообщение через резидента почты хост (если таковые имеется) с документом в качестве вложения.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Примечания

`OnFileSendMail`вызовы `OnSaveDocument` для сериализации (сохранения) безымянных и измененных документов во временный файл, который затем отправляется по электронной почте. Если документ не был изменен, временный файл не нужен; оригинал отправляется. `OnFileSendMail`загружает MAPI32. DLL, если он еще не загружен.

В отличие `OnFileSendMail` от `CDocument`реализации для, эта функция обрабатывает сложные файлы правильно.

Для получения дополнительной информации смотрите [темы MAPI](../../mfc/mapi.md) и [поддержку MAPI в](../../mfc/mapi-support-in-mfc.md) статьях MFC.

## <a name="coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnshowViews

Платформа вызывает эту функцию после изменения состояния видимости документа.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Параметры

*bVisible*<br/>
Указывает, стал ли документ видимым или невидимым.

### <a name="remarks"></a>Примечания

Версия этой функции по умолчанию ничего не делает. Переопределить его, если приложение должно выполнить специальную обработку при изменении видимости документа.

## <a name="coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon

Вызывается фреймворком для обновления команды Change Icon в меню Edit.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, представляющую меню, генерируемое командой обновления. Обработчик обновления `Enable` вызывает функцию члена `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

`OnUpdateEditChangeIcon`обновляет пользовательский интерфейс команды в зависимости от наличия действительного значка в документе. Переопределить эту функцию, чтобы изменить поведение.

## <a name="coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu

Вызывается в рамках для обновления команды Ссылки в меню Edit.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, представляющую меню, генерируемое командой обновления. Обработчик обновления `Enable` вызывает функцию члена `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Начиная с первого элемента `OnUpdateEditLinksMenu` OLE в документе, доступ к каждому элементу, проверяет, является ли элемент ссылкой, и, если это ссылка, позволяет команде Ссылки. Переопределить эту функцию, чтобы изменить поведение.

## <a name="coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnupdateObjectVerbMenu

Вызов в фреймворк для обновления команды *ObjectName* в меню Edit и подменю Verb, доступ к которому из команды *ObjectName,* где *ObjectName* — это имя объекта OLE, встроенного в документ.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, представляющую меню, генерируемое командой обновления. Обработчик обновления `Enable` вызывает функцию члена `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

`OnUpdateObjectVerbMenu`обновляет пользовательский интерфейс команды *ObjectName* в зависимости от наличия действительного объекта в документе. Если объект существует, включена команда *ObjectName* в меню Edit. При выборе этой команды меню отображается подменю verb. Подменю Verb содержит все команды глагола, доступные для объекта, такие как Edit, Properties и так далее. Переопределить эту функцию, чтобы изменить поведение.

## <a name="coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu

Вызывается по системе, чтобы определить, может ли связанный элемент OLE быть вставлен из Clipboard.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, представляющую меню, генерируемое командой обновления. Обработчик обновления `Enable` вызывает функцию члена `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Специальная команда меню Вставить включена или отключена в зависимости от того, можно ли вставить элемент в документ или нет.

## <a name="coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu

Вызывается по системе, чтобы определить, можно ли ввести встроенный элемент OLE из Clipboard.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, представляющую меню, генерируемое командой обновления. Обработчик обновления `Enable` вызывает функцию члена `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Команда меню вставки и кнопка включены или отключены в зависимости от того, можно ли вставить элемент в документ или нет.

## <a name="coledocumentremoveitem"></a><a name="removeitem"></a>ColeDocument::RemoveItem

Вызовите эту функцию, чтобы удалить элемент из документа.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, который будет удален.

### <a name="remarks"></a>Примечания

Обычно вам не нужно называть эту функцию явно; он называется деструкторов для `COleClientItem` `COleServerItem`и .

## <a name="coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag

Позвоните в эту функцию, чтобы отметить документ как измененный, если какие-либо из содержащихся элементов OLE были изменены.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Примечания

Это позволяет системе побудить пользователя сохранить документ до закрытия, даже если родные данные в документе не были изменены.

## <a name="see-also"></a>См. также раздел

[MFC Образец CONTAINER](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
