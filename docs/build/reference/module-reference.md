---
title: '/модуле: Reference (используйте именованный модуль ИФК)'
description: 'Используйте параметр компилятора/модуле: Reference, чтобы создать единицы заголовков модуля для указанных заголовочных или включаемых файлов.'
ms.date: 09/13/2020
f1_keywords:
- /module:reference
helpviewer_keywords:
- /module:reference
- Use named module IFC
ms.openlocfilehash: 5f40f6b700c38f3238cc7a621313621085fbc289
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079170"
---
# <a name="modulereference-use-named-module-ifc"></a>`/module:reference` (Используйте именованный модуль ИФК)

Указывает компилятору использовать существующую ИФК ( *`.ifc`* ) для текущей компиляции.

## <a name="syntax"></a>Синтаксис

> **`/module:reference`** *`module-name=filename`*\
> **`/module:reference`** *`filename`*

### <a name="arguments"></a>Аргументы

*`filename`*\
Имя файла, содержащего *данные ИФК*, предварительно сформированные сведения о модуле. Чтобы импортировать более одного модуля, включите отдельный **`/module:reference`** параметр для каждого файла.

*`module-name`*\
Допустимое имя экспортированного базового интерфейса основного модуля или полного имени секции модуля.

## <a name="remarks"></a>Примечания

Для **`/module:reference`** параметра компилятора требуется включить поддержку экспериментальных модулей с помощью [`/experimental:module`](experimental-module.md) параметра компилятора, а также параметр [/std: c + + Latest](std-specify-language-standard-version.md) . Этот параметр доступен начиная с Visual Studio 2019 версии 16,8.

Если **`/module:reference`** аргумент имеет значение *`filename`* без *`module-name`* , то файл открывается во время выполнения, чтобы проверить *`filename`* имена аргументов на наличие определенного импорта. Это может привести к снижению производительности среды выполнения в сценариях с множеством **`/module:reference`** аргументов.

*`module-name`* Должно быть допустимым именем единицы интерфейса основного модуля или полным именем секции модуля. Примеры имен основных интерфейсов модулей включают:

- `M`
- `M.N.O`
- `MyModule`
- `my_module`

Примеры полных имен разделов модулей включают:

- `M:P`
- `M.N.O:P.Q`
- `MyModule:Algorithms`
- `my_module:algorithms`

Если ссылка на модуль создается с помощью *`module-name`* , другие модули в командной строке не просматриваются, если компилятор встречает это имя. Например, при наличии следующей командной строки:

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m=n.ifc
```

В приведенном выше случае, если компилятор видит `import m;` , *`m.ifc`* Поиск не выполняется.

### <a name="examples"></a>Примеры

Указанные три модуля, перечисленные в следующей таблице:

| Модуль | Файл ИФК |
|--|--|
| *`M`* | *`m.ifc`* |
| *`M:Part1`* | *`m-part1.ifc`* |
| *`Core.Networking`* | *`Networking.ifc`* |

Ссылочные параметры, использующие *`filename`* аргумент, могут выглядеть следующим образом:

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m-part.ifc /module:reference Networking.ifc
```

Параметры ссылок с использованием *`module-name=filename`* могут выглядеть следующим образом:

```cmd
cl ... /experimental:module /module:reference m=m.ifc /module:reference M:Part1=m-part.ifc /module:reference Core.Networking=Networking.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите в раскрывающемся списке **Конфигурация** значение **все конфигурации**.

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы добавить *`/module:reference`* параметр и его аргументы. Затем нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также раздел

[`/experimental:module` (Включение поддержки модуля)](experimental-module.md)\
[`/headerUnit` (Используйте заголовок Unit ИФК)](headerunit.md)\
[`/module:exportHeader` (Создание единиц заголовка)](module-exportheader.md)\
[`/translateInclude` (Преобразование директив include в директивы Import)](translateinclude.md)
