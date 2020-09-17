---
title: marshal_as
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 2b2cacb0acf04aa40b3e299bffd7357e04916b16
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544847"
---
# <a name="marshal_as"></a>marshal_as

Этот метод преобразует данные между собственными и управляемыми средами.

## <a name="syntax"></a>Синтаксис

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>Параметры

*input*<br/>
окне Значение, которое необходимо маршалировать в переменную `To_Type`.

## <a name="return-value"></a>Возвращаемое значение

Переменная типа `To_Type`, которая является преобразованным значением `input`.

## <a name="remarks"></a>Примечания

Этот метод является упрощенным способом преобразования данных между собственными и управляемыми типами. Чтобы определить, какие типы данных поддерживаются, см. раздел [Общие сведения C++о маршалировании в ](../dotnet/overview-of-marshaling-in-cpp.md). Для некоторых преобразований данных требуется контекст. Эти типы данных можно преобразовать с помощью [класса marshal_context](../dotnet/marshal-context-class.md).

При попытке маршалирования пары типов данных, которые не поддерживаются, `marshal_as` выдаст ошибку [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Дополнительные сведения см. в сообщении, прилагаемом к этой ошибке. Ошибка `C4996` может быть создана только для нерекомендуемых функций. Одним из примеров является попытка маршалирования пары типов данных, которые не поддерживаются.

Библиотека упаковки состоит из нескольких файлов заголовков. Для любого преобразования требуется только один файл, но при необходимости для других преобразований можно включить дополнительные файлы. Чтобы узнать, какие преобразования связаны с файлами, просмотрите таблицу в `Marshaling Overview`. Независимо от того, какое преобразование необходимо выполнить, требование к пространству имен всегда действует.

Вызывает `System::ArgumentNullException(_EXCEPTION_NULLPTR)`, если входной параметр имеет значение null.

## <a name="example"></a>Пример

В этом примере выполняется упаковка из `const char*` в `System::String` тип переменной.

```cpp
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>Требования

**Заголовочный файл:** \<мсклр\маршал.х >, \<мсклр \ marshal_windows.h >, \<мсклр \ marshal_cppstd.h > или \<мсклр \ marshal_atl.h >

**Пространство имен:** мсклр:: Interop

## <a name="see-also"></a>См. также:

[Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[Класс marshal_context](../dotnet/marshal-context-class.md)
