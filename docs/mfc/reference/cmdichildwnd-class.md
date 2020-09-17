---
title: Класс CMDIChildWnd
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: 0acd42db19151001d9e292561ef20e469f9e14ea
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222970"
---
# <a name="cmdichildwnd-class"></a>Класс CMDIChildWnd

Предоставляет функции дочернего окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMDIChildWnd:: CMDIChildWnd](#cmdichildwnd)|Формирует объект `CMDIChildWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDIChildWnd:: Create](#create)|Создает дочернее окно Windows MDI, связанное с `CMDIChildWnd` объектом.|
|[CMDIChildWnd:: Жетмдифраме](#getmdiframe)|Возвращает родительский фрейм MDI окна клиента MDI.|
|[CMDIChildWnd:: Мдиактивате](#mdiactivate)|Активирует это дочернее окно MDI.|
|[CMDIChildWnd:: Мдидестрой](#mdidestroy)|Уничтожает это дочернее окно MDI.|
|[CMDIChildWnd:: Мдимаксимизе](#mdimaximize)|Разворачивает это дочернее окно MDI.|
|[CMDIChildWnd:: Мдиресторе](#mdirestore)|Восстанавливает дочернее окно MDI из развернутого или минимального размера.|
|[CMDIChildWnd:: Сесандлес](#sethandles)|Задает дескрипторы для ресурсов меню и ускорителя.|

## <a name="remarks"></a>Примечания

Дочернее окно MDI во многом похоже на обычное окно фрейма, за исключением того, что дочернее окно MDI отображается в окне фрейма MDI, а не на рабочем столе. Дочернее окно MDI не имеет собственной строки меню, а разделяет меню окна фрейма MDI. Платформа автоматически изменяет меню фрейма MDI для представления текущего активного дочернего окна MDI.

Чтобы создать полезное дочернее окно MDI для приложения, создайте класс, производный от `CMDIChildWnd` . Добавьте переменные члена в производный класс для хранения данных, относящихся к вашему приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Существует три способа создания дочернего окна MDI:

- Напрямую создавать его с помощью `Create` .

- Напрямую создавать его с помощью `LoadFrame` .

- Косвенно создать его с помощью шаблона документа.

Перед вызовом `Create` или `LoadFrame` необходимо создать объект окна фрейма в куче с помощью **`new`** оператора C++. Перед вызовом можно `Create` также зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Используйте `Create` функцию члена для передачи параметров создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов `Create` , чем, и вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню. Чтобы иметь доступ к `LoadFrame` , все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Если `CMDIChildWnd` объект содержит представления и документы, они создаются косвенно платформой, а не непосредственно программистом. `CDocTemplate`Объект управляет созданием фрейма, созданием содержащихся представлений и подключением представлений к соответствующему документу. Параметры `CDocTemplate` конструктора указывают, какие `CRuntimeClass` из трех участвующих классов (документ, фрейм и представление). `CRuntimeClass`Объект используется платформой для динамического создания новых фреймов при их указании пользователем (например, с помощью команды файл создать или окна «создать»).

Класс фреймового окна, производный от, `CMDIChildWnd` должен быть объявлен с DECLARE_DYNCREATE, чтобы механизм RUNTIME_CLASS работал правильно.

`CMDIChildWnd`Класс наследует большую часть своей реализации по умолчанию из `CFrameWnd` . Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) . `CMDIChildWnd`Класс имеет следующие дополнительные возможности:

- В сочетании с `CMultiDocTemplate` классом несколько `CMDIChildWnd` объектов из одного шаблона документа совместно используют одно и то же меню, сохраняя системные ресурсы Windows.

- Активное в настоящее время меню дочернего окна MDI полностью заменяет меню окна фрейма MDI, а заголовок текущего активного дочернего окна MDI добавляется в заголовок окна фрейма MDI. Дополнительные примеры функций дочерних окон MDI, реализованных в сочетании с окном фрейма MDI, см. в `CMDIFrameWnd` описании класса.

Не используйте **`delete`** оператор C++ для уничтожения окна фрейма. Используйте вместо этого `CWnd::DestroyWindow`. `CFrameWnd`Реализация служб `PostNcDestroy` удалит объект C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, обработчик по умолчанию `OnClose` выполнит вызов `DestroyWindow` .

Дополнительные сведения о см `CMDIChildWnd` . в разделе [окна с рамками](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd:: CMDIChildWnd

Вызовите метод, чтобы создать `CMDIChildWnd` объект.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` , чтобы создать видимое окно.

### <a name="example"></a>Пример

  См. пример для [CMDIChildWnd:: Create](#create).

## <a name="cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd:: Create

Вызовите эту функцию-член, чтобы создать дочернее окно Windows MDI и присоединить его к `CMDIChildWnd` объекту.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзкласснаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая именует класс Windows (структуру [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw) ). Имя класса может быть любым именем, зарегистрированным в глобальной функции [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) . Для стандарта должно быть задано значение NULL `CMDIChildWnd` .

*лпсзвиндовнаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая представляет имя окна. Используется в качестве текста для заголовка окна.

*двстиле*<br/>
Задает атрибуты [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) окна. Требуется стиль WS_CHILD.

*rect*<br/>
Содержит размер и расположение окна. Это `rectDefault` значение позволяет Windows указать размер и расположение нового объекта `CMDIChildWnd` .

*ппарентвнд*<br/>
Задает родительский элемент окна. Если значение равно NULL, используется главное окно приложения.

*pContext*<br/>
Задает структуру [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) . Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

В текущем активном окне дочернего фрейма MDI можно определить заголовок родительского окна фрейма. Эта функция отключена путем отключения FWS_ADDTOTITLE бит стиля окна дочернего фрейма.

Платформа вызывает эту функцию-член в ответ на команду пользователя для создания дочернего окна, а платформа использует параметр *пконтекст* для правильного подключения дочернего окна к приложению. При вызове `Create` метод *пконтекст* может иметь значение null.

### <a name="example"></a>Пример

Пример 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Пример

Пример 2.

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd:: Жетмдифраме

Вызовите эту функцию, чтобы вернуть родительский фрейм MDI.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно родительского фрейма MDI.

### <a name="remarks"></a>Примечания

Возвращенный кадр состоит из двух родителей, удаленных из `CMDIChildWnd` и является родителем окна типа мдиклиент, которое управляет `CMDIChildWnd` объектом. Вызовите функцию-член- [родитель](../../mfc/reference/cwnd-class.md#getparent) , чтобы вернуть `CMDIChildWnd` непосредственный родительский мдиклиент объекта в качестве временного `CWnd` указателя.

### <a name="example"></a>Пример

  См. пример для [CMDIFrameWnd:: мдисетмену](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd:: Мдиактивате

Вызовите эту функцию-член, чтобы активировать дочернее окно MDI независимо от окна фрейма MDI.

```cpp
void MDIActivate();
```

### <a name="remarks"></a>Примечания

Когда кадр становится активным, также активируется дочернее окно, которое было активировано последним.

### <a name="example"></a>Пример

  См. пример для [CMDIFrameWnd:: жетвиндовменупопуп](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd:: Мдидестрой

Вызовите эту функцию-член для уничтожения дочернего окна MDI.

```cpp
void MDIDestroy();
```

### <a name="remarks"></a>Примечания

Функция члена удаляет заголовок дочернего окна из окна фрейма и деактивирует дочернее окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd:: Мдимаксимизе

Вызовите эту функцию-член, чтобы развернуть дочернее окно MDI.

```cpp
void MDIMaximize();
```

### <a name="remarks"></a>Примечания

Когда дочернее окно разворачивается, Windows изменяет его размер, чтобы заполнить клиентскую область окна фрейма. Windows помещает меню элемента управления дочернего окна в строке меню фрейма, чтобы пользователь мог восстановить или закрыть дочернее окно и добавить заголовок дочернего окна в заголовок фрейма окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd:: Мдиресторе

Вызывайте эту функцию-член для восстановления дочернего окна MDI из развернутого или минимального размера.

```cpp
void MDIRestore();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd:: Сесандлес

Задает дескрипторы для ресурсов меню и ускорителя.

```cpp
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Маркер ресурса меню.

*хакцел*<br/>
Маркер ресурса ускорителя.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы задать ресурсы меню и ускорителя, используемые объектом дочернего окна MDI.

## <a name="see-also"></a>См. также статью

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример МДИДОКВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)
