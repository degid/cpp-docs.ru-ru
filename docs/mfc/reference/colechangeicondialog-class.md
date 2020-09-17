---
title: Класс COleChangeIconDialog
ms.date: 11/04/2016
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
ms.openlocfilehash: 6cdc0ed6bfa4765817de8b7628f339db5e7e5bf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369624"
---
# <a name="colechangeicondialog-class"></a>Класс COleChangeIconDialog

Используется для диалогового окна OLE "Изменить значок".

## <a name="syntax"></a>Синтаксис

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeChangeIconДиалог::ColeChangeIconДиалог](#colechangeicondialog)|Формирует объект `COleChangeIconDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeChangeIconДиалог::DoChangeIcon](#dochangeicon)|Выполняет изменение, указанное в диалоговом поле.|
|[ColeChangeIconДиалог::DoModal](#domodal)|Отображает диалоговую коробку ПОДОБОПН OLE 2 Change Icon.|
|[ColeChangeIconДиалог::GetIconicMetafile](#geticonicmetafile)|Получает ручку метафайла, связанную с культовой формой этого элемента.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeChangeIconДиалогок::m_ci](#m_ci)|Структура, контролирующая поведение диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COleChangeIconDialog` класса, когда вы хотите вызвать этот диалоговый ящик. После `COleChangeIconDialog` построения объекта можно использовать [структуру m_ci](#m_ci) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_ci` типа OLEUICHANGEICON. Для получения дополнительной информации об [использовании](#domodal) этого класса диалогов см.

Для получения дополнительной информации, см [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) структуры в Windows SDK.

Для получения дополнительной информации о OL-специфических диалоговых ящиков, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>ColeChangeIconДиалог::ColeChangeIconДиалог

Эта функция строит `COleChangeIconDialog` только объект.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указывает на элемент, который будет преобразован.

*dwFlags*<br/>
Флаг создания, который содержит любое количество следующих значений, объединенных с помощью bitwise-или оператора:

- CIF_SELECTCURRENT указывает, что текущая кнопка радио будет выбрана первоначально, когда диалоговая коробка называется. Это значение по умолчанию.

- CIF_SELECTDEFAULT указывает, что кнопка радио по умолчанию будет выбрана первоначально, когда диалоговая коробка называется.

- CIF_SELECTFROMFILE указывает, что кнопка радио Из файла будет выбрана первоначально, когда диалоговый ящик называется.

- CIF_SHOWHELP указывает, что при вызове диалогового окна будет отображаться кнопка справки.

- CIF_USEICONEXE указывает, что значок должен быть извлечен из исполняемого, указанного в `szIconExe` поле [m_ci,](#m_ci) а не извлечены из типа. Это полезно для встраивания или ссылки на файлы, не относящиеся к OLE.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов будет установлено на основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

Для получения дополнительной информации, см [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) структуры в Windows SDK.

## <a name="colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>ColeChangeIconДиалог::DoChangeIcon

Вызовите эту функцию, чтобы изменить значок, представляющий элемент, на тот, который выбран в поле диалога после того, как [DoModal](#domodal) возвращает IDOK.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указывает на элемент, значок которого изменяется.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если изменения успешны; в противном случае 0.

## <a name="colechangeicondialogdomodal"></a><a name="domodal"></a>ColeChangeIconДиалог::DoModal

Вызовите эту функцию для отображения диалогового окна ICON Change Icon.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, `COleDialog::GetLastError` позвоните функции участника, чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIChangeIcon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_ci,](#m_ci) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или информацию, вводимые пользователем в диалоговую будку.

## <a name="colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ColeChangeIconДиалог::GetIconicMetafile

Вызовите эту функцию, чтобы получить ручку метафайла, который содержит знаковый аспект выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к метафайлу, содержащему знаковый аспект новой иконки, если диалоговое окно было отклонено, выбрав **OK;** в противном случае, значок, как это было до диалога был показан.

## <a name="colechangeicondialogm_ci"></a><a name="m_ci"></a>ColeChangeIconДиалогок::m_ci

Структура типа OLEUICHANGEICON используется для управления поведением диалогового окна Change Icon.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены либо непосредственно, либо через функции членов.

Для получения дополнительной информации, см [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) структуры в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
