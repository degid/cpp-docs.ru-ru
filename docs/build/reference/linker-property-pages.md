---
title: Страницы свойств компоновщика
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 2f2068c6c51fc6bf4e4104213e946e243fc6df2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336589"
---
# <a name="linker-property-pages"></a>Страницы свойств компоновщика

Следующие свойства находятся в **соответствии** > с Project**Properties** > **Configuration Properties** > **Linker**. Для получения дополнительной информации о связующем, [см. CL Вызывает Linker](cl-invokes-the-linker.md) и [Linker options](linker-options.md).

## <a name="general-property-page"></a>Страница общего имущества

### <a name="output-file"></a>Выходной файл

Опция [/OUT](out-output-file-name.md) переопределяет имя по умолчанию и местоположение программы, которую создает связующий.

### <a name="show-progress"></a>Отображать ход выполнения

Печать сообщений о прогрессе Linker

**Choices**

- **Не набор** - Нет многословия.
- **Отображение всех сообщений прогресса** - Отображает все сообщения прогресса.
- **Для библиотек, наданных** - Отображаетсообщения сообщения о ходе работы, указывающие только на исискаленные библиотеки.
- **О складировании COMDAT во время оптимизированного соединения** - Отображает информацию о складировании COMDAT во время оптимизированного соединения.
- **О данных, удаленных во время оптимизированной связи** - Отображает информацию о функциях и данных, удаленных во время оптимизированного соединения.
- **О модулях, несовместимых с SEH** - Отображает информацию о модулях, несовместимую с безопасной обработкой исключений.
- **О деятельности linker, связанной с управляемым кодом** - Отображение информации о деятельности linker, связанной с управляемым кодом.

### <a name="version"></a>Version

Опция [/VERSION](version-version-information.md) говорит связующее звено, чтобы поместить номер версии в заголовок файла .exe или .dll. Используйте DUMPBIN /HEADERS, чтобы увидеть поле версии изображения ФАКУЛЬТИЯ HEADER VALUES, чтобы увидеть эффект **/VERSION**.

### <a name="enable-incremental-linking"></a>Включить инкрементную компоновку

Позволяет поэтапную связь. ([/ИНКРЕМЕНТНЫЙ,](incremental-link-incrementally.md)/ИНКРЕМЕНТНЫЙ:НЕТ)

### <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

Опция [/NOLOGO](nologo-suppress-startup-banner-linker.md) предотвращает отображение сообщения об авторском праве и номера версии.

### <a name="ignore-import-library"></a>Пропустить библиотеку импорта

Это свойство указывает компоновщику не связывать никакие выходные данные LIB, созданные этой сборкой, в любом зависимом проекте. Это позволяет системе проекта обрабатывать файлы .dll, которые не производят файл .lib при построении. Если проект зависит от другого проекта, создающего библиотеку DLL, система проектов автоматически связывает LIB-файл, созданный этим дочерним проектом. Это свойство может быть ненужным в проектах, которые производят COM DLLs или только ресурсы DLLs, потому что эти DLLs не имеют каких-либо значимых экспорта. Если DLL не имеет экспорта, ссылка не генерирует файл .lib. Если нет экспорта файла .lib, и система проекта сообщает связующим звеном с отсутствующим DLL, ссылка выходит из строя. Для устранения этой проблемы используйте свойство **Пропустить библиотеку импорта**. При установке **на Yes,** проектная система игнорирует наличие или отсутствие файла .lib, и вызывает любой проект, который зависит от этого проекта, чтобы не связываться с несуществующим файлом .lib.

Для программного доступа к этому свойству см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>Зарегистрировать вывод

Запускает `regsvr32.exe /s $(TargetPath)` для выходных данных сборки, что допустимо только для проектов DLL. Для проектов EXE это свойство не учитывается. Чтобы зарегистрировать вывод EXE, задайте событие после сборки для конфигурации для выполнения настраиваемой регистрации, которая всегда необходима для зарегистрированных файлов EXE.

Для программного доступа к этому свойству см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Перенаправление для пользователей

Регистрация в Visual Studio традиционно осуществлялась в HKEY_CLASSES_ROOT (HKCR). С Windows Vista и операционными системами более поздних версий для доступа к HKCR нужно запустить Visual Studio в режиме с повышенными правами. Разработчики не всегда хотят работать в повышенном режиме, но все равно должны работать с регистрацией. Перенаправление на пользователя позволяет зарегистрироваться без работы в повышенном режиме.

