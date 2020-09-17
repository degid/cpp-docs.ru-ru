---
title: /MD,-MT,-LD (использование библиотеки времени выполнения)
ms.date: 07/17/2019
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
ms.openlocfilehash: a66677ebbef984e9a4c8190f184ca3a9126a7b83
ms.sourcegitcommit: d4da3693f83a24f840e320e35c24a4a07cae68e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/18/2020
ms.locfileid: "83550762"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (использование библиотеки времени выполнения)

Указывает, является ли многопоточный модуль библиотекой DLL, и задает версию библиотеки времени выполнения для отладки или выпуска.

## <a name="syntax"></a>Синтаксис

```
/MD[d]
/MT[d]
/LD[d]
```

## <a name="remarks"></a>Примечания

|Параметр|Описание|
|------------|-----------------|
|**/MD**|Предписывает приложению использование специальной многопоточной и зависящей от DLL версии библиотеки времени выполнения. Определяет параметры `_MT` и `_DLL` и предписывает компилятору размещение имени библиотеки MSVCRT.lib в OBJ-файле.<br /><br /> Приложения, компилируемые с этим параметром, статически компонуются с библиотекой MSVCRT.lib. Эта библиотека содержит слой кода, позволяющий компоновщику разрешить внешние ссылки. Фактический рабочий код содержится в МСВКР*versionNumber*. DLL, которая должна быть доступна во время выполнения для приложений, связанных с MSVCRT. lib.|
|**/MDd**|Определяет параметры `_DEBUG`, `_MT` и `_DLL` и предписывает приложению использование отладочной многопоточной и зависящей от DLL версии библиотеки времени выполнения. Также предписывает компилятору размещение имени библиотеки MSVCRTD.lib в .obj-файле.|
|**/MT**|Предписывает приложению использовать многопоточную статическую версию библиотеки времени выполнения. Создает определение `_MT` и указывает компилятору на необходимость размещения имени библиотеки LIBCMT.lib в файле OBJ, чтобы компоновщик использовал библиотеку LIBCMT.lib для разрешения внешних символов.|
|**/MTd**|Создает определения `_DEBUG` и `_MT`. Этот параметр также предписывает компилятору размещение имени библиотеки LIBCMTD.lib в .obj-файле, чтобы компоновщик использовал LIBCMTD.lib для разрешения внешних символов.|
|**/LD**|Создает библиотеку DLL.<br /><br /> Передает параметр **/DLL** компоновщику. Компоновщик будет искать функцию `DllMain`; тем не менее, она не является обязательной. Если функция `DllMain` отсутствует, компоновщик вставляет функцию `DllMain`, возвращающую значение TRUE.<br /><br /> Компонует код запуска библиотеки DLL.<br /><br /> Создает библиотеку импорта (LIB), если файл экспорта (EXP) не указан в командной строке. Библиотека импорта связывается с приложениями, которые вызывают библиотеку DLL.<br /><br /> Интерпретирует [/Fe (имя EXE-файла)](fe-name-exe-file.md) как ИМЕНОВАНИЕ библиотеки DLL, а не exe-файла. По умолчанию имя программы преобразуется в *basename*. dll вместо *basename*. exe.<br /><br /> Подразумевает использование параметра **/MT** , если явно не указано **/MD**.|
|**/LDd**|Создает отладочную библиотеку DLL. Создает определения `_MT` и `_DEBUG`.|

Дополнительные сведения о библиотеках времени выполнения C и о том, какие библиотеки используются при компиляции с параметром [/CLR (компиляция среды CLR)](clr-common-language-runtime-compilation.md), см. в разделе [функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).

Все модули, передаваемые в данный вызов компоновщика, должны быть скомпилированы с одним и тем же параметром компилятора библиотеки времени выполнения (**/MD**, **/MT**, **/LD**).

Дополнительные сведения об использовании отладочных версий библиотек среды выполнения см. в разделе [Справочник по библиотеке времени выполнения C](../../c-runtime-library/c-run-time-library-reference.md).

Дополнительные сведения о библиотеках DLL см. [в статье Создание библиотек DLL C/C++ в Visual Studio](../dlls-in-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства "**  >  Создание кода**C/C++**"  >  **Code Generation** .

1. Измените свойство **Библиотека времени выполнения** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
