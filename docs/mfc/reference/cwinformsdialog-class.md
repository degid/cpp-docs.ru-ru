---
title: Класс Квинформсдиалог
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: a25823982b9276309e99a2a26cef8d6fe2e764bd
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040669"
---
# <a name="cwinformsdialog-class"></a>Класс Квинформсдиалог

Программа-оболочка для класса диалогового окна MFC, в котором размещается пользовательский элемент управления Windows Forms.

## <a name="syntax"></a>Синтаксис

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>Параметры

*тманажедконтрол*<br/>
.NET Framework пользовательский элемент управления, отображаемый в приложении MFC.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Квинформсдиалог:: Квинформсдиалог](#cwinformsdialog)|Формирует объект `CWinFormsDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Квинформсдиалог:: oncontrol](#getcontrol)|Извлекает ссылку на Windows Forms пользовательский элемент управления.|
|[Квинформсдиалог:: Жетконтролхандле](#getcontrolhandle)|Извлекает маркер окна для Windows Forms пользовательского элемента управления.|
|[Квинформсдиалог:: Онинитдиалог](#oninitdialog)|Инициализирует диалоговое окно MFC путем создания и размещения на нем Windows Forms пользовательского элемента управления.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-|
|[Квинформсдиалог::operator-&gt;](#operator_-_gt)|Заменяет [квинформсдиалог:: oncontrol](#getcontrol) в выражениях.|
|[Квинформсдиалог::operator Тманажедконтрол ^](#operator-tmanagedcontrol-hat)|Приводит тип в качестве ссылки на Windows Forms пользовательский элемент управления.|

## <a name="remarks"></a>Комментарии

`CWinFormsDialog` — Это оболочка для класса диалогового окна MFC ( [CDialog](../../mfc/reference/cdialog-class.md)), в котором размещен Windows Forms пользовательский элемент управления. Это позволяет отображать .NET Framework элементы управления в модальном или немодальном диалоговом окне MFC.

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows Forms в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) и [Размещение пользовательского элемента управления формы Windows Form в качестве диалогового окна MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).

## <a name="requirements"></a>Требования

**Заголовок:** афксвинформс.h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a> Квинформсдиалог:: Квинформсдиалог

Формирует объект `CWinFormsDialog`.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Параметры

*нидтемплате*<br/>
Содержит идентификатор ресурса шаблона диалогового окна. Используйте редактор диалоговых окон, чтобы создать шаблон диалогового окна и сохранить его в файле описания ресурсов приложения. Дополнительные сведения о шаблонах диалоговых окон см. в разделе [класс CDialog](../../mfc/reference/cdialog-class.md).

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a> Квинформсдиалог:: oncontrol

Извлекает ссылку на Windows Forms пользовательский элемент управления.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на элемент управления Windows Forms в диалоговом окне MFC.

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a> Квинформсдиалог:: Жетконтролхандле

Извлекает маркер окна для Windows Forms пользовательского элемента управления.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает обработчик окна Windows Forms пользовательском элементе управления.

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a> Квинформсдиалог:: Онинитдиалог

Инициализирует диалоговое окно MFC путем создания и размещения на нем Windows Forms пользовательского элемента управления.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, установил ли приложение фокус ввода на один из элементов управления в диалоговом окне. Если `OnInitDialog` возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления в диалоговом окне. Этот метод может возвращать значение 0, только если приложение явно установило фокус ввода на один из элементов управления в диалоговом окне.

### <a name="remarks"></a>Комментарии

При создании диалогового окна MFC (с помощью метода [CREATE](../../mfc/reference/cdialog-class.md#create), [креатеиндирект](../../mfc/reference/cdialog-class.md#createindirect)или [DoModal](../../mfc/reference/cdialog-class.md#domodal) , унаследованного от класса [CDialog](../../mfc/reference/cdialog-class.md)) отправляется сообщение WM_INITDIALOG и вызывается этот метод. Он создает экземпляр элемента управления Windows Forms в диалоговом окне и корректирует размер диалогового окна в соответствии с размером пользовательского элемента управления. Затем он размещает новый элемент управления в диалоговом окне MFC.

Переопределите эту функцию-член, если необходимо выполнить специальную обработку при инициализации диалогового окна. Дополнительные сведения об использовании этого метода см. в разделе [CDialog:: онинитдиалог](../../mfc/reference/cdialog-class.md#oninitdialog).

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a> Квинформсдиалог::operator-&gt;

Заменяет [квинформсдиалог:: oncontrol](#getcontrol) в выражениях.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Комментарии

Этот оператор предоставляет удобный синтаксис, который заменяет `GetControl` выражения.

Сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a> Квинформсдиалог::operator Тманажедконтрол ^

Приводит тип в качестве ссылки на Windows Forms пользовательский элемент управления.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Комментарии

Этот оператор приводит тип в качестве ссылки на элемент управления Windows Forms. Он используется для передачи `CWinFormsDialog<TManagedControl>` диалогового окна функциям, принимающим указатель на объект пользовательского элемента управления Windows Forms.

## <a name="see-also"></a>См. также раздел

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс Квинформсвиев](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
