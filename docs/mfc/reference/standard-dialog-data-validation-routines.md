---
title: Стандартные программы проверки данных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 19d1858d67802a7c464a9be783e4c1fb96fe3fae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844487"
---
# <a name="standard-dialog-data-validation-routines"></a>Стандартные программы проверки данных диалоговых окон

В этом разделе перечислены стандартные подпрограммы проверки данных диалогового окна (DDV), используемые для распространенных элементов управления диалогового окна MFC.

> [!NOTE]
> Стандартные подпрограммы обмена данными в диалоговом окне определяются в файле заголовка afxdd_.h. Однако приложения должны включать AFXWIN.h.

### <a name="ddv-functions"></a>Функции DDV

|Имя|Описание|
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Проверяет, что количество символов в заданном значении элемента управления не превышает заданное максимальное значение.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Проверяет, что данное значение элемента управления не превышает заданный диапазон **байтов** .|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Проверяет, что данное значение элемента управления не превышает заданный диапазон времени.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Проверяет, что данное значение элемента управления не превышает заданный **`double`** диапазон.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Проверяет, что данное значение элемента управления не превышает заданный диапазон **DWORD** .|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Проверяет, что данное значение элемента управления не превышает заданный **`float`** диапазон.|
|[DDV_MinMaxInt](#ddv_minmaxint)|Проверяет, что данное значение элемента управления не превышает заданный **`int`** диапазон.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Проверяет, что данное значение элемента управления не превышает заданный **`long`** диапазон.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Проверяет, что данное значение элемента управления не превышает заданный диапазон **лонглонг** .|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Проверяет, что данное значение элемента управления не превышает заданный диапазон дат.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Проверяет, что данное значение элемента управления не превышает заданный **`short`** диапазон.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Проверяет, попадает ли заданное значение элемента управления Slider в заданный диапазон.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Проверяет, что данное значение элемента управления не превышает заданный диапазон **uint** .|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Проверяет, попадает ли заданное значение элемента управления между двумя указанными значениями.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Проверяет, что данное значение элемента управления не превышает заданный диапазон **улонглонг** .|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a> DDV_MaxChars

Вызовите метод `DDV_MaxChars` , чтобы убедиться, что количество символов в элементе управления, связанное со *значением* , не превышает *nchar*.

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*типы nChar*<br/>
Максимально допустимое число символов.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a> DDV_MinMaxByte

Вызовите метод `DDV_MinMaxByte` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа BYTE).

*максвал*<br/>
Разрешено максимальное значение (типа BYTE).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a> DDV_MinMaxDateTime

Вызовите метод, `DDV_MinMaxDateTime` чтобы убедиться, что значение времени или даты в элементе управления выбора даты и времени ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)), связанного с *рефвалуе* , попадает в интервал между *рефминранже* и *рефмаксранже*.

```cpp
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление. Вам не нужно удалять этот объект.

*рефвалуе*<br/>
Ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) или [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , связанный с переменной-членом диалогового окна, представления формы или объекта представления элемента управления. Этот объект содержит данные для проверки.

*рефминранже*<br/>
Минимальное допустимое значение даты и времени.

*рефмаксранже*<br/>
Максимальное допустимое значение даты и времени.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a> DDV_MinMaxDouble

Вызовите метод `DDV_MinMaxDouble` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`double`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`double`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a> DDV_MinMaxDWord

Вызовите метод `DDV_MinMaxDWord` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа DWORD).

*максвал*<br/>
Разрешено максимальное значение (типа DWORD).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a> DDV_MinMaxFloat

Вызовите метод `DDV_MinMaxFloat` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`float`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`float`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a> DDV_MinMaxInt

Вызовите метод `DDV_MinMaxInt` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`int`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`int`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a> DDV_MinMaxLong

Вызовите метод `DDV_MinMaxLong` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`long`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`long`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a> DDV_MinMaxLongLong

Вызовите метод `DDV_MinMaxLongLong` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа ЛОНГЛОНГ).

*максвал*<br/>
Разрешено максимальное значение (типа ЛОНГЛОНГ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a> DDV_MinMaxMonth

Вызовите, `DDV_MinMaxMonth` чтобы убедиться, что значение времени или даты в элементе управления "календарь месяца" ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)), связанное с *рефвалуе* , попадает в интервал между *рефминранже* и *рефмаксранже*.

```cpp
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*рефвалуе*<br/>
Ссылка на объект типа `CTime` или, `COleDateTime` связанный с переменной-членом диалогового окна, представления формы или объекта представления элемента управления. Этот объект содержит данные для проверки. MFC передает эту ссылку при `DDV_MinMaxMonth` вызове.

*рефминранже*<br/>
Минимальное допустимое значение даты и времени.

*рефмаксранже*<br/>
Максимальное допустимое значение даты и времени.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a> DDV_MinMaxShort

Вызовите метод `DDV_MinMaxShort` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`short`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`short`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a> DDV_MinMaxSlider

Вызовите метод `DDV_MinMaxSlider` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на проверяемое значение. Этот параметр содержит или задает текущую положение бегунка элемента управления ползунка.

*минвал*<br/>
Минимальное допустимое значение.

*максвал*<br/>
Максимально допустимое значение.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md). Дополнительные сведения об элементах управления "ползунок" см. [в разделе using CSliderCtrl](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a> DDV_MinMaxUInt

Вызовите метод `DDV_MinMaxUInt` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа UINT).

*максвал*<br/>
Разрешено максимальное значение (типа UINT).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a> DDV_MinMaxULongLong

Вызовите метод `DDV_MinMaxULongLong` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа УЛОНГЛОНГ).

*максвал*<br/>
Разрешено максимальное значение (типа УЛОНГЛОНГ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

Вызовите метод `DDV_MinMaxUnsigned` , чтобы убедиться, что значение в элементе управления, связанное со *значением* , попадает в интервал между *минвал* и *максвал*.

### <a name="syntax"></a>Синтаксис

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с помощью которой проверяются данные.

*минвал*<br/>
Разрешено минимальное значение (типа **`unsigned`** ).

*максвал*<br/>
Разрешено максимальное значение (типа **`unsigned`** ).

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV см. в разделе [Обмен данными и проверка диалоговых окон](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdd_.h

## <a name="see-also"></a>См. также раздел

[Стандартные подпрограммы обмена данными в диалоговом окне](standard-dialog-data-exchange-routines.md)<br/>
[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
