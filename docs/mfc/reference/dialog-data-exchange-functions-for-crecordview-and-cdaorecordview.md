---
title: Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView
ms.date: 09/17/2019
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 06d0511317c21f6b132349d7d6cd6c2d6f20bc1b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837376"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView

В этом разделе перечислены функции DDX_Field, используемые для обмена данными между формами [CRecordset](../../mfc/reference/crecordset-class.md) и [CRecordView](../../mfc/reference/crecordview-class.md) , а также [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) . DAO используется с базами данных Access и поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей.

> [!NOTE]
> Функции DDX_Field подобны функциям DDX в том, что они обмениваются данными с элементами управления в форме. Но в отличие от DDX, они обмениваются данными с полями объекта набора записей, связанного с представлением, а не с полями самого представления записи. Дополнительные сведения см. в разделе Классы `CRecordView` и `CDaoRecordView` .

### <a name="ddx_field-functions"></a>Функции DDX_Field

|Имя|Описание|
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Передает целочисленные данные между элементом данных поля набора записей и индексом текущего выделения в поле со списком в списке [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Передает `CString` данные между элементом данных поля набора записей и элементом управления "поле со списком" в `CRecordView` или `CDaoRecordView` . При перемещении данных из набора записей в элемент управления эта функция выбирает элемент в поле со списком, который начинается с символов в указанной строке.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Передает `CString` данные между элементом данных поля набора записей и элементом управления "поле со списком" в `CRecordView` или `CDaoRecordView` . При перемещении данных из набора записей в элемент управления эта функция выбирает элемент в поле со списком, точно соответствующий указанной строке.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Передает логические данные между элементом данных поля набора записей и флажком в `CRecordView` или `CDaoRecordView` .|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Передает целочисленные данные между элементом данных поля набора записей и индексом текущего выделения в поле со списком в `CRecordView` или `CDaoRecordView` .|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между элементом управления "список" и элементами данных поля набора записей. При перемещении данных из набора записей в элемент управления эта функция выбирает элемент в списке, который начинается с символов в указанной строке.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Управляет передачей `CString` данных между элементом управления "список" и элементами данных поля в наборе записей. При перемещении данных из набора записей в элемент управления эта функция выбирает первый элемент, точно соответствующий указанной строке.|
|[DDX_FieldRadio](#ddx_fieldradio)|Передает целочисленные данные между элементом данных поля набора записей и группой переключателей в `CRecordView` или `CDaoRecordView` .|
|[DDX_FieldScroll](#ddx_fieldscroll)|Задает или получает расположение полосы прокрутки элемента управления "полоса прокрутки" в `CRecordView` или `CDaoRecordView` . Вызовите из функции [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) .|
|[DDX_FieldSlider](#ddx_fieldslider)|Синхронизирует положение бегунка элемента управления Slider в представлении записей и **`int`** элемент данных поля в наборе записей. |
|[DDX_FieldText](#ddx_fieldtext)|Перегруженные версии доступны для передачи **`int`** , **uint**, **`long`** , `DWORD` , [CString](../../atl-mfc-shared/reference/cstringt-class.md),,, **`float`** **`double`** **`short`** , [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)и [COleCurrency](../../mfc/reference/colecurrency-class.md) данных между элементом данных поля набора записей и полем редактирования в `CRecordView` или `CDaoRecordView` .|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a> DDX_FieldCBIndex

`DDX_FieldCBIndex`Функция синхронизирует индекс выбранного элемента в элементе управления "список" элемента управления "поле со списком" в представлении "запись" и **`int`** элемент данных поля набора записей, связанного с представлением записи.

```cpp
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*index*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элемент управления эта функция задает выбор в элементе управления на основе значения, указанного в поле *индекс*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, MFC устанавливает значение индекса равным 0. При переносе из элемента управления в набор записей, если элемент управления пуст или если элемент не выбран, поле набора записей устанавливается в значение 0.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Пример будет похож на `DDX_FieldCBIndex` .

### <a name="requirements"></a>Требования

**Заголовок:** афксдао.h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a> DDX_FieldCBString

`DDX_FieldCBString`Функция управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между элементом управления "поле ввода" поля со списком в представлении записей и `CString` элементом данных поля набора записей, связанным с представлением записей.

```cpp
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элемент управления эта функция устанавливает текущий выбор в поле со списком в первую строку, которая начинается с символов в строке, указанной в *параметре value*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, все выделенные элементы удаляются из поля со списком, а поле ввода поля со списком устанавливается в пустое значение. Если элемент управления является пустым, при переносе из элемента управления в набор записей поле набора записей устанавливается в значение null, если это поле разрешено.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Пример включает вызов `DDX_FieldCBString` .

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a> DDX_FieldCBStringExact

`DDX_FieldCBStringExact`Функция управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между элементом управления "поле ввода" поля со списком в представлении записей и `CString` элементом данных поля набора записей, связанным с представлением записей.

```cpp
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элемент управления эта функция задает для текущего выбора в поле со списком первую строку, которая точно совпадает со строкой, указанной в *параметре value*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение NULL, все выбранные элементы удаляются из поля со списком, а поле ввода поля со списком устанавливается в пустое значение. При переносе из элемента управления в набор записей, если элемент управления пуст, поле набора записей устанавливается в значение NULL.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldCBStringExact` похожи.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a> DDX_FieldCheck

`DDX_FieldCheck`Функция управляет передачей **`int`** данных между элементом управления "флажок" в диалоговом окне, представлении формы или объектом представления элемента управления и **`int`** элементом данных диалогового окна, представления формы или объекта представления элемента управления.

```cpp
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор ресурса элемента управления "флажок", связанного со свойством элемента управления.

*value*<br/>
Ссылка на переменную-член диалогового окна, представления формы или объекта представления элемента управления, с которыми осуществляется обмен данными.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При `DDX_FieldCheck` вызове метода *значение* устанавливается в текущее состояние элемента управления "флажок" или состояние элемента управления равно " *значение*" в зависимости от направления перемещения.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a> DDX_FieldLBIndex

`DDX_FieldLBIndex`Функция синхронизирует индекс выбранного элемента в элементе управления "список" в представлении записей и **`int`** элемент данных поля в наборе записей, связанном с представлением записей.

```cpp
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*index*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элемент управления эта функция задает выбор в элементе управления на основе значения, указанного в поле *индекс*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, MFC устанавливает значение индекса равным 0. При переносе из элемента управления в набор записей, если элемент управления пуст, поле набора записей устанавливается в значение 0.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) .

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a> DDX_FieldLBString

Копирует `DDX_FieldLBString` текущее выделение элемента управления "список" в представлении записей в элемент данных поля [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей, связанном с представлением записей.

```cpp
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

В обратном направлении эта функция устанавливает текущий выбор в списке в первую строку, которая начинается с символов в строке, указанной *значением*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, все выбранные элементы удаляются из списка. При переносе из элемента управления в набор записей, если элемент управления пуст, поле набора записей устанавливается в значение null.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldLBString` похожи.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a> DDX_FieldLBStringExact

Функция `DDX_FieldLBStringExact` копирует текущее выделение элемента управления "список" в представлении записей в элемент данных поля [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей, связанном с представлением записей.

```cpp
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

В обратном направлении эта функция устанавливает текущий выбор в списке в первую строку, которая точно соответствует строке, указанной в поле *значение*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, все выбранные элементы удаляются из списка. При переносе из элемента управления в набор записей, если элемент управления пуст, поле набора записей устанавливается в значение null.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldLBStringExact` похожи.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a> DDX_FieldRadio

`DDX_FieldRadio`Функция связывает переменную-член с нулевым значением **`int`** набора записей представления записей с выбранным в данный момент переключателем в группе переключателей в представлении записей.

```cpp
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор первого элемента в группе (с WS_GROUP стиля) соседних элементов управления "переключатель" в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При передаче из поля набора записей в представление эта функция включает в себя переключатель *n* (от нуля) и отключает другие кнопки. В обратном направлении эта функция задает в поле набора записей порядковый номер переключателя, находящегося в данный момент (флажок установлен). При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, кнопка не выбрана. Если при переносе из элемента управления в набор записей не выбран ни один элемент управления, то поле набора записей устанавливается в значение null, если это позволяет поле.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldRadio` похожи.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a> DDX_FieldScroll

`DDX_FieldScroll`Функция синхронизирует расположение прокрутки элемента управления "полоса прокрутки" в представлении записей и **`int`** элемент данных поля набора записей, связанного с представлением записи (или с любой целочисленной переменной, которую вы выбираете для сопоставления).

```cpp
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор первого элемента в группе (с WS_GROUP стиля) соседних элементов управления "переключатель" в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элемент управления эта функция задает для элемента управления "полоса прокрутки" значение, указанное в поле " *значение*". При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, то элемент управления "полоса прокрутки" имеет значение 0. При переносе из элемента управления в набор записей, если элемент управления пуст, значение поля набора записей равно 0.

Используйте первую версию при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldScroll` похожи.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a> DDX_FieldSlider

`DDX_FieldSlider`Функция синхронизирует положение бегунка элемента управления Slider в представлении записей и **`int`** элемент данных поля набора записей, связанного с представлением записи (или с любой целочисленной переменной, которую вы выбираете для сопоставления).

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DDX_FieldSlider(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset );

void AFXAPI DDX_FieldSlider(
   CDataExchange* pDX,
   int nIDC,
   int& value,
   CDaoRecordset* pRecordset );
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор ресурса элемента управления "ползунок".

*value*<br/>
Ссылка на значение для обмена. Этот параметр содержит или будет использоваться для задания текущего положения бегунка элемента управления ползунка.

*предшнур*<br/>
Указатель на связанный `CRecordset` объект или, `CDaoRecordset` с которым осуществляется обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей на ползунок эта функция задает положение ползунка в значении, указанном в поле *значение*. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, положение элемента управления Slider устанавливается равным 0. При переносе из элемента управления в набор записей, если элемент управления пуст, значение поля набора записей равно 0.

`DDX_FieldSlider` не обменивается сведениями о диапазоне с помощью элементов управления "ползунок", способных задавать диапазон, а не просто положение.

При работе с основанными на ODBC классами используйте Первое переопределение функции. Используйте второе переопределение классов, основанных на DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для `CRecordView` и `CDaoRecordView` см. в разделе [представления записей](../../data/record-views-mfc-data-access.md). Дополнительные сведения об элементах управления "ползунок" см. [в разделе using CSliderCtrl](../using-csliderctrl.md).

### <a name="example"></a>Пример

Пример общего DDX_Field см. в разделе [DDX_FieldText](#ddx_fieldtext) . Вызовы метода будут `DDX_FieldSlider` похожи.

### <a name="requirements"></a>Требования

**Заголовок:** афксдао.h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a> DDX_FieldText

`DDX_FieldText`Функция управляет передачей **`int`** **`short`** данных,, **`long`** , DWORD, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **`float`** , **`double`** , **bool**или **Byte** между элементом управления "поле ввода" и элементами данных поля в наборе записей.

```cpp
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    UINT& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    short& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BOOL& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*нидк*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) .

*value*<br/>
Ссылка на элемент данных поля в связанном `CRecordset` `CDaoRecordset` объекте или. Тип данных значения зависит от того, какая из перегруженных версий `DDX_FieldText` используется.

*предшнур*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) , с которым осуществляется обмен данными. Этот указатель позволяет `DDX_FieldText` обнаруживать и устанавливать значения NULL.

### <a name="remarks"></a>Примечания

Для объектов [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)`DDX_FieldText` также управляет передачей значений [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)и [COleCurrency](../../mfc/reference/colecurrency-class.md). Пустой элемент управления "поле ввода" указывает значение null. При переносе из набора записей в элемент управления, если поле набора записей имеет значение null, поле редактирования устанавливается в пустое значение. При переносе из элемента управления в набор записей, если элемент управления пуст, поле набора записей устанавливается в значение null.

Используйте версии с параметрами [CRecordset](../../mfc/reference/crecordset-class.md) , если работаете с классами на основе ODBC. При работе с классами, основанными на DAO, используйте параметры [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) .

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и дополнительные сведения о полях DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) см. в разделе [представления записей](../../data/record-views-mfc-data-access.md)статьи.

### <a name="example"></a>Пример

Следующая `DoDataExchange` функция для [CRecordView](../../mfc/reference/crecordview-class.md) содержит `DDX_FieldText` вызовы функций для трех типов данных: `IDC_COURSELIST` — это поле со списком; другие два элемента управления являются полями редактирования. Для программирования DAO параметр *m_pSet* является указателем на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)
