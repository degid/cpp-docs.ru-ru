---
title: Класс CHotKeyCtrl
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: a79cc0ab2c01633f96430477aa536a60385461e9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750799"
---
# <a name="chotkeyctrl-class"></a>Класс CHotKeyCtrl

Предоставляет функциональные возможности стандартного элемента управления "горячая клавиша" Windows.

## <a name="syntax"></a>Синтаксис

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Формирует объект `CHotKeyCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHotKeyCtrl::Создание](#create)|Создает горячий элемент ключа и `CHotKeyCtrl` прикрепляет его к объекту.|
|[CHotKeyCtrl:CreateEx](#createex)|Создает элемент управления горячим ключом с указанными расширенными стилями Windows и прикрепляет его к объекту. `CHotKeyCtrl`|
|[CHotKeyCtrl:GetHotKey](#gethotkey)|Извлекает виртуальный код ключа и флаги модификатора горячего ключа из горячего элемента управления ключа.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Получает ключевое имя в локальном наборе символов, назначенном горячему ключу.|
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Извлекает ключевое имя в локальном наборе символов, присвоенном указанному виртуальному коду ключа.|
|[CHotKeyCtrl:SetHotKey](#sethotkey)|Устанавливает комбинацию горячего ключа для горячего управления ключа.|
|[CHotKeyCtrl:SetRules](#setrules)|Определяет недействительные комбинации и комбинацию модификаторов по умолчанию для элемента горячего ключа.|

## <a name="remarks"></a>Примечания

"Горячий элемент управления ключами" — это окно, которое позволяет пользователю создать горячий ключ. "Горячий ключ" — это комбинация ключей, которую пользователь может нажать, чтобы быстро выполнить действие. (Например, пользователь может создать горячий ключ, который активирует данное окно и приносит его в верхней части заказа.) Управление горячим ключом отображает выбор пользователя и гарантирует, что пользователь выбирает действительную комбинацию ключей.

Этот элемент управления `CHotKeyCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Когда пользователь выбрал комбинацию ключей, приложение может получить указанную комбинацию ключей из элемента управления и использовать WM_SETHOTKEY сообщение для настройки горячего ключа в системе. Всякий раз, когда пользователь нажимает горячий ключ после этого, из любой части системы, окно, указанное в WM_SETHOTKEY сообщении, получает WM_SYSCOMMAND сообщение с указанием SC_HOTKEY. Это сообщение активирует окно, которое получает его. Горячий ключ остается в силе до тех пор, пока приложение, которое называется WM_SETHOTKEY выходит.

Этот механизм отличается от поддержки горячего ключа, которая зависит от WM_HOTKEY сообщения и функций Windows [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey) и [UnregisterHotKey.](/windows/win32/api/winuser/nf-winuser-unregisterhotkey)

Для получения дополнительной `CHotKeyCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl

Формирует объект `CHotKeyCtrl`.

```
CHotKeyCtrl();
```

## <a name="chotkeyctrlcreate"></a><a name="create"></a>CHotKeyCtrl::Создание

Создает горячий элемент ключа и `CHotKeyCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления горячим ключом. Примените любую комбинацию стилей управления. Для получения дополнительной информации можно ознакомиться с [общими стилями управления](/windows/win32/Controls/common-control-styles) в SDK Windows.

