---
title: Базовые операции CString
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: fa46e82f19d87c49f652779d0e86e78549935965
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220903"
---
# <a name="basic-cstring-operations"></a>Базовые операции CString

В этом разделе объясняются следующие основные операции [CString](../atl-mfc-shared/reference/cstringt-class.md) :

- [Создание объектов CString из стандартных строк литерала C](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Доступ к отдельным символам в CString](#_core_accessing_individual_characters_in_a_cstring)

- [Сцепление двух объектов CString](#_core_concatenating_two_cstring_objects)

- [Сравнение объектов CString](#_core_comparing_cstring_objects)

- [Преобразование объектов CString](#_core_converting_cstring_objects)

`Class CString`основано на классе класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md). `CString`имеет значение **`typedef`** `CStringT` . Точнее, `CString` — это **`typedef`** *явная специализация* `CStringT` , которая представляет собой распространенный способ использования шаблона класса для определения класса. Аналогично определенным классам являются `CStringA` и `CStringW` .

`CString`, `CStringA` и `CStringW` определены в atlstr.h. `CStringT`определен в CStringT.h.

`CString`, `CStringA` и `CStringW` каждый получают набор методов и операторов, определенных `CStringT` для использования со строковыми данными, которые они поддерживают. Некоторые из методов дублируются и, в некоторых случаях, препревосходят строковые службы библиотек времени выполнения C.

Примечание. `CString` является собственным классом. Для класса String, предназначенного для использования в управляемом проекте C++/CLI, используйте `System.String` .

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>Создание объектов CString из стандартных строк литерала C

Можно назначить строковые литералы в стиле C `CString` точно так же, как можно присвоить один `CString` объект другому.

- Присвоить значение литеральной строки C `CString` объекту.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Присвойте значение одного `CString` `CString` объекта другому.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Содержимое `CString` объекта копируется, когда один `CString` объект назначается другому. Таким образом, две строки не используют ссылку на фактические символы, которые составляют строку. Дополнительные сведения об использовании `CString` объектов в качестве значений см. в разделе [семантика CString](../atl-mfc-shared/cstring-semantics.md).

   > [!NOTE]
   > Для написания приложения, чтобы его можно было компилировать для Юникода или для ANSI, строки кода литерала с помощью макроса _T. Дополнительные сведения см. в разделе [Поддержка Юникода и многобайтовой кодировки (MBCS)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>Доступ к отдельным символам в CString

Доступ к отдельным символам в объекте можно получить с `CString` помощью `GetAt` `SetAt` методов и. Можно также использовать элемент массива или индекс, оператор ([]) вместо `GetAt` для получения отдельных символов. (Это напоминает доступ к элементам массива по индексу, как и в стандартных строках в стиле C.) Значения индекса для `CString` символов отсчитываются от нуля.

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>Сцепление двух объектов CString

Чтобы объединить два `CString` объекта, используйте операторы объединения (+ или + =), как показано ниже.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

По крайней мере один аргумент для операторов объединения (+ или + =) должен быть `CString` объектом, но можно использовать константную строку (например, `"big"` ) или символ **`char`** (например, "x") для другого аргумента.

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>Сравнение объектов CString

`Compare`Метод и оператор = = для `CString` являются эквивалентными. `Compare`, **operator = =** и `CompareNoCase` поддерживают многобайтовую кодировку и Юникод; `CompareNoCase` также учитывает регистр. `Collate`Метод не зависит от `CString` языкового стандарта и зачастую медленнее, чем `Compare` . Используйте `Collate` только там, где необходимо соблюдать правила сортировки, заданные текущим языковым стандартом.

В следующей таблице показаны доступные функции сравнения [CString](../atl-mfc-shared/reference/cstringt-class.md) и их эквивалентные функции Юникода/MBCS-portable в библиотеке времени выполнения C.

|CString, функция|MBCS, функция|Функция Юникода|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT`Шаблон класса определяет реляционные операторы (<, \<=, > =, >, = = и! =), которые доступны для использования `CString` . Можно сравнить два `CStrings` с помощью этих операторов, как показано в следующем примере.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>Преобразование объектов CString

Дополнительные сведения о преобразовании объектов CString в другие строковые типы см. [в разделе Практические руководства. преобразование между различными строковыми типами](../text/how-to-convert-between-various-string-types.md).

## <a name="using-cstring-with-wcout"></a>Использование CString с wcout

Чтобы использовать CString с `wcout` , необходимо явным образом привести объект к типу, `const wchar_t*` как показано в следующем примере:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

Без приведения `cs` функция интерпретируется как **`void*`** и `wcout` выводит адрес объекта. Это поведение вызвано незначительным взаимодействием между выведением аргумента шаблона и разрешением перегрузки, которое верно и соответствует стандарту C++.

## <a name="see-also"></a>См. также раздел

[Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Специализация шаблона](../cpp/template-specialization-cpp.md)<br/>
[Практические руководства. преобразование между различными строковыми типами](../text/how-to-convert-between-various-string-types.md)
