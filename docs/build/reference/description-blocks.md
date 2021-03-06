---
title: Блоки описания
description: NMAKE использует блоки описания для ассоциировать цели, зависимости и команды в makefile.
ms.date: 10/29/2019
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: e4e80b59d3d30b3b34c55b40d337ef5c078e6404
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322262"
---
# <a name="description-blocks"></a>Блоки описания

Блоки описания образуют ядро makefile. Они описывают *цели,* или файлы для создания, и их *зависимостей,* файлы, необходимые для создания целей. Блок описания может включать *команды,* описывающие, как создавать цели из зависимостей. Блок описания — это линия зависимости, за которой следует блок команд:

```makefile
targets... : dependents...
    commands...
```

## <a name="dependency-lines"></a>Линии зависимости

*Линия зависимости* определяет одну или несколько целей и нулевых или более иждивенцев. Если цель не существует или имеет более раннюю метку времени, чем зависимая, NMAKE выполняет команды в командном блоке. NMAKE также выполняет командный блок, если цель является [псевдоцелевым.](pseudotargets.md) Вот пример строки зависимости:

```makefile
hi_bye.exe : hello.obj goodbye.obj helper.lib
```

В этой линии `hi_bye.exe` зависимости, является целью. Его `hello.obj`зависимости, `goodbye.obj`и `helper.lib`. Линия зависимости говорит NMAKE построить `hello.obj`цель `goodbye.obj`всякий раз, когда, или `helper.lib` изменилась в последнее время. `hi_bye.exe`

