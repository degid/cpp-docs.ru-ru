---
title: Класс CUserToolsManager
ms.date: 11/04/2016
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
ms.openlocfilehash: 1e9be5d7cb81f2769b98d9baeae786873f5fa73d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751982"
---
# <a name="cusertoolsmanager-class"></a>Класс CUserToolsManager

Поддерживает коллекцию объектов [класса CUserTool](../../mfc/reference/cusertool-class.md) в приложении. Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Объект `CUserToolsManager` позволяет пользователю или разработчику добавить в приложение новые пользовательские инструменты. Он поддерживает выполнение команд, связанных со средствами пользователя, а также сохраняет сведения о пользовательских средствах в реестре Windows.

## <a name="syntax"></a>Синтаксис

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Создает документ `CUserToolsManager`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CUserToolsManager::CreateNewTool](#createnewtool)|Создает новый пользовательский инструмент.|
|[CUserToolsManager::FindTool](#findtool)|Возвращает указатель объекту, `CMFCUserTool` связанного с определенным идентификатором команды.|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Возвращает идентификатор ресурса, связанный с меню **Аргументы,** на вкладке **«Инструменты»** в поле **настраиваемых** диалогов.|
|[CUserToolsManager::GetDefExt](#getdefext)|Возвращает расширение по умолчанию, которое файл **Open** диалоговый ящик [(CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) использует в поле **команды** на вкладке **Инструменты** **настраиваемого** диалогового окна.|
|[CUserToolsManager::GetFilter](#getfilter)|Возвращает файловый фильтр, который файл **Open** диалоговый ящик [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)использует в поле **командования** на вкладке **Tools** box of the **Customize** dialog.|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Возвращает идентификатор ресурса, связанный с меню **Исходного каталога,** на вкладке **«Инструменты»** в поле **настраиваемых** диалогов.|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Возвращает максимальное количество пользовательских инструментов, которые могут быть выделены в приложении.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Возвращает идентификатор команды заполнителя элемента меню для пользовательских инструментов.|
|[CUserToolsManager::GetUserTools](#getusertools)|Возвращает ссылку на список пользовательских инструментов.|
|[CUserToolsManager::InvokeTool](#invoketool)|Выполняет приложение, связанное с пользовательским инструментом, который имеет определенный идентификатор команды.|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Определяет, связан ли идентификатор команды с пользовательским инструментом.|
|[CUserToolsManager::LoadState](#loadstate)|Загружает информацию об пользовательских инструментах из реестра Windows.|
|[CUserToolsManager::MoveToolDown](#movetooldown)|Перемещает указанный пользовательский инструмент вниз в списке пользовательских инструментов.|
|[CUserToolsManager::MoveToolUp](#movetoolup)|Перемещает указанный пользовательский инструмент в список пользовательских инструментов.|
|[CUserToolsManager::RemoveTool](#removetool)|Удаляет указанный пользовательский инструмент из приложения.|
|[CUserToolsManager::SaveState](#savestate)|Хранит информацию об пользовательских инструментах в реестре Windows.|
|[CUserToolsManager::SetDefExt](#setdefext)|Упомяните расширение по умолчанию, которое файл **Открыть** диалоговое окно [(CFileDialog класса](../../mfc/reference/cfiledialog-class.md)) использует в поле **команды** на вкладке **Инструменты** **настраиваемый** диалоговый ящик.|
|[CUserToolsManager::SetFilter](#setfilter)|Упоняет файловый фильтр, который файл **Open** диалоговый ящик [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)используется в поле **Командования** на вкладке **Tools** box of **the Customize** dialog.|

## <a name="remarks"></a>Примечания

Чтобы включить пользовательские инструменты в приложение, необходимо:

1. Зарезервируйте элемент меню и связанный с ним идентификатор команды для входа в меню пользовательского инструмента.

2. Зарезервируйте последовательный идентификатор команды для каждого пользователя, который пользователь может определить в вашем приложении.

3. Позвоните в [метод CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) и подавайте следующие параметры: идентификатор команды меню, первый идентификатор команды пользователя и последний идентификатор команды пользователя.

В приложении должен `CUserToolsManager` быть только один глобальный объект.

Например, в качестве примера инструментов для пользователей можно ознакомиться на примере проекта VisualStudioDemo.

## <a name="example"></a>Пример

В следующем примере показано, как получить `CUserToolsManager` ссылку на объект и как создать новые инструменты пользователя. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxusertoolsmanager.h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a>CUserToolsManager::CreateNewTool

Создает новый пользовательский инструмент.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на недавно созданный пользовательский инструмент, или NULL, если количество пользовательских инструментов превысило максимум. Возвращается тип такой же, как тип, который передается `CWinAppEx::EnableUserTools` в качестве параметра *pToolRTC.*

### <a name="remarks"></a>Примечания

Этот метод находит первый доступный идентификатор команды меню в диапазоне, который поставляется в вызове [cWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) и назначает пользователю этот идентификатор.

Метод выходит из строя, если количество инструментов достигло максимума. Это происходит, когда все иные иудки команд в диапазоне присваиваются пользовательским инструментам. Вы можете получить максимальное количество инструментов, позвонив [cUserToolsManager::GetMaxTools](#getmaxtools). Вы можете получить доступ к списку инструментов, позвонив в [CUserToolsManager::GetUserTools](#getusertools) метод.

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager

Создает документ `CUserToolsManager`. Каждое приложение должно иметь не более одного менеджера пользовательских инструментов.

```
CUserToolsManager();

CUserToolsManager(
    const UINT uiCmdToolsDummy,
    const UINT uiCmdFirst,
    const UINT uiCmdLast,
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),
    UINT uArgMenuID=0,
    UINT uInitDirMenuID=0);
```

### <a name="parameters"></a>Параметры

*uiCmdToolsDummy*<br/>
(в) Неподписанный целый ряд, который фреймворк использует в качестве заполнителя для идентификатора команды меню пользовательских инструментов.

*uiCmdFirst*<br/>
(в) Идентификатор команды для первой команды пользователя.

*uiCmdLast*<br/>
(в) Идентификатор команды для последней команды пользователя.

*pToolRTC*<br/>
(в) Класс, который создает [CUserToolsManager::CreateNewTool.](#createnewtool) Используя этот класс, можно использовать производный тип [класса CUserTool](../../mfc/reference/cusertool-class.md) вместо реализации по умолчанию.

*uArgMenuID*<br/>
(в) Идентификатор ресурса меню всплывающих меню аргументов.

*uInitDirMenuID*<br/>
(в) Идентификатор ресурса меню начального всплывающее меню каталога.

### <a name="remarks"></a>Примечания

Не называйте этот конструктор. Вместо этого позвоните [в CWinAppEx::EnableUserTools,](../../mfc/reference/cwinappex-class.md#enableusertools) чтобы включить пользовательские инструменты, и позвоните `CUserToolsManager` [cWinAppEx::GetUserToolsManager,](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) чтобы получить указатель на . Для получения дополнительной [User-defined Tools](../../mfc/user-defined-tools.md)информации см.

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a>CUserToolsManager::FindTool

Возвращает указатель на объект [класса CUserTool,](../../mfc/reference/cusertool-class.md) связанный с указанным идентификатором команды.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
(в) Идентификатор команды меню.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CUserTool](../../mfc/reference/cusertool-class.md) класса `CUserTool`или -производные объекта, если успех; в противном случае NULL.

### <a name="remarks"></a>Примечания

Когда `FindTool` он успешен, тип возврата такой же, как тип параметра *pToolRTC* для [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID

Возвращает идентификатор ресурса, связанный с меню **Аргументы,** на вкладке **«Инструменты»** в поле **настраиваемых** диалогов.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню.

### <a name="remarks"></a>Примечания

Параметр *uArgMenuID* [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) определяет идентификатор ресурса.

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a>CUserToolsManager::GetDefExt

Возвращает расширение по умолчанию, которое файл **Open** диалоговый ящик [(CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) использует в поле **команды** на вкладке **Инструменты** **настраиваемого** диалогового окна.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CString` объект, содержащий расширение.

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a>CUserToolsManager::GetFilter

Возвращает файловый фильтр, который файл **Open** диалоговый ящик [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)использует в поле **командования** на вкладке **Tools** box of the **Customize** dialog.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CString` объект, содержащий фильтр.

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID

Возвращает идентификатор ресурса, связанный с меню **Исходного каталога,** на вкладке **«Инструменты»** в поле **настраиваемых** диалогов.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурсов меню.

### <a name="remarks"></a>Примечания

Возвратный идентификатор указан в параметре *uInitDirMenuID* [CWinAppEx:EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a>CUserToolsManager::GetMaxTools

Возвращает максимальное количество пользовательских инструментов, которые могут быть выделены в приложении.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество пользовательских инструментов, которые могут быть выделены.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить максимальное количество инструментов, которые могут быть выделены в приложении. Это число является числом инт-идов в диапазоне от *uiCmdFirst* через *uiCmdLast* параметров, которые вы передайте [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd

Возвращает идентификатор команды заполнителя элемента меню для пользовательских инструментов.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды заполнителя.

### <a name="remarks"></a>Примечания

Для включения пользовательских инструментов вы [звоните CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Параметр *uiCmdToolsDummy* определяет идентификатор команды команды входа инструментов. Этот метод возвращает идентификатор команды входа инструментов. Везде, где этот идентификатор используется в меню, он заменяется списком пользовательских инструментов при поясне меню.

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a>CUserToolsManager::GetUserTools

Возвращает ссылку на список пользовательских инструментов.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект [класса CObList,](../../mfc/reference/coblist-class.md) содержащий список пользовательских инструментов.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить список пользовательских инструментов, которые поддерживает объект [CUserToolsManager.](../../mfc/reference/cusertoolsmanager-class.md) Каждый пользовательский инструмент представлен объектом [типа CUserTool Class](../../mfc/reference/cusertool-class.md) `CUserTool`или типом, полученным из. Тип указан параметром *pToolRTC* при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских инструментов.

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a>CUserToolsManager::InvokeTool

Выполняет приложение, связанное с пользовательским инструментом, который имеет определенный идентификатор команды.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
(в) Идентификатор команды меню, связанный с инструментом пользователя.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если команда, связанная с пользовательским инструментом, была успешно выполнена; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите этот метод для выполнения приложения, связанного с пользовательским инструментом, который имеет идентификатор команды, указанный *uiCmdId.*

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd

Определяет, связан ли идентификатор команды с пользовательским инструментом.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
(в) Идентификатор команды элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если данный идентификатор команды связан с пользовательским инструментом; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод проверяет, находится ли данный идентификатор команды в диапазоне идентификаторов команд. Вы указываете диапазон при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских инструментов.

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a>CUserToolsManager::LoadState

Загружает информацию об пользовательских инструментах из реестра Windows.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь ключа реестра Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если государство было загружено успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод загружает `CUserToolsManager` состояние объекта из реестра Windows.

Как правило, этот метод не называется напрямую. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) называет его частью процесса инициализации рабочей области.

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a>CUserToolsManager::MoveToolDown

Перемещает указанный пользовательский инструмент вниз в списке пользовательских инструментов.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
(в) Определяет пользовательский инструмент для перемещения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользовательский инструмент был успешно перемещен вниз; в противном случае 0.

### <a name="remarks"></a>Примечания

Метод не удается, если инструмент, который *pTool* определяет не во внутреннем списке или если инструмент является последним в списке.

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a>CUserToolsManager::MoveToolUp

Перемещает указанный пользовательский инструмент в список пользовательских инструментов.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
(в) Определяет пользовательский инструмент для перемещения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользовательский инструмент был успешно перемещен; в противном случае 0.

### <a name="remarks"></a>Примечания

Метод завершается неудачей, если инструмент, который указывает параметр *pTool,* не находится во внутреннем списке или если инструмент является первым элементом инструмента в списке.

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a>CUserToolsManager::RemoveTool

Удаляет указанный пользовательский инструмент из приложения.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
(в, вне) Указатель на пользовательский инструмент, который будет удален.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если инструмент успешно удален. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если инструмент успешно удален, этот метод удаляет *pTool.*

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a>CUserToolsManager::SaveState

Хранит информацию об пользовательских инструментах в реестре Windows.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь к ключу реестра Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если государство было сохранено успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Метод хранит текущее состояние `CUserToolsManager` объекта в реестре Windows.

Обычно вам не нужно вызывать этот метод напрямую, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) вызывает его автоматически как часть процесса сериализации рабочего пространства приложения.

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a>CUserToolsManager::SetDefExt

Упомяните расширение по умолчанию, которое файл **Открыть** диалоговое окно [(CFileDialog класса](../../mfc/reference/cfiledialog-class.md)) использует в поле **команды** на вкладке **Инструменты** **настраиваемый** диалоговый ящик.

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Параметры

*strDefExt*<br/>
(в) Текстовая строка, содержащая расширение имени файла по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать расширение имени файла по умолчанию в диалоговом поле **File Open,** которое отображается при выборе приложением для ассоциирования с пользователем. По умолчанию является "exe".

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a>CUserToolsManager::SetFilter

Упоняет файловый фильтр, который файл **Open** диалоговый ящик [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)используется в поле **Командования** на вкладке **Tools** box of **the Customize** dialog.

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Параметры

*strFilter*<br/>
(в) Определяет фильтр.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Класс CUserTool](../../mfc/reference/cusertool-class.md)
