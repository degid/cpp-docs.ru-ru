---
title: Класс CDialogImpl
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: b92b5130b31e88565d79b59a24b2bd377d0d84c0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834730"
---
# <a name="cdialogimpl-class"></a>Класс CDialogImpl

Этот класс предоставляет методы для создания модального или немодального диалогового окна.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `CDialogImpl` .

*тбасе*<br/>
Базовый класс нового класса. Базовым классом по умолчанию является [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[Создание](#create)|Создает немодальное диалоговое окно.|
|[дестройвиндов](#destroywindow)|Уничтожает немодальное диалоговое окно.|
|[DoModal](#domodal)|Создает модальное диалоговое окно.|
|[EndDialog](#enddialog)|Уничтожает модальное диалоговое окно.|

### <a name="cdialogimplbaset-methods"></a>Методы Кдиалогимплбасет

|Функция|Описание|
|-|-|
|[жетдиалогпрок](#getdialogproc)|Возвращает текущую процедуру диалогового окна.|
|[мапдиалогрект](#mapdialogrect)|Сопоставляет единицы диалогового окна указанного прямоугольника с единицами экрана (в пикселях).|
|[онфиналмессаже](#onfinalmessage)|Вызывается после получения последнего сообщения, обычно WM_NCDESTROY.|

### <a name="static-functions"></a>Статические функции

|Функция|Описание|
|-|-|
|[DialogProc](#dialogproc)|Обрабатывает сообщения, отправленные в диалоговое окно.|
|[стартдиалогпрок](#startdialogproc)|Вызывается при получении первого сообщения для обработки сообщений, отправляемых в диалоговое окно.|

## <a name="remarks"></a>Примечания

С помощью `CDialogImpl` можно создать модальное или немодальное диалоговое окно. `CDialogImpl` предоставляет процедуру диалогового окна, которая использует схему сообщений по умолчанию для направления сообщений соответствующим обработчикам.

Деструктор базового класса `~CWindowImplRoot` гарантирует, что окно исчезнет перед уничтожением объекта.

`CDialogImpl` является производным от `CDialogImplBaseT` , который, в свою очередь, является производным от `CWindowImplRoot` .

> [!NOTE]
> Класс должен определять `IDD` член, указывающий идентификатор ресурса шаблона диалогового окна. Например, мастер проектов ATL автоматически добавляет в класс следующую строку:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

где `MyDlg` — **короткое имя** , указанное на странице **имен** мастера.

|Дополнительные сведения|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование диалоговых окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|
|Диалоговые окна|[Диалоговые окна](/windows/win32/dlgbox/dialog-boxes) и последующие разделы в Windows SDK|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cdialogimplcreate"></a><a name="create"></a> CDialogImpl:: Create

Создает немодальное диалоговое окно.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*хвндпарент*<br/>
окне Маркер окна владельца.

**Rect&** *Rect* [in] структура [Rect](/windows/win32/api/windef/ns-windef-rect) , указывающая размер и расположение диалогового окна.

*двинитпарам*<br/>
окне Указывает значение, передаваемое в диалоговое окно в параметре *lParam* сообщения WM_INITDIALOG.

### <a name="return-value"></a>Возвращаемое значение

Маркер для вновь созданного диалогового окна.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически прикрепляется к `CDialogImpl` объекту. Чтобы создать модальное диалоговое окно, вызовите [DoModal](#domodal). Второе переопределение, приведенное выше, используется только с [ккомконтрол](../../atl/reference/ccomcontrol-class.md).

## <a name="cdialogimpldestroywindow"></a><a name="destroywindow"></a> CDialogImpl::D Естройвиндов

Уничтожает немодальное диалоговое окно.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если диалоговое окно было успешно удалено; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если диалоговое окно было успешно удалено; в противном случае — FALSE.

## <a name="cdialogimpldialogproc"></a><a name="dialogproc"></a> CDialogImpl::D Иалогпрок

Эта статическая функция реализует процедуру диалогового окна.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер диалогового окна.

*Uiacp*<br/>
окне Сообщение, отправленное в диалоговое окно.

*wParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сообщение обрабатывается; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`DialogProc` использует схему сообщений по умолчанию, чтобы направить сообщения соответствующим обработчикам.

Можно переопределить `DialogProc` , чтобы предоставить другой механизм обработки сообщений.

## <a name="cdialogimpldomodal"></a><a name="domodal"></a> CDialogImpl::D Омодал

Создает модальное диалоговое окно.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*хвндпарент*<br/>
окне Маркер окна владельца. Значение по умолчанию — возвращаемое значение функции Win32 [жетактивевиндов](/windows/win32/api/winuser/nf-winuser-getactivewindow) .

*двинитпарам*<br/>
окне Указывает значение, передаваемое в диалоговое окно в параметре *lParam* сообщения WM_INITDIALOG.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха значение параметра *нреткоде* , указанное при вызове [EndDialog](#enddialog). В противном случае –1.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически прикрепляется к `CDialogImpl` объекту.

Чтобы создать немодальное диалоговое окно, вызовите [CREATE](#create).

## <a name="cdialogimplenddialog"></a><a name="enddialog"></a> CDialogImpl:: EndDialog

Уничтожает модальное диалоговое окно.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Параметры

*нреткоде*<br/>
окне Значение, возвращаемое функцией [CDialogImpl::D омодал](#domodal).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если диалоговое окно уничтожается; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`EndDialog` метод должен вызываться с помощью процедуры диалогового окна. После уничтожения диалогового окна Windows использует значение *нреткоде* в качестве возвращаемого значения для `DoModal` , которое создало диалоговое окно.

> [!NOTE]
> Не вызывайте `EndDialog` для уничтожения немодального диалогового окна. Вызовите [CWindow::D естройвиндов](../../atl/reference/cwindow-class.md#destroywindow) .

## <a name="cdialogimplgetdialogproc"></a><a name="getdialogproc"></a> CDialogImpl:: Жетдиалогпрок

Возвращает `DialogProc` текущую процедуру диалогового окна.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущая процедура диалогового окна.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы заменить процедуру диалогового окна собственным.

## <a name="cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a> CDialogImpl:: Мапдиалогрект

Преобразует (сопоставляет) единицы диалогового окна указанного прямоугольника на единицы экрана (в пикселях).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*лпрект*<br/>
Указывает на `CRect` структуру объекта или [Rect](/windows/win32/api/windef/ns-windef-rect) , которая будет принимать клиентские координаты обновления, охватывающего регион обновления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если обновление завершилось с ошибкой; 0, если обновление завершается сбоем. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

Функция заменяет координаты в указанной `RECT` структуре преобразованными координатами, что позволяет использовать структуру для создания диалогового окна или размещения элемента управления в диалоговом окне.

## <a name="cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a> CDialogImpl:: Онфиналмессаже

Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY` ).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер для уничтожения окна.

### <a name="remarks"></a>Примечания

Обратите внимание, что если вы хотите автоматически удалить объект при уничтожении окна, можно вызвать **Delete** . здесь.

## <a name="cdialogimplstartdialogproc"></a><a name="startdialogproc"></a> CDialogImpl:: Стартдиалогпрок

Вызывается только один раз при получении первого сообщения для обработки сообщений, отправляемых в диалоговое окно.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер диалогового окна.

*Uiacp*<br/>
окне Сообщение, отправленное в диалоговое окно.

*wParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

### <a name="return-value"></a>Возвращаемое значение

Процедура окна.

### <a name="remarks"></a>Примечания

После начального вызова метод `StartDialogProc` `DialogProc` задается в качестве процедуры диалогового окна, а последующие вызовы попадают в нее.

## <a name="see-also"></a>См. также раздел

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