Перенаправление для пользователей принудительно перенаправляет все записи для HKCR в раздел HKEY\_CURRENT\_USER (HKCU). Если перенаправление для пользователей отключено, это может вызвать [ошибку сборки проекта PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md) при попытке программы выполнить запись в HKCR.

### <a name="additional-library-directories"></a>Дополнительные каталоги библиотек

Разрешает пользователю переопределять путь окружения библиотеки. ([/LIBPATH](libpath-additional-libpath.md):папка)

### <a name="link-library-dependencies"></a>Компоновать зависимости библиотек

Указывает, следует ли связывать LIB-файлы, созданные с помощью зависимых проектов. Как правило, требуется ссылка в файлах .lib, но это может быть не так для некоторых DLLs.

Можно также задать OBJ-файл, указав имя файла и относительный путь, например "..\\..\MyLibProject\MyObjFile.obj". Если исходный код файла .obj #includes предварительно скомпилированный заголовок, например pch.h, то файл pch.obj находится в той же папке, что и MyObjFile.obj. Вы также должны добавить pch.obj в качестве дополнительной зависимости.

### <a name="use-library-dependency-inputs"></a>Использовать входные данные зависимостей библиотек

Определяет, следует ли использовать входные данные в библиотечном инструменте, а не сам файл библиотеки при увязке в библиотечных выводах зависимостей проекта. Если в большом проекте зависимый проект создает LIB-файл, инкрементная компоновка отключена. Если существует много зависимых проектов, создающих LIB-файлы, сборка приложения может занять много времени. Когда это свойство настроено **на Yes,** система проекта связывает сявки в файлах .obj для .libs, производимых зависимыми проектами, что позволяет поэтапную связь.

Для получения информации о том, как получить доступ к странице свойств **Общего** ссылка, [см.](../working-with-project-properties.md)

### <a name="link-status"></a>состояние канала;

Определяет, должен ли связующий отображать индикатор прогресса, показывающий, какой процент ссылки завершен. По умолчанию не отображаются данные этого статуса. ([/LTCG](ltcg-link-time-code-generation.md):СТАТУС LTCG:NOSTATUS)

### <a name="prevent-dll-binding"></a>Предотвращение связывания DLL

[/ALLOWBIND](allowbind-prevent-dll-binding.md):NO устанавливает немного в заголовке DLL, который указывает на Bind.exe, что изображение не может быть связано. Если DLL имеет цифровую подпись, привязывать ее не следует (при привязке цифровая подпись становится недействительной).

### <a name="treat-linker-warning-as-errors"></a>Относитесь к предупреждению Linker как к ошибкам

[/WX](wx-treat-linker-warnings-as-errors.md) не вызывает генерации выходного файла, если ссылка генерирует предупреждение.

### <a name="force-file-output"></a>Вывод файла силы

Опция [/FORCE](force-force-file-output.md) указывает связующее элементосёт для создания файла .exe или DLL, даже если символ отослужен, но не определен или умножается. Это может создать недействительный файл .exe.

**Choices**

- **Включено** - /FORCE без аргументов подразумевает как несколько, так и нерешенные.
- **Умножьте только определенный символ** - Используйте /FORCE:MULTIPLE для создания выходного файла, даже если LINK находит более одного определения символа.
- **Только неопределенный символ** - Использование /FORCE:UNRESOLVED для создания выходного файла независимо от того, находит ли LINK неопределенный символ. /FORCE:UNRESOLVED игнорируется, если символ точки входа не решен.

### <a name="create-hot-patchable-image"></a>Создание горячего патчейного изображения

Готовит изображение для hotpatching.

**Choices**

- **Включено** - готовит изображение для hotpatching.
- **Только X86 Image** - готовит изображение X86 для горячего доступа.
- **Только X64 Image** - готовит изображение X64 для горячего доступа.
- **Itanium Image Only** - готовит изображение Itanium для нагревания.

### <a name="specify-section-attributes"></a>Указать атрибуты раздела

Параметр [/SECTION](section-specify-section-attributes.md) изменяет атрибуты раздела, перекрывая атрибуты, установленные при компилировании файла .obj для раздела.

## <a name="input-property-page"></a>Страница входной недвижимости

### <a name="additional-dependencies"></a>Дополнительные зависимости

Определяет дополнительные элементы для добавления в строку командной линии ссылки, например *kernel32.lib*.

