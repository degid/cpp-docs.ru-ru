---
title: Практическое руководство. Переход на -clr
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 0c21fe585049ebce6383c5d8f673704e7362cd72
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225700"
---
# <a name="how-to-migrate-to-clr"></a>Практическое руководство. Переход на /clr

В этом разделе обсуждаются проблемы, возникающие при компиляции машинного кода с **параметром/CLR** (Дополнительные сведения см. в разделе [/CLR (компиляция среды CLR)](../build/reference/clr-common-language-runtime-compilation.md) . **/CLR** позволяет машинному коду c++ вызываться и вызываться из сборок .NET в дополнение к другому машинному коду c++. Дополнительные сведения о преимуществах компиляции с **параметром/CLR**см. в разделе [смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md) и [взаимодействие машинного кода и взаимодействия с .NET](../dotnet/native-and-dotnet-interoperability.md) .

## <a name="known-issues-compiling-library-projects-with-clr"></a>Известные проблемы при компиляции проектов библиотек с помощью/CLR

Visual Studio содержит некоторые известные проблемы при компиляции проектов библиотек с помощью **/CLR**:

- Код может запрашивать типы во время выполнения с помощью [крунтимекласс:: фромнаме](../mfc/reference/cruntimeclass-structure.md#fromname). Однако если тип находится в коде MSIL. dll (скомпилированном с **параметром/CLR**), вызов метода `FromName` может завершиться ошибкой, если он происходит перед выполнением статических конструкторов в Managed. dll (эта проблема не возникает, если вызов фромнаме происходит после выполнения кода в Managed. dll). Чтобы обойти эту проблему, можно принудительно построить управляемый статический конструктор, определив функцию в Managed. dll, экспортировав ее и вызывая из собственного приложения MFC. Например:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Компиляция с помощью Visual C++

Прежде чем использовать **/CLR** для любого модуля в проекте, сначала Скомпилируйте и свяжите собственный проект с Visual Studio 2010.

Следующие шаги следуют по порядку, чтобы предоставить самый простой путь к компиляции **/CLR** . Важно компилировать и запускать проект после каждого из этих шагов.

### <a name="versions-prior-to-visual-studio-2003"></a>Версии до Visual Studio 2003

При обновлении до Visual Studio 2010 с версии до Visual Studio 2003 могут возникать ошибки компилятора, связанные с расширенным стандартом соответствия C++ в Visual Studio 2003

### <a name="upgrading-from-visual-studio-2003"></a>Обновление с Visual Studio 2003

Проекты, созданные ранее с помощью Visual Studio 2003, также должны быть скомпилированы без **/CLR** , так как Visual Studio теперь повысила соответствие требованиям ANSI/ISO и некоторые критические изменения. Изменение, которое, скорее всего, потребует больше внимания, — [функции безопасности в CRT](../c-runtime-library/security-features-in-the-crt.md). Код, использующий CRT, скорее всего, создает предупреждения об устаревании. Эти предупреждения можно подавлять, но переход на новые [версии функций CRT с повышенной безопасностью](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) является предпочтительным, так как они обеспечивают лучшую безопасность и могут обнаружить проблемы безопасности в коде.

### <a name="upgrading-from-managed-extensions-for-c"></a>Обновление с управляемые расширения для C++

Начиная с Visual Studio 2005 код, написанный с управляемые расширения для C++, не будет компилироваться в **/CLR**.

## <a name="convert-c-code-to-c"></a>Преобразование кода C в C++

Хотя Visual Studio будет компилировать файлы C, необходимо преобразовать их в C++ для компиляции **/CLR** . Реальное имя файла изменять не нужно; можно использовать параметр **/TP** (см. раздел [/TC,/TP,/TC,/TP (укажите тип исходного файла)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) Обратите внимание, что хотя файлы исходного кода C++ необходимы для **/CLR**, нет необходимости рефакторинга кода для использования объектно-ориентированных парадигм.

В коде C, скорее всего, потребуется внести изменения при компиляции в виде файла C++. Правила безопасности типов C++ строгие, поэтому преобразования типов должны быть сделаны явными с приведением. Например, функция malloc возвращает указатель void, но может быть назначен указателю на любой тип в C с приведением:

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

Указатели функций также строго типизированы в C++, поэтому следующий код на языке C требует изменения. В C++ лучше создать объект **`typedef`** , который определяет тип указателя функции, а затем использовать этот тип для приведения указателей функций:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

Кроме того, C++ требует, чтобы функции либо были созданы прототипом, либо были полностью определены до того, как на них можно будет ссылаться или вызывать.

Идентификаторы, используемые в коде C, которые должны быть ключевыми словами в C++ (например,,,,,, **`virtual`** **`new`** **`delete`** **`bool`** **`true`** **`false`** и т. д.), необходимо переименовать. Обычно это можно сделать с помощью простых операций поиска и замены.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>Перенастройка параметров проекта

После компиляции и запуска проекта в Visual Studio 2010 следует создать новые конфигурации проекта для **/CLR** , а не изменять конфигурации по умолчанию. **параметр/CLR** несовместим с некоторыми параметрами компилятора, и создание отдельных конфигураций позволяет построить проект как машинный или управляемый. Если в диалоговом окне страницы свойств выбран **параметр/CLR** , то параметры проекта, несовместимые с **/CLR** , отключены (и отключенные параметры не восстанавливаются автоматически, если **параметр/CLR** впоследствии не выбран).

### <a name="create-new-project-configurations"></a>Создание новых конфигураций проектов

**Build**Для создания конфигурации проекта на основе существующих параметров проекта можно использовать параметр **Копировать параметры из** **диалогового окна "Создание конфигурации проекта"** (сборка  >  **Configuration Manager**  >  **Активная конфигурация решения**  >  **New**). Сделайте это один раз для конфигурации отладки и для конфигурации выпуска. Последующие изменения можно применять только к конфигурациям **/CLR** , при этом исходные конфигурации проекта остаются без изменений.

Для проектов, использующих настраиваемые правила сборки, может потребоваться дополнительное внимание.

Этот шаг имеет различные последствия для проектов, использующих файлы Makefile. В этом случае можно настроить отдельную сборку-цель или создать версию, относящуюся к компиляции с **параметром/CLR** , из копии исходного файла.

### <a name="change-project-settings"></a>Изменить параметры проекта

**параметр/CLR** можно выбрать в среде разработки, следуя инструкциям в разделе [/CLR (компиляция общеязыковой среды выполнения)](../build/reference/clr-common-language-runtime-compilation.md). Как упоминалось ранее, этот шаг автоматически отключает конфликтующие параметры проекта.

> [!NOTE]
> При обновлении управляемой библиотеки или проекта веб-службы из Visual Studio 2003 параметр компилятора **/Zl** будет добавлен на страницу свойств **Командная строка** . Это вызовет ошибку LNK2001. Чтобы устранить проблему, удалите параметр **/Zl** со страницы свойств **командной строки** . Дополнительные сведения см. в разделе [/Zl (опустить имя библиотеки по умолчанию)](../build/reference/zl-omit-default-library-name.md) и [Задайте свойства компилятора и сборки](../build/working-with-project-properties.md) . Или добавьте msvcrt. lib и msvcmrt. lib в свойство **Дополнительные зависимости** компоновщика.

Для проектов, созданных с помощью файлов makefile, несовместимые параметры компилятора должны быть отключены вручную после добавления **/CLR** . Сведения о параметрах компилятора, несовместимых с **/CLR**, см. в разделе[ограничения//CLR](../build/reference/clr-restrictions.md) .

### <a name="precompiled-headers"></a>Предкомпилированные заголовочные файлы

В **параметре/CLR**поддерживаются предкомпилированные заголовки. Однако если скомпилировать только некоторые файлы CPP с параметром **/CLR** (компиляция остальных файлов как машинного), некоторые изменения будут необходимы, так как предкомпилированные заголовки, созданные с помощью **/CLR** , несовместимы с параметрами, созданными без **/CLR**. Такая несовместимость обусловлена тем, что **/CLR** создает и требует метаданных. Поэтому модули, скомпилированные с помощью **/CLR** , не могут использовать предкомпилированные заголовки, которые не включают метаданные, а модули без **/CLR** не могут использовать файлы предкомпилированных заголовков, которые содержат метаданные.

Самый простой способ скомпилировать проект, в **котором скомпилированы некоторые модули, —** это полностью отключить предкомпилированные заголовки. (В диалоговом окне страницы свойств проекта откройте узел C/C++ и выберите предварительно скомпилированные заголовки. Затем измените значение свойства создать или использовать предварительно скомпилированные заголовки на «не использовать предкомпилированные заголовки».)

Однако, особенно для больших проектов, предкомпилированные заголовки обеспечивают гораздо более высокую скорость компиляции, поэтому отключение этой функции нежелательно. В этом случае лучше настроить файлы **/CLR** и не **/CLR** для использования отдельных предкомпилированных заголовков. Это можно сделать за один шаг, выбрав несколько модулей для компиляции **/CLR** с помощью **Обозреватель решений**, щелкнув группу правой кнопкой мыши и выбрав пункт Свойства. Затем измените оба свойства файла заголовка создать/использовать PCH-файл и предкомпилированный файл заголовка, чтобы использовать другое имя заголовочного файла и PCH-файл соответственно.

## <a name="fixing-errors"></a>Устранение ошибок

Компиляция с параметром **/CLR** может привести к ошибкам компилятора, компоновщика или среды выполнения. В этом разделе обсуждаются наиболее распространенные проблемы.

### <a name="metadata-merge"></a>Слияние метаданных

Различные версии типов данных могут привести к сбою компоновщика из-за того, что метаданные, созданные для двух типов, не совпадают. (Обычно это происходит, когда члены типа определяются условно, но условия не одинаковы для всех CPP-файлов, использующих этот тип.) В этом случае компоновщик завершается ошибкой, сообщая только имя символа и имя второго OBJ-файла, в котором был определен тип. Часто бывает полезно повернуть порядок, в котором OBJ-файлы отправляются компоновщику для обнаружения расположения другой версии типа данных.

### <a name="loader-lock-deadlock"></a>Взаимоблокировка загрузчика

Может произойти блокировка блокировки загрузчика, но она детерминирована и обнаружена и сообщается во время выполнения. Подробные сведения, рекомендации и решения см. в разделе [Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md) .

### <a name="data-exports"></a>Экспорт данных

Экспорт данных библиотеки DLL является подверженным ошибкам и не рекомендуется. Это обусловлено тем, что не гарантируется Инициализация раздела данных библиотеки DLL до тех пор, пока не будет выполнена какая-либо управляемая часть библиотеки DLL. Ссылочные метаданные с помощью [директивы #using](../preprocessor/hash-using-directive-cpp.md).

### <a name="type-visibility"></a>Видимость типов

Собственные типы являются частными по умолчанию. Это может привести к тому, что собственный тип не будет виден за пределами библиотеки DLL. Устраните эту ошибку, добавив **`public`** к этим типам.

### <a name="floating-point-and-alignment-issues"></a>Проблемы с плавающей запятой и выравниванием

`__controlfp`не поддерживается в среде CLR (Дополнительные сведения см. в разделе [_control87, _controlfp, \_ _control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) ). CLR также не учитывает [согласованность](../cpp/align-cpp.md).

### <a name="com-initialization"></a>Инициализация COM

Среда CLR автоматически инициализирует COM при инициализации модуля (когда инициализация COM выполняется автоматически, как и MTA). В результате явная инициализация COM дает коды возврата, указывающие, что COM уже инициализирован. Попытка явно инициализировать модель COM с одной потоковой моделью, когда среда CLR уже инициализировала COM в другую потоковую модель, может привести к сбою приложения.

Среда CLR по умолчанию запускает COM как MTA; чтобы изменить этот параметр, используйте [/CLRTHREADATTRIBUTE (задать атрибут потока CLR)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) .

### <a name="performance-issues"></a>Проблемы с производительностью

Производительность может быть снижена, когда собственные методы C++, созданные в MSIL, вызываются косвенно (вызовы виртуальных функций или использование указателей функций). Дополнительные сведения см. в разделе [Двойное преобразователь](../dotnet/double-thunking-cpp.md).

При переходе от Native к MSIL вы заметите увеличение размера рабочего множества. Это обусловлено тем, что среда CLR предоставляет множество функций, обеспечивающих правильную работу программ. Если приложение **/CLR** выполняется неправильно, может потребоваться включить C4793 (отключено по умолчанию). Дополнительные сведения см. в разделе [Предупреждение компилятора (уровень 1 и 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) .

### <a name="program-crashes-on-shutdown"></a>Сбой программы при завершении работы

В некоторых случаях среда CLR может завершить работу до завершения выполнения управляемого кода. `std::set_terminate` `SIGTERM` Это может быть вызвано использованием и. Дополнительные сведения см. в разделе [сигнальные константы](../c-runtime-library/signal-constants.md) и [set_terminate](../c-runtime-library/abnormal-termination.md) .

## <a name="using-new-visual-c-features"></a>Использование новых функций Visual C++

После компиляции, ссылок и выполнения приложения можно приступить к использованию функций .NET в любом модуле, скомпилированном с **параметром/CLR**. Дополнительные сведения см. в статье [Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md).

Дополнительные сведения о программировании .NET в Visual C++ см. в следующих статьях:

- [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [Взаимодействие машинного кода и .NET](../dotnet/native-and-dotnet-interoperability.md)

- [Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>См. также статью

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)
