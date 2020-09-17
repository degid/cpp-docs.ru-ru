---
title: Класс CUserTool
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: 183b30961e4a7d3079fa0d035a4ddc38bc2eebac
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752028"
---
# <a name="cusertool-class"></a>Класс CUserTool

Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Вкладка **Tools** Box for the **Customize** dialog [(CMFCToolBarsCustomizeDialog Class)](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)позволяет пользователю добавлять инструменты пользователя и указывать имя, команду, аргументы и начальный каталог для каждого пользовательского инструмента.

## <a name="syntax"></a>Синтаксис

```
class CUserTool : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CUserTool::CopyiconToClipboard](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|Рисует значок пользовательского инструмента в указанном прямоугольнике.|
|[CUserTool::GetCommand](#getcommand)|Возвращает строку, содержащую текст команды, связанную с инструментом пользователя.|
|[CUserTool::GetCommandId](#getcommandid)|Возвращает идентификатор команды элемента меню пользователя.|
|[CUserTool::Invoke](#invoke)|Выполняет команду, связанную с пользовательским инструментом.|
|[CUserTool::Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CUserTool::SetCommand](#setcommand)|Устанавливает команду, связанную с пользовательским инструментом.|
|[CUserTool::SetToolIcon](#settoolicon)|Загружает значок для пользовательского инструмента из приложения, связанного с инструментом.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Загружает значок по умолчанию для пользовательского инструмента.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|Аргументы командной строки для пользовательского инструмента.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Первоначальный каталог для пользовательского инструмента.|
|[CUserTool::m_strLabel](#m_strlabel)|Имя инструмента, отображаемое в пункте меню для инструмента.|

## <a name="remarks"></a>Примечания

Для получения дополнительной информации о том, как включить пользовательские инструменты в приложении, [см.](../../mfc/reference/cusertoolsmanager-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как `CUserToolsManager` создать инструмент `m_strLabel` из объекта, установить переменную участника и установить приложение, которое выполняет пользовательский инструмент. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxusertool.h

## <a name="cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::CopyiconToClipboard

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon

Рисует значок пользовательского инструмента в центре указанного прямоугольника.

```cpp
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectImage*<br/>
(в) Определяет координаты области для отображения значка.

## <a name="cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::GetCommand

Возвращает строку, содержащую текст команды, связанную с инструментом пользователя.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка `CString` на объект, содержащий текст команды, связанный с пользовательским инструментом.

## <a name="cusertoolgetcommandid"></a><a name="getcommandid"></a>CUserTool::GetCommandId

Возвращает идентификатор команды пользователя.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды этого пользовательского инструмента.

## <a name="cusertoolinvoke"></a><a name="invoke"></a>CUserTool::Invoke

Выполняет команду, связанную с пользовательским инструментом.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если команда была выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывает [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) для выполнения команды, связанной с инструментом пользователя. Функция выходит из строя, если команда пуста или если [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) не работает.

## <a name="cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUserTool::LoadDefaultIcon

Загружает значок по умолчанию для пользовательского инструмента.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к загруженной иконке (HICON) или NULL, если значок по умолчанию не может быть загружен.

### <a name="remarks"></a>Примечания

Рамочная система вызывает этот метод, когда он не может загрузить значок для пользовательского инструмента из исполняемого файла инструмента.

Переизбь этот метод для предоставления собственного значка инструмента по умолчанию.

## <a name="cusertoolm_strarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments

Аргументы командной строки для пользовательского инструмента.

```
CString m_strArguments;
```

### <a name="remarks"></a>Примечания

Эта строка передается инструменту при вызове [CUserTool::Invoke](#invoke) или когда пользователь нажимает на команду, связанную с этим инструментом.

## <a name="cusertoolm_strinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory

Определяет начальный каталог для пользовательского инструмента.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Примечания

Эта переменная определяет исходный каталог, в который выполняется инструмент при вызове [CUserTool::Invoke](#invoke) или когда пользователь нажимает на команду, связанную с этим инструментом.

## <a name="cusertoolm_strlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel

Метка, отображаемый в пункте меню для инструмента.

```
CString m_strLabel;
```

## <a name="cusertoolserialize"></a><a name="serialize"></a>CUserTool::Serialize

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

[in] *ar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::SetCommand

Устанавливает приложение, которое запускает пользовательский инструмент.

```cpp
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Параметры

*lpszCmd*<br/>
(в) Упоняет новое приложение, связанное с пользовательским инструментом.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы установить новое приложение, которое запускает пользовательский инструмент. Метод разрушает старую иконку и загружает новую иконку из данного приложения. Если он не может загрузить значок из приложения, он загружает значок по умолчанию для пользовательского инструмента, позвонив [в CUserTool::LoadDefaultIcon.](#loaddefaulticon)

## <a name="cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::SetToolIcon

Загружает значок для пользовательского инструмента из приложения, которое использует инструмент.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к загруженной иконке.

### <a name="remarks"></a>Примечания

Вызовите этот метод для загрузки значка для отображения в пункте меню. Этот метод ищет значок в исполняемом файле, который использует инструмент. Если у него нет значка по умолчанию, вместо него используется значок [CUserTool::LoadDefaultIcon.](#loaddefaulticon)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Класс CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)
