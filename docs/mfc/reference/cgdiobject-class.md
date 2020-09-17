---
title: Класс Кгдиобжект
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: 759b25a8f77bb4e6b372431b637b4a97aca8e149
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212414"
---
# <a name="cgdiobject-class"></a>Класс Кгдиобжект

Предоставляет базовый класс для различных типов объектов интерфейса графических устройств Windows (GDI), таких как растровые изображения, области, кисти, перья, палитры и шрифты.

## <a name="syntax"></a>Синтаксис

```
class CGdiObject : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кгдиобжект:: Кгдиобжект](#cgdiobject)|Формирует объект `CGdiObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кгдиобжект:: Attach](#attach)|Присоединяет объект Windows GDI к `CGdiObject` объекту.|
|[Кгдиобжект:: Креатестоккобжект](#createstockobject)|Извлекает маркер одного из предопределенных стандартных перьев, кистей или шрифтов Windows.|
|[Кгдиобжект::D Елетеобжект](#deleteobject)|Удаляет объект Windows GDI, присоединенный к `CGdiObject` объекту из памяти, освобождая все системное хранилище, связанное с объектом.|
|[Кгдиобжект::D Елететемпмап](#deletetempmap)|Удаляет все временные `CGdiObject` объекты, созданные `FromHandle` .|
|[Кгдиобжект::D етач](#detach)|Отсоединяет объект Windows GDI от `CGdiObject` объекта и возвращает маркер для объекта Windows GDI.|
|[Кгдиобжект:: FromHandle](#fromhandle)|Возвращает указатель на объект, `CGdiObject` заданный маркером для объекта Windows GDI.|
|[Кгдиобжект:: GetObject](#getobject)|Заполняет буфер данными, описывающими объект Windows GDI, присоединенный к `CGdiObject` объекту.|
|[Кгдиобжект:: Жетобжекттипе](#getobjecttype)|Извлекает тип объекта GDI.|
|[Кгдиобжект:: Жетсафехандле](#getsafehandle)|Возвращает `m_hObject` **`this`** , если не равно null, в этом случае возвращается значение null.|
|[Кгдиобжект:: Унреализеобжект](#unrealizeobject)|Сбрасывает источник кисти или сбрасывает логическую палитру.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кгдиобжект::operator!=](#operator_neq)|Определяет, логически не равны два объекта GDI.|
|[Кгдиобжект::operator==](#operator_eq_eq)|Определяет, логически ли равны два объекта GDI.|
|[Кгдиобжект::operator ХГДИОБЖ](#operator_hgdiobj)|Извлекает маркер присоединенного объекта Windows GDI.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кгдиобжект:: m_hObject](#m_hobject)|МАРКЕР, содержащий ХБИТМАП, ХПАЛЕТТЕ, ХРГН, ХБРУШ, ХПЕН или ХФОНТ, прикрепленный к этому объекту.|

## <a name="remarks"></a>Примечания

Вы никогда не создаете `CGdiObject` напрямую. Вместо этого создается объект из одного из производных от него классов, например `CPen` или `CBrush` .

Дополнительные сведения о см `CGdiObject` . в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cgdiobjectattach"></a><a name="attach"></a>Кгдиобжект:: Attach

Присоединяет объект Windows GDI к `CGdiObject` объекту.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
МАРКЕР для объекта Windows GDI (например, ХПЕН или ХБРУШ).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если вложение выполнено успешно; в противном случае — 0.

## <a name="cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>Кгдиобжект:: Кгдиобжект

Формирует объект `CGdiObject`.

```
CGdiObject();
```

### <a name="remarks"></a>Примечания

Вы никогда не создаете `CGdiObject` напрямую. Вместо этого создается объект из одного из производных от него классов, например `CPen` или `Cbrush` .

## <a name="cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>Кгдиобжект:: Креатестоккобжект

Извлекает маркер одного из стандартных геопера, кистей и шрифтов GDI Windows и присоединяет объект GDI к `CGdiObject` объекту.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Константа, указывающая тип требуемого запасного объекта. Описание соответствующих значений см. в параметре *фнобжект* для [жетстоккобжект](/windows/win32/api/wingdi/nf-wingdi-getstockobject) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию с одним из производных классов, которые соответствуют типу объекта Windows GDI, например `CPen` для фондовой биржи.

## <a name="cgdiobjectdeleteobject"></a><a name="deleteobject"></a>Кгдиобжект::D Елетеобжект

Удаляет присоединенный объект Windows GDI из памяти, освобождая все системное хранилище, связанное с объектом Windows GDI.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект GDI был успешно удален; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот вызов не влияет на хранилище, связанное с `CGdiObject` объектом. Приложение не должно вызываться `DeleteObject` для `CGdiObject` объекта, выбранного в данный момент в контексте устройства.

При удалении узорной кисти растровое изображение, связанное с кистью, не удаляется. Растровое изображение необходимо удалить независимо друг от друга.

## <a name="cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>Кгдиобжект::D Елететемпмап

Вызывается автоматически `CWinApp` обработчиком времени простоя, `DeleteTempMap` удаляет все временные `CGdiObject` объекты, созданные `FromHandle` .

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Примечания

`DeleteTempMap`Отсоединяет объект Windows GDI, присоединенный к временному `CGdiObject` объекту, перед удалением `CGdiObject` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

## <a name="cgdiobjectdetach"></a><a name="detach"></a>Кгдиобжект::D етач

Отсоединяет объект Windows GDI от `CGdiObject` объекта и возвращает маркер для объекта Windows GDI.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Возвращаемое значение

`HANDLE`Объект для отсоединенного объекта Windows GDI; в противном случае — значение null, если объект GDI не присоединен.

## <a name="cgdiobjectfromhandle"></a><a name="fromhandle"></a>Кгдиобжект:: FromHandle

Возвращает указатель на объект, `CGdiObject` заданный маркером для объекта Windows GDI.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
МАРКЕР для объекта Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CGdiObject` , который может быть временным или постоянным.

### <a name="remarks"></a>Примечания

Если `CGdiObject` объект еще не присоединен к объекту Windows GDI, `CGdiObject` создается и прикрепляется временный объект.

Этот временный `CGdiObject` объект действителен до тех пор, пока приложение не найдет время простоя в цикле событий, во время которого все временные графические объекты будут удалены. Другой способ сказать, что временный объект допустим только во время обработки одного сообщения окна.

## <a name="cgdiobjectgetobject"></a><a name="getobject"></a>Кгдиобжект:: GetObject

Заполняет буфер данными, определяющими указанный объект.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Параметры

*нкаунт*<br/>
Указывает число байтов для копирования в буфер *лпобжект* .

*лпобжект*<br/>
Указывает на предоставляемый пользователем буфер, предназначенный для получения сведений.

### <a name="return-value"></a>Возвращаемое значение

Число извлеченных байтов; в противном случае — 0, если возникает ошибка.

### <a name="remarks"></a>Примечания

Функция получает структуру данных, тип которой зависит от типа графического объекта, как показано в следующем списке:

|Объект|Тип буфера|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[логбруш](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[МАССИВ](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|Не поддерживается|

Если объект является `CBitmap` объектом, `GetObject` возвращает только сведения о ширине, высоте и формате цвета точечного рисунка. Фактические биты можно получить с помощью [CBitmap:: жетбитмапбитс](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Если объект является `CPalette` объектом, `GetObject` извлекает слово, указывающее количество записей в палитре. Функция не получает структуру [логпалетте](/windows/win32/api/wingdi/ns-wingdi-logpalette) , определяющую палитру. Приложение может получать сведения о записях палитры путем вызова [кпалетте:: жетпалеттинтриес](../../mfc/reference/cpalette-class.md#getpaletteentries).

## <a name="cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>Кгдиобжект:: Жетобжекттипе

Извлекает тип объекта GDI.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип объекта, если он успешно выполнен; в противном случае — 0. Он может иметь одно из следующих значений:

- OBJ_BITMAP точечный рисунок

- OBJ_BRUSHная кисть

- Шрифт OBJ_FONT

- Палитра OBJ_PAL

- OBJ_PENное перо

- Расширенное перо OBJ_EXTPEN

- Регион OBJ_REGION

- Контекст устройства OBJ_DC

- Контекст устройства памяти OBJ_MEMDC

- Метафайл OBJ_METAFILE

- Контекст OBJ_METADCного устройства для метафайлов

- OBJ_ENHMETAFILE расширенный метафайл

- OBJ_ENHMETADC контекст устройства расширенного метафайла

## <a name="cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>Кгдиобжект:: Жетсафехандле

Возвращает `m_hObject` **`this`** , если не равно null, в этом случае возвращается значение null.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

МАРКЕР присоединенного объекта Windows GDI; в противном случае значение NULL, если объект не присоединен.

### <a name="remarks"></a>Примечания

Это является частью парадигмы интерфейса общего обработчика и полезна, когда NULL является допустимым или специальным значением для маркера.

### <a name="example"></a>Пример

  См. пример для [CWnd:: исвиндовенаблед](../../mfc/reference/cwnd-class.md#iswindowenabled).

## <a name="cgdiobjectm_hobject"></a><a name="m_hobject"></a>Кгдиобжект:: m_hObject

МАРКЕР, содержащий ХБИТМАП, ХРГН, ХБРУШ, ХПЕН, ХПАЛЕТТЕ или ХФОНТ, прикрепленный к этому объекту.

```
HGDIOBJ m_hObject;
```

## <a name="cgdiobjectoperator-"></a><a name="operator_neq"></a>Кгдиобжект::operator!=

Определяет, логически не равны два объекта GDI.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Указатель на существующий объект `CGdiObject` .

### <a name="remarks"></a>Примечания

Определяет, не равен ли объект GDI в левой части объекта GDI в правой части.

## <a name="cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>Кгдиобжект::operator==

Определяет, логически ли равны два объекта GDI.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Ссылка на существующий объект `CGdiObject` .

### <a name="remarks"></a>Примечания

Определяет, равен ли объект GDI в левой части объекту GDI справа.

## <a name="cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>Кгдиобжект::operator ХГДИОБЖ

Извлекает маркер присоединенного объекта Windows GDI; в противном случае значение NULL, если объект не присоединен.

```
operator HGDIOBJ() const;
```

## <a name="cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>Кгдиобжект:: Унреализеобжект

Сбрасывает источник кисти или сбрасывает логическую палитру.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Хотя `UnrealizeObject` является функцией-членом `CGdiObject` класса, она должна вызываться только для `CBrush` `CPalette` объектов или.

Для `CBrush` объектов `UnrealizeObject` направляет систему на сброс источника заданной кисти при следующем выборе в контексте устройства. Если объект является `CPalette` объектом, `UnrealizeObject` направляет систему для реализации палитры так, как будто она не была реализована ранее. При следующем вызове приложением функции [CDC:: реализепалетте](../../mfc/reference/cdc-class.md#realizepalette) для указанной палитры система полностью пересопоставляет логическую палитру с системной палитрой.

`UnrealizeObject`Функция не должна использоваться с объектами акции. `UnrealizeObject`Функция должна вызываться при каждом задании нового источника кисти (с помощью функции [CDC:: сетбрушорг](../../mfc/reference/cdc-class.md#setbrushorg) ). `UnrealizeObject`Функция не должна вызываться для текущей выбранной кисти или выбранной палитры любого контекста вывода.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CBitmap](../../mfc/reference/cbitmap-class.md)<br/>
[Класс Кбруш](../../mfc/reference/cbrush-class.md)<br/>
[Класс Кфонт](../../mfc/reference/cfont-class.md)<br/>
[Класс Кпалетте](../../mfc/reference/cpalette-class.md)<br/>
[Класс Кпен](../../mfc/reference/cpen-class.md)<br/>
[Класс Кргн](../../mfc/reference/crgn-class.md)
