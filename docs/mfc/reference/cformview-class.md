---
title: Класс CFormView
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: a9b897c661731878f0bf78c9d04ae7c4ba28cd42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373800"
---
# <a name="cformview-class"></a>Класс CFormView

Базовый класс, используемый для представлений формы.

## <a name="syntax"></a>Синтаксис

```
class CFormView : public CScrollView
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|Формирует объект `CFormView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Используется для синхронизации во время инициализации.|

## <a name="remarks"></a>Примечания

По сути, представление формы — это представление, содержащее элементы управления. Эти элементы управления располагаются на основе ресурса шаблона диалогового окна. Используйте `CFormView`, если вы хотите задействовать формы в своем приложении. Эти представления поддерживают прокрутку, по мере необходимости, используя функциональность [CScrollView.](../../mfc/reference/cscrollview-class.md)

При [создании приложения на основе форм](../../mfc/reference/creating-a-forms-based-mfc-application.md)вы можете основывать `CFormView`его класс представления на, что делает его приложением на основе форм.

Можно также вставить новые [темы формы](../../mfc/form-views-mfc.md) в приложения на основе просмотра документов. Даже если ваше приложение изначально не поддерживает формы, при вставке новой формы Visual C++ обеспечит их поддержку.

Приложения на основе форм рекомендуется создавать с помощью мастера приложений MFC и команды Add Class. Если вам необходимо создать приложение на основе форм без использования этих методов, [см.](../../mfc/reference/creating-a-forms-based-mfc-application.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="cformviewcformview"></a><a name="cformview"></a>CFormView::CFormView

Формирует объект `CFormView`.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Содержит строку с нулевым завершением, которая является названием ресурса диалог-шаблон.

*nIDTemplate*<br/>
Содержит идентификационный номер ресурса диалог-шаблон.

### <a name="remarks"></a>Примечания

При создании объекта типа, полученного `CFormView`из, вызвать один из конструкторов для создания объекта представления и идентификации ресурса диалога, на котором основано представление. Можно определить ресурс либо по имени (пройти строку в качестве аргумента к конструктору), либо по его идентификатору (пройти неподписанный целый ряд в качестве аргумента).

Окно представления формы и элементы управления `CWnd::Create` детьми не создаются до тех пор, пока не будет вызвано. `CWnd::Create`называется рамкой как часть процесса создания документа и представления, который определяется шаблоном документа.

> [!NOTE]
> Ваш производный класс *должен* поставлять свой собственный конструктор. В конструкторе вызвать `CFormView::CFormView`конструктора с именем ресурса или идентификатором в качестве аргумента, как показано в предыдущем обзоре класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>CFormView:IsInitDlgЗавершено

Используется MFC, чтобы убедиться, что инициализация завершена до выполнения других операций.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация для этого диалогового окна была завершена.

## <a name="see-also"></a>См. также раздел

[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Класс CScrollView](../../mfc/reference/cscrollview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Класс CScrollView](../../mfc/reference/cscrollview-class.md)
