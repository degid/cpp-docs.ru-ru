---
title: Класс Кмфкриббонкустомизепропертипаже
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 92408e91b41b474da3a2da6ad0646feb3a6b8fc2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831844"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>Класс Кмфкриббонкустомизепропертипаже

Реализует пользовательскую страницу для диалогового окна **Настройка** в приложениях на основе ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|[Кмфкриббонкустомизепропертипаже:: Кмфкриббонкустомизепропертипаже](#cmfcribboncustomizepropertypage)|Формирует объект `CMFCRibbonCustomizePropertyPage`.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфкриббонкустомизепропертипаже:: Аддкустомкатегори](#addcustomcategory)|Добавляет пользовательскую категорию в поле со списком **команд** .|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкриббонкустомизепропертипаже:: ОНОК](#onok)|Вызывается системой, когда пользователь нажимает кнопку " **ОК** " в диалоговом окне " **Настройка** ".|

## <a name="remarks"></a>Примечания

Если необходимо добавить пользовательские команды в диалоговое окно **Настройка** , необходимо выполнить обработку сообщения AFX_WM_ON_RIBBON_CUSTOMIZE. В обработчике сообщений создайте экземпляр `CMFCRibbonCustomizePropertyPage` объекта в стеке. Создайте список настраиваемых команд, а затем вызовите, `AddCustomCategory` чтобы добавить новую страницу в диалоговое окно " **Настройка** ".

## <a name="example"></a>Пример

В следующем примере показано, как создать `CMFCRibbonCustomizePropertyPage` объект и добавить пользовательскую категорию.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[кмфкриббонкустомизепропертипаже](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксриббонкустомизедиалог.h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a> Кмфкриббонкустомизепропертипаже:: Аддкустомкатегори

Добавляет пользовательскую категорию в поле со списком **команд** .

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*\
окне Указывает имя пользовательской категории.

*лстидс*\
окне Содержит идентификаторы команд ленты, которые должны отображаться в пользовательской категории.

### <a name="remarks"></a>Примечания

Этот метод добавляет категорию с именем *лпсзнаме* в поле со списком **команд** . Когда пользователь выбирает категорию, команды, указанные в *лстидс* , отображаются в списке команд.

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a> Кмфкриббонкустомизепропертипаже:: Кмфкриббонкустомизепропертипаже

Формирует объект `CMFCRibbonCustomizePropertyPage`.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Параметры

*приббонбар*<br/>
окне Указатель на элемент управления ленты, для которого необходимо настроить параметры.

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a> Кмфкриббонкустомизепропертипаже:: ОНОК

Каллелд системой, когда пользователь нажимает кнопку " **ОК** " в диалоговом окне " **Настройка** ".

```
virtual void OnOK();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию применяет параметры, выбранные в диалоговом окне **Настройка** , к панели быстрого доступа.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
