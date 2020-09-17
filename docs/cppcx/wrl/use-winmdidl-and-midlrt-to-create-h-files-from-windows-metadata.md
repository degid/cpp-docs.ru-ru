---
title: Практическое руководство. Использование winmdidl.exe и midlrt.exe для создания H-файлов из метаданных Windows
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
ms.openlocfilehash: bceb4aff22f6ebba9c8705b3b5a55d0478f244c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213542"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Практическое руководство. Использование winmdidl.exe и midlrt.exe для создания H-файлов из метаданных Windows

Winmdidl.exe и midlrt.exe разрешают взаимодействие COM-уровня между машинным кодом C++ и компонентами среды выполнения Windows. Winmdidl.exe принимает в качестве входных данных WINMD-файл, содержащий метаданные для компонента среды выполнения Windows, и выводит IDL-файл. Midlrt.exe преобразовывает этот IDL-файл в файлы заголовков, которые можно использовать в коде C++. Оба инструмента запускаются с помощью командной строки.

Эти инструменты используются в следующих двух сценариях:

- создание пользовательских IDL-файлов и файлов заголовков, чтобы приложение C++, написанное с помощью библиотеки шаблонов среды выполнения Windows (WRL), могло использовать пользовательский компонент среды выполнения Windows;

- создание прокси-сервера и файлов-заглушек для определяемых пользователем типов событий в компоненте среды выполнения Windows. Дополнительные сведения см. [в разделе Пользовательские события и методы доступа к событиям в среда выполнения Windows компонентах](/windows/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).

Эти инструменты требуются только для синтаксического анализа пользовательских WINMD-файлов. IDL- и H-файлы для компонентов операционной системы Windows уже созданы. По умолчанию в Windows 8.1 они находятся в папке \Program Files (x86) \Windows Kits\8.1\Include\winrt\\.

## <a name="location-of-the-tools"></a>Расположение инструментов

По умолчанию в [Windows 8.1, winmdidl. exe и midlrt. exe находятся в папке C:\Program Files (x86) \Windows Kits\8.1\\. Различные версии этих инструментов также доступны в папках \bin\x86\ и \bin\x64\.

## <a name="winmdidl-command-line-arguments"></a>Аргументы командной строки winmdidl

```
Winmdidl.exe [/nologo] [/suppressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile
```

**/nologo**<br/>
Блокирует отображение в консоли сообщения об авторских правах и номере версии winmdidl.

**/суппрессверсиончекк**<br/>
Не используется.

**/тиме**<br/>
Выводит общее время выполнения в окно консоли.

**/OutDir:** <em>dir</em><br/>
Задает выходной каталог. Если путь содержит пробелы, используйте кавычки. Каталог вывода по умолчанию — *\<диск >* : \Users\\ *\<имя_пользователя >* \аппдата\локал\виртуалсторе\програм Files (x86) \Microsoft Visual Studio 12,0\\.

**/баннер:** <em>файл</em><br/>
Указывает файл, содержащий пользовательский текст, который необходимо вставить в начало сообщения по умолчанию об авторских правах и версии winmdidl в верхней части сгенерированного IDL-файла. Если путь содержит пробелы, используйте кавычки.

**/utf8**<br/>
Файл будет отформатирован в кодировке UTF-8.

*винмдфиле*<br/>
Имя WINMD-файла для анализа. Если путь содержит пробелы, используйте кавычки.

## <a name="midlrt-command-line-arguments"></a>Аргументы командной строки midlrt

См. раздел [компоненты MIDLRT и среда выполнения Windows](/windows/win32/Midl/midlrt-and-windows-runtime-components).

## <a name="examples"></a>Примеры

В следующем примере показана работа команды winmdidl в командной строке Visual Studio x86. Она определяет выходную папку и файл, содержащий специальный текст баннера, который следует добавить в сгенерированный IDL-файл.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0>winmdidl /nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\Test_for_winmdidl\test_for_winmdidl.winmd"`

В следующем примере показан вывод в окно консоли результата работы команды winmdidl, который указывает, что операция выполнена успешно.

**Создание к:\усерс\гираффе\документс\\\ Test_for_winmdidl. idl**

Затем для созданного IDL-файла выполняется команда midlrt. Обратите внимание, что аргумент **metadata_dir** указывается после имени IDL-файла. Путь \WinMetadata\ является обязательным — это расположение для windows.winmd.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0> midlrt "c:\users\username\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"`

## <a name="remarks"></a>Примечания

Выходной файл операции winmdidl будет иметь то же имя, что и входной файл, но с расширением IDL.

При разработке компонента среды выполнения Windows, который будет доступен из WRL, можно указать в качестве действий после сборки запуск инструментов winmdidl.exe и midlrt.exe для создания IDL- и H-файлов при каждой сборке. Пример см. в разделе [вызов событий в компонентах среда выполнения Windows](/windows/uwp/winrt-components/raising-events-in-windows-runtime-components).
