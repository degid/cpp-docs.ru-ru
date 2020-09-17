---
title: Класс CBrush
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: 15132bb5497886638edfe431ae769dd446785df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352482"
---
# <a name="cbrush-class"></a>Класс CBrush

Инкапсулирует кисть интерфейса графических устройств Windows (GDI).

## <a name="syntax"></a>Синтаксис

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|Формирует объект `CBrush`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кбраш::СоздатьБрусИнпрямой](#createbrushindirect)|Инициализирует кисть со стилем, цветом и узором, указанным в структуре [LOGBRUSH.](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Инициализирует кисть с рисунком, указанным устройством-независимым bitmap (DIB).|
|[CBrush::CreateHatchBrush](#createhatchbrush)|Инициирует кисть с указанным вылупимым узором и цветом.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|Инициализирует кисть с рисунком, указанным битовой картой.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|Инициализирует кисть с указанным твердым цветом.|
|[Кбраш::CreateSysColorBrush](#createsyscolorbrush)|Создает кисть, которая является цветом системы по умолчанию.|
|[CBrush::FromHandle](#fromhandle)|Возвращает указатель объекту `CBrush` при отваге ручки объекту Windows. `HBRUSH`|
|[Кбраш::GetLogBrush](#getlogbrush)|Получает структуру [LOGBRUSH.](/windows/win32/api/wingdi/ns-wingdi-logbrush)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кбраш:Оператор HBRUSH](#operator_hbrush)|Возвращает ручку Windows, `CBrush` прикрепленную к объекту.|

## <a name="remarks"></a>Примечания

Чтобы использовать `CBrush` объект, `CBrush` построить объект и `CDC` передать его любому члену функции, которая требует кисти.

Кисти могут быть твердыми, вылупимыми или узорчатыми.

Для получения `CBrush`дополнительной информации о, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cbrushcbrush"></a><a name="cbrush"></a>CBrush::CBrush

Формирует объект `CBrush`.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Определяет цвет переднего плана кисти как цвет RGB. Если кисть вылупилась, этот параметр определяет цвет штриховки.

*Nindex*<br/>
Определяет стиль люка кисти. Это может быть любое из следующих значений:

- HS_BDIAGONAL люк вниз (слева направо) при 45 градусах

- HS_CROSS Горизонтальный и вертикальный кросс-тючн

- HS_DIAGCROSS Кроссхэтч при 45 градусах

- HS_FDIAGONAL люк вверх (слева направо) при 45 градусах

- HS_HORIZONTAL горизонтальный люк

- HS_VERTICAL Вертикальный люк

*pBitmap*<br/>
Указывает на `CBitmap` объект, который определяет битную карту, с помощью которой красит кисть.

### <a name="remarks"></a>Примечания

`CBrush`имеет четыре перегруженных конструктора. Конструктор без каких-либо аргументов строит `CBrush` непрепренифицированный объект, который должен быть инициализирован, прежде чем он может быть использован.

Если вы используете конструктор без каких-либо аргументов, вы должны инициализировать `CBrush` полученный объект с [CreateSolidBrush,](#createsolidbrush) [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), или [CreateDIBPatternBrush](#createdibpatternbrush). Если вы используете один из конструкторов, который принимает аргументы, то никакой дальнейшей инициализации не требуется. Конструкторы с аргументами могут сделать исключение, если встречаются ошибки, в то время как конструктор без каких-либо аргументов всегда будет успешным.

Конструктор с одним параметром [COLORREF](/windows/win32/gdi/colorref) строит твердую кисть с указанным цветом. Цвет определяет значение RGB и может быть построен с макросом RGB в WINDOWS. H.

Конструктор с двумя параметрами строит кисть люка. Параметр *nIndex* определяет индекс вылупивого узора. Параметр *crColor* определяет цвет.

Конструктор с параметром `CBitmap` строит узорчатую кисть. Параметр определяет бит-карту. Бит-карта, как предполагается, была создана с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Минимальный размер битной карты, который будет использоваться в шаблоне заполнения, составляет 8 пикселей на 8 пикселей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

## <a name="cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>Кбраш::СоздатьБрусИнпрямой

Инициализирует кисть со стилем, цветом и узором, указанным в структуре [LOGBRUSH.](/windows/win32/api/wingdi/ns-wingdi-logbrush)

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Параметры

*lpLogBrush*<br/>
Указывает на структуру [LOGBRUSH,](/windows/win32/api/wingdi/ns-wingdi-logbrush) содержащую информацию о кисти.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Кисть впоследствии может быть выбрана в качестве текущей кисти для любого контекста устройства.

Кисти, созданной с помощью монохромной (1 плоскость, 1 бит на пиксель) бит-карты обращается с использованием текущего текста и фоновых цветов. Пиксели, представленные немного набором до 0, будут нарисованы с текущим цветом текста. Пиксели, представленные немного набор омичем 1, будут нарисованы с текущим цветом фона.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

## <a name="cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush

Инициализирует кисть с рисунком, указанным устройством-независимым bitmap (DIB).

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>Параметры

*hPackedDIB*<br/>
Идентифицирует объект глобальной памяти, содержащий упакованную независимую бик-карту (DIB).

*nUsage*<br/>
Уточняется, содержат `bmiColors[]` ли поля структуры данных [BITMAPINFO](/windows/win32/api/wingdi/ns-wingdi-bitmapinfo) (часть "упакованного DIB") явные значения RGB или индексы в реализуемую в настоящее время логическую палитру. Параметр должен быть одним из следующих значений:

- DIB_PAL_COLORS Цветовая таблица состоит из массива 16-битных индексов.

- DIB_RGB_COLORS Цветовая таблица содержит буквальное значение RGB.

*lpPackedDIB*<br/>
Указывает на упакованный DIB, `BITMAPINFO` состоящий из структуры, сразу же после чего массив байтов, определяющих пиксели битовой карты.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть может быть выбрана для любого контекста устройства, который поддерживает операции raster.

Эти две версии отличаются тем, как вы обрабатываете DIB:

- В первой версии, чтобы получить ручку для `GlobalAlloc` DIB вы называете функцию Windows, чтобы выделить блок глобальной памяти, а затем заполнить память с упакованы DIB.

- Во второй версии не обязательно `GlobalAlloc` звонить, чтобы выделить память для упакованного DIB.

Упакованный DIB состоит `BITMAPINFO` из структуры данных, непосредственно за которой следует массив байтов, определяющий пиксели битовой карты. Bitmaps, используемые в качестве шаблонов заполнения, должны быть 8 пикселей на 8 пикселей. Если бит-карта больше, Windows создает шаблон заполнения, используя только биты, соответствующие первым 8 строк и 8 столбцов пикселей в верхнем левом углу битной карты.

Когда приложение выбирает двухцветную кисть DIB в контекст монохромного устройства, Windows игнорирует цвета, указанные в DIB, и вместо этого отображает кисти шаблона с использованием текущего текста и фоновых цветов контекста устройства. Пиксели, отображенные к первому цвету (в смещении 0 в цветовой таблице DIB) DIB отображаются с помощью цвета текста. Пиксели, отображаемые ко второму цвету (при смещении 1 в цветовой таблице), отображаются с помощью фонового цвета.

Для получения информации об использовании следующих функций Windows, см.

- [CreateDIBPatternBrush](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrush) (Эта функция предусмотрена только для совместимости с приложениями, написанными `CreateDIBPatternBrushPt` для версий Windows раньше, чем 3.0; использовать функцию.)

- [CreateDIBPatternBrushPt](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrushpt) (Эта функция должна использоваться для приложений на основе Win32.)

- [ГлобалАлок](/windows/win32/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

## <a name="cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>CBrush::CreateHatchBrush

Инициирует кисть с указанным вылупимым узором и цветом.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет стиль люка кисти. Это может быть любое из следующих значений:

- HS_BDIAGONAL люк вниз (слева направо) при 45 градусах

- HS_CROSS Горизонтальный и вертикальный кросс-тючн

- HS_DIAGCROSS Кроссхэтч при 45 градусах

- HS_FDIAGONAL люк вверх (слева направо) при 45 градусах

- HS_HORIZONTAL горизонтальный люк

- HS_VERTICAL Вертикальный люк

*crColor*<br/>
Определяет цвет переднего плана кисти как цвет RGB (цвет люков). Для получения дополнительной информации можно ознакомиться с [COLORREF](/windows/win32/gdi/colorref) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть впоследствии может быть выбрана в качестве текущей кисти для любого контекста устройства.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

## <a name="cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>CBrush::CreatePatternBrush

Инициализирует кисть с рисунком, указанным битовой картой.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Идентифицирует бит-карту.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть может быть выбрана для любого контекста устройства, который поддерживает операции raster. Биткарта, идентифицированная *pBitmap,* обычно инициализирована с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) функции.

Bitmaps, используемые в качестве шаблонов заполнения, должны быть 8 пикселей на 8 пикселей. Если бит-карта больше, Windows будет использовать только биты, соответствующие первым 8 строк и столбцов пикселей в верхнем левом углу битной карты.

Кисть шаблона может быть удалена, не затрагивая связанную битную карту. Это означает, что бит-карта может быть использована для создания любого количества кистей шаблона.

Кисть, созданная с помощью монохромной битовой карты (1 цветная плоскость, 1 бит на пиксель), нарисована с использованием текущего текста и фоновых цветов. Пиксели, представленные немного набором до 0, нарисованы с текущим цветом текста. Пиксели, представленные немного набором 1, нарисованы с текущим цветом фона.

Для получения информации об использовании [CreatePatternBrush](/windows/win32/api/wingdi/nf-wingdi-createpatternbrush), функция Windows, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

## <a name="cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>CBrush::CreateSolidBrush

Инициализирует кисть с указанным твердым цветом.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Структура [COLORREF,](/windows/win32/gdi/colorref) которая определяет цвет кисти. Цвет определяет значение RGB и может быть построен с макросом RGB в WINDOWS. H.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть впоследствии может быть выбрана в качестве текущей кисти для любого контекста устройства.

Когда приложение закончило использование `CreateSolidBrush`кисти, созданной, оно должно выбрать кисть из контекста устройства.

### <a name="example"></a>Пример

  Смотрите пример [для CBrush::CBrush](#cbrush).

## <a name="cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>Кбраш::CreateSysColorBrush

Инициализирует цвет кисти.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет цветовой индекс. Это значение соответствует цвету, используемому для нарисования одного из 21 оконных элементов. Список значений можно узнать в [SDK Windows.](/windows/win32/api/winuser/nf-winuser-getsyscolor)

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть впоследствии может быть выбрана в качестве текущей кисти для любого контекста устройства.

Когда приложение закончило использование `CreateSysColorBrush`кисти, созданной, оно должно выбрать кисть из контекста устройства.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

## <a name="cbrushfromhandle"></a><a name="fromhandle"></a>CBrush::FromHandle

Возвращает указатель объекту `CBrush` при отваге ручки объекту Windows [HBRUSH.](#operator_hbrush)

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Параметры

*hBrush*<br/>
HANDLE к кисти GDI Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CBrush` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если `CBrush` объект еще не прикреплен к ручке, создается и прикрепляется временный `CBrush` объект. Этот `CBrush` временный объект действителен только до следующего времени, когда приложение не будет проходить время простоя в цикле событий. В это время все временные графические объекты удаляются. Другими словами, временный объект действителен только при обработке одного сообщения окна.

Для получения дополнительной информации об использовании графических объектов [см.](/windows/win32/gdi/graphic-objects)

### <a name="example"></a>Пример

  Смотрите пример [для CBrush::CBrush](#cbrush).

## <a name="cbrushgetlogbrush"></a><a name="getlogbrush"></a>Кбраш::GetLogBrush

Вызов исчерпе функции `LOGBRUSH` этого члена для получения структуры.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Параметры

*pLogBrush*<br/>
Указывает на структуру [LOGBRUSH,](/windows/win32/api/wingdi/ns-wingdi-logbrush) содержащую информацию о кисти.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно работает, а *pLogBrush* является действительным указателем, значение возврата — это число байтов, хранящихся в буфере.

Если функция удавлена, а *pLogBrush* является NULL, значение возврата — это число байтов, необходимых для хранения информации, которую функция будет хранить в буфере.

Если функция выходит из строя, значение возврата составляет 0.

### <a name="remarks"></a>Примечания

Структура `LOGBRUSH` определяет стиль, цвет и узор кисти.

Например, `GetLogBrush` вызов, соответствующий определенному цвету или шаблону битовой карты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

## <a name="cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>Кбраш:Оператор HBRUSH

Используйте этот оператор, чтобы получить прилагаемую ручку Windows GDI `CBrush` объекта.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка для объекта Windows `CBrush` GDI, представленная объектом; в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот оператор является оператором литья, который поддерживает прямое использование объекта HBRUSH.

Для получения дополнительной информации об использовании графических объектов [см.](/windows/win32/gdi/graphic-objects)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBitmap](../../mfc/reference/cbitmap-class.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
