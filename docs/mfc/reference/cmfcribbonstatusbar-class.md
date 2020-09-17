---
title: Класс CMFCRibbonStatusBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: 8d90e01db022c33edd654e83af05e9986799f2b9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754054"
---
# <a name="cmfcribbonstatusbar-class"></a>Класс CMFCRibbonStatusBar

Класс `CMFCRibbonStatusBar` реализует элементы панели статуса, которые могут отображать элементы ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Добавляет динамический элемент в бар состояния ленты.|
|[CMFCRibbonStatusBar::AddElement](#addelement)|Добавляет новый элемент ленты в бар статуса ленты.|
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Добавляет элемент ленты в расширенную область ленты статус бар.|
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Добавляет сепаратор в ленточное положение.|
|[CMFCRibbonStatusBar::Создание](#create)|Создает ленту статус бар.|
|[CMFCRibbonStatusBar::CreateEx](#createex)|Создает лента статус бар с расширенным стилем.|
|[CMFCRibbonStatusBar:FindbyID](#findbyid)||
|[CMFCRibbonStatusBar::FindElement](#findelement)|Возвращает указатель элементу с указанным идентификатором команды.|
|[CMFCRibbonStatusBar::GetCount](#getcount)|Возвращает количество элементов, которые расположены в основной области ленты статус бар.|
|[CMFCRibbonStatusBar::GetElement](#getelement)|Возвращает указатель элементу, расположенному в указанном индексе.|
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Возвращает количество элементов, расположенных в расширенной области ленты статус бар.|
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты.|
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCRibbonStatusBar::GetSpace](#getspace)||
|[CMFCRibbonStatusBar::IsbottomFrame](#isbottomframe)||
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||
|[CMFCRibbonStatusBar::IsinformationMode](#isinformationmode)|Определяет, включен ли информационный режим для панели состояния ленты.|
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Переопределяет [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Удаляет все элементы из ленты статус а.|
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Удаляет элемент с указанным идентификатором команды из панели состояния ленты.|
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Позволяет или отсвагает информационный режим для ленты статус бар.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBar::OndrawInformation](#ondrawinformation)|Отображает строку информации, которая отображается на строке состояния ленты при включении информационного режима.|

## <a name="remarks"></a>Примечания

Пользователи могут изменить видимость элементов ленты на ленте статус бар с помощью встроенного контекстного меню для ленты статус бар. Вы можете добавлять или удалять элементы динамически.

Бар статуса ленты имеет две области: основную область и расширенную область. Расширенная область отображается на правой стороне ленты статус бар и появляется в другом цвете, чем основная область делает.

Как правило, основная область панели статуса отображает уведомления о состоянии, а расширенная область отображает элементы управления представлениями. Расширенная область остается видимой как можно дольше, когда пользователь изменяет планку состояния ленты.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonStatusBar` . На примере показано, как добавить новый элемент ленты в бар состояния ленты, добавить элемент ленты в расширенную область ленты статус бар, добавить сепаратор, и включить регулярный режим для ленты статус бар.

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonstatusbar.h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a>CMFCRibbonStatusBar::AddDynamicElement

Добавляет динамический элемент в бар состояния ленты.

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>Параметры

*pElement*<br/>
(в) Указатель на динамический элемент.

### <a name="remarks"></a>Примечания

В отличие от обычных элементов, динамические элементы не настраиваются и настраиваемое меню панели статуса не отображает их.

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a>CMFCRibbonStatusBar::AddElement

Добавляет новый элемент ленты в бар статуса ленты.

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Параметры

*pElement*<br/>
(в) Указатель на добавленный элемент.

*lpszLabel*<br/>
(в) Текстовая метка элемента.

*bIsVisible*<br/>
(в) ПРАВДА, если вы хотите добавить элемент, как видимые, FALSE, если вы хотите добавить элемент как скрытый.

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement

Добавляет элемент ленты в расширенную область ленты статус бар.

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Параметры

*pElement*<br/>
(в) Указатель на добавленный элемент.

*lpszLabel*<br/>
(в) Текстовая метка элемента.

*bIsVisible*<br/>
(в) ПРАВДА, если вы хотите добавить элемент, как видимые, FALSE, если вы хотите добавить элемент как скрытый.

### <a name="remarks"></a>Примечания

Расширенная область находится в правой части элемента управления состоянием строки.

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator

Добавляет сепаратор в ленточное положение.

```cpp
void AddSeparator();
```

### <a name="remarks"></a>Примечания

Платформа добавляет сепаратор по методу [CMFCRibbonStatusBar::AddElement](#addelement). вставляет последний элемент.

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a>CMFCRibbonStatusBar::Создание

Создает ленту статус бар.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в) Указатель на родительское окно.

*dwStyle*<br/>
(в) Логическое или сочетание стилей управления.

*nID*<br/>
(в) Идентификатор управления панели статуса.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если статус бар создан успешно, FALSE в противном случае.

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a>CMFCRibbonStatusBar::CreateEx

Создает лента статус бар, который имеет расширенный стиль.

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно.

*dwCtrlStyle*<br/>
Логическое или сочетание дополнительных стилей для создания объекта панели статуса.

*dwStyle*<br/>
Стиль управления адвокатской сословием статуса.

*nID*<br/>
Идентификатор управления панели статуса.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если статус бар создан успешно, FALSE в противном случае.

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a>CMFCRibbonStatusBar:FindbyID

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *uiCmdID*<br/>
(в) *БУЛ*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a>CMFCRibbonStatusBar::FindElement

Возвращает указатель элементу с указанным идентификатором команды.

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент с указанным идентификатором команды. NULL, если нет такого элемента.

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a>CMFCRibbonStatusBar::GetCount

Возвращает количество элементов, которые расположены в основной области ленты статус бар.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, расположенных в основной области ленты статус бар.

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a>CMFCRibbonStatusBar::GetElement

Возвращает указатель элементу, расположенному в указанном индексе.

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс нулевой основе элемента, который находится в основной области управления баром статуса.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, расположенный в указанном индексе. NULL, если индекс отрицательный или превышает количество элементов в панели статуса.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount

Возвращает количество элементов, расположенных в расширенной области ленты статус бар.

```
int GetExCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, расположенных в расширенной области ленты статус бар.

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement

Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. Расширенная область находится в правой части элемента управления состоянием строки.

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс нулевой основе элемента, расположенного в расширенной области управления панели статуса.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. NULL, если *nIndex* отрицательный или превышает количество элементов в расширенной области ленты статус бар.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a>CMFCRibbonStatusBar::GetSpace

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
int GetSpace() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a>CMFCRibbonStatusBar::IsbottomFrame

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>Параметры

(в) *pElement*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a>CMFCRibbonStatusBar::IsinformationMode

Определяет, включен ли информационный режим для панели состояния ленты.

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель статуса может работать в информационном режиме; в противном случае FALSE.

### <a name="remarks"></a>Примечания

В информационном режиме строка состояния скрывает все обычные панели и отображает строку сообщения.

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a>CMFCRibbonStatusBar::OndrawInformation

Отображает строку, которая отображается на панели состояния ленты при включении информационного режима.

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*strInfo*<br/>
(в) Информационная строка.

*rectInfo*<br/>
(в) Ограничивающий прямоугольник.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе, если вы хотите настроить внешний вид строки информации на строке статуса. Используйте [метод CMFCRibbonStatusBar::SetInformation,](#setinformation) чтобы поместить планку статуса в информационном режиме. В этом режиме строка состояния скрывает все панели и отображает строку информации, указанную *strInfo.*

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll

Удаляет все элементы из ленты статус а.

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement

Удаляет элемент с указанным идентификатором команды из панели состояния ленты.

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор элемента для удаления из панели статуса.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент с указанным *uiID* удаляется. FALSE в противном случае.

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation

Позволяет или отсвагает информационный режим для ленты статус бар.

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>Параметры

*lpszInfo*<br/>
(в) Информационная строка.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы поместить панель статуса в информационном режиме. В этом режиме строка состояния скрывает все панели и отображает строку информации, указанную *lpszInfo.*

Когда lpszInfo является NULL, панель статуса возвращается в обычный режим.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
