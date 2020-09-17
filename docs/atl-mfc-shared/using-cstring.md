---
title: Использование CString
ms.date: 06/18/2018
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
ms.openlocfilehash: 8ebf3441c7d8856fe412e2efed4c717b01ced362
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219018"
---
# <a name="using-cstring"></a>Использование CString

В следующих подразделах этого раздела описывается программирование с использованием `CString`. Справочную документацию по `CString` классу см. в документации по [CStringT](../atl-mfc-shared/reference/cstringt-class.md).

Чтобы использовать `CString`, включите заголовок `atlstr.h`.

`CString`Классы, `CStringA` и `CStringW` являются специализациями шаблона класса с именем [CStringT](../atl-mfc-shared/reference/cstringt-class.md) на основе типа символьных данных, которые они поддерживают.

`CStringW`Объект содержит **`wchar_t`** тип и поддерживает строки в Юникоде. `CStringA`Объект содержит **`char`** тип и поддерживает однобайтовые и многобайтовые (MBCS) строки. `CString`Объект поддерживает либо **`char`** тип, либо тип в **`wchar_t`** зависимости от того, ОПРЕДЕЛЕН ли символ MBCS или символ Юникода во время компиляции.

Объект `CString` хранит символьные данные в объекте `CStringData`. `CString`принимает строки в стиле C, заканчивающиеся нулем. `CString`отслеживает длину строки для повышения производительности, но также оставляет символ NULL в хранимых символьных данных для поддержки преобразования в ЛПКВСТР. `CString`включает признак конца null при экспорте строки в стиле C. Можно вставить значение NULL в другие расположения в `CString` , но это может привести к непредвиденным результатам.

Следующий набор строковых классов можно использовать без привязки библиотеки MFC, как с поддержкой CRT, так и без нее: `CAtlString`, `CAtlStringA` и `CAtlStringW`.

`CString` используется в машинных проектах. Для проектов с управляемым кодом (C++/CLI) используйте `System::String`.

Чтобы добавить больше возможностей, чем предлагает `CString`, `CStringA` или `CStringW`, необходимо создать подкласс `CStringT`, содержащий дополнительные компоненты.

В следующем коде показано создание `CString` и его распечатка в стандартном выводе:

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>в этом разделе

[Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md)<br/>
Описывает базовые операции `CString`, включая создание объектов из строковых литералов C, доступ к отдельным символам в `CString`, объединение двух объектов и сравнение объектов `CString`.

[Строка Управление данными](../atl-mfc-shared/string-data-management.md)<br/>
Описывает использование Юникода и многобайтовой кодировки с `CString`.

[Семантика CString](../atl-mfc-shared/cstring-semantics.md)<br/>
Поясняет использование объектов `CString`.

[Операции CString, относящиеся к строкам в стиле C](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
Описывает операции с содержимым объекта `CString` как со строкой с завершающим нулевым байтом в стиле C.

[Выделение и освобождение памяти для BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
Описывает использование памяти для объектов BSTR и COM.

[Очистка исключения CString](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
Поясняет, что явная очистка в MFC 3.0 и последующих версий больше не требуется.

[Передача аргументов CString](../atl-mfc-shared/cstring-argument-passing.md)<br/>
Поясняет, как передать объекты CString в функции и как вернуть объекты `CString` из функций.

[Поддержка Юникода и многобайтовой кодировки (MBCS)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
Описывает реализацию поддержки Юникода и многобайтовой кодировки в MFC.

## <a name="reference"></a>Справочник

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Содержит справочные сведения о классе `CStringT`.

[Класс CSimpleStringT](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
Содержит справочные сведения о классе `CSimpleStringT`.

## <a name="related-sections"></a>Связанные разделы

[Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
Содержит ссылки на разделы, в которых описаны несколько способов управления строковыми данными.

[Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)