*rect*<br/>
Определяет размер и положение элемента горячего ключа. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо [структура RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно элемента горячего ключа, обычно [CDialog.](../../mfc/reference/cdialog-class.md) Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор элемента управления горячим ключом.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы строите `CHotKeyCtrl` объект в два этапа. Сначала позвоните конструктору, `Create`а затем вызов, который создает горячий `CHotKeyCtrl` элемент ключа и прикрепляет его к объекту.

Если вы хотите использовать расширенные стили `Create`окон с вашим управлением, позвоните [CreateEx](#createex) вместо .

## <a name="chotkeyctrlcreateex"></a><a name="createex"></a>CHotKeyCtrl:CreateEx

Вызовите эту функцию, чтобы создать элемент управления `CHotKeyCtrl` (окно ребенка) и связать его с объектом.

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
Определяет стиль управления горячим ключом. Примените любую комбинацию стилей управления. Для получения дополнительной информации [см.](/windows/win32/Controls/common-control-styles)

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="chotkeyctrlgethotkey"></a><a name="gethotkey"></a>CHotKeyCtrl:GetHotKey

Извлекает виртуальный код ключа и модификатор флаги клавиатуры ярлык из горячего элемента управления ключа.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>Параметры

*wVirtualKeyCode*<br/>
(ваут) Виртуальный код ключа от ярлыка клавиатуры. Список стандартных виртуальных кодов ключей можно узнать на примере Winuser.h.

*wМодизаторы*<br/>
(ваут) Битовая комбинация (ИЛИ) флагов, указывающих клавиши модификатора в ярлыке клавиатуры.

Флаги модификатора следующие:

|Флаг|Соответствующий ключ|
|----------|-----------------------|
|HOTKEYF_ALT|ALT - клавиша|
|HOTKEYF_CONTROL|Ключ CTRL|
|HOTKEYF_EXT|Расширенный ключ|
|HOTKEYF_SHIFT|КЛЮЧ SHIFT|

### <a name="return-value"></a>Возвращаемое значение

В первом перегруженном методе DWORD содержит виртуальный код ключа и флаги модификаторов. Низкое упорядоченное байт слова низкого порядка содержит виртуальный код ключа, байт высокого порядка слова низкого порядка содержит флаги модификатора, а слово высокого порядка равен нулю.

### <a name="remarks"></a>Примечания

Виртуальный код ключа и клавиши модификатора вместе определяют ярлык клавиатуры.

## <a name="chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName

Вызовите эту функцию участника, чтобы получить локализованное имя горячего ключа.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Локализованное название выбранного в настоящее время горячего ключа. Если нет выбранного горячего `GetHotKeyName` ключа, возвращаетпустую строку.

### <a name="remarks"></a>Примечания

Имя, которое возвращает функция участника, происходит от драйвера клавиатуры. Вы можете установить нелокализованный драйвер клавиатуры в локализованную версию Windows, и наоборот.

## <a name="chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>CHotKeyCtrl::GetKeyName

Вызовите эту функцию участника, чтобы получить локализованное имя ключа, назначенного указанному виртуальному коду ключа.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>Параметры

*Vk*<br/>
Виртуальный код ключа.

*fРасширенный*<br/>
Если виртуальный код ключа является расширенным ключом, TRUE; в противном случае FALSE.

### <a name="return-value"></a>Возвращаемое значение

Локализованное название ключа, указанное параметром *vk.* Если ключ не имеет отображенного имени, `GetKeyName` возвращаетпустую строку.

### <a name="remarks"></a>Примечания

Ключевое имя, которое возвращает эта функция, происходит от драйвера клавиатуры, так что вы можете установить нелокализованный драйвер клавиатуры в локализованной версии Windows, и наоборот.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

## <a name="chotkeyctrlsethotkey"></a><a name="sethotkey"></a>CHotKeyCtrl:SetHotKey

Устанавливает ярлык клавиатуры для горячего управления ключом.

```cpp
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>Параметры

*wVirtualKeyCode*<br/>
(в) Виртуальный код ключа от ярлыка клавиатуры. Список стандартных виртуальных кодов ключей можно узнать на примере Winuser.h.

*wМодизаторы*<br/>
(в) Битовая комбинация (ИЛИ) флагов, указывающих клавиши модификатора в ярлыке клавиатуры.

Флаги модификатора следующие:

|Флаг|Соответствующий ключ|
|----------|-----------------------|
|HOTKEYF_ALT|ALT - клавиша|
|HOTKEYF_CONTROL|Ключ CTRL|
|HOTKEYF_EXT|Расширенный ключ|
|HOTKEYF_SHIFT|КЛЮЧ SHIFT|

### <a name="remarks"></a>Примечания

Виртуальный код ключа и клавиши модификатора вместе определяют ярлык клавиатуры.

## <a name="chotkeyctrlsetrules"></a><a name="setrules"></a>CHotKeyCtrl:SetRules

Вызовите эту функцию, чтобы определить недействительные комбинации и комбинацию модификаторов по умолчанию для горячего элемента управления ключа.

```cpp
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>Параметры

*wInvalidComb*<br/>
Массив флагов, который определяет недействительные комбинации ключей. Это может быть сочетание следующих значений:

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA КТРЛЗАТ

- HKCOMB_NONE неизмененные ключи

- HKCOMB_S SHIFT

- HKCOMB_SA SHIFT-ALT

- HKCOMB_SC SHIFT-CTRL

- HKCOMB_SCA СДВИГ-КТРЛ-АЛТ

*wМодизаторы*<br/>
Массив флагов, который определяет комбинацию ключей для использования при вводе пользователем недействительной комбинации. Для получения дополнительной информации о [GetHotKey](#gethotkey)флагах модификатора см.

### <a name="remarks"></a>Примечания

Когда пользователь вводит недействительную комбинацию ключей, как это определено флагами, указанными в *wInvalidComb,* система использует оператора OR для объединения ключей, введенных пользователем, с флагами, указанными в *wModifiers.* Полученная комбинация ключей преобразуется в строку, а затем отображается в горячем элементе управления ключа.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