### <a name="ignore-all-default-libraries"></a>Игнорировать все библиотеки по умолчанию

Опция [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) говорит связующее звено об удалении одной или нескольких библиотек по умолчанию из списка библиотек, которые он ищет при разрешении внешних ссылок.

### <a name="ignore-specific-default-libraries"></a>Игнорировать конкретные стандартные библиотеки

Указывает одно или несколько имен пропускаемых библиотек по умолчанию. Отдельные несколько библиотек с полуколонами. (/NODEFAULTLIB: «имя, имя, ...»)

### <a name="module-definition-file"></a>Файл определения модуля

Опция [/DEF](def-specify-module-definition-file.md) передает файл определения модуля (.def) связующее звено. Только один файл .def может быть указан в LINK.

### <a name="add-module-to-assembly"></a>Добавление модуля в сборку

Опция [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md) позволяет добавить ссылку на модуль к сборке. Введите информацию в модуле не будет доступна для программы сборки, которая добавила ссылку на модуль. Тем не менее, введите информацию в модуле будет доступна для любой программы, которая ссылается на сборку.

### <a name="embed-managed-resource-file"></a>Встраиваемый файл управляемых ресурсов

[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) встраивает файл ресурса в выводный файл.

### <a name="force-symbol-references"></a>Принудительно включать ссылки на символы

Опция [/INCLUDE](include-force-symbol-references.md) говорит связующее звено добавить указанный символ в таблицу символов.

### <a name="delay-loaded-dlls"></a>Задержка загруженных DLLs

Опция [/DELAYLOAD](delayload-delay-load-import.md) вызывает задержку загрузки DLLs. Название dll определяет DLL для задержки загрузки.

### <a name="assembly-link-resource"></a>Ресурс связи ассамблеи

Опция [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md) создает ссылку на ресурс .NET Framework в файле вывода; файл ресурса не помещается в выводной файл.

## <a name="manifest-file-property-page"></a>Страница свойств файла manifest

### <a name="generate-manifest"></a>Генерировать манифест

[/MANIFEST](manifest-create-side-by-side-assembly-manifest.md) указывает, что связующий должен создать бок о бок манифест файла.

### <a name="manifest-file"></a>Файл манифеста

[/MANIFESTFILE](manifestfile-name-manifest-file.md) позволяет изменить имя файла манифеста по умолчанию. Имя файла по умолчанию — это имя файла с придативным .manifest.

### <a name="additional-manifest-dependencies"></a>Дополнительные явные зависимости

[/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md) позволяет указать атрибуты, которые будут помещены в раздел зависимости файла манифеста.

### <a name="allow-isolation"></a>Разрешить изоляцию

Задает поведение нахождения файлов манифеста. ([/ALLOWISOLATION](allowisolation-manifest-lookup.md):НЕТ)

### <a name="enable-user-account-control-uac"></a>Включить управление учетной записью пользователя (UAC)

Определяет, включен ли контроль учетной записи пользователя.  ([/МАНИФЕСТУАК](manifestuac-embeds-uac-information-in-manifest.md), /МАНИФЕСТУАК:НЕТ)

### <a name="uac-execution-level"></a>Уровень выполнения UAC

Уотек запрашиваемого уровня выполнения приложения при запуске с помощью управления учетной записью пользователя.  (/МАНИФЕСТУАК:уровень »значение»)

**Choices**

- **asInvoker** - Уровень выполнения UAC: как invoker.
- **highestAvailable** - Уровень выполнения UAC: самый высокий доступный.
- **требуетсяАдминистратор** - Уровень выполнения UAC: требуйте администратора.

### <a name="uac-bypass-ui-protection"></a>UAC Обходный uI защита

