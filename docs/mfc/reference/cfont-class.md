---
title: Класс CFont
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 36fd469b182d5f3e0d3449112d04c1a8623d7526
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373843"
---
# <a name="cfont-class"></a>Класс CFont

Инкапсулирует шрифт интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим шрифтом.

## <a name="syntax"></a>Синтаксис

```
class CFont : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFont::CFont](#cfont)|Формирует объект `CFont`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|Инициализируется `CFont` с указанными характеристиками.|
|[Кфонт::CreateFontIndirect](#createfontindirect)|Инициализирует `CFont` объект с `LOGFONT` характеристиками, приведенными в структуре.|
|[CFont::CreatePointFont](#createpointfont)|Инициализирует `CFont` с указанной высотой, измеренной в десятых количествах точки, и шрифтом.|
|[Кфонт::CreatePointFontIndirect](#createpointfontindirect)|То `CreateFontIndirect` же, что высота шрифта измеряется в десятых точках, а не логических единиц.|
|[CFont::FromHandle](#fromhandle)|Возвращает указатель объекту `CFont` при приведении ВКС.|
|[CFont::GetLogFont](#getlogfont)|Заполняет `LOGFONT` информацию о логическом шрифте, прикрепленном к объекту. `CFont`|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFont:оператор HFONT](#operator_hfont)|Возвращает ручку шрифта Windows GDI, прикрепленную к объекту. `CFont`|

## <a name="remarks"></a>Примечания

Чтобы использовать `CFont` объект, `CFont` построить объект и прикрепить шрифт Windows к нему с [CreateFont,](#createfont) [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), или [CreatePointFontIndirect](#createpointfontindirect), а затем использовать функции члена объекта для манипулирования шрифтом.

`CreatePointFont` Функции `CreatePointFontIndirect` и функции часто `CreateFont` `CreateFontIndirect` проще в использовании, чем или так как они делают преобразование для высоты шрифта от размера точки к логическим единицам автоматически.

Для получения `CFont`дополнительной информации о, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cfontcfont"></a><a name="cfont"></a>CFont::CFont

Формирует объект `CFont`.

```
CFont();
```

### <a name="remarks"></a>Примечания

Полученный объект должен быть `CreateFont` `CreateFontIndirect`инициализирован с , `CreatePointFont`или `CreatePointFontIndirect` до того, как он может быть использован.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a>CFont::CreateFont

Инициализирует `CFont` объект с указанными характеристиками.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>Параметры

*nВысота*<br/>
Определяет нужную высоту (в логических единицах) шрифта. Ознакомьтесь с представителем `lfHeight` структуры [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)в SDK Windows для описания. Абсолютное значение *nHeight* не должно превышать 16 384 единиц устройства после его преобразования. Для всех сравнений высоты картограф шрифта ищет самый большой шрифт, который не превышает запрашиваемый размер, или самый маленький шрифт, если все шрифты превышают запрашиваемый размер.

*nWidth*<br/>
Определяет среднюю ширину (в логических единицах) символов шрифта. Если *nWidth* равна 0, соотношение сторон устройства будет сопоставлено с соотношением аспектов оцифровки доступных шрифтов, чтобы найти ближайший совпадение, которое определяется абсолютным значением разницы.

*nПобег*<br/>
Определяет угол (в 0,1-градусных единиц) между вектором побега и x-оси поверхности дисплея. Вектор побега — это линия через происхождение первого и последнего символов на линии. Угол измеряется против часовой стрелки от оси x. Дополнительную `lfEscapement` информацию `LOGFONT` можно узнать о участнике в структуре Windows SDK.

*nОриентация*<br/>
Определяет угол (в 0,1-градусных единиц) между исходной линией символа и оси x. Угол измеряется против часовой стрелки от оси x для систем координат, в которых y-направление вниз и по часовой стрелке от оси x для систем координат, в которых y-направление вверх.

*nВес*<br/>
Определяет вес шрифта (в чернилах пикселей на 1000). Дополнительную информацию можно `LOGFONT` узнать о участнике *lfWeight* в структуре Windows SDK. Описанные значения являются приблизительными; фактический внешний вид зависит от шрифта. Некоторые шрифты имеют только FW_NORMAL, FW_REGULAR и FW_BOLD веса. Если FW_DONTCARE указан, используется вес по умолчанию.

*bИтальский*<br/>
Уточняется, является ли шрифт курсивным.

*bСЭподчеркнуте*<br/>
Определяет, подчеркивается ли шрифт.

*cStrikeOut*<br/>
Уточняется, вычеркнуты ли символы шрифта. Упоньте шрифт вычеркивая если установлен на ненулевое значение.

*nCharSet*<br/>
Оценивайте набор символов `lfCharSet` шрифтаСмотрите `LOGFONT` член в структуре в Windows SDK для списка значений.

Набор символов OEM зависит от системы.

В системе могут существовать шрифты с другими наборами символов. Приложение, используюваеео шрифт с неизвестным набором символов, не должно пытаться переводить или интерпретировать строки, которые должны быть отображаются с помощью этого шрифта. Вместо этого строки должны передаваться непосредственно драйверу вывода устройства.

Картограф шрифта не использует DEFAULT_CHARSET значение. Приложение может использовать это значение, чтобы позволить имени и размеру шрифта полностью описать логический шрифт. Если шрифт с указанным именем не существует, шрифт из любого набора символов может быть заменен на указанный шрифт. Чтобы избежать неожиданных результатов, приложения должны использовать DEFAULT_CHARSET значение экономно.

*nOutPrecision*<br/>
Определяет нужную точность вывода. Точность вывода определяет, насколько близко выход должен соответствовать высоте, ширине, ориентации, побегу и высоте запрашиваемого шрифта. Список `lfOutPrecision` значений `LOGFONT` и дополнительной информации можно увидеть в структуре Windows SDK.

*nClipPrecision*<br/>
Определяет нужную точность отсечения. Точность отсечения определяет, как обрезать символы, которые частично находятся за пределами области отсечения. Список `lfClipPrecision` значений `LOGFONT` можно увидеть в структуре Windows SDK.

Чтобы использовать встроенный шрифт только для чтения, приложение должно указать CLIP_ENCAPSULATE.

Для обеспечения последовательного вращения устройств, TrueType и векторных шрифтов приложение может использовать оператора OR для объединения CLIP_LH_ANGLES значения с любым идругим значением *nClipPrecision.* Если набор CLIP_LH_ANGLES бита, вращение для всех шрифтов зависит от того, является ли ориентация системы координат левой рукой или правой рукой. (Для получения дополнительной информации о ориентации систем *nOrientation* координат см. Если CLIP_LH_ANGLES не установлен, шрифты устройства всегда вращаются против часовой стрелки, но вращение других шрифтов зависит от ориентации системы координат.

*nКачество*<br/>
Определяет качество вывода шрифта, которое определяет, насколько тщательно GDI должен попытаться сопоставить атрибуты логического шрифта с атрибутами фактического физического шрифта. Список `lfQuality` значений `LOGFONT` можно увидеть в структуре Windows SDK.

*nPitchAndFamily*<br/>
Указывает шаг и семейство шрифтов. Список `lfPitchAndFamily` значений `LOGFONT` и дополнительной информации можно увидеть в структуре Windows SDK.

*lpszFacename*<br/>
A `CString` или указатель на нулевую строку, которая определяет имя шрифта шрифта. Длина этой строки не должна превышать 30 символов. Функция Windows [EnumFontFamilies](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) может быть использована для перечисления всех доступных в настоящее время шрифтов. Если *lpszFacename* является NULL, GDI использует независимый от устройства шрифт.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Впоследствии шрифт может быть выбран в качестве шрифта для любого контекста устройства.

Функция `CreateFont` не создает новый шрифт Windows GDI. Он просто выбирает ближайший матч из физических шрифтов, доступных для GDI.

Приложения могут использовать параметры по умолчанию для большинства параметров при создании логического шрифта. Параметры, которым всегда должны быть даны конкретные значения *nHeight* и *lpszFacename.* Если *nHeight* и *lpszFacename* не устанавливаются приложением, создаваемый логический шрифт зависит от устройства.

`CFont` Когда вы закончите с `CreateFont` объектом, `CDC::SelectObject` созданным функцией, используйте для `CFont` выбора другого шрифта в контексте устройства, а затем удалите объект, который больше не нужен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a>Кфонт::CreateFontIndirect

Инициализирует `CFont` объект с характеристиками, приведенными в структуре [LOGFONT.](/windows/win32/api/wingdi/ns-wingdi-logfontw)

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
Указывает на `LOGFONT` структуру, определяющую характеристики логического шрифта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Впоследствии шрифт может быть выбран в качестве текущего шрифта для любого устройства.

Этот шрифт имеет характеристики, указанные в структуре [LOGFONT.](/windows/win32/api/wingdi/ns-wingdi-logfontw) При выборе шрифта с помощью функции члена [CDC:SelectObject](../../mfc/reference/cdc-class.md#selectobject) картограф gDI пытается сопоставить логический шрифт с существующим физическим шрифтом. Если картограф шрифта не может найти точное соответствие логическому шрифту, он предоставляет альтернативный шрифт, характеристики которого соответствуют как можно большему количеством запрошенных характеристик.

Если объект больше `CFont` не нужен `CreateFontIndirect` функции, используйте `CDC::SelectObject` для выбора другого шрифта в контексте устройства, а затем удалите `CFont` объект, который больше не нужен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a>CFont::CreatePointFont

Эта функция обеспечивает простой способ создания шрифта указанного шрифта и размера точки.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Параметры

*nPointSize*<br/>
Запрошенная высота шрифта в десятых количествах точки. (Например, пройти 120, чтобы запросить 12-точечный шрифт.)

*lpszFaceName*<br/>
A `CString` или указатель на нулевую строку, которая определяет имя шрифта шрифта. Длина этой строки не должна превышать 30 символов. Функция Windows 'EnumFontFamilies может быть использована для перечисления всех доступных в настоящее время шрифтов. Если *lpszFaceName* является NULL, GDI использует независимый от устройства шрифт.

*pDC*<br/>
Указатель на объект [CDC,](../../mfc/reference/cdc-class.md) который будет использоваться для преобразования высоты в *nPointSize* в логические единицы. Если NULL, для преобразования используется контекст экранного устройства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Примечания

Он автоматически преобразует высоту в *nPointSize* в логические единицы, используя объект CDC, на который указывает *pDC.*

Когда вы закончите `CFont` с `CreatePointFont` объектом, созданным функцией, сначала выберите `CFont` шрифт из контекста устройства, а затем удалите объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>Кфонт::CreatePointFontIndirect

Эта функция такая же, как [CreateFontIndirect,](#createfontindirect) за исключением того, что `lfHeight` член `LOGFONT` интерпретируется в десятых точках, а не единиц устройства.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
Указывает на структуру [LOGFONT,](/windows/win32/api/wingdi/ns-wingdi-logfontw) определяющую характеристики логического шрифта. Член `lfHeight` `LOGFONT` структуры измеряется в десятых точках, а не логических единиц. (Например, `lfHeight` установить 120, чтобы запросить 12-точечный шрифт.)

*pDC*<br/>
Указатель на объект [CDC,](../../mfc/reference/cdc-class.md) который будет `lfHeight` использоваться для преобразования высоты в логические единицы. Если NULL, для преобразования используется контекст экранного устройства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция автоматически преобразует `lfHeight` высоту в логические единицы, используя объект `LOGFONT` CDC, на который указывает *pDC,* прежде чем передать структуру на Windows.

Когда вы закончите `CFont` с `CreatePointFontIndirect` объектом, созданным функцией, сначала выберите `CFont` шрифт из контекста устройства, а затем удалите объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a>CFont::FromHandle

Возвращает указатель объекту `CFont` при отнесев к ручке HFONT объекту шрифта Windows GDI.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Параметры

*hFont*<br/>
Ручка HFONT для шрифта Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFont` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если `CFont` объект еще не прикреплен к ручке, создается и прикрепляется временный `CFont` объект. Этот `CFont` временный объект действителен только до следующего времени, когда приложение не будет проходить время в цикле событий, после чего все временные графические объекты удаляются. Другой способ сказать это заключается в том, что временный объект действителен только при обработке одного окна сообщения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a>CFont::GetLogFont

Вызов ими функции, чтобы `LOGFONT` получить `CFont`копию структуры для .

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Параметры

*pLogFont*<br/>
Указатель на структуру [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) для получения информации о шрифте.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешно, в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a>CFont:оператор HFONT

Используйте этот оператор, чтобы получить ручку Windows `CFont` GDI шрифта, прикрепленного к объекту.

```
operator HFONT() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка шрифта Windows GDI объект `CFont` прилагается в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Поскольку этот оператор автоматически используется `CFont` для конверсий из `CFont` [шрифтов и текста,](/windows/win32/gdi/fonts-and-text)вы можете передавать объекты функциям, которые ожидают HFONTs.

Для получения дополнительной информации об использовании графических объектов [см.](/windows/win32/gdi/graphic-objects)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
