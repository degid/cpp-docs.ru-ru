---
title: Класс Кстрбуфт
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 4d9d0b403e572d6fdea65355702467c89587cc3a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219083"
---
# <a name="cstrbuft-class"></a>Класс Кстрбуфт

Этот класс обеспечивает автоматическую очистку ресурсов для `GetBuffer` и `ReleaseBuffer` вызывает существующий `CStringT` объект.

## <a name="syntax"></a>Синтаксис

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Параметры

*тчартипе*<br/>
Символьный тип `CStrBufT` класса. Может применяться один из перечисленных ниже типов.

- **`char`**(для строк символов ANSI)

- **`wchar_t`**(для символьных строк Юникода)

- TCHAR (для символьных строк ANSI и Unicode)

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|пкксстр|Указатель на константную строку.|
|пксстр|Указатель на строку.|
|`StringType`|Строковый тип, буфер которого должен управляться специализациями этого шаблона класса.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кстрбуфт:: Кстрбуфт](#cstrbuft)|Конструктор для объекта строкового буфера.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кстрбуфт:: SetLength](#setlength)|Задает длину символьного буфера для связанного строкового объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кстрбуфт::operator ПККССТР](#operator_pcxstr)|Извлекает **`const`** указатель на символьный буфер связанного строкового объекта.|
|[Кстрбуфт::operator ПКССТР](#operator_pxstr)|Извлекает указатель на символьный буфер связанного строкового объекта.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Кстрбуфт:: AUTO_LENGTH](#auto_length)|Автоматически определять новую длину строки в выпуске.|
|[Кстрбуфт:: SET_LENGTH](#set_length)|Установка длины строкового объекта во время выполнения в буфере|

## <a name="remarks"></a>Примечания

Этот класс используется в качестве класса-оболочки для замены вызовов функций [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) [релеасебуффер](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), [жетбуфферсетленгс](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) и `ReleaseBuffer` .

В основном разработан в качестве вспомогательного класса, `CStrBufT` предоставляет разработчику удобный способ работы с символьным буфером объекта String, не беспокоясь о том, как или когда вызывать `ReleaseBuffer` . Это возможно потому, что объект-оболочка выходит за пределы области действия в случае исключения или нескольких путей выхода из кода. вызов его деструктора для освобождения строкового ресурса.

## <a name="requirements"></a>Требования

**Заголовок:** атлсимпстр.h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>Кстрбуфт:: AUTO_LENGTH

Автоматически определять новую длину строки в выпуске.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Примечания

Автоматически определять новую длину строки в выпуске. Строка должна завершаться нулем.

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>Кстрбуфт:: Кстрбуфт

Конструирует объект buffer.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строковый объект, связанный с буфером. Как правило, разработчик будет использовать предопределенные определения типов `CStrBuf` (TCHAR Variant), `CStrBufA` ( **`char`** Variant) и `CStrBufW` ( **`wchar_t`** Variant).

*нминленгс*<br/>
Минимальная длина символьного буфера.

*dwFlags*<br/>
Определяет, определяется ли длина строки автоматически. Может применяться один из перечисленных ниже типов.

- AUTO_LENGTH длина строки определяется автоматически при вызове [ксимплестрингт:: Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) . Строка должна завершаться нулем. Значение по умолчанию.

- SET_LENGTH длина строки задается при вызове [ксимплестрингт::](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) GetString.

### <a name="remarks"></a>Примечания

Создает строковый буфер для связанного строкового объекта. Во время создания вызывается [ксимплестрингт::-buffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) или [CSimpleStringT:: жетбуфферсетленгс](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) .

Обратите внимание, что конструктор копий имеет значение **`private`** .

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>Кстрбуфт::operator ПККССТР

Прямой доступ к символам, хранящимся в связанном строковом объекте, в виде строки в стиле C.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символа на данные строки.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы вернуть указатель на символьный буфер строкового объекта. Содержимое объекта String не может быть изменено с помощью этого указателя.

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>Кстрбуфт::operator ПКССТР

Прямой доступ к символам, хранящимся в связанном строковом объекте, в виде строки в стиле C.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символа на данные строки.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы вернуть указатель на символьный буфер строкового объекта. Разработчик может изменить содержимое строкового объекта с помощью этого указателя.

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>Кстрбуфт::P ККССТР

Указатель на константную строку.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>Кстрбуфт::P КССТР

Указатель на строку.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>Кстрбуфт:: SET_LENGTH

Задает длину объекта строки в `GetBuffer` момент времени.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Примечания

Задание длины строкового объекта во время выполнения в буфере.

Определяет, вызываются ли [ксимплестрингт::](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) GetString и [CSimpleStringT:: жетбуфферсетленгс](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) при создании объекта строкового буфера.

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>Кстрбуфт:: SetLength

Задает длину символьного буфера.

```cpp
void SetLength(int nLength);
```

### <a name="parameters"></a>Параметры

*нленгс*<br/>
Новая длина символьного буфера строкового объекта.

> [!NOTE]
> Значение должно быть меньше или равно минимальной длине буфера, указанной в конструкторе `CStrBufT` .

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы задать длину строки, представленной объектом buffer.

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>Кстрбуфт:: Стрингтипе

Строковый тип, буфер которого должен управляться специализациями этого шаблона класса.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Примечания

`TCharType`символьный тип, используемый для специализации шаблона класса.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
