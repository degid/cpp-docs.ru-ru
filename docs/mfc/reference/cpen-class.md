---
title: Класс CPen
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: e15dc53fafa0d80f1b52b3fe77f3635c592a4346
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364071"
---
# <a name="cpen-class"></a>Класс CPen

Инкапсулирует перо интерфейса графических устройств Windows (GDI).

## <a name="syntax"></a>Синтаксис

```
class CPen : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPen::CPen](#cpen)|Формирует объект `CPen`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|Создает логическую косметическую или геометричную ручку с указанными атрибутами стиля, `CPen` ширины и кисти и прикрепляет ее к объекту.|
|[CPen::CreatePenInDirect](#createpenindirect)|Создает ручку со стилем, шириной и цветом, приведенным в `CPen` структуре [LOGPEN,](/windows/win32/api/wingdi/ns-wingdi-logpen) и прикрепляет ее к объекту.|
|[CPen::FromHandle](#fromhandle)|Возвращает указатель объекту `CPen` при приведении ВКС.|
|[CPen::GetExtLogPen](#getextlogpen)|Получает основную структуру [EXTLOGPEN.](/windows/win32/api/wingdi/ns-wingdi-extlogpen)|
|[CPen::GetLogPen](#getlogpen)|Получает основную структуру [LOGPEN.](/windows/win32/api/wingdi/ns-wingdi-logpen)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPen:оператор HPEN](#operator_hpen)|Возвращает ручку Windows, `CPen` прикрепленную к объекту.|

## <a name="remarks"></a>Примечания

Для получения дополнительной `CPen`информации об использовании, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a>CPen::CPen

Формирует объект `CPen`.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Параметры

*nPenStyle*<br/>
Определяет стиль пера. Этот параметр в первой версии конструктора может быть одним из следующих значений:

- PS_SOLID создает твердую ручку.

- PS_DASH создает пунктирной ручкой. Действителен только тогда, когда ширина пера составляет 1 или менее, в единицах устройства.

- PS_DOT создает пунктирную ручку. Действителен только тогда, когда ширина пера составляет 1 или менее, в единицах устройства.

- PS_DASHDOT создает ручку с чередующимися тире и точками. Действителен только тогда, когда ширина пера составляет 1 или менее, в единицах устройства.

- PS_DASHDOTDOT создает ручку с чередующимися тире и двойными точками. Действителен только тогда, когда ширина пера составляет 1 или менее, в единицах устройства.

- PS_NULL создает нулевую ручку.

- PS_INSIDEFRAME Создает ручку, которая рисует линию внутри рамки закрытых форм, производимых функциями вывода Windows `Ellipse`GDI, `Pie`которые `Chord` определяют граничащий прямоугольник (например, `Rectangle` `RoundRect`функции участника и члена). Когда этот стиль используется с функциями вывода Windows GDI, которые не указывают `LineTo` ограничивающий прямоугольник (например, функцию члена), область рисования пера не ограничивается кадром.

Вторая версия `CPen` конструктора определяет сочетание типа, стиля, конечной крышки и атрибутов соединения. Значения из каждой категории должны быть объединены с помощью bitwise or оператора (&#124;). Тип пера может быть одним из следующих значений:

- PS_GEOMETRIC создает геометрическое перо.

- PS_COSMETIC создает косметическую ручку.

   Вторая версия `CPen` конструктора добавляет следующие стили пера для *nPenStyle:*

- PS_ALTERNATE создает ручку, которая устанавливает каждый другой пиксель. (Этот стиль применим только для косметических ручек.)

- PS_USERSTYLE создает ручку, которая использует набор для укладки, поставляемый пользователем.

   Конечная крышка может быть одним из следующих значений:

- PS_ENDCAP_ROUND конец колпачки круглые.

- PS_ENDCAP_SQUARE конец колпачки квадратные.

- PS_ENDCAP_FLAT конец колпачки плоские.

   Соединение может быть одним из следующих значений:

- PS_JOIN_BEVEL соединения смошены.

- PS_JOIN_MITER соединения митерируются, когда они находятся в пределах текущего предела, установленного функцией [SetMiterLimit.](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) Если соединение превышает этот предел, оно слежено.

- PS_JOIN_ROUND соединения круглые.

*nWidth*<br/>
Определяет ширину пера.

- Для первой версии конструктора, если это значение равен 0, ширина блоков устройства всегда составляет 1 пиксель, независимо от режима отображения.

- Для второй версии конструктора, если *nPenStyle* PS_GEOMETRIC, ширина приведена в логических единицах. Если *nPenStyle* PS_COSMETIC, ширина должна быть установлена до 1.

*crColor*<br/>
Содержит цвет RGB для пера.

*pLogBrush*<br/>
Указывает на `LOGBRUSH` структуру. Если *nPenStyle* является PS_COSMETIC, член `LOGBRUSH` *структуры lbColor* определяет цвет пера, а член `LOGBRUSH` *структуры lbStyle* должен быть установлен на BS_SOLID. Если *nPenStyle* является PS_GEOMETRIC, все участники должны быть использованы для указания атрибутов кисти пера.

*nStyleCount*<br/>
Определяет длину, в двойных единицах, массива *lpStyle.* Это значение должно быть нулевым, если *nPenStyle* не PS_USERSTYLE.

*lpStyle*<br/>
Указывает на массив значений двойных слов. Первое значение определяет длину первого тире в пользовательском стиле, второе значение определяет длину первого пространства и так далее. Этот указатель должен быть NULL, если *nPenStyle* не является PS_USERSTYLE.

### <a name="remarks"></a>Примечания

Если вы используете конструктор без каких-либо аргументов, вы `CreatePenIndirect`должны `CreateStockObject` инициализировать полученный `CPen` объект с функциями, `CreatePen`или функциями члена.

Если вы используете конструктор, который принимает аргументы, то никакой дальнейшей инициализации не требуется. Конструктор с аргументами может сделать исключение, если встречаются ошибки, в то время как конструктор без каких-либо аргументов всегда будет успешным.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a>CPen::CreatePen

Создает логическую косметическую или геометричную ручку с указанными атрибутами стиля, `CPen` ширины и кисти и прикрепляет ее к объекту.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Параметры

*nPenStyle*<br/>
Определяет стиль для пера. Список возможных значений можно узнать в *конструкторе* [CPen.](#cpen)

*nWidth*<br/>
Определяет ширину пера.

- Для первой версии, `CreatePen`если это значение 0, ширина в единицах устройства всегда 1 пиксель, независимо от режима отображения.

- Для второй версии, `CreatePen`если *nPenStyle* PS_GEOMETRIC, ширина дается в логических единицах. Если *nPenStyle* PS_COSMETIC, ширина должна быть установлена до 1.

*crColor*<br/>
Содержит цвет RGB для пера.

*pLogBrush*<br/>
Указывает на структуру [LOGBRUSH.](/windows/win32/api/wingdi/ns-wingdi-logbrush) Если *nPenStyle* является `lbColor` PS_COSMETIC, `LOGBRUSH` член структуры определяет цвет пера и *член lbStyle* `LOGBRUSH` структуры должен быть установлен, чтобы BS_SOLID. Если nPenStyle является PS_GEOMETRIC, все участники должны быть использованы для указания атрибутов кисти пера.

*nStyleCount*<br/>
Определяет длину, в двойных единицах, массива *lpStyle.* Это значение должно быть нулевым, если *nPenStyle* не PS_USERSTYLE.

*lpStyle*<br/>
Указывает на массив значений двойных слов. Первое значение определяет длину первого тире в пользовательском стиле, второе значение определяет длину первого пространства и так далее. Этот указатель должен быть NULL, если *nPenStyle* не является PS_USERSTYLE.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, или ноль, если метод не удается.

### <a name="remarks"></a>Примечания

Первая версия `CreatePen` инициализирует ручку с указанным стилем, шириной и цветом. Ручка может быть впоследствии выбрана в качестве текущей ручки для любого контекста устройства.

Ручки шириной более 1 пикселя всегда должны иметь либо PS_NULL, PS_SOLID, либо PS_INSIDEFRAME стиль.

Если перо имеет PS_INSIDEFRAME стиль и цвет, который не соответствует цвету в логическом цветовом столе, перо нарисовано с смягченным цветом. Стиль PS_SOLID пера не может быть использован для создания пера с смягчим цветом. Стиль PS_INSIDEFRAME идентичен PS_SOLID если ширина пера меньше или равна 1.

Вторая версия `CreatePen` инициализирует логическую косметическую или геометрическое перо, имевавщее указанный стиль, ширину и атрибуты кисти. Ширина косметической ручки всегда 1; ширина геометрической ручки всегда указана в мировых единицах. После того, как приложение создает логическое перо, оно может выбрать эту ручку в контекст устройства, позвонив в функцию [CDC:SelectObject.](../../mfc/reference/cdc-class.md#selectobject) После того, как ручка выбрана в контекст устройства, она может быть использована для рисования линий и кривых.

- Если *nPenStyle* является PS_COSMETIC и PS_USERSTYLE, записи в массиве *lpStyle* указывают длину тире и пробелы в единицах стиля. Единица стиля определяется устройством, в котором ручка используется для рисования линии.

- Если *nPenStyle* является PS_GEOMETRIC и PS_USERSTYLE, записи в массиве *lpStyle* указывают длину тире и пробелы в логических единицах.

- Если *nPenStyle* PS_ALTERNATE, единица стиля игнорируется и устанавливается каждый другой пиксель.

Когда приложение больше не требует данной ручки, оно должно вызвать функцию члена `CPen` [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) или уничтожить объект, чтобы ресурс больше не использовался. Приложение не должно удалять ручку при выборе пера в контексте устройства.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::CreatePenInDirect

Инициализирует ручку, которая имеет стиль, ширину и цвет, приведенный в структуре, на которую указывает *lpLogPen.*

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Параметры

*lpLogPen*<br/>
Указывает на структуру Windows [LOGPEN,](/windows/win32/api/Wingdi/ns-wingdi-logpen) содержащую информацию о пере.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Ручки шириной более 1 пикселя всегда должны иметь либо PS_NULL, PS_SOLID, либо PS_INSIDEFRAME стиль.

Если перо имеет PS_INSIDEFRAME стиль и цвет, который не соответствует цвету в логическом цветовом столе, перо нарисовано с смягченным цветом. Стиль PS_INSIDEFRAME идентичен PS_SOLID если ширина пера меньше или равна 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a>CPen::FromHandle

Возвращает указатель объекту, `CPen` данной ручке объекту Пера Windows.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Параметры

*hPen*<br/>
`HPEN`ручка для Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPen` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Если объект `CPen` не прикреплен к дескриптору, создается и прикрепляется временный объект `CPen`. Этот `CPen` временный объект действителен только до следующего времени, когда приложение не будет проходить время в цикле событий, после чего все временные графические объекты удаляются. Другими словами, временный объект действителен только при обработке одного сообщения окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen

