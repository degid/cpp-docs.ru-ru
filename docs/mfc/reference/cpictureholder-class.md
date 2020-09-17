---
title: Класс CPictureHolder
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: edb93b05c1187d2c78f4c1120ee76282167c9b49
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753594"
---
# <a name="cpictureholder-class"></a>Класс CPictureHolder

Реализует свойство Picture, которое позволяет пользователю отображать изображение в элементе управления.

## <a name="syntax"></a>Синтаксис

```
class CPictureHolder
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|Формирует объект `CPictureHolder`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::CreateEmpty](#createempty)|Создает пустой объект `CPictureHolder`.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Создает `CPictureHolder` объект из битной карты.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|Создает `CPictureHolder` объект из значка.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Создает `CPictureHolder` объект из метафайла.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Извлекает строку, отображаемую в браузере свойств контейнера управления.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Возвращает `CPictureHolder` `IDispatch` интерфейс объекта.|
|[CPictureHolder::GetType](#gettype)|Сообщает, `CPictureHolder` является ли объект битовой картой, метафайлом или иконой.|
|[CPictureHolder::Render](#render)|Рендерс изображение.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Устанавливает `CPictureHolder` `IDispatch` интерфейс объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::m_pPict](#m_ppict)|Указатель на объект изображения.|

## <a name="remarks"></a>Примечания

`CPictureHolder`не имеет базового класса.

С свойством stock Picture разработчик может указать битную карту, значок или метафайл для отображения.

Для получения информации о создании [MFC ActiveX Controls: Using Pictures in an ActiveX Control](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)пользовательских свойств изображения, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPictureHolder`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a>CPictureHolder::CPictureHolder

Формирует объект `CPictureHolder`.

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a>CPictureHolder::CreateEmpty

Создает пустой `CPictureHolder` объект и соединяет `IPicture` его с интерфейсом.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект успешно создан; в противном случае 0.

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap

Использует бит-карту для инициализации объекта изображения в `CPictureHolder`.

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*idРесурс*<br/>
Идентификатор ресурса ресурса ресурса bitmap.

*pBitmap*<br/>
Указатель на объект [CBitmap.](../../mfc/reference/cbitmap-class.md)

*pPal*<br/>
Указатель на объект [CPalette.](../../mfc/reference/cpalette-class.md)

*bTransferВладение*<br/>
Указывает, будет ли объект изображения владельцем бит-карты и объектов палитры.

*Hbm*<br/>
Обработка к биткарте, `CPictureHolder` из которой создается объект.

*hpal*<br/>
Обработка к палитре, используемой для визуализации битной карты.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* является правдой, абонент не должен использовать битmap или объект палитры в любом случае после этого вызова возвращается. Если *bTransferOwnership* является FALSE, абонент несет ответственность за обеспечение того, чтобы битовая карта и объекты палитры оставались действительными в течение всего срока службы объекта изображения.

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a>CPictureHolder::CreateFromIcon

Использует значок для инициализации объекта изображения в `CPictureHolder`.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*idРесурс*<br/>
Идентификатор ресурса ресурса ресурса bitmap.

*hIcon*<br/>
Обработка к значку, `CPictureHolder` из которой создается объект.

*bTransferВладение*<br/>
Указывает, будет ли объект изображения владельцем объекта иконы.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* является правдой, абонент не должен использовать объект значка в любом случае после этого вызова возвращается. Если *bTransferOwnership* является FALSE, абонент несет ответственность за обеспечение того, чтобы объект значка оставался действительным в течение всего срока службы объекта изображения.

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile

Использует метафайл для инициализации `CPictureHolder`объекта изображения в .

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*Hmf*<br/>
Обработка метафайла, используемого `CPictureHolder` для создания объекта.

*xExt*<br/>
X степень изображения.

*yExt*<br/>
Y степень картины.

*bTransferВладение*<br/>
Указывает, будет ли объект изображения владельцем метафайлного объекта.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* является правдой, абонент не должен использовать объект метафайла в любом случае после этого вызова возвращается. Если *bTransferOwnership* является FALSE, абонент несет ответственность за обеспечение того, чтобы объект метафайла оставался действительным в течение всего срока службы объекта изображения.

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a>CPictureHolder::GetDisplayString

Извлекает строку, отображаемую в браузере свойств контейнера.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Параметры

*strValue*<br/>
Ссылка на [CString,](../../atl-mfc-shared/reference/cstringt-class.md) которая должна удерживать строку дисплея.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если строка успешно извлечена; в противном случае 0.

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch

Эта функция возвращает указатель `CPictureHolder` в `IPictureDisp` интерфейс объекта.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель `IPictureDisp` на `CPictureHolder` интерфейс объекта.

### <a name="remarks"></a>Примечания

Звонящее `Release` должно вызвать этот указатель, когда он закончил с ним.

## <a name="cpictureholdergettype"></a><a name="gettype"></a>CPictureHolder::GetType

Указывает, является ли изображение битовой картой, метафайлом или иконой.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее тип изображения. Возможные значения и их значения таковы:

|Значение|Значение|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder`объект унифицирован.|
|PICTYPE_NONE|`CPictureHolder`объект пуст.|
|PICTYPE_BITMAP|Изображение бит-карта.|
|PICTYPE_METAFILE|Изображение - это метафил.|
|PICTYPE_ICON|Изображение является иконой.|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a>CPictureHolder::m_pPict

Указатель `IPicture` на `CPictureHolder` интерфейс объекта.

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a>CPictureHolder::Render

Renders изображение в прямоугольнике, на который ссылается *rcRender*.

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст отображения, в котором отображается изображение.

*rcRender*<br/>
Прямоугольник, в котором изображение должно быть отрисовано.

*rcWBounds*<br/>
Прямоугольник, представляющий ограничивающий прямоугольник объекта, рендеринга изображения. Для элемента управления этот прямоугольник представляет собой параметр *rcBounds,* передаваемый переопределением [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch

Подключает `CPictureHolder` объект `IPictureDisp` к интерфейсу.

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на `IPictureDisp` новый интерфейс.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFontHolder](../../mfc/reference/cfontholder-class.md)
