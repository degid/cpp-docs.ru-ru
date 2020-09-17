---
title: CmFCDesktopAlertWndInfo класс
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: f51c1b75e0c096a34b190e36e097aaca4109b5f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367588"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CmFCDesktopAlertWndInfo класс

Класс `CMFCDesktopAlertWndInfo` используется с [классом CMFCDesktopAlertWnd.](../../mfc/reference/cmfcdesktopalertwnd-class.md) Определяет элементы управления, которые отображаются, если всплывает окно оповещения.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWnDInfo::оператор](#operator_eq)||

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Ручка к отображаемому значку.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Идентификатор команды, связанный со ссылкой на окне оповещения рабочего стола.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Текст, отображаемый на окне оповещения рабочего стола.|
|[CMFCDesktopAlertWnDInfo::m_strURL](#m_strurl)|Ссылка, отображаемый на окне оповещения рабочего стола.|

## <a name="remarks"></a>Примечания

Класс `CMFCDesktopAlertWndInfo` передается [на CMFCDesktopAlertWnd::Создание метода](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) для определения элементов, отображаемых в диалоге по умолчанию окна оповещения рабочего стола. Диалог по умолчанию может содержать три элемента:

- Значок, который устанавливается по телефону [CMFCDesktopAlertWnDInfo::m_hIcon](#m_hicon).

- Метка, или текстовое сообщение, которое устанавливается по телефону [CMFCDesktopAlertWnWnDInfo::m_strText](#m_strtext).

- Ссылка, которая устанавливается по телефону [CMFCDesktopAlertWnDInfo::m_strURL](#m_strurl). Чтобы настроить команду, которая выполняется при нажатии ссылки, позвоните [по телефону CMFCDesktopAlertWnDInfo::m_nURLCmdID](#m_nurlcmdid).

Если диалог по умолчанию недостаточен, можно создать пользовательский диалог и передать его [cmfcDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) method вместо использования этого класса. Для получения дополнительной информации [см.](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCDesktopAlertWndInfo` использовать различные члены в классе. На примере показано, как настроить ручку на отображаемый значок, текст, отображаемый на окне оповещения рабочего стола, ссылку, отображаемую на окне оповещения рабочего стола, и идентификатор команды, связанный со ссылкой на окно оповещения рабочего стола. Этот пример является частью [демо-образца оповещения рабочего стола.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDesktopAlertDialog.h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>CMFCDesktopAlertWnDInfo::оператор

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Параметры

(в) *src*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon

Ручка к отображаемому значку.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID

Идентификатор команды, связанный со ссылкой на окне оповещения рабочего стола.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Примечания

Идентификатор команды отправляется владельцу всплывающее окно, когда пользователь нажимает на ссылку, указанную [CMFCDesktopAlertWnWnDInfo::m_strURL](#m_strurl).

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText

Текст, отображаемый на окне оповещения рабочего стола.

```
CString m_strText;
```

### <a name="remarks"></a>Примечания

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a>CMFCDesktopAlertWnDInfo::m_strURL

Ссылка, отображаемый на окне оповещения рабочего стола.

```
CString m_strURL;
```

### <a name="remarks"></a>Примечания

Когда пользователь нажимает на ссылку, команда, которая имеет [CMFCDesktopAlertWnWnDInfo::m_nURLCmdID](#m_nurlcmdid) идентификатор команды будет отправлен владельцу всплывающее окно.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Создание](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
