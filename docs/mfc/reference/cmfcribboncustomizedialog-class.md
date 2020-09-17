---
title: CMFCRibbonНастройкаДиолог класс
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: a66c0a19c04e0a900b91c0c28c45bb9c766d25c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375207"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonНастройкаДиолог класс

Отображает ленту **Настройка страницы.**

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonCustomizeДиалог::CMFCRibbonCustomizeДиалог](#cmfcribboncustomizedialog)|Формирует объект `CMFCRibbonCustomizeDialog`.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|

## <a name="remarks"></a>Примечания

MFC автоматически мгновенно обрабатывает этот класс, если вы не обрабатываете AFX_WM_ON_RIBBON_CUSTOMIZE сообщение, или если вы возвращаете 0 от обработчика сообщений.

Если вы хотите использовать этот класс в приложении для отображения ленточной `DoModal` **телефонной** настройки диалогового окна, просто мгновенно его и вызов метода.

Поскольку этот класс происходит от [cmFCPropertySheet Class,](../../mfc/reference/cmfcpropertysheet-class.md)вы `CMFCPropertySheet` можете добавлять пользовательские страницы с помощью API.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonНастройкаДиалог](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncustomizedialog.h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeДиалог::CMFCRibbonCustomizeДиалог

Формирует объект `CMFCRibbonCustomizeDialog`.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно (обычно основной кадр).

*pRibbon*<br/>
(в) Указатель на `CMFCRibbonBar` то, что должно быть настроено.

### <a name="example"></a>Пример

В следующем примере показано, `CMFCRibbonCustomizeDialog` как построить объект.

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>Примечания

Конструктор мгновенно увеличивает объект [класса CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) и добавляет его в коллекцию страниц листа свойств.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
