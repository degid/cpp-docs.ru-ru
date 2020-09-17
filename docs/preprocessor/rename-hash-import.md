---
title: переименовать атрибут импорта
ms.date: 08/29/2019
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 520369f0308078fead2947e27a512f25a3ad3fab
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447485"
---
# <a name="rename-import-attribute"></a>переименовать атрибут импорта

**C++Зависящ**

Обходит проблемы конфликтов имен.

## <a name="syntax"></a>Синтаксис

> **#import** " **Переименование** *библиотеки типов* " ("*oldname*" **,** "*newname*" **)**

### <a name="parameters"></a>Параметры

*OldName*\
Старое имя в библиотеке типов.

*Новое*\
Имя, используемое вместо старого имени.

## <a name="remarks"></a>Примечания

Если указан атрибут **Rename** , компилятор заменяет все вхождения *oldname* в *Type-Library* на предоставляемое пользователем *новое* имя в результирующих файлах заголовков.

Атрибут **Rename** можно использовать, если имя в библиотеке типов совпадает с определением макроса в системных файлах заголовков. Если эта ситуация не устранена, компилятор может выдавать различные синтаксические ошибки, такие как [Ошибка компилятора C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) и [Ошибка компилятора C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Замена предоставляется для имени, используемого в библиотеке типов, а не для имени, используемого в открывшемся файле заголовка.

Например, предположим, что свойство `MyParent` существует в библиотеке типов, а макрос `GetMyParent` определен в файле заголовка и используется перед `#import`. Поскольку `GetMyParent` является именем по умолчанию функции-оболочки для свойства `get` обработки ошибок, возникнет конфликт имен. Для решения проблемы используйте следующий атрибут в инструкции `#import`:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

чтобы переименовать имя `MyParent` в библиотеке типов. Попытка переименовать программу-оболочку `GetMyParent` завершится ошибкой:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Это связано с тем, что имя `GetMyParent` происходит только в результирующем файле заголовка библиотеки типов.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также раздел

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