Получает `EXTLOGPEN` основную структуру.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Параметры

*pLogPen*<br/>
Указывает на структуру [EXTLOGPEN,](/windows/win32/api/wingdi/ns-wingdi-extlogpen) содержащую информацию о пере.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Структура `EXTLOGPEN` определяет стиль, ширину и атрибуты кисти пера. Например, `GetExtLogPen` звоните в соответствии с определенным стилем пера.

См. следующие темы в SDK Windows для получения информации о атрибутах пера:

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [ЭКСТЛОГПЕН](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [ЛОГПЕН](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [ExtCreatePen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Пример

Следующий пример кода `GetExtLogPen` демонстрирует вызов для получения атрибутов пера, а затем создать новую косметическую ручку с тем же цветом.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen

Получает `LOGPEN` базовую структуру.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Параметры

*pLogPen*<br/>
Указывает на структуру [LOGPEN,](/windows/win32/api/wingdi/ns-wingdi-logpen) содержащую информацию о пере.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Структура `LOGPEN` определяет стиль, цвет и узор пера.

Например, `GetLogPen` звоните в соответствии с определенным стилем пера.

См. следующие темы в SDK Windows для получения информации о атрибутах пера:

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [ЛОГПЕН](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>Пример

Следующий пример кода `GetLogPen` демонстрирует вызов для получения символа пера, а затем создать новую, прочную ручку с тем же цветом.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a>CPen:оператор HPEN

Получает прилагаемую ручку `CPen` Windows GDI объекта.

```
operator HPEN() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка для объекта Windows `CPen` GDI, представленная объектом; в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот оператор является оператором литья, который поддерживает прямое использование объекта HPEN.

Для получения дополнительной информации об [Graphic Objects](/windows/win32/gdi/graphic-objects) использовании графических объектов, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBrush](../../mfc/reference/cbrush-class.md)
