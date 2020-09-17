---
title: Класс CStringT
ms.date: 03/27/2019
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 3e6d61bdf296e85bee5d41ec2131fa3d83122c2b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832091"
---
# <a name="cstringt-class"></a>Класс CStringT

Этот класс представляет `CStringT` объект.

## <a name="syntax"></a>Синтаксис

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Параметры

*BaseType*<br/>
Символьный тип класса String. Может применяться один из перечисленных ниже типов.

- **`char`** (для строк символов ANSI).

- **`wchar_t`** (для символьных строк Юникода).

- TCHAR (для символьных строк ANSI и Unicode).

*стрингтраитс*<br/>
Определяет, требуется ли классу String поддержка библиотеки времени выполнения C (CRT) и где находятся строковые ресурсы. Может применяться один из перечисленных ниже типов.

- **Стртраитатл< wchar_t** &#124; **`char`** &#124; **tchar, чтраитскрт< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Класс требует поддержки CRT и ищет строки ресурсов в модуле, указанном `m_hInstResource` (членом класса модуля приложения).

- **Стртраитатл< wchar_t** &#124; **`char`** &#124; **tchar, чтраитсос< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Класс не требует поддержки CRT и ищет строки ресурсов в модуле, указанном `m_hInstResource` (членом класса модуля приложения).

- **Стртраитмфк< wchar_t** &#124; **`char`** &#124; **tchar, чтраитскрт< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Класс требует поддержки CRT и ищет строки ресурсов с помощью стандартного алгоритма поиска MFC.

