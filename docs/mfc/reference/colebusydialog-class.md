---
title: Класс COleBusyDialog
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: 5be42463c08cacd83de84900fb4d98771774e897
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364246"
---
# <a name="colebusydialog-class"></a>Класс COleBusyDialog

Используется для диалоговых окон OLE "Сервер не отвечает" или "Сервер занят".

## <a name="syntax"></a>Синтаксис

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeBusyДиалог::ColeBusyДиалог](#colebusydialog)|Формирует объект `COleBusyDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeBusyДиалог::DoModal](#domodal)|Отображает диалоговую коробку OLE Server Busy.|
|[ColeBusyDialog::GetSelectionType](#getselectiontype)|Определяет сяопредел, сделанный в диалоговом окне.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeBusyДиалог::m_bz](#m_bz)|Структура типа OLEUIBUSY, которая контролирует поведение диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COleBusyDialog` класса, когда вы хотите вызвать эти диалоговые коробки. После `COleBusyDialog` построения объекта можно использовать [структуру m_bz](#m_bz) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_bz` типа OLEUIBUSY. Для получения дополнительной информации об [использовании](#domodal) этого класса диалогов см.

> [!NOTE]
> Этот класс используется с генерируемым приложением Wizard.?

Для получения дополнительной [информации,](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) см.

Для получения дополнительной информации о OL-специфических диалоговых ящиков, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colebusydialogcolebusydialog"></a><a name="colebusydialog"></a>ColeBusyДиалог::ColeBusyДиалог

Эта функция только `COleBusyDialog` строит объект.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*htaskBusy*<br/>
Обработка задачи сервера, которая занята.

*bNotResponding*<br/>
Если это правда, позвоните в диалоговый ящик «Не отвечая» вместо диалогового окна Server Busy. Формулировка в диалоговом поле «Не отвечая» немного отличается от формулировки в диалоговом окне Server Busy, и кнопка «Отмена» отключена.

*dwFlags*<br/>
Флаг создания. Может содержать ноль или более следующих значений в сочетании с оператором bitwise-OR:

- BZ_DISABLECANCELBUTTON отключить кнопку Отмена при вызове диалогового окна.

- BZ_DISABLESWITCHTOBUTTON отключить кнопку переключения при вызове диалогового окна.

- BZ_DISABLERETRYBUTTON отключить кнопку Retry при вызове диалогового окна.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно объекта диалога устанавливается к основному окну приложения.

### <a name="remarks"></a>Примечания

Для отображения диалогового окна позвоните [в DoModal](#domodal).

Для получения дополнительной [информации,](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) см.

## <a name="colebusydialogdomodal"></a><a name="domodal"></a>ColeBusyДиалог::DoModal

Вызовите эту функцию для отображения бизнес-бокса OLE Server Busy или Server NoInIn.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, `COleDialog::GetLastError` позвоните функции участника, чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIBusy](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_bz,](#m_bz) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или информацию, вводимые пользователем в диалоговую будку.

## <a name="colebusydialoggetselectiontype"></a><a name="getselectiontype"></a>ColeBusyDialog::GetSelectionType

Вызовите эту функцию, чтобы получить выбранный пользователем тип выбора в диалоговом окне Server Busy.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип выбора сделан.

### <a name="remarks"></a>Примечания

Значения типа возврата определяются `Selection` типом перечисления, `COleBusyDialog` объявленным в классе.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Краткие описания этих значений следуют:

- `COleBusyDialog::switchTo`Кнопка переключения кнопки была нажата.

- `COleBusyDialog::retry`Кнопка повтора была нажата.

- `COleBusyDialog::callUnblocked`Звонок для активации сервера теперь разблокирован.

## <a name="colebusydialogm_bz"></a><a name="m_bz"></a>ColeBusyДиалог::m_bz

Структура типа OLEUIBUSY используется для управления поведением диалогового окна Server Busy.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены непосредственно или через функции членов.

Для получения дополнительной [информации,](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) см.

## <a name="see-also"></a>См. также раздел

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
