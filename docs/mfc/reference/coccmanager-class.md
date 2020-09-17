---
title: Класс COccManager
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: 5637a4709e90bb14caff3fe4e396487e62e213e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360353"
---
# <a name="coccmanager-class"></a>Класс COccManager

Управляет разными сайтами пользовательского элемента управления, реализованного объектами `COleControlContainer` и `COleControlSite` .

## <a name="syntax"></a>Синтаксис

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|Создает объект `COleContainer`.|
|[COccManager::CreateDlgControls](#createdlgcontrols)|Создает элементы управления ActiveX, размещенные соответствующим `COleContainer` объектом.|
|[COccManager::CreateSite](#createsite)|Создает объект `COleClientSite`.|
|[COccManager::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопки по умолчанию.|
|[COccManager::IsDialogMessage](#isdialogmessage)|Определяет цель сообщения диалога.|
|[COccManager::IsLabelControl](#islabelcontrol)|Определяет, является ли указанный элемент управления меткой.|
|[COccManager::IsMatchingMmonic](#ismatchingmnemonic)|Определяет, соответствует ли текущий мнемонический мнемоник указанному элементу управления.|
|[COccManager::Onevent](#onevent)|Попытки обработки указанного события.|
|[COccManager::PostCreateDialog](#postcreatedialog)|Освобождает ресурсы, выделенные при создании диалога.|
|[COccManager::PreCreateDialog](#precreatedialog)|Обрабатывает шаблон диалога для элементов управления ActiveX.|
|[COccManager::SetDefaultButton](#setdefaultbutton)|Переключает состояние по умолчанию указанного элемента управления.|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Отделяет любые существующие элементы управления ActiveX от общих элементов управления в указанном шаблоне диалога.|

## <a name="remarks"></a>Примечания

Базовый класс, `CNoTrackObject`является незарегистрированным базовым классом (расположен в AFXTLS. H). Классы, полученные из `CNoTrackObject` класса, освобождаются от обнаружения утечки памяти. Не рекомендуется, чтобы вы `CNoTrackObject`получаете непосредственно от .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxocc.h

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a>COccManager::CreateContainer

Вызывается фреймворком для создания контейнера управления.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект окна, связанный с пользовательским контейнером сайта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный контейнер; в противном случае NULL.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о создании пользовательских сайтов, [см. COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>COccManager::CreateDlgControls

Вызовите эту функцию для создания элементов управления ActiveX, указанных по параметру *pOccDialogInfo.*

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
Указатель на родительский объект диалога.

*lpszResourceName*<br/>
Название создаваемого ресурса.

*pOccDialogInfo*<br/>
Указатель шаблона диалогов, используемого для создания объекта диалога.

*lpResource*<br/>
Указатель на ресурс.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент управления был создан успешно; в противном случае ноль.

## <a name="coccmanagercreatesite"></a><a name="createsite"></a>COccManager::CreateSite

Вызывается рамки для создания сайта управления, размещенные на контейнере указал *на pCtrlCont*.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Параметры

*pCtrlCont*<br/>
Указатель на контрольный контейнер, принимающий новый контрольный участок.

### <a name="return-value"></a>Возвращаемое значение

Указатель на недавно созданный сайт управления.

### <a name="remarks"></a>Примечания

Переизвейдите эту функцию для создания пользовательского сайта управления, используя ваш класс [COleControlSite.](../../mfc/reference/colecontrolsite-class.md)

Каждый контейнер управления может размещать несколько сайтов. Создание дополнительных сайтов `CreateSite`с несколькими вызовами.

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>COccManager::GetDefBtnCode

Вызов исчерпнивите эту функцию, чтобы определить, является ли элемент управления кнопкой нажатия по умолчанию.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащий управление кнопкой.

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

- DLGC_DEFPUSHBUTTON управление — это кнопка по умолчанию в диалоге.

- DLGC_UNDEFPUSHBUTTON управление не является кнопкой по умолчанию в диалоге.

- **0** Управление не является кнопкой.

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>COccManager::IsDialogMessage

Вызывается фректовой, чтобы определить, предназначено ли сообщение для указанного окна диалога, и, если это так, обрабатывает сообщение.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*pWndDlg*<br/>
Указатель на целевой диалог сообщения.

*lpMsg*<br/>
Указатель на `MSG` структуру, содержащую проверенное сообщение.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение обработано; в противном случае ноль.

### <a name="remarks"></a>Примечания

Поведение по `IsDialogMessage` умолчанию состоит в том, чтобы проверить сообщения клавиатуры и преобразовать их в выбор для соответствующего диалогового окна. Например, ключ TAB при нажатии выбирает следующий элемент управления или группу элементов управления.

Переопределить эту функцию, чтобы обеспечить пользовательское поведение для сообщений, отправляемых в указанный диалог.

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>COccManager::IsLabelControl

Вызов исчерпнивите эту функцию, чтобы определить, является ли указанный элемент управления меткой.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент управления является меткой; в противном случае ноль

### <a name="remarks"></a>Примечания

Контроль метки — это элемент, который действует как метка для любого элемента управления, следующего в порядке.

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>COccManager::IsMatchingMmonic

Вызовите эту функцию, чтобы определить, совпадают ли текущие мнемонические, представленные элементом управления.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

*lpMsg*<br/>
Указатель на сообщение, содержащее мнемоника, чтобы соответствовать.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если мнемоническая соответствует контролю; в противном случае ноль

### <a name="remarks"></a>Примечания

## <a name="coccmanageronevent"></a><a name="onevent"></a>COccManager::Onevent

Вызывается по системе для обработки указанного события.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*pCmdTarget*<br/>
Указатель на `CCmdTarget` объект, пытающийся справиться с событием

*idCtrl*<br/>
Идентификатор ресурса элемента управления.

*pEvent*<br/>
Мероприятие обрабатывается.

*pHandlerInfo*<br/>
Если не `OnEvent` NULL, `pTarget` заполняет `pmf` и `AFX_CMDHANDLERINFO` членов структуры вместо отправки команды. Как правило, этот параметр должен быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если событие было обработано, в противном случае ноль.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы настроить процесс обработки событий по умолчанию.

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>COccManager::PreCreateDialog

Вызывается инфраструктурой для обработки шаблона диалога для элементов управления ActiveX перед созданием фактического окна диалога.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
Структура, `_AFX_OCC_DIALOG_INFO` содержащая информацию о шаблоне диалога и любых элементах управления ActiveX, размещенных в диалоге.

*pOrigTemplate*<br/>
Указатель на шаблон диалогов, который будет использоваться при создании диалогового окна.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогов, используемую для создания диалогового окна.

### <a name="remarks"></a>Примечания

Поведение по умолчанию `SplitDialogTemplate`делает вызов, определяющий, есть ли какие-либо элементы управления ActiveX настоящее время, а затем возвращает резонирующее шаблон диалога.

Переопределить эту функцию, чтобы настроить процесс создания диалогового окна, в которой размещаются элементы управления ActiveX.

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>COccManager::PostCreateDialog

Вызывается инфраструктурой для свободной памяти, выделенной для шаблона диалога.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
Структура, `_AFX_OCC_DIALOG_INFO` содержащая информацию о шаблоне диалога и любых элементах управления ActiveX, размещенных в диалоге.

### <a name="remarks"></a>Примечания

Эта память была выделена `SplitDialogTemplate`путем вызова, и использовалась для любых размещенных элементов управления ActiveX в диалоговом поле.

Переопределить эту функцию, чтобы настроить процесс очистки любых ресурсов, используемых объектом диалоговой коробки.

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>COccManager::SetDefaultButton

Вызов ими функции, чтобы установить элемент управления в качестве кнопки по умолчанию.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

*bDefault*<br/>
Nonzero, если элемент управления должен стать кнопкой по умолчанию; в противном случае ноль.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Элемент управления должен иметь набор бита OLEMISC_ACTSLIKEBUTTON статуса. Для получения дополнительной информации о [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) флагах OLEMISC, см.

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate

Вызывается фреймворком для разделения элементов управления ActiveX от общих элементов управления диалогом.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Параметры

*pTemplate*<br/>
Указатель на шаблон диалога, который будет рассмотрен.

*ppOleDlgItems*<br/>
Список указателей на элементы диалоговых коробок, которые являются элементами управления ActiveX.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогов, содержащую только элементы управления ActiveX. Если элементов управления ActiveX нет, NULL возвращается.

### <a name="remarks"></a>Примечания

При обнаружении каких-либо элементов управления ActiveX анализируется шаблон и создается новый шаблон, содержащий только элементы управления ActiveX. Любые элементы управления ActiveX, найденные в ходе этого процесса, добавляются *в ppOleDlgItems.*

Если в шаблоне нет элементов управления ActiveX, NULL *возвращается.*

> [!NOTE]
> Память, выделенная для нового `PostCreateDialog` шаблона, освобождается в функции.

Переопределить эту функцию, чтобы настроить этот процесс.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)<br/>
[Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)
