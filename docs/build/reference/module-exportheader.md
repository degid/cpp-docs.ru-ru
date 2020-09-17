---
title: '/модуле: Експорсеадер (создание единиц заголовка)'
description: 'Используйте параметр компилятора/модуле: Експорсеадер, чтобы создать единицы заголовка модуля для указанных заголовочных или включаемых файлов.'
ms.date: 09/13/2020
f1_keywords:
- /module:exportHeader
helpviewer_keywords:
- /module:exportHeader
- Create header units
ms.openlocfilehash: f0c0ce1c593df742af77aa36189df1e89de75b6b
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079166"
---
# <a name="moduleexportheader-create-header-units"></a>`/module:exportHeader` (Создание единиц заголовка)

Указывает компилятору создавать единицы заголовка, заданные входными аргументами. Компилятор создает выходные данные в файлах ИФК ( *`.ifc`* ).

## <a name="syntax"></a>Синтаксис

> **`/module:exportHeader`** *`header-name`* \[...]\
> **`/module:exportHeader`** *`filename`* \[...]

### <a name="arguments"></a>Аргументы

*`header-name`*\
Экспортируемый файл заголовка. *`header-name`* Аргумент должен принимать ту же форму, что и аргумент, в `#include` директиву.

*`filename`*\
Относительный или абсолютный путь к файлу заголовка, из которого создается единица заголовка.

## <a name="remarks"></a>Примечания

Для **`/module:exportHeader`** параметра компилятора требуется включить поддержку экспериментальных модулей с помощью [`/experimental:module`](experimental-module.md) параметра компилятора, а также параметр [/std: c + + Latest](std-specify-language-standard-version.md) . Этот параметр доступен начиная с Visual Studio 2019 версии 16,8.

Один **`/module:exportHeader`** параметр компилятора может указывать столько аргументов заголовка, сколько требуется для сборки. Их не нужно указывать отдельно.

По умолчанию компилятор не создает объектный файл при компиляции блока заголовка. Чтобы создать объектный файл, укажите **`/Fo`** параметр компилятора. Дополнительные сведения см. в разделе [ `/Fo` (имя объектного файла)](fo-object-file-name.md).

Компилятор разрешает объект на *`header-name`* основе порядка поиска включаемых каталогов, включая все указанные вами. Дополнительные сведения см. в разделе [ `/I` (дополнительные каталоги включаемых данных)](i-additional-include-directories.md).

Аргумент *`header-name`* должен быть указан так же, как в источнике. Аргумент чувствителен к правилам заключения в кавычки и `<` `>` операторам и в командной строке. Правильно экранированная команда для создания единицы заголовка, например, `<vector>` с помощью командной строки VS2019, может выглядеть следующим образом:

```cmd
cl ... /experimental:module /module:exportHeader "<vector>"
```

Создание локального заголовка проекта, например, `"utils/util.h"` может выглядеть следующим образом:

```cmd
cl ... /experimental:module /module:exportHeader """util/util.h"""
```

Правила заключения в кавычки в других процессорах командной строки могут отличаться.

При использовании такой *`header-name`* формы **`/module:exportHeader`** может оказаться полезным использовать дополнительный вариант **`/module:showResolvedHeader`** . **`/module:showResolvedHeader`** Параметр выводит абсолютный путь к файлу, *`header-name`* в который разрешается аргумент.

**`/module:exportHeader`** может одновременно управлять несколькими входами, даже в **`/MP`** . Мы рекомендуем использовать **`/module:output <directory>`** для создания отдельного файла ИФК для каждой компиляции.

### <a name="examples"></a>Примеры

Заданные заголовки `"C:\util\util.h"` и `"C:\app\app.h"` , их можно экспортировать в качестве *`header-name`* аргументов с помощью следующей команды:

```cmd
cl /IC:\ /experimental:module /module:exportHeader """util/util.h""" """app/app.h""" /FoC:\obj
```

Их можно экспортировать в качестве *`filename`* аргументов с помощью следующей команды:

```cmd
cl /IC:\ /experimental:module /module:exportHeader C:\util\util.h C:\app\app.h /FoC:\obj
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите в раскрывающемся списке **Конфигурация** значение **все конфигурации**.

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы добавить *`/module:exportHeader`* параметр и все аргументы. Затем нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также раздел

[`/experimental:module` (Включение поддержки модуля)](experimental-module.md)\
[`/headerUnit` (Используйте заголовок Unit ИФК)](headerunit.md)\
[`/module:reference` (Используйте именованный модуль ИФК)](module-reference.md)\
[`/translateInclude` (Преобразование директив include в директивы Import)](translateinclude.md)