- **Стртраитмфк< wchar_t** &#124; **`char`** &#124; **tchar, чтраитсос< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Класс не требует поддержки CRT и ищет строки ресурсов с помощью стандартного алгоритма поиска MFC.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStringT:: CStringT](#cstringt)|Конструирует `CStringT` объект различными способами.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|Уничтожает объект `CStringT` .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringT:: Аллоксисстринг](#allocsysstring)|Выделяет строку BSTR из `CStringT` данных.|
|[CStringT:: Анситуем](#ansitooem)|Выполняет преобразование на месте из набора символов ANSI в набор символов OEM.|
|[CStringT:: AppendFormat](#appendformat)|Добавляет форматированные данные к существующему `CStringT` объекту.|
|[CStringT:: COLLATE](#collate)|Сравнивает две строки (с учетом регистра, использует сведения, относящиеся к языку).|
|[CStringT:: Коллатенокасе](#collatenocase)|Сравнивает две строки (без учета регистра, использует сведения, относящиеся к языку).|
|[CStringT:: Compare](#compare)|Сравнивает две строки (с учетом регистра).|
|[CStringT:: Компаренокасе](#comparenocase)|Сравнивает две строки (без учета регистра).|
|[CStringT::D удалить](#delete)|Удаляет символ или символы из строки.|
|[CStringT:: Find](#find)|Находит символ или подстроку в более длинной строке.|
|[CStringT:: Финдонеоф](#findoneof)|Находит первый соответствующий символ из набора.|
|[CStringT::Format](#format)|Форматирует строку как `sprintf` есть.|
|[CStringT::FormatMessage](#formatmessage)|Форматирует строку сообщения.|
|[CStringT:: Форматмессажев](#formatmessagev)|Форматирует строку сообщения с помощью переменного списка аргументов.|
|[CStringT:: Форматв](#formatv)|Форматирует строку, используя переменный список аргументов.|
|[CStringT:: GetEnvironmentVariable](#getenvironmentvariable)|Присваивает строке значение указанной переменной среды.|
|[CStringT:: INSERT](#insert)|Вставляет в строку один символ или подстроку с заданным индексом.|
|[CStringT:: Left](#left)|Извлекает левую часть строки.|
|[CStringT:: Лоадстринг](#loadstring)|Загружает существующий `CStringT` объект из ресурса Windows.|
|[CStringT:: Макеловер](#makelower)|Преобразует все символы в этой строке в символы нижнего регистра.|
|[CStringT:: Макереверсе](#makereverse)|Изменяет направление строки на противоположную.|
|[CStringT:: Макеуппер](#makeupper)|Преобразует все символы в этой строке в символы верхнего регистра.|
|[CStringT:: mid](#mid)|Извлекает среднюю часть строки.|
|[CStringT:: Оемтоанси](#oemtoansi)|Выполняет преобразование на месте из набора символов OEM в кодировку ANSI.|
|[CStringT:: Remove](#remove)|Удаляет указанные символы из строки.|
|[CStringT:: Replace](#replace)|Заменяет указанные символы другими символами.|
|[CStringT:: Реверсефинд](#reversefind)|Находит символ в более длинной строке; начинается с конца.|
|[CStringT:: right](#right)|Извлекает правую часть строки.|
|[CStringT:: Сетсисстринг](#setsysstring)|Устанавливает существующий объект BSTR с данными из `CStringT` объекта.|
|[CStringT:: Спанексклудинг](#spanexcluding)|Извлекает из строки символы, начиная с первого символа, которые не входят в набор символов, определяемых параметром `pszCharSet` .|
|[CStringT:: Спанинклудинг](#spanincluding)|Извлекает подстроку, содержащую только символы в наборе.|
|[CStringT:: маркировка](#tokenize)|Извлекает указанные токены в целевой строке.|
|[CStringT:: Trim](#trim)|Обрезает все начальные и конечные символы пробела из строки.|
|[CStringT:: Тримлефт](#trimleft)|Обрезает начальные символы пробела из строки.|
|[CStringT:: Тримригхт](#trimright)|Обрезает пробелы в конце строки.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[CStringT::operator=](#operator_eq)|Присваивает новое значение `CStringT` объекту.|
|[CStringT::operator+](#operator_add)|Сцепляет две строки или символ и строку.|
|[CStringT::operator+=](#operator_add_eq)|Сцепляет новую строку до конца существующей строки.|
|[CStringT::operator==](#operator_eq_eq)|Определяет логическую равенство двух строк.|
|[CStringT::operator!=](#operator_neq)|Определяет логическую неравенство двух строк.|
|[CStringT::operator &lt;](#operator_lt)|Определяет, является ли строка в левой части оператора меньше, чем строка с правой стороны.|
|[CStringT::operator &gt;](#operator_gt)|Определяет, что строка в левой части оператора больше, чем строка с правой стороны.|
|[CStringT::operator &lt;=](#operator_lt_eq)|Определяет, является ли строка в левой части оператора меньше или равна строке в правой части.|
|[CStringT::operator &gt;=](#operator_gt_eq)|Определяет, является ли строка в левой части оператора больше или равна строке в правой части.|

## <a name="remarks"></a>Примечания

`CStringT` наследует от [класса ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md). Дополнительные функции, такие как обработка символов, упорядочение и поиск, реализуются с помощью `CStringT` .

> [!NOTE]
> `CStringT` объекты способны создавать исключения. Это происходит, когда `CStringT` по какой-либо причине объекту не хватает памяти.

`CStringT`Объект состоит из последовательности символов с переменной длиной. `CStringT` предоставляет функции и операторы, используя синтаксис, аналогичный базовому. Операторы объединения и сравнения, а также упрощенное управление памятью упрощают `CStringT` использование объектов, чем обычные массивы символов.

> [!NOTE]
> Несмотря на то `CStringT` , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

Используя разные сочетания `BaseType` `StringTraits` параметров и, `CStringT` объекты могут поступать в следующие типы, которые были предопределены библиотеками ATL.

При использовании в приложении ATL:

`CString`, `CStringA` и `CStringW` экспортируются из библиотеки DLL MFC (MFC90.DLL), никогда не из пользовательских библиотек DLL. Это делается для предотвращения `CStringT` определения множественного умножения.

> [!NOTE]
> Если в коде содержится обходной путь для ошибок компоновщика, описанный в разделе [Экспорт строковых классов с помощью CStringT](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md), следует удалить этот код. Он больше не требуется.

В приложениях на основе MFC доступны следующие типы строк:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CStringA`|Строка типа символов ANSI с поддержкой CRT.|
|`CStringW`|Строка типа символов Юникода с поддержкой CRT.|
|`CString`|Типы символов ANSI и Юникод с поддержкой CRT.|

В проектах, в которых определено ATL_CSTRING_NO_CRT, доступны следующие типы строк:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа символов ANSI без поддержки CRT.|
|`CAtlStringW`|Строка типа символов Юникода без поддержки CRT.|
|`CAtlString`|Типы символов ANSI и Юникод без поддержки CRT.|

В проектах, где не определен ATL_CSTRING_NO_CRT, доступны следующие типы строк:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа символов ANSI с поддержкой CRT.|
|`CAtlStringW`|Строка типа символов Юникода с поддержкой CRT.|
|`CAtlString`|Типы символов ANSI и Юникод с поддержкой CRT.|

`CString` объекты также имеют следующие характеристики.

- `CStringT` объекты могут увеличиваться в результате операций объединения.

- `CStringT` объекты следуют за семантикой значений. Представьте себе `CStringT` объект как фактическую строку, а не указатель на строку.

- Можно свободно заменять `CStringT` объекты для `PCXSTR` аргументов функции.

- Пользовательское управление памятью для буферов строк. Дополнительные сведения см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>Предопределенные типы CStringT

Поскольку `CStringT` использует аргумент шаблона для определения типа символа ( [wchar_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)), типы параметров метода могут быть сложными в моменты времени. Для упрощения этой проблемы набор предопределенных типов определяется и используется во всем `CStringT` классе. В следующей таблице перечислены различные типы.

|Имя|Описание|
|----------|-----------------|
|`XCHAR`|Одиночный символ ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и у `CStringT` объекта.|
|`YCHAR`|Один символ ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве `CStringT` объекта.|
|`PXSTR`|Указатель на символьную строку ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и у `CStringT` объекта.|
|`PYSTR`|Указатель на символьную строку ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве `CStringT` объекта.|
|`PCXSTR`|Указатель на **`const`** символьную строку ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и у `CStringT` объекта.|
|`PCYSTR`|Указатель на **`const`** символьную строку ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве `CStringT` объекта.|

> [!NOTE]
> Код, который ранее использовал недокументированные методы `CString` (например, `AssignCopy` ), должен быть заменен кодом, который использует приведенные ниже документированные методы `CStringT` (например, `GetBuffer` или `ReleaseBuffer` ). Эти методы наследуются от `CSimpleStringT` .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Требования

|Заголовок|Назначение|
|------------|-------------|
|CStringT.h|Строковые объекты только MFC|
|atlstr.h|Объекты-строки, не относящиеся к MFC|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a> CStringT:: Аллоксисстринг

Выделяет совместимую со службой автоматизации строку типа BSTR и копирует в `CStringT` нее содержимое объекта, включая завершающий нуль-символ.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вновь выделенная строка.

### <a name="remarks"></a>Примечания

В программах MFC создается [класс CMemoryException](../../mfc/reference/cmemoryexception-class.md) , если недостаточно памяти. В программах ATL создается исключение [катлексцептион](../../atl/reference/catlexception-class.md) . Эта функция обычно используется для возврата строк для автоматизации.

Как правило, если эта строка передается в COM-функцию в качестве параметра [in], то для этого необходимо, чтобы вызывающий объект освободит строку. Это можно сделать с помощью [сисфристринг](/windows/win32/api/oleauto/nf-oleauto-sysfreestring), как описано в Windows SDK. Дополнительные сведения см. в разделе [выделение и освобождение памяти для BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Дополнительные сведения о функциях выделения OLE в Windows см. в разделе [сисаллокстринг](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) в Windows SDK.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a> CStringT:: Анситуем

Преобразует все символы в этом `CStringT` объекте из набора символов ANSI в набор символов OEM.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Примечания

Функция недоступна, если определен _UNICODE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a> CStringT:: AppendFormat

Добавляет форматированные данные к существующему `CStringT` объекту.

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Строка управления форматированием.

*нформатид*<br/>
Строковый идентификатор ресурса, содержащий строку управления форматированием.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Эта функция форматирует и добавляет ряд символов и значений в `CStringT` . Каждый необязательный аргумент (при его наличии) преобразуется и добавляется в соответствии с соответствующей спецификацией формата в *псзформат* или из строкового ресурса, определенного параметром *нформатид*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a> CStringT:: COLLATE

Сравнивает две строки с помощью функции Generic-Text `_tcscoll` .

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*псз*<br/>
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если этот `CStringT` объект меньше *ПСЗ*, или > 0, если этот `CStringT` объект больше *ПСЗ*.

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscoll` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `strcoll` `wcscoll` `_mbscoll` , определенной во время компиляции. Каждая функция выполняет сравнение строк с учетом регистра в соответствии с используемой в настоящий момент кодовой страницей. Дополнительные сведения см. в разделе [strcoll, вксколл, _mbscoll, _strcoll_l, _wcscoll_l _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a> CStringT:: Коллатенокасе

Сравнивает две строки с помощью функции Generic-Text `_tcscoll` .

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*псз*<br/>
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра), < 0, если этот `CStringT` объект меньше *ПСЗ* (без учета регистра), или > 0, если этот `CStringT` объект больше *ПСЗ* (без учета регистра).

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscoll` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `stricoll` `wcsicoll` `_mbsicoll` , определенной во время компиляции. Каждая функция выполняет сравнение строк без учета регистра в соответствии с используемой в настоящий момент кодовой страницей. Дополнительные сведения см. в разделе [strcoll, вксколл, _mbscoll, _strcoll_l, _wcscoll_l _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a> CStringT:: Compare

Сравнивает две строки (с учетом регистра).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Параметры

*псз*<br/>
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если этот `CStringT` объект меньше *ПСЗ*, или > 0, если этот `CStringT` объект больше *ПСЗ*.

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscmp` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `strcmp` `wcscmp` `_mbscmp` , определенной во время компиляции. Каждая функция выполняет сравнение строк с учетом регистра и не влияет на языковой стандарт. Дополнительные сведения см. в разделе [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Если строка содержит внедренные значения NULL, в целях сравнения строка считается усеченной по первому внедренному символу null.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a> CStringT:: Компаренокасе

Сравнивает две строки (без учета регистра).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*псз*<br/>
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра), <0, если этот `CStringT` объект меньше *ПСЗ* (без учета регистра), или >0, если этот `CStringT` объект больше *ПСЗ* (без учета регистра).

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcsicmp` , определенная в файле Tchar. H, сопоставляется либо с `_stricmp` , либо, в зависимости от кодировки `_wcsicmp` `_mbsicmp` , определенной во время компиляции. Каждая функция выполняет сравнение строк без учета регистра. Сравнение зависит от LC_CTYPEного аспекта языкового стандарта, но не LC_COLLATE. Дополнительные сведения см. в разделе [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a> CStringT:: CStringT

Формирует объект `CStringT`.

```
CStringT() throw() :
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :
    CThisSimpleString( pStringMgr);

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType,
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :
    CThisSimpleString( strSrc);

template <class SystemString>
CStringT(SystemString^ pString) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>Параметры

*PCH*<br/>
Указатель на массив символов длины *нленгс*, а не заканчивающийся символом NULL.

*нленгс*<br/>
Число символов в *PCH*.

*канал*<br/>
Один символ.

*псзсрк*<br/>
Строка, завершающаяся нулем, для копирования в этот `CStringT` объект.

*пстрингмгр*<br/>
Указатель на диспетчер памяти для `CStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управлении памятью для `CStringT` см. в разделе [Управление памятью с помощью CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

*стрсрк*<br/>
Существующий `CStringT` объект, который будет скопирован в этот `CStringT` объект. Дополнительные сведения о `CThisString` и см `CThisSimpleString` . в разделе "Примечания".

*varSrc*<br/>
Объект Variant, который необходимо скопировать в этот `CStringT` объект.

*BaseType*<br/>
Символьный тип класса String. Может применяться один из перечисленных ниже типов.

**`char`** (для строк символов ANSI).

**`wchar_t`** (для символьных строк Юникода).

TCHAR (для символьных строк ANSI и Unicode).

*бмфкдлл*<br/>
Логическое значение, указывающее, является ли проект DLL-библиотекой MFC (TRUE) или нет (FALSE).

*системстринг*<br/>
Должен быть `System::String` , а проект должен быть скомпилирован с помощью/CLR.

*пстринг*<br/>
Маркер для `CStringT` объекта.

### <a name="remarks"></a>Примечания

Поскольку конструкторы копируют входные данные в новое выделенное хранилище, следует помнить, что могут возникнуть исключения памяти. Обратите внимание, что некоторые из этих конструкторов действуют как функции преобразования. Это позволяет заменить, например, LPTSTR, где `CStringT` ожидается объект.

- `CStringT`( `LPCSTR` `lpsz` ): Формирует Юникод `CStringT` из строки ANSI. Этот конструктор также можно использовать для загрузки строкового ресурса, как показано в примере ниже.

- `CStringT(``LPCWSTR` `lpsz` ): Конструирует объект `CStringT` из строки в Юникоде.

- `CStringT`( `const unsigned char*` `psz` ): Позволяет создать объект `CStringT` из указателя на **`unsigned char`** .

> [!NOTE]
> Определите _CSTRING_DISABLE_NARROW_WIDE_CONVERSION макрос, чтобы отключить неявное преобразование строк между строками ANSI и Юникод. Макрос исключает из конструкторов компиляции, поддерживающих преобразование.

Обратите внимание, что параметр *стрсрк* может быть `CStringT` либо `CThisSimpleString` объектом, либо. Для `CStringT` используйте один из экземпляров по умолчанию ( `CString` , `CStringA` или `CStringW` ); для `CThisSimpleString` Используйте **`this`** указатель. `CThisSimpleString` объявляет экземпляр [класса ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md), который представляет собой класс строк меньшего размера с менее встроенными функциями, чем `CStringT` класс.

Оператор перегрузки `CSimpleStringT<>&()` конструирует `CStringT` объект из `CSimpleStringT` объявления.

> [!NOTE]
> Несмотря на то `CStringT` , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a> CStringT:: ~ CStringT

Уничтожает `CStringT` объект.

```
~CStringT() throw();
```

### <a name="remarks"></a>Примечания

Уничтожает `CStringT` объект.

## <a name="cstringtdelete"></a><a name="delete"></a> CStringT::D удалить

Удаляет символ или символы из строки, начинающейся с символа по указанному индексу.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Параметры

*ииндекс*<br/>
Отсчитываемый от нуля индекс первого символа в `CStringT` объекте, который необходимо удалить.

*нкаунт*<br/>
Число удаляемых символов.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Примечания

Если *нкаунт* длиннее, чем строка, оставшаяся часть строки будет удалена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a> CStringT:: Find

Ищет в этой строке первое совпадение символа или подстроки.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Параметры

*псзсуб*<br/>
Подстрока для поиска.

*истарт*<br/>
Индекс символа в строке, с которого начинается поиск, или значение 0, чтобы начать с начала.

*канал*<br/>
Один символ для поиска.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в этом `CStringT` объекте, соответствующего запрошенной подстроке или символам;-1, если не найдена подстрока или символ.

### <a name="remarks"></a>Примечания

Функция перегружена, чтобы принимать как одиночные символы (аналогично функции времени выполнения `strchr` ), так и строки (аналогично `strstr` ).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a> CStringT:: Финдонеоф

Ищет в этой строке первый символ, совпадающий с любым символом, содержащимся в *псзчарсет*.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Параметры

*псзчарсет*<br/>
Строка, содержащая символы для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в этой строке, который также находится в *псзчарсет*; -1, если совпадений нет.

### <a name="remarks"></a>Примечания

Находит первое вхождение любого из символов в *псзчарсет*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a> CStringT::Format

Записывает форматированные данные в, `CStringT` точно так же, как [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) форматирует данные в массив символов в стиле C.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Параметры

*нформатид*<br/>
Строковый идентификатор ресурса, содержащий строку управления форматированием.

*псзформат*<br/>
Строка управления форматированием.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Эта функция форматирует и сохраняет ряд символов и значений в `CStringT` . Каждый необязательный аргумент (при его наличии) преобразуется и выводится в соответствии с соответствующей спецификацией формата в *псзформат* или из строкового ресурса, определенного параметром *нформатид*.

Вызов завершится ошибкой, если сам строковый объект предлагается в качестве параметра для `Format` . Например, следующий код приведет к непредсказуемым результатам:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a> CStringT::FormatMessage

Форматирует строку сообщения.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Параметры

*нформатид*<br/>
Строковый идентификатор ресурса, содержащий неформатированный текст сообщения.

*псзформат*<br/>
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле *printf*-Style, за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Для функции требуется определение сообщения в качестве входных данных. Определение сообщения определяется с помощью *псзформат* или из строкового ресурса, определенного параметром *нформатид*. Функция копирует форматированный текст сообщения в `CStringT` объект, обрабатывая все внедренные последовательности вставки по запросу.

> [!NOTE]
> `FormatMessage` пытается выделить системную память для вновь отформатированной строки. В случае сбоя этой попытки автоматически создается исключение памяти.

Каждая Вставка должна иметь соответствующий параметр после параметра *псзформат* или *нформатид* . В тексте сообщения для динамического форматирования сообщения поддерживаются несколько escape-последовательностей. Дополнительные сведения см. в описании функции [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) Windows в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a> CStringT:: Форматмессажев

Форматирует строку сообщения с помощью переменного списка аргументов.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле функции времени выполнения `printf` , за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*парглист*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Функции требуется определение сообщения в качестве входных данных, определяемое *псзформат*. Функция копирует форматированный текст сообщения и переменный список аргументов в `CStringT` объект, обрабатывая все внедренные последовательности вставки по запросу.

> [!NOTE]
> `FormatMessageV` вызывает метод [CStringT::FormatMessage](#formatmessage), который пытается выделить системную память для вновь отформатированной строки. В случае сбоя этой попытки автоматически создается исключение памяти.

Дополнительные сведения см. в описании функции [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) Windows в Windows SDK.

## <a name="cstringtformatv"></a><a name="formatv"></a> CStringT:: Форматв

Форматирует строку сообщения с помощью переменного списка аргументов.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле функции времени выполнения `printf` , за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*args*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Записывает отформатированную строку и переменный список аргументов в `CStringT` строку таким же образом, чтобы `vsprintf_s` форматировать данные в массив символов в стиле C.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a> CStringT:: GetEnvironmentVariable

Присваивает строке значение указанной переменной среды.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Параметры

*псзвар*<br/>
Указатель на строку, завершающуюся нулем, которая указывает переменную среды.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Получает значение указанной переменной из блока среды вызывающего процесса. Значение в виде строки символов, завершающейся нулем.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a> CStringT:: INSERT

Вставляет в строку один символ или подстроку с заданным индексом.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Параметры

*ииндекс*<br/>
Индекс символа, перед которым будет выполнена вставка.

*псз*<br/>
Указатель на подстроку для вставки.

*канал*<br/>
Вставляемый символ.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Примечания

Параметр *ииндекс* определяет первый символ, который будет перемещен, чтобы освободить место для символа или подстроки. Если *ниндекс* равен нулю, вставка выполняется перед всей строкой. Если *ниндекс* превышает длину строки, функция объединяет текущую строку и новый материал, предоставляемый *CH* или *ПСЗ*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a> CStringT:: Left

Извлекает крайние левые *нкаунт* символы из этого `CStringT` объекта и возвращает копию извлеченной подстроки.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Параметры

*нкаунт*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Возвращенный объект `CStringT` может быть пустым.

### <a name="remarks"></a>Примечания

Если *нкаунт* превышает длину строки, извлекается вся строка. Функция `Left` аналогична функции `Left` в языке Basic.

Для многобайтовых кодировок (MBCS) *нкаунт* обрабатывает каждую 8-разрядную последовательность как символ, поэтому *нкаунт* возвращает число многобайтовых символов, умноженное на два.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a> CStringT:: Лоадстринг

Считывает строковый ресурс Windows, идентифицируемый *NID*, в существующий `CStringT` объект.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Маркер экземпляра модуля.

*nID*<br/>
Идентификатор ресурса строки Windows.

*влангуажеид*<br/>
Язык строкового ресурса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если загрузка ресурса прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Загружает строковый ресурс (*NID*) из указанного модуля (*HINSTANCE*), используя указанный язык (*влангуаже*).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a> CStringT:: Макеловер

Преобразует `CStringT` объект в строку нижнего регистра.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Возвращаемое значение

Результирующая строка в нижнем регистре.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a> CStringT:: Макереверсе

Изменяет порядок символов в объекте на обратный `CStringT` .

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Возвращаемое значение

Полученная Обратная строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a> CStringT:: Макеуппер

Преобразует `CStringT` объект в строку в верхнем регистре.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Возвращаемое значение

Итоговая строка в верхнем регистре.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a> CStringT:: mid

Извлекает подстроку длиной *нкаунт* символов из этого `CStringT` объекта, начиная с позиции *ифирст* (с нуля).

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Параметры

*ифирст*<br/>
Отсчитываемый от нуля индекс первого символа в этом `CStringT` объекте, который должен быть включен в извлеченную подстроку.

*нкаунт*<br/>
Число символов, извлекаемых из данного объекта `CStringT`. Если этот параметр не указан, извлекается оставшаяся часть строки.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объект может быть пустым.

### <a name="remarks"></a>Примечания

Функция возвращает копию извлеченной подстроки. `Mid` функция аналогична базовой функции Mid (за исключением того, что индексы в базовых основаны на единицу).

Для многобайтовых кодировок (MBCS) *нкаунт* ссылается на каждый 8-разрядный символ; Таким образом, ведущий и младший байт в одном многобайтном символе считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a> CStringT:: Оемтоанси

Преобразует все символы в этом `CStringT` объекте из набора символов OEM в кодировку ANSI.

```cpp
void OemToAnsi();
```

### <a name="remarks"></a>Примечания

Эта функция недоступна, если определен _UNICODE.

### <a name="example"></a>Пример

См. пример для [CStringT:: анситуем](#ansitooem).

## <a name="cstringtoperator-"></a><a name="operator_eq"></a> CStringT::operator=

Назначает новое значение строке.

```
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);

CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>Параметры

*стрсрк*<br/>
Объект, `CStringT` присваиваемый этой строке.

*str*<br/>
Ссылка на объект `CThisSimpleString`.

*бмфкдлл*<br/>
Логическое значение, указывающее, является ли проект библиотекой DLL MFC.

*BaseType*<br/>
Базовый тип строки.

*var*<br/>
Объект Variant, присваиваемый этой строке.

*канал*<br/>
Символ ANSI или Unicode, присваиваемый строке.

*псзсрк*<br/>
Указатель на исходную строку, которой присваивается значение.

### <a name="remarks"></a>Примечания

Оператор присваивания принимает другой `CStringT` объект, указатель на символ или один символ. Следует иметь в виду, что при использовании этого оператора могут возникнуть исключения памяти, так как может быть выделено новое хранилище.

Дополнительные сведения о см `CThisSimpleString` . в подразделе "Примечания" раздела [CStringT:: CStringT](#cstringt).

> [!NOTE]
> Несмотря на то `CStringT` , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

## <a name="cstringtoperator-"></a><a name="operator_add"></a> CStringT::operator+

Сцепляет две строки или символ и строку.

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Символ ANSI или Unicode для сцепления со строкой.

*ch2*<br/>
Символ ANSI или Unicode для сцепления со строкой.

*str1*<br/>
Объект `CStringT` для сцепления со строкой или символом.

*str2*<br/>
Объект `CStringT` для сцепления со строкой или символом.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сцепления со строкой или символом.

*psz2*<br/>
Указатель на строку, которую необходимо сцепить со строкой или символом.

### <a name="remarks"></a>Примечания

Существует семь форм перегруженных `CStringT::operator+` функций функции. Первая версия объединяет два существующих `CStringT` объекта. Следующие два сцепления `CStringT` объекта и строки с завершающим нулем. Следующие два сцепления `CStringT` объекта и СИМВОЛА ANSI. Последние два присоединяются к `CStringT` объекту и символу Юникода.

> [!NOTE]
> Несмотря на то `CStringT` , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a> CStringT::operator+=

Сцепляет символы в конец строки.

```
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Ссылка на объект `CThisSimpleString`.

*бмфкдлл*<br/>
Логическое значение, указывающее, является ли проект библиотекой DLL MFC.

*BaseType*<br/>
Базовый тип строки.

*var*<br/>
Объект Variant для сцепления с этой строкой.

*канал*<br/>
Символ ANSI или Unicode для сцепления со строкой.

*псзсрк*<br/>
Указатель на исходную строку, в которой выполняется сцепление.

*стрсрк*<br/>
Объект `CStringT` для сцепления с этой строкой.

### <a name="remarks"></a>Примечания

Оператор принимает другой `CStringT` объект, указатель на символ или один символ. Следует иметь в виду, что исключения памяти могут возникать при каждом использовании оператора объединения, так как для символов, добавляемых в этот объект, можно выделить новое хранилище `CStringT` .

Дополнительные сведения о см `CThisSimpleString` . в подразделе "Примечания" раздела [CStringT:: CStringT](#cstringt).

> [!NOTE]
> Несмотря на то `CStringT` , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a> CStringT::operator==

Определяет, являются ли две строки логически равными.

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Символ ANSI или Unicode для сравнения.

*ch2*<br/>
Символ ANSI или Unicode для сравнения.

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

*psz2*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Примечания

Проверяет, равен ли строка или символ в левой части строке или символу справа, и соответственно возвращает значение TRUE или FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a> CStringT::operator!=

Определяет, логически не равны ли две строки.

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Символ ANSI или Unicode для сцепления со строкой.

*ch2*<br/>
Символ ANSI или Unicode для сцепления со строкой.

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

*psz2*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Примечания

Проверяет, не равен ли строка или символ в левой части строке или символу в правой части.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a> CStringT::operator &lt;

Определяет, меньше ли строка в левой части оператора, чем строка с правой стороны.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

*psz2*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a> CStringT::operator &gt;

Определяет, больше ли строка в левой части оператора, чем строка с правой стороны.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

*psz2*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a> CStringT::operator &lt;=

Определяет, является ли строка в левой части оператора меньше или равна строке в правой части.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

*psz2*<br/>
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a> CStringT::operator &gt;=

Определяет, является ли строка в левой части оператора больше или равна строке в правой части.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
`CStringT`Для сравнения.

*str2*<br/>
`CStringT`Для сравнения.

*psz1*<br/>
Указатель на строку для сравнения.

*psz2*<br/>
Указатель на строку для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a> CStringT:: Remove

Удаляет все экземпляры указанного символа из строки.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Параметры

*чремове*<br/>
Символ, удаляемый из строки.

### <a name="return-value"></a>Возвращаемое значение

Число символов, удаленных из строки. Нуль, если строка не изменяется.

### <a name="remarks"></a>Примечания

При сравнении символов учитывается регистр.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a> CStringT:: Replace

Существует две версии `Replace` . Первая версия заменяет одну или несколько копий подстроки с помощью другой подстроки. Обе подстроки завершаются нулем. Вторая версия заменяет одну или несколько копий символа, используя другой символ. Обе версии работают с символьными данными, хранящимися в `CStringT` .

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Параметры

*псзолд*<br/>
Указатель на строку, завершающуюся нулем, которую необходимо заменить на *псзнев*.

*псзнев*<br/>
Указатель на строку, завершающуюся нулем, которая заменяет *псзолд*.

*чолд*<br/>
Символ, заменяемый *чнев*.

*чнев*<br/>
Символ, заменяющий *чолд*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество замененных экземпляров символа или подстроки или нуль, если строка не была изменена.

### <a name="remarks"></a>Примечания

`Replace` может изменить длину строки, так как *псзнев* и *псзолд* не должны иметь одинаковую длину, и несколько копий старой подстроки можно изменить на новую. Функция выполняет совпадение с учетом регистра.

Примеры `CStringT` экземпляров: `CString` , `CStringA` и `CStringW` .

Для `CStringA` `Replace` параметр работает с символами ANSI или многобайтовой кодировкой (MBCS). Для `CStringW` службы `Replace` работает с расширенными символами.

Для `CString` тип данных character выбирается во время компиляции в зависимости от того, определены ли константы в следующей таблице.

|Определенная константа|Символьный тип данных|
|----------------------|-------------------------|
|_UNICODE|Расширенные символы|
|_MBCS|Многобайтовые символы|
|Нет|Однобайтовые символы|
|Оба|Не определено.|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a> CStringT:: Реверсефинд

Поиск `CStringT` последнего совпадения символа в этом объекте.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Параметры

*канал*<br/>
Искомый символ.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс последнего символа в этом `CStringT` объекте, соответствующего запрошенному символу, или значение-1, если символ не найден.

### <a name="remarks"></a>Примечания

Функция аналогична функции времени выполнения `strrchr` .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a> CStringT:: right

Извлекает последние (то есть самые правые) *нкаунт* символы из этого `CStringT` объекта и возвращает копию извлеченной подстроки.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Параметры

*нкаунт*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объект может быть пустым.

### <a name="remarks"></a>Примечания

Если *нкаунт* превышает длину строки, извлекается вся строка. `Right` функция аналогична базовой `Right` функции (за исключением того, что индексы в Basic отсчитываются от нуля).

Для многобайтовых кодировок (MBCS) *нкаунт* ссылается на каждый 8-разрядный символ; Таким образом, ведущий и младший байт в одном многобайтном символе считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a> CStringT:: Сетсисстринг

Перераспределяет BSTR, на который указывает *пбстр* , и копирует в `CStringT` него содержимое объекта, включая символ null.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Параметры

*пбстр*<br/>
Указатель на символьную строку.

### <a name="return-value"></a>Возвращаемое значение

Новая строка.

### <a name="remarks"></a>Примечания

В зависимости от содержимого `CStringT` объекта значение BSTR, на которое ссылается *пбстр* , может измениться. Функция вызывает исключение, `CMemoryException` если недостаточно памяти.

Эта функция обычно используется для изменения значения строк, передаваемых по ссылке для службы автоматизации.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a> CStringT:: Спанексклудинг

Извлекает из строки символы, начиная с первого символа, которые не входят в набор символов, определяемых параметром *псзчарсет*.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*псзчарсет*<br/>
Строка, интерпретируемая как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, содержащая символы в строке, которые не находятся в *псзчарсет*, начиная с первого символа в строке и заканчивая первым символом в строке, который также находится в *псзчарсет* (т. е. Начиная с первого символа в строке и до, но исключая первый символ в строке, найденной *псзчарсет*). Он возвращает всю строку, если в строке не найден символ *псзчарсет* .

### <a name="remarks"></a>Примечания

`SpanExcluding` Извлекает и возвращает все символы, предшествующие первому вхождению символа из *псзчарсет* (иными словами, символ из *псзчарсет* и все символы, следующие за ним в строке, не возвращаются). Если в строке не найден символ из *псзчарсет* , `SpanExcluding` возвращается вся строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a> CStringT:: Спанинклудинг

Извлекает из строки символы, начиная с первого символа, которые находятся в наборе символов, определяемых параметром *псзчарсет*.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*псзчарсет*<br/>
Строка, интерпретируемая как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, содержащая символы в строке, находящиеся в *псзчарсет*, начиная с первого символа в строке и заканчивая при обнаружении символа в строке, которая не находится в *псзчарсет*. `SpanIncluding` Возвращает пустую подстроку, если первый символ в строке отсутствует в указанном наборе.

### <a name="remarks"></a>Примечания

Если первый символ строки не находится в кодировке, `SpanIncluding` возвращается пустая строка. В противном случае возвращается последовательность последовательных символов, находящиеся в наборе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a> CStringT:: маркировка

Находит следующий токен в целевой строке

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Параметры

*псзтокенс*<br/>
Строка, содержащая разделители токенов. Порядок этих разделителей не важен.

*истарт*<br/>
Отсчитываемый от нуля индекс, с которого начинается поиск.

### <a name="return-value"></a>Возвращаемое значение

`CStringT`Объект, содержащий текущее значение токена.

### <a name="remarks"></a>Примечания

`Tokenize`Функция находит следующий токен в целевой строке. Набор символов в *псзтокенс* указывает возможные разделители для найденных токенов. При каждом вызове `Tokenize` функции начинается с *истарт*, пропускает начальные разделители и возвращает `CStringT` объект, содержащий текущий токен, который представляет собой строку символов вплоть до следующего символа-разделителя. Значение *истарт* обновляется до позиции, следующей за завершающим символом-разделителем, или – 1, если достигнут конец строки. Дополнительные токены могут быть разбиты из оставшейся части целевой строки на последовательность вызовов `Tokenize` , используя *истарт* для наблюдения за тем, где в строке находится следующий токен для считывания. Если больше нет токенов, функция возвратит пустую строку, а для *истарт* будет задано значение-1.

В отличие от таких функций CRT, как [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), не `Tokenize` изменяет целевую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Примечания

Выходные данные этого примера выглядят следующим образом:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a> CStringT:: Trim

Обрезает начальные и конечные символы из строки.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Параметры

*чтаржет*<br/>
Целевой символ для усечения.

*псзтаржетс*<br/>
Указатель на строку, содержащую целевые символы для усечения. Все начальные и конечные вхождения символов в *псзтаржет* будут обрезаны из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обрезанную строку.

### <a name="remarks"></a>Примечания

Удаляет все начальные и конечные вхождения одного из следующих элементов:

- Символ, указанный параметром *чтаржет*.

- Все символы, найденные в строке, указанной параметром *псзтаржетс*.

- Бель.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Примечания

Выходные данные этого примера выглядят следующим образом:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a> CStringT:: Тримлефт

Обрезает начальные символы из строки.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Параметры

*чтаржет*<br/>
Целевой символ для усечения.

*псзтаржетс*<br/>
Указатель на строку, содержащую целевые символы для усечения. Все ведущие экземпляры символов в *псзтаржет* будут обрезаны из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Результирующая усеченная строка.

### <a name="remarks"></a>Примечания

Удаляет все начальные и конечные вхождения одного из следующих элементов:

- Символ, указанный параметром *чтаржет*.

- Все символы, найденные в строке, указанной параметром *псзтаржетс*.

- Бель.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a> CStringT:: Тримригхт

Обрезает конечные символы из строки.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Параметры

*чтаржет*<br/>
Целевой символ для усечения.

*псзтаржетс*<br/>
Указатель на строку, содержащую целевые символы для усечения. Все конечные вхождения символов в *псзтаржет* будут обрезаны из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CStringT` объект, содержащий обрезанную строку.

### <a name="remarks"></a>Примечания

Удаляет конечные вхождения одного из следующих элементов:

- Символ, указанный параметром *чтаржет*.

- Все символы, найденные в строке, указанной параметром *псзтаржетс*.

- Бель.

`CStringT& TrimRight(XCHAR chTarget)`Версия принимает один символьный параметр и удаляет все копии этого символа из конца `CStringT` строковых данных. Он начинается с конца строки и работает в направлении к началу. Она останавливается при обнаружении другого символа или при `CSTringT` нехватке символьных данных.

`CStringT& TrimRight(PCXSTR pszTargets)`Версия принимает строку, завершающуюся нулем, которая содержит все различные символы для поиска. Он удаляет все копии этих символов в `CStringT` объекте. Он начинается в конце строки и работает в направлении к началу. Он останавливается при обнаружении символа, не находящейся в целевой строке, или при `CStringT` отсутствии символьных данных. Он не пытается сопоставить всю целевую строку с подстрокой в конце `CStringT` .

Для `CStringT& TrimRight()` версии не требуются параметры. Все конечные пробелы в конце строки обрезаются `CStringT` . Символы пробела могут быть разрывами строк, пробелами или символами табуляции.

-

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[Класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)
