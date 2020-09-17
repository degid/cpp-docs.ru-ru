---
title: Класс CIPAddressCtrl
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: 0613dea766b022acf140a82bb4b01784793c2589
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754966"
---
# <a name="cipaddressctrl-class"></a>Класс CIPAddressCtrl

Предоставляет функциональные возможности стандартного элемента управления "IP-адрес" Windows.

## <a name="syntax"></a>Синтаксис

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Формирует объект `CIPAddressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Очищает содержимое IP-адреса управления.|
|[CIPAddressCtrl::Создание](#create)|Создает IP-адрес управления и прикрепляет его к объекту. `CIPAddressCtrl`|
|[CIPAddressCtrl::CreateEx](#createex)|Создает элемент управления IP-адресом с указанными расширенными стилями Windows и прикрепляет его к объекту. `CIPAddressCtrl`|
|[CIPAddressCtrl::GetAddress](#getaddress)|Извлекает значения адресов для всех четырех полей в IP-управлении.|
|[CIPAddressCtrl::IsBlank](#isblank)|Определяет, пусты ли все поля в управлении IP-адресами.|
|[CIPAddressCtrl::SetAddress](#setaddress)|Устанавливает значения адресов для всех четырех полей в ip-управлении.|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Устанавливает фокус клавиатуры на указанное поле в IP-управлении.|
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Устанавливает диапазон в указанном поле в IP-управлении.|

## <a name="remarks"></a>Примечания

Контроль IP-адреса, элемент управления, аналогичный правку, позволяет вводить и манипулировать числовым адресом в формате Интернет-протокола (IP).

Этот элемент управления `CIPAddressCtrl` (и, следовательно, класс) доступен только для программ, работающих в Microsoft Internet Explorer 4.0 и позже. Они также будут доступны в рамках будущих версий Windows и Windows NT.

Более подробную информацию о контроле IP-адреса [можно](/windows/win32/Controls/ip-address-controls) узнать в SDK Windows.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl

Создает объект `CIPAddressCtrl`.

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a>CIPAddressCtrl::ClearAddress

Очищает содержимое IP-адреса управления.

```cpp
void ClearAddress();
```

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_CLEARADDRESS,](/windows/win32/Controls/ipm-clearaddress)как описано в SDK Windows.

## <a name="cipaddressctrlcreate"></a><a name="create"></a>CIPAddressCtrl::Создание

Создает IP-адрес управления и прикрепляет его к объекту. `CIPAddressCtrl`

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Стиль управления IP-адресом. Примените комбинацию стилей окон. Вы должны включить WS_CHILD стиль, потому что элемент управления должен быть окном ребенка. Смотрите [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в SDK Windows для списка стилей windows.

*rect*<br/>
Ссылка на размер и положение IP-адреса. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Указатель на родительское окно IP-адреса Control. Она не должна быть NULL.

*nID*<br/>
Идентификатор IP-адреса control.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если инициализация была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы строите `CIPAddressCtrl` объект в два этапа.

1. Вызовите конструктора, `CIPAddressCtrl` который создает объект.

1. Вызов `Create`, который создает IP-адрес управления.

Если вы хотите использовать расширенные стили `Create`окон с вашим управлением, позвоните [CreateEx](#createex) вместо .

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a>CIPAddressCtrl::CreateEx

Вызовите эту функцию, чтобы создать элемент управления `CIPAddressCtrl` (окно ребенка) и связать его с объектом.

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
Стиль управления IP-адресом. Примените комбинацию стилей окон. Вы должны включить WS_CHILD стиль, потому что элемент управления должен быть окном ребенка. Смотрите [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в SDK Windows для списка стилей windows.

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

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a>CIPAddressCtrl::GetAddress

Извлекает значения адресов для всех четырех полей в IP-управлении.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>Параметры

*nField0*<br/>
Ссылка на значение поля 0 с упакованного IP-адреса.

*nField1*<br/>
Ссылка на значение поля 1 с упакованного IP-адреса.

*nField2*<br/>
Ссылка на значение поля 2 с упакованного IP-адреса.

*nField3*<br/>
Ссылка на значение поля 3 с упакованного IP-адреса.

*dwАдрес*<br/>
Ссылка на адрес значения DWORD, который получает IP-адрес. Смотрите **замечания** для таблицы, которая показывает, как *dwAddress* заполнен.

### <a name="return-value"></a>Возвращаемое значение

Количество непустых полей в IP-управлении.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_GETADDRESS,](/windows/win32/Controls/ipm-getaddress)как описано в SDK Windows. В первом прототипе выше, номера в полях от 0 до 3 управления, читать слева направо соответственно, заполнить четыре параметра. Во втором прототипе выше, *dwAddress* заселен следующим образом.

|Поле|Биты, содержащие значение поля|
|-----------|-------------------------------------|
|0|от 24 до 31|
|1|от 16 до 23|
|2|от 8 до 15|
|3|От 0 до 7|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a>CIPAddressCtrl::IsBlank

Определяет, пусты ли все поля в управлении IP-адресами.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если все поля ip-адреса управления пусты; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_ISBLANK,](/windows/win32/Controls/ipm-isblank)как описано в SDK Windows.

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a>CIPAddressCtrl::SetAddress

Устанавливает значения адресов для всех четырех полей в ip-управлении.

```cpp
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>Параметры

*nField0*<br/>
Значение поля 0 с упакованного IP-адреса.

*nField1*<br/>
Значение поля 1 с упакованного IP-адреса.

*nField2*<br/>
Значение поля 2 с упакованного IP-адреса.

*nField3*<br/>
Значение поля 3 с упакованного IP-адреса.

*dwАдрес*<br/>
Значение DWORD, содержащее новый IP-адрес. Смотрите **замечания** для таблицы, которая показывает, как заполняется значение DWORD.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETADDRESS,](/windows/win32/Controls/ipm-setaddress)как описано в SDK Windows. В первом прототипе выше, номера в полях от 0 до 3 управления, читать слева направо соответственно, заполнить четыре параметра. Во втором прототипе выше, *dwAddress* заселен следующим образом.

|Поле|Биты, содержащие значение поля|
|-----------|-------------------------------------|
|0|от 24 до 31|
|1|от 16 до 23|
|2|от 8 до 15|
|3|От 0 до 7|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus

Устанавливает фокус клавиатуры на указанное поле в IP-управлении.

```cpp
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Параметры

*nФилд*<br/>
Индекс полей на нулевой основе, на который следует установить фокус. Если это значение больше, чем количество полей, фокус устанавливается на первое пустое поле. Если все поля не пустые, фокус устанавливается на первое поле.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETFOCUS,](/windows/win32/Controls/ipm-setfocus)как описано в SDK Windows.

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange

Устанавливает диапазон в указанном поле в IP-управлении.

```cpp
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Параметры

*nФилд*<br/>
Индекс полей на нулевой основе, к которому будет применяться диапазон.

*nLower*<br/>
Ссылка на ряд, получающий нижний предел указанного поля в данном IP-управлении.

*nУппер*<br/>
Ссылка на ряд, получающий верхний предел указанного поля в данном IP-управлении.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETRANGE,](/windows/win32/Controls/ipm-setrange)как описано в SDK Windows. Используйте два параметра, *nLower* и *nUpper*, чтобы указать нижние и верхние пределы поля, вместо параметра *wRange,* используемого с сообщением Win32.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
