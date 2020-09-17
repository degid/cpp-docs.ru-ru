---
title: Класс COlePropertiesDialog
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: f065894ff49af755ab4020f71b0213b19db49054
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374894"
---
# <a name="colepropertiesdialog-class"></a>Класс COlePropertiesDialog

Инкапсулирует стандартное диалоговое окно свойств объекта OLE Windows.

## <a name="syntax"></a>Синтаксис

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColePropertiesДиалог::COlePropertiesDialog](#colepropertiesdialog)|Формирует объект `COlePropertiesDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColePropertiesDialog::DoModal](#domodal)|Отображает диалоговую коробку и позволяет пользователю сделать выбор.|
|[ColePropertiesDialog::OnapplyScale](#onapplyscale)|Вызывается рамочой при изменении масштабирования элемента документа.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColePropertiesДиалог::m_gp](#m_gp)|Структура, используемая для инициализации `COlePropertiesDialog` страницы объекта "Общая".|
|[ColePropertiesДиалог::m_lp](#m_lp)|Структура, используемая для инициализации `COlePropertiesDialog` страницы объекта "Link".|
|[ColePropertiesДиалог::m_op](#m_op)|Структура, используемая для `COlePropertiesDialog` инициализации объекта.|
|[ColePropertiesДиалог::m_psh](#m_psh)|Структура, используемая для добавления дополнительных пользовательских страниц свойств.|
|[ColePropertiesДиалог::m_vp](#m_vp)|Структура, используемая для настройки страницы `COlePropertiesDialog` объекта "Вид".|

## <a name="remarks"></a>Примечания

Общие диалоговые ящики OLE Object Properties обеспечивают простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows. Эти свойства включают, среди прочего, информацию о файле, представленном элементом документа, варианты отображения значка и масштабирования изображения, а также информацию о ссылке элемента (если элемент связан).

Чтобы использовать `COlePropertiesDialog` объект, сначала создайте `COlePropertiesDialog` объект с помощью конструктора. После построения диалогового окна `DoModal` позвоните функции участника для отображения диалогового окна и позвольте пользователю изменить любые свойства элемента. `DoModal`возвращает сярот, выбрал ли пользователь кнопку OK (IDOK) или кнопку «Отмена» (IDCANCEL). В дополнение к кнопкам OK и Cancel есть кнопка Apply. Когда пользователь выбирает Apply, любые изменения, внесенные в свойства элемента документа, применяются к элементу, и его изображение автоматически обновляется, но остается активным.

Член [m_psh](#m_psh) данных является указателем на структуру, `PROPSHEETHEADER` и в большинстве случаев вам не нужно будет получать к ней явное доступ. Одно исключение, когда вам нужны дополнительные страницы свойств за пределами страниц "Общий", "Вид" и "Ссылка". В этом случае можно `m_psh` изменить состав данных, чтобы `DoModal` включить пользовательские страницы перед вызовом функции участника.

Для получения дополнительной информации о OL [Dialog Boxes in OLE](../../mfc/dialog-boxes-in-ole.md)диалоговые коробки, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>ColePropertiesДиалог::COlePropertiesDialog

Создает объект `COlePropertiesDialog`.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, свойства которого доступны.

*nScaleMin*<br/>
Минимальный процент масштабирования для изображения элемента документа.

*nScaleMax*<br/>
Максимальный процент масштабирования для изображения элемента документа.

*pParentWnd*<br/>
Указатель на родителей или владельца диалогового окна.

### <a name="remarks"></a>Примечания

Из этого следует из `COlePropertiesDialog` общего класса диалогов OLE Object Properties, чтобы реализовать масштабирование элементов документа. Любые диалоговые коробки, реализованные экземпляром этого класса, не будут поддерживать масштабирование элемента документа.

По умолчанию общий диалоговый ящик OLE Object Properties имеет три страницы по умолчанию:

- Общие сведения

   Эта страница содержит системную информацию для файла, представленного выбранным элементом документа. С этой страницы пользователь может преобразовать выбранный элемент в другой тип.

- Представление

   Эта страница содержит параметры отображения элемента, изменения значка и изменения масштабирования изображения.

- Ссылка

   Эта страница содержит параметры изменения местоположения связанного элемента и обновления связанного элемента. С этой страницы пользователь может разорвать ссылку на выбранный элемент.

Чтобы добавить страницы, выходящие [m_psh](#m_psh) за рамки, предусмотренные по `COlePropertiesDialog`умолчанию, измените переменную m_psh члена перед выходом из конструктора вашего класса, полученного. Это передовая реализация `COlePropertiesDialog` конструктора.

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a>ColePropertiesDialog::DoModal

Вызовите эту функцию участника для отображения диалогового окна OL Object Properties Windows и позвольте пользователю просматривать и/или изменять различные свойства элемента документа.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL в случае успеха; в противном случае 0. IDOK и IDCANCEL являются константами, указывающими на то, выбрал ли пользователь кнопку OK или Cancel.

При возврате IDCANCEL можно позвонить в функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка.

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a>ColePropertiesДиалог::m_gp

Структура типа [OLEUIGNRLPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw), используемая для инициализации общей страницы диалогового окна OLE Object Properties.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Примечания

На этой странице показан тип и размер встраивания и позволяет пользователю получить доступ к диалоговому окну Convert. На этой странице также отображается пункт назначения ссылки, если объект является ссылкой.

Для получения дополнительной `OLEUIGNRLPROPS` информации о структуре, см.

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a>ColePropertiesДиалог::m_lp

Структура типа [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw), используется для инициализации страницы ссылки в диалоговом поле OLE Object Properties.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Примечания

На этой странице отображается местоположение связанного элемента и пользователь может обновить или разбить ссылку на элемент.

Для получения дополнительной `OLEUILINKPROPS` информации о структуре, см.

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a>ColePropertiesДиалог::m_op

Структура типа [OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw), используемая для инициализации общего диалогового ящика OLE Object Properties.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Примечания

Эта структура содержит членов, используемых для инициализации страниц General, Link и View.

Для получения дополнительной информации, см OLEUIOBJECTPROPS и [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw) структур в Windows SDK.

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a>ColePropertiesДиалог::m_psh

Структура типа [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2), члены которой хранят характеристики объекта диалога.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Примечания

После построения `COlePropertiesDialog` объекта можно `m_psh` использовать для установки различных аспектов диалогового окна перед вызовом функции `DoModal` участника.

Если вы `m_psh` измените напрямую данный, вы отмените любое поведение по умолчанию.

Для получения дополнительной `PROPSHEETHEADER` информации о структуре, см.

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a>ColePropertiesДиалог::m_vp

Структура типа [OLEUIVIEWPROPS,](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)используемая для инициализации страницы View в диалоговом поле OLE Object Properties.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Примечания

Эта страница позволяет пользователю переключаться между "контентом" и "иконическим" представлениями объекта и изменять его масштабирование в контейнере. Он также позволяет пользователю получить доступ к диалоговому окону изменения, когда объект отображается в виде значка.

Для получения дополнительной `OLEUIVIEWPROPS` информации о структуре, см.

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>ColePropertiesDialog::OnapplyScale

Вызывается инфраструктурой при изменении значения масштабирования и выбрано или OK, либо Apply.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, свойства которого доступны.

*nТекущийшкал*<br/>
Численное значение шкалы диалога.

*b RelativeToOrig*<br/>
Указывает, применяется ли масштабирование к исходной размеру элемента документа.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обрабатывается; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Вы должны переопределить эту функцию, чтобы включить элементы управления масштабирования.

> [!NOTE]
> Перед отображением общего диалогового окна OLE Object Properties фреймворк вызывает эту функцию с NULL для *pItem* и - 1 для *nCurrentScale.* Это делается для определения того, следует ли включено элементы управления масштабирования.

## <a name="see-also"></a>См. также раздел

[MFC Образец CIRC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Класс CPropertyPage](../../mfc/reference/cpropertypage-class.md)
