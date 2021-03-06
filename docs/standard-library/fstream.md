---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 46f65f746179740f2d67dd1ada2f96ab3fb6aaf6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203238"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся во внешних файлах.

## <a name="syntax"></a>Синтаксис

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Тип, `basic_filebuf` специализированный для **`char`** параметров шаблона.|
|[FStream](../standard-library/fstream-typedefs.md#fstream)|Тип, `basic_fstream` специализированный для **`char`** параметров шаблона.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Тип, `basic_ifstream` специализированный для **`char`** параметров шаблона.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Тип, `basic_ofstream` специализированный для **`char`** параметров шаблона.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Тип, `basic_fstream` специализированный для **`wchar_t`** параметров шаблона.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Тип, `basic_ifstream` специализированный для **`wchar_t`** параметров шаблона.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Тип, `basic_ofstream` специализированный для **`wchar_t`** параметров шаблона.|
|[вфилебуф](../standard-library/fstream-typedefs.md#wfilebuf)|Тип, `basic_filebuf` специализированный для **`wchar_t`** параметров шаблона.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Шаблон класса описывает буфер потока, который управляет передачей элементов типа `Elem` , признаки символов которых определяются классом `Tr` , в последовательность элементов, хранящуюся во внешнем файле, и из нее.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Шаблон класса описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem` , признаки символов которых определяются классом `Tr` .|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Шаблон класса описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem` , признаки символов которых определяются классом `Tr` .|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Шаблон класса описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem` , признаки символов которых определяются классом `Tr` .|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
