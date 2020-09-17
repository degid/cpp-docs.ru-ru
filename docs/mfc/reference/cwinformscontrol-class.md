---
title: Класс CWinFormsControl
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: c91f50be1ea30efac81ff67c43633bedd7b0ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377181"
---
# <a name="cwinformscontrol-class"></a>Класс CWinFormsControl

Предоставляет базовую функцию для размещения элементов управления Windows Forms.

## <a name="syntax"></a>Синтаксис

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>Параметры

*TManagedControl*<br/>
Контроль форм windows .NET Framework Forms, который будет отображаться в приложении MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Создает объект управления формами MFC Windows.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Создает элемент управления формами Windows в контейнере MFC.|
|[CWinFormsControl::GetControl](#getcontrol)|Извлекает указатель на элемент управления форм Windows.|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Извлекает ручку в управление форм Windows.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl:оператор -&gt;](#operator_-_gt)|Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.|
|[CWinFormsControl::оператор TManagedControl](#operator_tmanagedcontrol)|Отбрасывает тип в качестве указателя на элемент управления формами Windows.|

## <a name="remarks"></a>Примечания

Класс `CWinFormsControl` предоставляет основную функциональность для хостинга управления формами Windows.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

Ваш код MFC не должен кэшировать `m_hWnd`ручки window (обычно хранящиеся в). Некоторые свойства управления Windows Forms требуют, `Window` чтобы базовый Win32 был уничтожен и воссоздан с помощью `DestroyWindow` и. `CreateWindow` Реализация MFC Windows Forms `Destroy` обрабатывает `Create` события элементов управления `m_hWnd` для обновления участника.

> [!NOTE]
> Интеграция MFC Windows Forms работает только в проектах, которые динамически связывают сяпонического отношения с MFC (в которых определен AFXDLL).

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl

Создает элемент управления формами Windows в контейнере MFC.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>Параметры

*pType*<br/>
Тип элемента управления данных, который будет создан. Должен быть тип данных [типа.](/dotnet/api/system.type)

*dwStyle*<br/>
Стиль окна для применения к элементу управления. Укажите комбинацию [стилей окон](../../mfc/reference/styles-used-by-mfc.md#window-styles). В настоящее время поддерживаются только следующие стили: WS_TABSTOP, WS_VISIBLE, WS_DISABLED и WS_GROUP.

*rect*<br/>
[Структура RECT,](/windows/win32/api/windef/ns-windef-rect) определяющая координаты верхнего левого и нижнего правого углов управления (только первая перегрузка).

*nPlaceHolderID*<br/>
Ручка элементаконтроля держателя места, помещенная в редактор ресурса. Вновь созданный элемент управления Windows Forms заменяет статический элемент управления, предполагая его положение, z-заказ и стили (только вторую перегрузку).

*pParentWnd*<br/>
Указатель на родительское окно.

*nID*<br/>
Идентификационный номер ресурса, который будет присвоен вновь созданному элементу управления.

*pControl*<br/>
Пример элемента управления Windows Forms, связанный с объектом [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) (только четвертая перегрузка).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает ненулевое значение. В случае неудачи, возвращаетнулно ноль.

### <a name="remarks"></a>Примечания

Этот метод мгновенно управляет системой форм Windows .NET в контейнере MFC.

Первая перегрузка метода принимает *pType* данных .NET Framework, чтобы MFC мог мгновенно выводить новый объект этого типа. *pType* должен быть типом данных [типа.](/dotnet/api/system.type)

Вторая перегрузка метода создает элемент управления `TManagedControl` формами `CWinFormsControl` Windows на основе параметра шаблона класса. Размер и положение элемента управления `RECT` основаны на структуре, передаваемых методу. Только *dwStyle* имеет значение для стилей.

Третья перегрузка метода создает элемент управления Windows Forms, который заменяет статический элемент управления, разрушая его и принимая на себя его положение, z-порядок и стили. Статический элемент управления служит лишь заполнителем для управления формами Windows. При создании элемента управления эта перегрузка сочетает стили *dwStyle* с стилями ресурсов статического управления.

Четвертая перегрузка метода позволяет вам пройти в уже мгновенной Windows Forms управления *pControl,* что MFC будет обернуть. Он должен быть того же `TManagedControl` типа, `CWinFormsControl` что и параметр шаблона класса.

[См. Использование системы управления пользователями Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) для образцов с помощью элементов управления windows Form.

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl

Создает объект управления формами MFC Windows.

```
CWinFormsControl();
```

### <a name="remarks"></a>Примечания

Управление формами Windows мгновенно происходит при вызове [CWinFormsControl::CreateManagedControl.](#createmanagedcontrol)

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinFormsControl::GetControl

Извлекает указатель на элемент управления форм Windows.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в элемент управления форм Windows.

### <a name="example"></a>Пример

  Смотрите [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle

Извлекает ручку в управление форм Windows.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в управление форм Windows.

### <a name="remarks"></a>Примечания

`GetControlHandle`— это метод помощника, который возвращает ручку окна, хранящуюся в свойствах управления .NET Framework. Значение ручки окна скопировано в [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) во время вызова [к CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinFormsControl:оператор -&gt;

Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Примечания

Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.

Для получения дополнительной информации о формах Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinFormsControl::оператор TManagedControl

Отбрасывает тип в качестве указателя на элемент управления формами Windows.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Примечания

Этот оператор `CWinFormsControl<TManagedControl>` переходит к функциям, которые принимают указатель на управление формами Windows.

## <a name="see-also"></a>См. также раздел

[Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)<br/>
[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)
