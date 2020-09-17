---
title: Класс CFontHolder
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 36fbebc39101c5534bd52d4f79fee5286487a6e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754995"
---
# <a name="cfontholder-class"></a>Класс CFontHolder

Реализует свойство Font и инкапсулирует функциональность объекта шрифта Windows и интерфейса `IFont` .

## <a name="syntax"></a>Синтаксис

```
class CFontHolder
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|Формирует объект `CFontHolder`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Извлекает строку, отображаемую в браузере свойств контейнера.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Возвращает интерфейс шрифта. `IDispatch`|
|[CFontHolder::GetFontHandle](#getfonthandle)|Возвращает ручку шрифту Windows.|
|[CFontHolder::InitializeFont](#initializefont)|Инициализирует объект `CFontHolder`.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Извлекает информацию для связанного шрифта.|
|[CFontHolder::ReleaseFont](#releasefont)|Отключает `CFontHolder` объект от `IFont` интерфейсов и `IFontNotification` интерфейсов.|
|[CFontHolder::Выбрать](#select)|Выберите ресурс шрифта в контексте устройства.|
|[CFontHolder::SetFont](#setfont)|Подключает `CFontHolder` объект `IFont` к интерфейсу.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFontHolder:::m_pFont](#m_pfont)|Указатель `IFont` на `CFontHolder` интерфейс объекта.|

## <a name="remarks"></a>Примечания

`CFontHolder`не имеет базового класса.

Используйте этот класс для реализации пользовательских свойств шрифта для управления. Для получения информации о создании [ActiveX Controls: Using Fonts](../../mfc/mfc-activex-controls-using-fonts.md)таких свойств см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CFontHolder`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a>CFontHolder::CFontHolder

Формирует объект `CFontHolder`.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Параметры

*pNotify*<br/>
Указатель на интерфейс `IPropertyNotifySink` шрифта.

### <a name="remarks"></a>Примечания

Перед его `InitializeFont` использованием необходимо позвонить, чтобы инициализировать полученный объект.

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a>CFontHolder::GetDisplayString

Извлекает строку, которая может отображаться в браузере свойств контейнера.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Параметры

*strValue*<br/>
Ссылка на [CString,](../../atl-mfc-shared/reference/cstringt-class.md) которая должна удерживать строку дисплея.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если строка успешно извлечена; в противном случае 0.

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a>CFontHolder::GetFontDispatch

Вызов исправьте эту функцию, чтобы получить указатель на интерфейс отправки шрифта.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель `IFontDisp` на `CFontHolder` интерфейс объекта. Обратите внимание, что `GetFontDispatch` функция, вызываемый вызовами, должна вызывать `IUnknown::Release` этот указатель интерфейса, когда она будет сделана с ней.

### <a name="remarks"></a>Примечания

Позвоните `InitializeFont` `GetFontDispatch`перед вызовом .

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a>CFontHolder::GetFontHandle

Вызовите эту функцию, чтобы получить ручку для шрифта Windows.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Параметры

*cyLogical*<br/>
Высота, в логических единицах, прямоугольника, в котором элемент управления обращается.

*цихиметрические*<br/>
Высота, в MM_HIMETRIC единицах, управления.

### <a name="return-value"></a>Возвращаемое значение

Ручка к объекту шрифта; в противном случае NULL.

### <a name="remarks"></a>Примечания

Соотношение *cyLogical* и *cyHimetric* используется для расчета правильного размера дисплея, в логических единицах, для размера точки шрифта, выраженного в MM_HIMETRIC единиц:

Размер дисплея - *(цилогический* / *цихиметрический*) размер шрифта X

Версия без параметров возвращает ручку шрифту размером правильно для экрана.

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a>CFontHolder::InitializeFont

Инициализирует объект `CFontHolder`.

```cpp
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Параметры

*pFontDesc*<br/>
Указатель на структуру описания шрифта [(FONTDESC),](/windows/win32/api/olectl/ns-olectl-fontdesc)которая определяет характеристики шрифта.

*pFontDispАмбent*<br/>
Указатель на свойство окружающего шрифта контейнера.

### <a name="remarks"></a>Примечания

Если *pFontDispAmbient* не является `CFontHolder` NULL, объект подключен к `IFont` клону интерфейса, используемого свойством окружающего шрифта контейнера.

Если *pFontDispAmbient* является NULL, новый объект шрифта создается либо из описания шрифта, на который указывает *pFontDesc,* либо, если *pFontDesc* является NULL, из описания по умолчанию.

Вызовите эту функцию после построения `CFontHolder` объекта.

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a>CFontHolder:::m_pFont

Указатель `IFont` на `CFontHolder` интерфейс объекта.

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics

Извлекает информацию о физическом `CFontHolder` шрифте, представленном объектом.

```cpp
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Параметры

*lptm*<br/>
Указатель на структуру [TEXTMETRIC,](/windows/win32/api/wingdi/ns-wingdi-textmetricw) которая будет получать информацию.

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a>CFontHolder::ReleaseFont

Эта функция отключает `CFontHolder` объект `IFont` от интерфейса.

```cpp
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a>CFontHolder::Выбрать

Вызовите эту функцию, чтобы выбрать шрифт элемента управления в указанном контексте устройства.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Контекст устройства, в который выбран шрифт.

*cyLogical*<br/>
Высота, в логических единицах, прямоугольника, в котором элемент управления обращается.

*цихиметрические*<br/>
Высота, в MM_HIMETRIC единицах, управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заменяемый шрифт.

### <a name="remarks"></a>Примечания

Смотрите [GetFontHandle](#getfonthandle) для обсуждения *циклических* и *цихиметрических* параметров.

## <a name="cfontholdersetfont"></a><a name="setfont"></a>CFontHolder::SetFont

Выпускает любой существующий `CFontHolder` шрифт и `IFont` соединяет объект с интерфейсом.

```cpp
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Параметры

*pNewFont*<br/>
Указатель на `IFont` новый интерфейс.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPropExchange](../../mfc/reference/cpropexchange-class.md)