Уточняется, следует ли обходить уровни защиты пользовательского интерфейса для других окон на рабочем столе.  Установите это свойство на "Да" только для приложений доступности.  ([/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md):uiAccess »правда » ложный»

## <a name="debugging-property-page"></a>Страница свойств отладки

### <a name="generate-debug-info"></a>Генерация информации об ошибке

Эта опция позволяет создавать информацию об отладке для файла .exe или DLL.

**Choices**

- **Нет** - Не производит информацию об отладке.
- **Создание информации об ошибке** - Создание полной базы данных программ (PDB), идеально подходит для распространения на Microsoft Symbol Server.
- **Создание информации об ошибке, оптимизированной для более быстрых ссылок** - Создает базу данных программы (PDB), идеально подходят для цикла отсылки от отсылки от отсылки.
- **Создание информации об ошибке, оптимизированной для обмена и публикации** - Создает программную базу данных (PDB), идеально подобающие циклу отсылки к отсеиванию ссылок.

### <a name="generate-program-database-file"></a>Создание файла базы данных программы

По умолчанию, когда [/DEBUG](debug-generate-debug-info.md) указан, связующий создает базу данных программы (PDB), которая содержит информацию об отладке. Имя файла по умолчанию для PDB имеет базовое название программы и расширение .pdb.

### <a name="strip-private-symbols"></a>Стрип Частные символы

Опция [/PDBSTRIPPED](pdbstripped-strip-private-symbols.md) создает второй файл базы данных программы (PDB) при создании изображения программы с любым из параметров компилятора или связующим звеном, которые генерируют файл PDB (/DEBUG, / Q7, / Зд, или /Зи).

### <a name="generate-map-file"></a>Создание файла карты

Опция [/MAP](map-generate-mapfile.md) говорит связующее звено о создании картфайла.

### <a name="map-file-name"></a>Имя файла сопоставления

Имя, указанное пользователем для картфайла. Он заменяет имя по умолчанию.

### <a name="map-exports"></a>Карта Экспорт

Опция [/MAPINFO](mapinfo-include-information-in-mapfile.md) говорит связующее звено включить указанную информацию в картофайл, который создается, если вы указываете опцию /MAP. EXPORTS сообщает связующим звеном включить экспортированные функции.

### <a name="debuggable-assembly"></a>Отсеновьтечная сборка

[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md) излучает атрибут DebuggableAttribute с отладкой отслеживания информации и отклоняет оптимизацию JIT.

## <a name="system-property-page"></a>Страница Свойства системы

### <a name="subsystem"></a>Подсистемы

Опция [/SUBSYSTEM](subsystem-specify-subsystem.md) показывает операционной системе, как запустить файл .exe. Выбор подсистемы влияет на символ точки входа (или функцию точки входа), которую выберет связующий.

**Choices**

- **Не набор** - нет подсистемы набор.
- **Консоль** - Приложение win32 характер-режим. Консольные приложения получают консоль от операционной системы. Если основной или wmain определен, CONSOLE является по умолчанию.
- **Windows** - Приложение не требует консоли, вероятно, потому, что он создает свои собственные окна для взаимодействия с пользователем. Если WinMain или wWinMain определены, WINDOWS по умолчанию.
- **Родной** - Драйверы устройств для Windows NT. Если /DRIVER:WDM указан, NATIVE является по умолчанию.
- **Приложение EFI** - Приложение EFI.
- **Водитель сервиса EFI** Boot - водитель сервиса EFI Boot.
- **EFI ROM** - EFI ROM.
- **EFI Runtime** - EFI Runtime.
- **POSIX** - Приложение, которое работает с подсистемой POSIX в Windows NT.

### <a name="minimum-required-version"></a>Минимальная требуемая версия

Укажите минимально необходимый вариант подсистемы. Аргументы десятичные числа в диапазоне от 0 до 65 535.

### <a name="heap-reserve-size"></a>Размер кучи заповедника

Определяет общий размер распределения кучи в виртуальной памяти. По умолчанию 1 МБ.    ([/HEAP](heap-set-heap-size.md):резерв)

### <a name="heap-commit-size"></a>Куча Commit Размер

Определяет общий размер распределения кучи в физической памяти. По умолчанию 4 КБ.    ([/HEAP](heap-set-heap-size.md):reserve,commit)

### <a name="stack-reserve-size"></a>Размер резерва стека

Определяет общий размер виртуальной памяти, выделяемой для стека. По умолчанию 1 МБ.     ([/STACK](stack-stack-allocations.md):Reserve)

### <a name="stack-commit-size"></a>Стек Размер обязательства

Определяет общий размер распределения стека в физической памяти. По умолчанию 4 КБ.     ([/STACK](stack-stack-allocations.md):reserve,commit)

### <a name="enable-large-addresses"></a>Включить большие адреса

Опция [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md) сообщает связующее приложение о том, что приложение может обрабатывать адреса больше 2 гигабайт. По умолчанию/ LARGEADDRESSAWARE:NO включен, если /LARGEADDRESSAWARE не указан в строке linker.

### <a name="terminal-server"></a>Сервер терминалов

Опция [/TSAWARE](tsaware-create-terminal-server-aware-application.md) устанавливает флаг в поле IMAGE_OPTIONAL_HEADER DllCharacteristics в дополнительном заголовке изображения программы. Если этот флаг установлен, сервер терминалов не будет вносить определенные изменения в приложение.

### <a name="swap-run-from-cd"></a>Своп Run from CD

Опция [/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) говорит операционной системе сначала скопировать выход ссылки в файл своп, а затем запустить изображение оттуда. Эта опция является функцией Windows NT 4.0 (и позже). Когда **cd** указан, операционная система будет копировать изображение на съемном диске на файл страницы, а затем загрузить его.

### <a name="swap-run-from-network"></a>Своп Run from Network

Опция [/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) говорит операционной системе сначала скопировать выход ссылки в файл своп, а затем запустить изображение оттуда. Эта опция является функцией Windows NT 4.0 (и позже). Если **NET** указан, операционная система сначала скопирует двоичное изображение из сети в файл своп и загружает его оттуда. Эта опция полезна для работы приложений по сети.

### <a name="driver"></a>Драйвер

Используйте опцию [/DRIVER](driver-windows-nt-kernel-mode-driver.md) linker для создания драйвера режима ядра Windows NT.

**Choices**

- **Не набор** - настройка драйвера по умолчанию.
- **Водитель** - Водитель
- **ТОЛЬКО** UP - /DRIVER:UPONLY вызывает ссылку, чтобы добавить IMAGE_FILE_UP_SYSTEM_ONLY бит к характеристикам в заголовок вывода, чтобы указать, что это однопроцессор (UP) драйвер. Операционная система откажется от загрузки драйвера UP на многопроцессорную (MP) систему.
- **WDM** - /DRIVER:WDM вызывает ссылку установить IMAGE_DLLCHARACTERISTICS_WDM_DRIVER бит в поле DllCharacteristics факультативного заголовка.

## <a name="optimization-property-page"></a>Страница оптимизации свойства

### <a name="references"></a>Ссылки

[/OPT](opt-optimizations.md):REF устраняет функции и/или данные, на которые никогда не ссылаются, в то время как /OPT:NOREF сохраняет функции и/или данные, на которые никогда не ссылались.

### <a name="enable-comdat-folding"></a>Включить свертывание записей COMDAT

Используйте [/OPT](opt-optimizations.md)\[:ICF (итерации) для выполнения идентичных складывающихся COMDAT.

### <a name="function-order"></a>Порядок функций

Опция [/ORDER](order-put-functions-in-order.md)говорит LINK оптимизировать вашу программу, размещая определенные COMDATs в изображении в заранее определенном порядке. LINK помещает функции в указанном порядке в каждом разделе на изображении.

### <a name="profile-guided-database"></a>База данных для профилей

Укажите файл .pgd для оптимизации профиля. ([/PGD](pgd-specify-database-for-profile-guided-optimizations.md))

### <a name="link-time-code-generation"></a>Создание кода во время компоновки

Задает создание кода во время компоновки. ([/LTCG](ltcg-link-time-code-generation.md))

**Choices**

- **По умолчанию** - настройка LTCG по умолчанию.
- **Используйте быстрое время генерации кода** - Используйте ссылка Время код поколения с [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md).
- **Использование поколения кода времени ссылки** - Использование [поколения кода времени ссылки](ltcg-link-time-code-generation.md).
- **Профиль Руководствуясь Оптимизация - Инструмент** - Использование [профиля управляемой оптимизации](../profile-guided-optimizations.md) с :PGINSTRUMENT.
- **Оптимизация профиля - Оптимизация** - указывает, что связующее звено должно использовать данные профиля, созданные после запуска инструментируемого двоичного файла для создания оптимизированного изображения.
- **Профиль Руководствуясь Оптимизация - Обновление** - Позволяет и отслеживает список входных файлов, которые будут добавлены или изменены из того, что было указано в :PGINSTRUMENT фазы.

## <a name="embedded-idl-property-page"></a>Встроенная страница свойства IDL

### <a name="midl-commands"></a>Команды MIDL

Укажите параметры командной строки MIDL. ([/MIDL](midl-specify-midl-command-line-options.md):@responsefile)

### <a name="ignore-embedded-idl"></a>Игнорировать встроенный IDL

Опция [/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md) указывает на то, что любые атрибуты IDL в исходном коде не должны обрабатываться в файл .idl.

### <a name="merged-idl-base-file-name"></a>Слияние имен базового файла IDL

Опция [/IDLOUT](idlout-name-midl-output-files.md) определяет имя и расширение файла .idl.

### <a name="type-library"></a>Тип библиотеки

Опция [/TLBOUT](tlbout-name-dot-tlb-file.md) определяет имя и расширение файла .tlb.

### <a name="typelib-resource-id"></a>Идентификатор ресурсов TypeLib

Позволяет указать идентификатор ресурсов библиотеки типа linker. ([/TLBID](tlbid-specify-resource-id-for-typelib.md):id)

## <a name="windows-metadata-property-page"></a>Страница свойства метаданных Windows

### <a name="generate-windows-metadata"></a>Создание метаданных Windows

Позволяет или отменяет генерацию метаданных Windows.

**Choices**

- **Да** - Включите генерацию файлов Метаданных Windows.
- **Нет** - отключить генерацию файлов Windows Metadata.

### <a name="windows-metadata-file"></a>Файл метаданных Windows

Переключатель опции [/WINMDFILE.](winmdfile-specify-winmd-file.md)

### <a name="windows-metadata-key-file"></a>Ключевой файл Метаданных Windows

Укажите пару ключей или ключ ей для подписания метаданных Windows. ([/WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md):filename)

### <a name="windows-metadata-key-container"></a>Контейнер для ключей Windows Метаданные

Укажите ключевой контейнер для подписания метаданных Windows. ([/WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md):имя)

### <a name="windows-metadata-delay-sign"></a>Знак задержки метаданных Windows

Частично подпишите метаданные Windows. Используйте [/WINMDDELAYSIGN,](winmddelaysign-partially-sign-a-winmd.md) если вы хотите разместить общедоступный ключ в Метаданных Windows. По умолчанию /WINMDDELAYSIGN:NO.

## <a name="advanced-property-page"></a>Расширенная страница свойств

### <a name="entry-point"></a>Точка входа

Опция [/ENTRY](entry-entry-point-symbol.md) определяет функцию точки входа в качестве стартового адреса файла .exe или DLL.

### <a name="no-entry-point"></a>Точка входа не имеет

Для создания DLL, предназначенного только для ресурсов, требуется опция [/NOENTRY.](noentry-no-entry-point.md) Используйте эту опцию, чтобы `_main` предотвратить ссылку LINK на DLL.

### <a name="set-checksum"></a>Установить Checksum

Опция [/RELEASE](release-set-the-checksum.md) устанавливает Checksum в заголовке файла .exe.

### <a name="base-address"></a>Базовый адрес

Задает базовый адрес для программы. ([/BASE](base-base-address.md):\[«адрес, размер» @filename,ключ)

### <a name="randomized-base-address"></a>Рандомизированный базовый адрес

Рандомизированный базовый адрес. ([/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)\[:НЕТ)

### <a name="fixed-base-address"></a>Адрес фиксированной базы

Создает программу, которая может загружаться только по предпочтительному базовому адресу. ([/ИСПРАВЛЕНо:Нет)](fixed-fixed-base-address.md)\[

### <a name="data-execution-prevention-dep"></a>Предотвращение выполнения данных (DEP)

Отметка исполняемой как проверенная на совместимость с функцией предотвращения выполнения windows data. ([/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)\[:NO)

### <a name="turn-off-assembly-generation"></a>Выключить поколение сборки

Опция [/NOASSEMBLY](noassembly-create-a-msil-module.md) говорит связующее элементосмешение создать изображение для текущего вывода файла без сборки .NET Framework.

### <a name="unload-delay-loaded-dll"></a>Выгрузить задержку загруженной DLL

Квалификатор **UNLOAD** сообщает функции помощника задержки и загрузки для поддержки явной разгрузки DLL. ([/ЗАДЕРЖКА](delay-delay-load-import-settings.md):РАЗГРУЗКА)

### <a name="nobind-delay-loaded-dll"></a>Задержка Nobind загружена DLL

Квалификатор **NOBIND** говорит связующее не включать связующий IAT в окончательное изображение. По умолчанию задано создание связываемой таблицы IAT для библиотек DLL, загружаемых с задержкой. ([/ЗАДЕРЖКА](delay-delay-load-import-settings.md):NOBIND)

### <a name="import-library"></a>Библиотека импорта

Переопределяет имя библиотеки импорта по умолчанию. ([/IMPLIB](implib-name-import-library.md):filename)

### <a name="merge-sections"></a>Разделы слияния

Опция [/MERGE](merge-combine-sections.md) сочетает в себе первый раздел (от) со вторым разделом (к), называя результирующую секцию. Например, /слияние:.rdata.text.

### <a name="target-machine"></a>Целевая машина

Опция [/MACHINE](machine-specify-target-platform.md) определяет целевую платформу для программы.

**Choices**

- **Не установлен**
- **Машинар**
- **МашинАРМ64**
- **Машина**
- **Машина64**
- **Машинные МИПС**
- **МашинаMIPS16**
- **МашинныйMIPSFPU**
- **МашинныйMIPSFPU16**
- **МашинаSH4**
- **MachineTHUMB**
- **MachineX64**
- **MachineX86**

### <a name="profile"></a>Профиль

Создает выходной файл, который может быть использован для профилировщика производительности инструментов. Требуется GenerateDebugInformation (/[/DEBUG),](debug-generate-debug-info.md)который будет установлен. ([/ПРОФИЛЬ](profile-performance-tools-profiler.md))

### <a name="clr-thread-attribute"></a>Атрибут потока CLR

Явно укажите атрибут потока для точки входа в программу CLR.

**Choices**

- **Атрибут потока MTA** - применяет атрибут MTAThreadAttribute к точке входа в программу.
- **Атрибут потока STA** - применяет атрибут STAThreadAttribute к точке входа в программу.
- **Атрибут потока по умолчанию** - То же, что не указано [/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md). Позволяет общему языку Runtime (CLR) установить атрибут потока по умолчанию.

### <a name="clr-image-type"></a>Тип изображения CLR

Задает тип (IJW, pure или safe) CLR-образа.

**Choices**

- **Сила IJW изображение**
- **Сила Чистая IL изображение**
- **Сила Безопасный IL изображение**
- **Тип изображения по умолчанию**

### <a name="key-file"></a>Файл ключа

Укажите ключевую или ключевую пару для подписания сборки. ([/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md):filename)

### <a name="key-container"></a>Ключевой контейнер

Укажите ключевой контейнер для подписания сборки. ([/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md):имя)

### <a name="delay-sign"></a>Знак задержки

Частично подпишите сборку. Используйте [/DELAYSIGN,](delaysign-partially-sign-an-assembly.md) если вы хотите разместить только открытый ключ в сборке. По умолчанию /DELAYSIGN:NO.

### <a name="clr-unmanaged-code-check"></a>Проверка неуправляемого кода CLR

[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md) указывает, будет ли связующий применять SuppressUnmanagedCodeSecurityAttribute для ссылки генерируемых вызовов PInvoke из управляемого кода в родные DLLs.

### <a name="error-reporting"></a>Отчет об ошибках

Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в группу Visual C++.

**Choices**

- **PromptImmediately** - Подспотеть немедленно.
- **Очередь для следующего входа** - Очередь для следующего входа.
- **Отправка отчета об ошибке** - Отправить отчет об ошибке.
- **Отчет об ошибке** - Нет отчета об ошибке.

### <a name="sectionalignment"></a>SectionAlignment

Опция [/ALIGN](align-section-alignment.md) определяет выравнивание каждого раздела в линейном адресном пространстве программы. Аргумент числа находится в байтах и должен быть силой двух.

### <a name="preserve-last-error-code-for-pinvoke-calls"></a>Сохранить последний код ошибки для вызовов PInvoke

[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md), который находится на по умолчанию, сохраняет последний код ошибки функций, вызванных через p/ Invoke механизм, который позволяет вызывать родные функции в DLLS, из кода, компилированного с /clr.

**Choices**

- **Включено** - Включите CLRSupportLastError.
- **Инвалид** - Отключить CLRSupportLastError.
- **Система Dlls Только** - Включить CLRSupportLastError только для системных dlls только.

### <a name="image-has-safe-exception-handlers"></a>Изображение имеет безопасные обработчики исключений

Когда [/SAFESEH](safeseh-image-has-safe-exception-handlers.md) указан, связующий будет производить изображение только в том случае, если он может также создать таблицу обработчиков безопасных исключений изображения. В этой таблице указывается, какие обработчики исключений действительны для изображения.
