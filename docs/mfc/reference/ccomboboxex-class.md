---
title: Класс CComboBoxEx
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: a948d54be17103fa83848ff5f0e86dd2c522f0a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754822"
---
# <a name="ccomboboxex-class"></a>Класс CComboBoxEx

Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.

## <a name="syntax"></a>Синтаксис

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Формирует объект `CComboBoxEx`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComboBoxEx::Создание](#create)|Создает комбо-коробку и прикрепляет ее к объекту. `CComboBoxEx`|
|[CComboBoxEx::CreateEx](#createex)|Создает комбо-коробку с указанными расширенными стилями Windows и прикрепляет ее к объекту. `ComboBoxEx`|
|[CComboBoxEx::DeleteItem](#deleteitem)|Удаляет элемент из `ComboBoxEx` элемента.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Извлекает указатель на управление коробкой для дочерних комбо-|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Извлекает ручку в элементуправления элемента `ComboBoxEx` управления.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые `ComboBoxEx` используются для управления.|
|[CComboBoxEx::GetImageList](#getimagelist)|Извлекает указатель в список изображений, присвоенный элементу `ComboBoxEx` управления.|
|[CComboBoxEx::GetItem](#getitem)|Извлекает информацию о `ComboBoxEx` товаре для данного элемента.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Определяет, изменил ли пользователь содержимое `ComboBoxEx` элемента управления дейтом, введя его.|
|[CComboBoxEx::InsertItem](#insertitem)|Вставляет новый `ComboBoxEx` элемент в элемент управления.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Устанавливает расширенные `ComboBoxEx` стили в элементе управления.|
|[CComboBoxEx::SetImageList](#setimagelist)|Устанавливает список изображений для элемента `ComboBoxEx` управления.|
|[CComboBoxEx::Setitem](#setitem)|Устанавливает атрибуты элемента в `ComboBoxEx` элементе управления.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Устанавливает визуальный стиль расширенного управления комбо-коробкой.|

## <a name="remarks"></a>Примечания

С `CComboBoxEx` помощью элементов управления комбо-коробкой вам больше не нужно реализовывать свой собственный код рисования изображений. Вместо этого `CComboBoxEx` используйте для доступа к изображениям из списка изображений.

## <a name="image-list-support"></a>Поддержка списка изображений

В стандартной комбо-коробке владелец комбо-коробки отвечает за рисование изображения, создавая комбо-коробку в качестве управления владельца.draw. При использовании `CComboBoxEx`вам не нужно устанавливать стили рисования CBS_OWNERDRAWFIXED и CBS_HASSTRINGS, потому что они подразумеваются. В противном случае необходимо написать код для выполнения операций рисования. Элемент `CComboBoxEx` управления поддерживает до трех изображений на элемент: одно для выбранного состояния, одно для невыбранного состояния и одно для изображения наложения.

## <a name="styles"></a>Стили

`CComboBoxEx`поддерживает стили CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST и WS_CHILD. Все остальные стили, пройдение при создании окна, игнорируются элементом управления. После создания окна можно предоставить другие стили `CComboBoxEx` комбо-боксов, позвонив в функцию участника [SetExtendedStyle.](#setextendedstyle) С помощью этих стилей, вы можете:

- Установите поиск строки в списке, чтобы быть чувствительным к случаям.

- Создайте элементуправления комбо-коробки, использующее слэш\\('/'), backslash (') и период ('') символы в качестве делимитеров слов. Это позволяет пользователям переходить от слова к слову, используя клавиатуру ярлык CTRL' ARROW.

- Установите управление комбо-коробкой для отображения или неотображения изображения. Если изображение не отображается, комбо-поле может удалить текст отступ, который вмещает изображение.

- Создайте узкий комбо-бокс управления, в том числе размер ований, чтобы он клипы более широкой комбо-окно он содержит.

Эти флаги стиля описаны далее в [использовании CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="item-retention-and-callback-item-attributes"></a>Атрибуты элемента хранения и возврата вызовов

Информация о товарах, таких как индексы для элементов и изображений, значения отступов и строки текста, хранится в структуре Win32 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw), как описано в SDK Windows. Структура также содержит участников, которые соответствуют флагам обратного вызова.

Для подробного, концептуального обсуждения, [см.](../../mfc/using-ccomboboxex.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx

Вызовите эту функцию участника для создания `CComboBoxEx` объекта.

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a>CComboBoxEx::Создание

Создает комбо-коробку и прикрепляет ее к объекту. `CComboBoxEx`

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет сочетание стилей комбо-боксов, применяемых к комбо-коробке. Более **подробную** информацию о стилях можно узнать ниже.

*rect*<br/>
Ссылка на объект [CRect](../../atl-mfc-shared/reference/crect-class.md) или структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая является положением и размером комбо-коробки.

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном `CDialog`комбо-коробки (обычно a). Она не должна быть NULL.

*nID*<br/>
Определяет идентификатор управления комбо-коробкой.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект был создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Создание `CComboBoxEx` объекта в два этапа:

1. Позвоните [CComboBoxEx](#ccomboboxex) `CComboBoxEx` для построения объекта.

1. Вызов исвызывайте эту функцию участника, которая создает `CComboBoxEx` расширенную комбо-коробку Windows и прикрепляет ее к объекту.

При вызове `Create`MFC инициализирует общие элементы управления.

При создании комбо-коробки можно указать любой или все следующие стили комбо-бокса:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Все остальные стили, пройдение при создании окна, игнорируются. Элемент `ComboBoxEx` управления также поддерживает расширенные стили, которые предоставляют дополнительные функции. Эти стили описаны в [Расширенном стиле Управления ComboBoxEx,](/windows/win32/Controls/comboboxex-control-extended-styles)в Windows SDK. Установите эти стили, позвонив [в SetExtendedStyle.](#setextendedstyle)

Если вы хотите использовать расширенные стили `Create`окон с вашим управлением, позвоните [CreateEx](#createex) вместо .

## <a name="ccomboboxexcreateex"></a><a name="createex"></a>CComboBoxEx::CreateEx

Вызовите эту функцию, чтобы создать расширенное управление комбо-коробкой (детское окно) и связать ее с объектом. `CComboBoxEx`

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Стиль управления комбо-коробкой. Смотрите [Создать](#create) список стилей.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` `Create` вместо того, чтобы применять расширенные стили Windows, указанные в предисловии расширенного стиля Windows **WS_EX_.**

`CreateEx`создает элемент управления с расширенными стилями Windows, указанными *dwExStyle.* Вы должны установить расширенные стили, характерные для расширенного управления комбо-коробкой с помощью [SetExtendedStyle.](#setextendedstyle) Например, `CreateEx` использовать для установки таких `SetExtendedStyle` стилей, как WS_EX_CONTEXTHELP, но использовать для установки таких стилей, как CBES_EX_CASESENSITIVE. Для получения дополнительной информации, см стилей, описанных в теме [ComboBoxEx управления Расширенные стили](/windows/win32/Controls/comboboxex-control-extended-styles) в Windows SDK.

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a>CComboBoxEx::DeleteItem

Удаляет элемент из `ComboBoxEx` элемента.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Нулевой индекс элемента, который будет удален.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, оставшихся в элементе управления. Если *iIndex* недействителен, функция возвращается CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция члена реализует функциональность сообщения [CBEM_DELETEITEM,](/windows/win32/Controls/cbem-deleteitem)как описано в SDK Windows. При вызове DeleteItem в родительское окно будет отправлено [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с уведомлением CBEN_DELETEITEM.

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl

Вызов исправиэту функцию участника, чтобы получить `CComboBoxEx` указатель на управление комбо-коробкой внутри объекта.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CComboBox`.

### <a name="remarks"></a>Примечания

Элемент `CComboBoxEx` управления состоит из родительского окна, которое инкапсулирует `CComboBox`.

Объект, `CComboBox` на который указывает сятвое значение возврата, является временным объектом и уничтожается во время следующего простоя обработки.

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl

Вызов исправиэту функцию участника, чтобы получить указатель на управление реитом для комбо-бокса.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CEdit.](../../mfc/reference/cedit-class.md)

### <a name="remarks"></a>Примечания

Элемент `CComboBoxEx` управления использует редактированную коробку, когда он создается с CBS_DROPDOWN стилем.

Объект, `CEdit` на который указывает сятвое значение возврата, является временным объектом и уничтожается во время следующего простоя обработки.

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle

Вызовите эту функцию участника, `CComboBoxEx` чтобы получить расширенные стили, используемые для управления.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее расширенные стили, которые используются для управления комбо-коробкой.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации об этих стилях можно ознакомиться с [расширенными стилями Управления ComboBoxEx](/windows/win32/Controls/comboboxex-control-extended-styles) в SDK windows.

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a>CComboBoxEx::GetImageList

Вызовите эту функцию участника, чтобы получить `CComboBoxEx` указатель на список изображений, используемый элементом управления.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList.](../../mfc/reference/cimagelist-class.md) Если это не удается, эта функция члена возвращает NULL.

### <a name="remarks"></a>Примечания

Объект, `CImageList` на который указывает сятвое значение возврата, является временным объектом и уничтожается во время следующего простоя обработки.

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a>CComboBoxEx::GetItem

Извлекает информацию о `ComboBoxEx` товаре для данного элемента.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на структуру [COMBOBOXEXITEM,](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) которая будет получать информацию о товаре.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональность сообщения [CBEM_GETITEM,](/windows/win32/Controls/cbem-getitem)как описано в SDK Windows.

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>CComboBoxEx::HasEditChanged

Определяет, изменил ли пользователь содержимое `ComboBoxEx` элемента управления дейтом, введя его.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь набрал в поле отсвагиваем элемента управления; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональность сообщения [CBEM_HASEDITCHANGED,](/windows/win32/Controls/cbem-haseditchanged)как описано в SDK Windows.

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a>CComboBoxEx::InsertItem

Вставляет новый `ComboBoxEx` элемент в элемент управления.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на структуру [COMBOBOXEXITEM,](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) которая будет получать информацию о товаре. Эта структура содержит значения флага обратного вызова для элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс, по которому новый элемент был вставлен в случае успеха; в противном случае -1.

### <a name="remarks"></a>Примечания

При вызове `InsertItem` [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с [уведомлением CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) будет отправлено в родительское окно.

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle

Вызовите эту функцию члена для установки расширенных стилей, используемых для расширенного управления комбо-коробкой.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Параметры

*dwExМаск*<br/>
Значение DWORD, которое указывает, какие стили в *dwExStyles* должны быть затронуты. Только расширенные стили в *dwExMask* будут изменены. Все остальные стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в *dwExStyles* будут затронуты.

*dwExStyles*<br/>
Значение DWORD, содержащее расширенные стили управления комбо-коробкой, для управления.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее расширенные стили, ранее использовавававаемые для управления.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации об этих стилях можно ознакомиться с [расширенными стилями Управления ComboBoxEx](/windows/win32/Controls/comboboxex-control-extended-styles) в SDK windows.

Для создания комбо-коробки расширенного управления с расширенными стилями окон используйте [CreateEx.](#createex)

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a>CComboBoxEx::SetImageList

Устанавливает список изображений для элемента `ComboBoxEx` управления.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на `CImageList` объект, содержащий изображения для `CComboBoxEx` использования с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList,](../../mfc/reference/cimagelist-class.md) содержащий изображения, `CComboBoxEx` ранее используемые элементом управления. NULL, если список изображений не был установлен ранее.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональность сообщения [CBEM_SETIMAGELIST,](/windows/win32/Controls/cbem-setimagelist)как описано в SDK Windows. Если вы измените высоту управления изменениями по умолчанию, позвоните функции Win32 [SetWindowPos,](/windows/win32/api/winuser/nf-winuser-setwindowpos) чтобы изменить размер управления после вызова, `SetImageList`или он не будет отображаться должным образом.

Объект, `CImageList` на который указывает сятвое значение возврата, является временным объектом и уничтожается во время следующего простоя обработки.

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a>CComboBoxEx::Setitem

Устанавливает атрибуты элемента в `ComboBoxEx` элементе управления.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на структуру [COMBOBOXEXITEM,](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) которая будет получать информацию о товаре.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует функциональность сообщения [CBEM_SETITEM,](/windows/win32/Controls/cbem-setitem)как описано в SDK Windows.

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme

Устанавливает визуальный стиль расширенного управления комбо-коробкой.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*pszSubAppName*<br/>
Указатель на строку Unicode, которая содержит расширенный визуальный стиль комбо-коробки для установки.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата не используется.

### <a name="remarks"></a>Примечания

Эта функция члена имитирует функциональность [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) сообщения, как описано в SDK Windows.

## <a name="see-also"></a>См. также раздел

[Пример MFC MFCIE](../../overview/visual-cpp-samples.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)
