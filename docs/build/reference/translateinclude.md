---
title: /Транслатеинклуде (преобразование директив include в директивы Import)
description: 'Используйте параметр компилятора/Транслатеинклуде, чтобы преобразовать директивы #include для импортируемого заголовка-name в директиву Import Header-Name.'
ms.date: 09/13/2020
f1_keywords:
- /translateInclude
helpviewer_keywords:
- /translateInclude
- Translate include directives into import directives
ms.openlocfilehash: 0050f2cb117e48d69cf97a587ef128b9b45790af
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079163"
---
# <a name="translateinclude-translate-include-directives-into-import-directives"></a>`/translateInclude` (Преобразование директив include в директивы Import)

Указывает компилятору на необходимость преобразования `#include` директив для импорта имени заголовка в `import header-name;` директиву вместо использования текстового включения.

## <a name="syntax"></a>Синтаксис

> **`/translateInclude`**

## <a name="remarks"></a>Примечания

Для **`/translateInclude`** параметра компилятора требуется включить поддержку экспериментальных модулей с помощью [`/experimental:module`](experimental-module.md) параметра компилятора, а также параметр [/std: c + + Latest](std-specify-language-standard-version.md) . Этот параметр доступен начиная с Visual Studio 2019 версии 16,8.

Этот **`/translateInclude`** параметр обеспечивает следующее преобразование, в котором в качестве примера `<vector>` используется импортная единица заголовка:

```cpp
#include <vector>
```

Компилятор заменяет эту директиву следующим:

```cpp
import <vector> ;
```

В КОМПИЛЯТОРОМ MSVC единица заголовка с импортом называется **`/headerUnit`** ссылкой. Дополнительные сведения см. в разделе [ `/headerUnit` (использование единицы заголовка ИФК)](headerunit.md).

### <a name="examples"></a>Примеры

При наличии проекта, который ссылается на два файла заголовков и их единицы заголовка, перечисленные в этой таблице:

| Файл заголовка | Файл ИФК |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

И исходный *`.cpp`* файл, содержащий заголовки,

```cpp
#include "utils/util.h"
#include "app/app.h"

int main() { }
```

**`/translateInclude`** Параметр позволяет компилятору импортировать единицы заголовка вместо компиляции заголовков. Ниже приведен пример командной строки, которая преобразует директивы include для *`util.h`* и *`app.h`* в импортируемые единицы заголовков.

```CMD
cl /IC:\ /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите в раскрывающемся списке **Конфигурация** значение **все конфигурации**.

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы добавить *`/translateInclude`* параметр. Затем нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также раздел

[`/experimental:module` (Включение поддержки модуля)](experimental-module.md)\
[ `/headerUnit` (Используйте единицу заголовка ИФК)](headerunit.md). \
[`/module:exportHeader` (Создание единиц заголовка)](module-exportheader.md)\
[`/module:reference` (Используйте именованный модуль ИФК)](module-reference.md)
