---
title: Класс CAxDialogImpl
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: d8e60a817d197f67c14318a7d50ddf796e570142
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318740"
---
# <a name="caxdialogimpl-class"></a>Класс CAxDialogImpl

Этот класс реализует диалоговый ящик (модальный или безрежимный), в котором размещается элементы управления ActiveX.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `CAxDialogImpl`.

*TBase*<br/>
Базовый класс `CDialogImplBaseT`окна для .

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Позвоните по этому методу, чтобы посоветовать или не сообщить все записи на карте событий, составление карты событий объекта.|
|[CAxDialogImpl::Создание](#create)|Вызовите этот метод, чтобы создать нештатную диалоговую коробку.|
|[CAxDialogImpl: :DestroyWindow](#destroywindow)|Вызовите этот метод, чтобы уничтожить безрежимный диалоговой ящик.|
|[CAxDialogImpl: :DoModal](#domodal)|Вызовите этот метод, чтобы создать модальный диалоговый ящик.|
|[CAxDialogImpl::EndDialog](#enddialog)|Вызовите этот метод, чтобы уничтожить модальный диалоговый ящик.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Вызовите этот метод, чтобы `DialogProc` получить указатель на функцию обратного вызова.|
|[CAxDialogImpl::GetIDD](#getidd)|Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогов|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Вызов иметод, чтобы определить, предназначено ли сообщение для этого диалогового окна, и, если это так, обработать сообщение.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|Переменная, которая существует только в отладке сборки и устанавливается в верной, если диалоговая коробка является модальной.|

## <a name="remarks"></a>Примечания

`CAxDialogImpl`позволяет создать модальный или бесрежимный диалоговый ящик. `CAxDialogImpl`обеспечивает процедуру диалогового окна, которая использует карту сообщений по умолчанию для направления сообщений соответствующим обработчикам.

`CAxDialogImpl`вытекает `CDialogImplBaseT`из , который, в свою очередь, `CWindow`происходит `CMessageMap`от *TBase* (по умолчанию, ) и .

Ваш класс должен определить члена IDD, который определяет идентификатор ресурса шаблона диалогов. Например, добавление объекта ATL Dialog с помощью диалогового окна **Add Class** автоматически добавляет в класс следующую строку:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

где `MyDialog` короткое **имя,** вписаное в ATL Dialog Wizard.

Дополнительную информацию можно узнать о [приведении в ней dialog Box.](../../atl/implementing-a-dialog-box.md)

Обратите внимание, что управление ActiveX на модальном диалоговом поле, созданном с `CAxDialogImpl` не будет поддерживать клавиши ускорителя. Для поддержки клавиш акселератора на `CAxDialogImpl`диалоговом поле, созданном с помощью, создайте бесрежимный диалоговый ящик и, используя свой собственный цикл сообщений, используйте [CAxDialogImpl::IsDialogMessage](#isdialogmessage) после получения сообщения из очереди для обработки ключа акселератора.

Для получения `CAxDialogImpl`дополнительной информации о , см. [ATL Control Containment FAQ](../../atl/atl-control-containment-faq.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap

Позвоните по этому методу, чтобы посоветовать или не сообщить все записи на карте событий, составление карты событий объекта.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Параметры

*bAdvise*<br/>
Установить на верно, если все записи раковины должны быть рекомендованы; ложные, если все записи раковины должны быть нерекомендуетыми.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::Создание

Вызовите этот метод, чтобы создать нештатную диалоговую коробку.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Ручка к окну владельца.

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

*&RECT*<br/>
Этот параметр не используется. Этот параметр передается в `CComControl`.

### <a name="return-value"></a>Возвращаемое значение

Ручка к недавно созданному диалоговому ящику.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически `CAxDialogImpl` прикрепляется к объекту. Чтобы создать модальный диалоговый ящик, позвоните [doModal](#domodal).

Второе переопределение обеспечивается только для того, чтобы диалоговые ящики можно было использовать с [помощью CComControl.](../../atl/reference/ccomcontrol-class.md)

## <a name="caxdialogimpldestroywindow"></a><a name="destroywindow"></a>CAxDialogImpl: :DestroyWindow

Вызовите этот метод, чтобы уничтожить безрежимный диалоговой ящик.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно успешно разрушено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Не звоните, `DestroyWindow` чтобы уничтожить модальный диалоговый ящик. Вместо этого позвоните [в EndDialog.](#enddialog)

## <a name="caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl: :DoModal

Вызовите этот метод, чтобы создать модальный диалоговый ящик.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Ручка к окну владельца. Значение по умолчанию — это значение возврата функции [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32.

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха значение параметра *nRetCode,* указанное в вызове [к EndDialog;](#enddialog) в противном случае, -1.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически `CAxDialogImpl` прикрепляется к объекту.

Чтобы создать бесрежимный диалоговый ящик, вызов [Создать](#create).

## <a name="caxdialogimplenddialog"></a><a name="enddialog"></a>CAxDialogImpl::EndDialog

Вызовите этот метод, чтобы уничтожить модальный диалоговый ящик.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
(в) Значение, подаваемые [DoModal](#domodal).

### <a name="return-value"></a>Возвращаемое значение

TRUE, если диалоговая будка уничтожена; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

`EndDialog`должны быть вызваны через процедуру диалогового окна. После того, как диалоговое окно уничтожено, Windows использует значение `DoModal` *nRetCode* в качестве значения возврата для , который создал диалоговое окно.

> [!NOTE]
> Не звоните, `EndDialog` чтобы уничтожить безрежимный диалоговой ящик. Вместо этого [позвоните destroyWindow.](#destroywindow)

## <a name="caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc

Вызовите этот метод, чтобы `DialogProc` получить указатель на функцию обратного вызова.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `DialogProc` функцию обратного вызова.

### <a name="remarks"></a>Примечания

Функция `DialogProc` является функцией обратного вызова, определяемой приложением.

## <a name="caxdialogimplgetidd"></a><a name="getidd"></a>CAxDialogImpl::GetIDD

Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалога.

```
int GetIDD();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор ресурса шаблона диалога.

## <a name="caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage

Вызов иметод, чтобы определить, предназначено ли сообщение для этого диалогового окна, и, если это так, обработать сообщение.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на структуру [MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую необходимое сообщение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сообщение было обработано, FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот метод предназначен для вызова из цикла сообщений.

## <a name="caxdialogimplm_bmodal"></a><a name="m_bmodal"></a>CAxDialogImpl::m_bModal

Переменная, которая существует только в отладке сборки и устанавливается в верной, если диалоговая коробка является модальной.

```
bool m_bModal;
```

## <a name="see-also"></a>См. также раздел

[Класс CDialogImpl](../../atl/reference/cdialogimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
