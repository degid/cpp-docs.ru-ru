---
title: /Хеадерунит (использование единицы заголовка ИФК)
description: Используйте параметр компилятора/Хеадерунит, чтобы указать существующую единицу заголовка ИФК для импорта в текущей компиляции.
ms.date: 09/13/2020
f1_keywords:
- /headerUnit
helpviewer_keywords:
- /headerUnit
- Use header unit IFC
ms.openlocfilehash: 2734df728b188dcfbbe5f475cfc67715a070975d
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079174"
---
# <a name="headerunit-use-header-unit-ifc"></a>`/headerUnit` (Используйте заголовок Unit ИФК)

Указывает компилятору на необходимость преобразования `#include` директив для импорта имени заголовка в `import header-name;` директиву вместо использования текстового включения.

## <a name="syntax"></a>Синтаксис

> **`/headerUnit`** *`header-filename`*=*`ifc-filename`*

### <a name="arguments"></a>Аргументы

*`header-filename`*\
Имя файла, к которому компилятор разрешает `header-name` . Во время `import header-name ;` компиляции компилятор разрешается `header-name` в некоторый файл на диске. Используйте *`header-filename`* для указания этого файла. После сопоставления компилятор открывает соответствующий ИФК с именем в *`ifc-filename`* для импорта.

*`ifc-filename`*\
Имя файла, содержащего *данные ИФК*, предварительно сформированные сведения о модуле. Чтобы импортировать более одной единицы заголовка, включите отдельный **`/headerUnit`** параметр для каждого файла.

## <a name="remarks"></a>Примечания

Для **`/headerUnit`** параметра компилятора требуется включить поддержку экспериментальных модулей с помощью [`/experimental:module`](experimental-module.md) параметра компилятора, а также параметр [/std: c + + Latest](std-specify-language-standard-version.md) . Этот параметр доступен начиная с Visual Studio 2019 версии 16,8.

Компилятор не может сопоставлять один или *`header-name`* несколько файлов ИФК. При одновременном сопоставлении нескольких *`header-name`* аргументов с одним ИФК это не рекомендуется. Содержимое ИФК импортируется так, как если бы оно имело только заголовок, заданный параметром *`header-name`* .

### <a name="examples"></a>Примеры

При наличии проекта, который ссылается на два файла заголовков и их единицы заголовка, перечисленные в этой таблице:

| Файл заголовка | Файл ИФК |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

Параметры компилятора для ссылки на единицы заголовка для этих отдельных файлов заголовков могут выглядеть, как в следующем примере:

```CMD
cl ... /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите в раскрывающемся списке **Конфигурация** значение **все конфигурации**.

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы добавить *`/headerUnit`* Параметры и аргументы. Затем нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также раздел

[`/experimental:module` (Включение поддержки модуля)](experimental-module.md)\
[`/module:exportHeader` (Создание единиц заголовка)](module-exportheader.md)\
[`/module:reference` (Используйте именованный модуль ИФК)](module-reference.md)\
[`/translateInclude` (Преобразование директив include в директивы Import)](translateinclude.md)\
