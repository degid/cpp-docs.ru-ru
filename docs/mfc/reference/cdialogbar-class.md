---
title: Класс CDialogBar
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: cf9a2658807959108b3bb0af672d4c1835b58bc5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375675"
---
# <a name="cdialogbar-class"></a>Класс CDialogBar

Предоставляет функциональные возможности немодального диалогового окна Windows на панели элементов управления.

## <a name="syntax"></a>Синтаксис

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDialogBar::CDialogBar](#cdialogbar)|Формирует объект `CDialogBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDialogBar::Создание](#create)|Создает диалоговую панель Windows и `CDialogBar` прикрепляет его к объекту.|

## <a name="remarks"></a>Примечания

Панель диалогов напоминает диалоговое окно, в котором он содержит стандартные элементы управления Windows, между которыми пользователь может прокладку. Еще одно сходство заключается в том, что вы создаете шаблон диалога для представления диалоговой панели.

Создание и использование диалогового бара аналогично `CFormView` созданию и использованию объекта. Во-первых, используйте [редактор диалогов](../../windows/dialog-editor.md) для определения шаблона диалога со стилем WS_CHILD и никакой другой стиль. Шаблон не должен иметь стиль WS_VISIBLE. В коде приложения позвоните конструктору, чтобы построить `CDialogBar` объект, затем позвоните, `Create` чтобы `CDialogBar` создать окно диалог-бара и прикрепить его к объекту.

Для получения `CDialogBar`дополнительной информации о , см. статью [Dialog бары](../../mfc/dialog-bars.md) и [техническое примечание 31](../../mfc/tn031-control-bars.md), контроль баров.

> [!NOTE]
> В текущем выпуске `CDialogBar` объект не может размещать элементы управления Windows Forms. Для получения дополнительной информации о windows Forms управления в visual C , [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a>CDialogBar::CDialogBar

Формирует объект `CDialogBar`.

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a>CDialogBar::Создание

Загружает шаблон ресурса диалог-бокс, указанный `lpszTemplateName` или `nIDTemplate`создающий окно диалог-бара, устанавливает `CDialogBar` свой стиль и связывает его с объектом.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительский `CWnd` объект.

*lpszTemplateName*<br/>
Указатель на название шаблона ресурсов диалогового ящика `CDialogBar` объекта.

*nStyle*<br/>
Стиль панели инструментов. Дополнительные стили панели инструментов поддерживаются:

- CBRS_TOP панель управления находится в верхней части окна рамы.

- CBRS_BOTTOM панель управления находится в нижней части окна кадра.

- CBRS_NOALIGN панель управления не перепозиционируется при повторном размере.

- CBRS_TOOLTIPS панели Управления отображает советы инструментов.

- CBRS_SIZE_DYNAMIC панель управления динамична.

- CBRS_SIZE_FIXED панель управления фиксируется.

- CBRS_FLOATING панель управления плавает.

- CBRS_FLYBY-хау отображает информацию о кнопке.

- CBRS_HIDE_INPLACE панель управления не отображается пользователю.

*nID*<br/>
Идентификатор управления диалогового бара.

*nIDTemplate*<br/>
Идентификатор `CDialogBar` ресурса шаблона диалогового ящика объекта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если указать CBRS_TOP или CBRS_BOTTOM стилю выравнивания, ширина панели диалогов — это ширина окна кадра, а высота — ресурса, указанного *nIDTemplate.* Если указать CBRS_LEFT или CBRS_RIGHT стилю выравнивания, высота диалогового бара — высота окна кадра, а ширина — ресурса, указанного *nIDTemplate.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)
