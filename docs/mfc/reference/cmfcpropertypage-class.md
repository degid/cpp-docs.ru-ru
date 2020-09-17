---
title: Класс CMFCPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: e493f016b6384a768935186c31e3fc71ade6382f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361760"
---
# <a name="cmfcpropertypage-class"></a>Класс CMFCPropertyPage

Класс `CMFCPropertyPage` поддерживает отображение всплывающих меню на странице свойств.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Формирует объект `CMFCPropertyPage`.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCPropertyPage::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|`CMFCPropertyPage::OnSetActive`|Эта функция участника вызывается инфраструктурой, когда страница выбрана пользователем и становится активной страницей. (Переопределяет [CPropertyPage:OnsetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. Для получения дополнительной информации и метода синтаксиса, [см. CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Примечания

Класс `CMFCPropertyPage` представляет отдельные страницы листа свойств, иначе известный как диалоговый ящик вкладок.

Используйте `CMFCPropertyPage` класс вместе с классом [CMFCPropertySheet.](../../mfc/reference/cmfcpropertysheet-class.md) Чтобы использовать меню на странице свойств, замените `CPropertyPage` все `CMFCPropertyPage` случаи класса классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertypage.h

## <a name="cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a>CMFCPropertyPage::CMFCPropertyPage

Формирует объект `CMFCPropertyPage`.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Идентификатор ресурса шаблона для этой страницы.

*nIDCaption*<br/>
Идентификатор ресурса метки для вкладки для этой страницы. Если 0, имя получено из шаблона диалогового окна для этой страницы. Значение по умолчанию — 0.

*lpszTemplateName*<br/>
Уотравли имя шаблона для этой страницы. Не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о параметрах конструктора см. [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)
