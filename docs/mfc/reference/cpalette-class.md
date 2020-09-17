---
title: Класс CPalette
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: f5740b3b073c4f564f9cac0fa04e5687ce1d8f00
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753677"
---
# <a name="cpalette-class"></a>Класс CPalette

Инкапсулирует цветовую палитру Windows.

## <a name="syntax"></a>Синтаксис

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPalette::Палтпал](#cpalette)|Конструирует `CPalette` объект без прилагаемых windows.» Прежде чем его `CPalette` можно будет использовать, необходимо инициализировать объект с одной из функций члена инициализации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|Заменяет записи в логической `CPalette` палитре, идентифицированной объектом. Приложение не обязано обновлять свою клиентскую область, потому что Windows карты новых записей в системной палитре немедленно.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Создает полутонную палитру для контекста `CPalette` устройства и прикрепляет его к объекту.|
|[CPalette::CreatePalette](#createpalette)|Создает цветовую палитру Windows `CPalette` и прикрепляет ее к объекту.|
|[CPalette::FromHandle](#fromhandle)|Возвращает указатель объекту `CPalette` при отваге ручки объекту палитры Windows.|
|[CPalette::GetEntryCount](#getentrycount)|Получает количество записей палитры в логической палитре.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Возвращает индекс входа в логическую палитру, которая наиболее точно соответствует цветовому значению.|
|[CPalette::GetPaletteEзаписи](#getpaletteentries)|Извлекает ряд палитры записей в логической палитре.|
|[CPalette:ResizePalette](#resizepalette)|Изменяет размер логической палитры, указанной объектом, `CPalette` на указанное количество записей.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|Устанавливает значения цвета RGB и флаги в диапазоне записей в логической палитре.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPalette:оператор Hpalette](#operator_hpalette)|Возвращает Hpalette прилагается `CPalette`к .|

## <a name="remarks"></a>Примечания

Палитра обеспечивает интерфейс между приложением и цветным устройством (например, устройством отображения). Интерфейс позволяет приложению в полной мере использовать цветовые возможности выходного устройства, не мешая при этом цветам, отображаемым другими приложениями. Windows использует логическую палитру приложения (список необходимых цветов) и системную палитру (которая определяет доступные цвета) для определения используемых цветов.

Объект `CPalette` предоставляет функции члена для манипулирования палитрой, на которую ссылается объект. Постройте `CPalette` объект и используйте его функции члена для создания фактической палитры, объекта интерфейса графического устройства (GDI), а также для управления его записями и другими свойствами.

Для получения дополнительной `CPalette`информации об использовании, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cpaletteanimatepalette"></a><a name="animatepalette"></a>CPalette::AnimatePalette

Заменяет записи в логической палитре, прикрепленной к объекту. `CPalette`

```cpp
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*nСтарт-индекс*<br/>
Определяет первую запись в палитре, которая будет анимирована.

*nNumEзаписи*<br/>
Определяет количество записей в палитре, которые будут анимированы.

*lpPaletteColors*<br/>
Указывает на первого члена массива структур [paletteENTRY,](/previous-versions/dd162769\(v=vs.85\)) чтобы заменить палитру записей, определенных *nStartIndex* и *nNumEзаписи*.

### <a name="remarks"></a>Примечания

Когда приложение `AnimatePalette`звонит, он не должен обновлять свою клиентскую область, потому что Windows карты новых записей в палитру системы немедленно.

Функция `AnimatePalette` будет изменять записи только с PC_RESERVED `palPaletteEntry` флагом, установленным в соответствующем `CPalette` члене структуры [LOGPALETTE,](/windows/win32/api/wingdi/ns-wingdi-logpalette) которая прикреплена к объекту. Более подробную информацию об этой структуре можно узнать в SDK Windows.

## <a name="cpalettecpalette"></a><a name="cpalette"></a>CPalette::Палтпал

Формирует объект `CPalette`.

```
CPalette();
```

### <a name="remarks"></a>Примечания

Объект не имеет прилагаемый палитры, пока вы не позвоните, `CreatePalette` чтобы прикрепить один.

## <a name="cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette

Создает полутонную палитру для контекста устройства.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Идентифицирует контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение должно создать полутонную палитру, когда режим растяжения контекста устройства установлен на HALFTONE. Логическая палитра полутона, возвращенная функцией члена [CreateHalftonePalette,](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) должна быть выбрана и реализована в контексте устройства до того, как называется функция [CDC:StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) или [StretchDIBits.](/windows/win32/api/wingdi/nf-wingdi-stretchdibits)

Дополнительную информацию о `CreateHalftonePalette` и . `StretchDIBits`

## <a name="cpalettecreatepalette"></a><a name="createpalette"></a>CPalette::CreatePalette

Инициализирует `CPalette` объект, создавая логическую цветовую `CPalette` палитру Windows и прикрепляя его к объекту.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Параметры

*lpLogPalette*<br/>
Указывает на структуру [LOGpalette,](/windows/win32/api/wingdi/ns-wingdi-logpalette) содержащую информацию о цветах в логической палитре.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительную информацию о структуре `LOGPALETTE` можно узнать в SDK Windows.

## <a name="cpalettefromhandle"></a><a name="fromhandle"></a>CPalette::FromHandle

Возвращает указатель объекту `CPalette` при отваге ручки объекту палитры Windows.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Параметры

*hPalette*<br/>
Ручка к цветовой палитре Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPalette` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если `CPalette` объект еще не подключен к палитре `CPalette` Windows, создается и прикрепляется временный объект. Этот `CPalette` временный объект действителен только до следующего времени, когда приложение не будет проходить время в цикле событий, после чего все временные графические объекты удаляются. Другими словами, временный объект действителен только при обработке одного сообщения окна.

## <a name="cpalettegetentrycount"></a><a name="getentrycount"></a>CPalette::GetEntryCount

Вызовите эту функцию участника, чтобы получить количество записей в данной логической палитре.

```
int GetEntryCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей в логической палитре.

## <a name="cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex

Возвращает индекс входа в логическую палитру, которая наиболее точно соответствует указанному цветовому значению.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Определяет цвет, который должен быть согласован.

### <a name="return-value"></a>Возвращаемое значение

Индекс входа в логическую палитру. Запись содержит цвет, который наиболее почти соответствует указанному цвету.

## <a name="cpalettegetpaletteentries"></a><a name="getpaletteentries"></a>CPalette::GetPaletteEзаписи

Извлекает ряд палитры записей в логической палитре.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Параметры

*nСтарт-индекс*<br/>
Определяет первую запись в логической палитре, которая будет извлечена.

*nNumEзаписи*<br/>
Определяет количество записей в логической палитре, которые необходимо получить.

*lpPaletteColors*<br/>
Указывает на массив структур данных [paletteENTRY](/previous-versions/dd162769\(v=vs.85\)) для получения записей палитры. Массив должен содержать не менее столько структур данных, чем указано в *nNumEntries.*

### <a name="return-value"></a>Возвращаемое значение

Количество записей, извлеченных из логической палитры; 0, если функция не сработала.

## <a name="cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a>CPalette:оператор Hpalette

Используйте этот оператор, чтобы получить прилагаемую ручку Windows GDI `CPalette` объекта.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка для объекта Windows `CPalette` GDI, представленная объектом; в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот оператор является оператором литья, который поддерживает прямое использование объекта Hpalette.

Для получения дополнительной информации об использовании графических объектов смотрите статью [Графические объекты](/windows/win32/gdi/graphic-objects) в Windows SDK.

## <a name="cpaletteresizepalette"></a><a name="resizepalette"></a>CPalette:ResizePalette

Изменяет размер логической палитры, прилагаемый к `CPalette` объекту, на количество записей, указанных *nNumEntries.*

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Параметры

*nNumEзаписи*<br/>
Определяет количество записей в палитре после того, как она была уменьшена.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если палитра была успешно переобезврена; в противном случае 0.

### <a name="remarks"></a>Примечания

Если приложение `ResizePalette` призывает уменьшить размер палитры, записи, оставшиеся в переразмерной палитре, остаются неизменными. Если приложение `ResizePalette` призывает увеличить палитру, дополнительные записи палитры устанавливаются на черный цвет (красные, зеленые и синие значения все 0), а флаги для всех дополнительных записей установлены на 0.

Для получения дополнительной информации `ResizePalette`о API Windows, см. [ResizePalette](/windows/win32/api/wingdi/nf-wingdi-resizepalette) в Windows SDK.

## <a name="cpalettesetpaletteentries"></a><a name="setpaletteentries"></a>CPalette::SetPaletteEntries

Устанавливает значения цвета RGB и флаги в диапазоне записей в логической палитре.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*nСтарт-индекс*<br/>
Определяет первую запись в логической палитре, которая будет установлена.

*nNumEзаписи*<br/>
Определяет количество записей в логической палитре, которая будет установлена.

*lpPaletteColors*<br/>
Указывает на массив структур данных [paletteENTRY](/previous-versions/dd162769\(v=vs.85\)) для получения записей палитры. Массив должен содержать не менее столько структур данных, чем указано в *nNumEntries.*

### <a name="return-value"></a>Возвращаемое значение

Количество записей, установленных в логической палитре; 0, если функция не сработала.

### <a name="remarks"></a>Примечания

Если логическая палитра выбрана в контексте устройства при вызове `SetPaletteEntries`приложения, изменения не вступят в силу до тех пор, пока приложение не позвонит [cdc::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).

Для получения дополнительной информации [см.](/previous-versions/dd162769\(v=vs.85\))

## <a name="see-also"></a>См. также раздел

[MFC Образец DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEзаписи](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)