Цель должна быть в начале линии. Он не может быть отступом с любыми пробелами или вкладками. Используйте толстую кишку ()`:`для отделения целей от иждивенцев. Пространства или вкладки допускаются между целями,`:`сепаратор толстой кишки (), и иждивенцев. Чтобы разделить линию зависимости, используйте backslash (`\`) после цели или иждивенца.

Перед выполнением блоков команд NMAKE сканирует все зависимости и любые применимые правила выводов для создания *дерева зависимостей.* Дерево зависимостей определяет шаги, необходимые для полного обновления цели. NMAKE повторно проверяет, является ли иждивенец самой мишенью в другом списке зависимостей. После того, как оно строит дерево зависимости, NMAKE проверяет временные марки. Если какие-либо иждивенцы в дереве новее, чем цель, NMAKE строит цель.

## <a name="targets"></a><a name="targets"></a>Цели

В разделе целей линии зависимости указана одна или несколько целей. Целью может быть любое действительное имя файла, имя каталога или [псевдоцелевой таргет.](pseudotargets.md) Разделите несколько целей, используя одно или несколько пробелов или вкладок. Цели не чувствительны к случаям. Пути разрешены с именами файлов. Цель и ее путь не могут превышать 256 символов. Если цель, предшествующая толстой кишке, является одним символом, используйте отделяющее пространство. В противном случае, NMAKE интерпретирует комбинацию буквы и толстой кишки как разоспектор диска.

### <a name="multiple-targets"></a><a name="multiple-targets"></a>Несколько целей

NMAKE оценивает несколько целей в одной зависимости, как если бы каждая из них была указана в отдельном блоке описания.

Например, это правило:

```makefile
bounce.exe leap.exe : jump.obj
   echo Building...
```

оценивается как:

```makefile
bounce.exe : jump.obj
   echo Building...

leap.exe : jump.obj
   echo Building...
```

### <a name="cumulative-dependencies"></a><a name="cumulative-dependencies"></a>Совокупные зависимости

Зависимости являются кумулятивными в блоке описания, если цель повторяется.

Например, этот набор правил,

```makefile
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

оценивается как:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Когда у вас есть несколько целей в нескольких линиях зависимостей в одном блоке описания, NMAKE оценивает их так, как если бы каждая из них была указана в отдельном блоке описания. Однако только цели в последней строке зависимости используют блок команд. NMAKE пытается использовать правило выводов для других целей.

Например, этот набор правил,

```makefile
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

оценивается как:

```makefile
leap.exe : jump.obj
# invokes an inference rule

bounce.exe : jump.obj up.obj
   echo Building bounce.exe...

climb.exe : up.obj
   echo Building bounce.exe...
```

### <a name="targets-in-multiple-description-blocks"></a><a name="targets-in-multiple-description-blocks"></a>Цели в нескольких блоках описания

Чтобы обновить цель в нескольких блоках описания с помощью различных команд, укажите две последовательные двоеточия (::) между целями и иждивениями.

```makefile
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

### <a name="dependency-side-effects"></a><a name="dependency-side-effects"></a>Побочные эффекты зависимости

Можно указать цель с толстой (:) в двух линиях зависимости в разных местах. Если команды появляются только после одной из строк, NMAKE интерпретирует зависимости так, как если бы линии были смежными или комбинированными. Он не ссылается на правило выводов для зависимости, которая не имеет команд. Вместо этого NMAKE предполагает, что зависимые должны принадлежать одному блоку описания, и выполняет команды, указанные с другой зависимостью. Рассмотрим этот набор правил:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

оценивается как:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Этот эффект не происходит, если`::`двойная толстая кишка () используется. Например, этот набор правил:

```makefile
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

оценивается как:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

### <a name="pseudotargets"></a><a name="pseudotargets"></a>Псевдоцели

*Псевдоцелевой —* это метка, используемая вместо имени файла в строке зависимости. Он интерпретируется как файл, который не существует, и поэтому устарел. NMAKE предполагает, что метка времени псевдоцелевого утилика такая же, как и самая последняя из всех его иждивенцев. Если у него нет иждивенцев, предполагается текущее время. Если псевдоцелевой таргет используется в качестве цели, ее команды всегда выполняются. Псевдоцелевой, используемый в качестве зависимого, также должен отображаться в качестве цели в другой зависимости. Однако эта зависимость не должна иметь блок команд.

Имена псевдоцелевых объектов следуют правилам синтаксиса filename для целей. Однако, если имя не имеет расширения, оно может превышать лимит 8 символов для имен файлов и может составить до 256 символов в длину.

Псевдоцели полезны, когда вы хотите, чтобы NMAKE автоматически построить несколько целей. NMAKE строит только цели, указанные в командной строке. Или, если цель командной строки не указана, она строит только первую цель в первой зависимости в makefile. Вы можете сказать NMAKE построить несколько целей, не перечисляя их индивидуально на командной строке. Напишите блок описания с зависимостью, содержащей псевдоцелевой объект, и перечислите цели, которые вы хотите построить в качестве иждивенцев. Затем поместите этот блок описания сначала в makefile или укажите псевдоцелевой показатель на командной строке NMAKE.

В этом примере UPDATE является псевдоцелевым объектом.

```makefile
UPDATE : *.*
!COPY $** c:\product\release
```

Когда ОБНОВЛЕНИЕ оценивается, NMAKE копирует все файлы в текущем каталоге в указанный диск и каталог.

В следующем makefile `all` псевдоцелевой строит `project1.exe` `project2.exe` ся, `all` и если на командной строке указана цель или нет. Псевдоцелевой `setenv` изменяет переменную `.exe` среды LIB перед обновлением файлов:

```makefile
all : setenv project1.exe project2.exe

project1.exe : project1.obj
    LINK project1;

project2.exe : project2.obj
    LINK project2;

setenv :
    set LIB=\project\lib
```

## <a name="dependents"></a><a name="dependents"></a>Иждивенцев

В строке зависимости укажите ноль или`:`более иждивенцев после толстой кишки () или двойной толстой кишки (),`::`используя любое действительное имя файла или [псевдоцелевой таргет.](pseudotargets.md) Разделите несколько иждивенцев, используя одно или несколько пробелов или вкладок. Иждивенцы не чувствительны к случаям. Пути разрешены с именами файлов.

### <a name="inferred-dependents"></a><a name="inferred-dependents"></a>Выведенные иждивенцы

Наряду с иждивенцем, которые вы явно перечисляете в строке зависимости, NMAKE может предположить *выведенный зависимый*. Выведенный иждивенец выводится из правила выводов и оценивается перед явными иждивениями. Когда выведенный зависимый устарел по сравнению с целью, NMAKE вызывает блок команды для зависимости. Если выведенный иждивенец не существует или устарел по сравнению со своими иждивениями, NMAKE сначала обновляет выведенный иждивенец. Для получения дополнительной информации о [Inference rules](inference-rules.md)выведенных иждивенцах см.

### <a name="search-paths-for-dependents"></a><a name="search-paths-for-dependents"></a>Пути поиска для иждивенцев

Можно указать дополнительный путь поиска для каждого иждивенца. Вот синтаксис, чтобы указать набор каталогов для поиска:

> каталог **;** _directory_ **{**\[ _каталог_...» **- зависимый**_dependent_

Приложить имена каталога в`{ }`скобках ( ). Отдельные несколько каталогов`;`с запятой (). Пробелы или вкладки не допускаются. NMAKE ищет иждивенцев сначала в текущем каталоге, а затем в списке каталогов в указанном порядке. Можно использовать макрос для указания части или всего пути поиска. Только указанный зависимый использует этот путь поиска.

#### <a name="directory-search-path-example"></a>Пример поиска каталога

Эта строка зависимости показывает, как создать спецификацию каталога для поиска:

```makefile
reverse.exe : {\src\omega;e:\repo\backwards}retro.obj
```

Цель `reverse.exe` имеет один `retro.obj`зависимый, . Список, закрытый скобками, определяет два каталога. NMAKE ищет `retro.obj` в текущем каталоге в первую очередь. Если его нет, NMAKE ищет `\src\omega` каталог, то `e:\repo\backwards` каталог.

## <a name="see-also"></a>См. также раздел

[Справка NMAKE](nmake-reference.md)
