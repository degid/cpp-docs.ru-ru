---
title: /UTF-8 (установка исходных и исполняемых наборов символов UTF-8в)
ms.date: 04/26/2020
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
no-loc:
- UTF
- UTF-8
- UTF-16
ms.openlocfilehash: c98a30b0ec4b36b8bd87fb0956d9382751975cfd
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168869"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-opno-locutf-8"></a>`/utf-8`(Задайте для UTF-8исходных и исполняемых наборов символов значение).

Задает как исходную кодировку, так и кодировку выполнения UTF-8в виде.

## <a name="syntax"></a>Синтаксис

> **`/utf-8`**

## <a name="remarks"></a>Примечания

С помощью **`/utf-8`** параметра можно указать как кодировку исходного кода, так и кодировку выполнения, используя UTF-8. Он эквивалентен указанию **`/source-charset:utf-8 /execution-charset:utf-8`** в командной строке. Любой из этих параметров также включает **`/validate-charset`** параметр по умолчанию. Список поддерживаемых идентификаторов кодовых страниц и имен наборов символов см. в разделе [идентификаторы кодовых страниц](/windows/win32/Intl/code-page-identifiers).

По умолчанию Visual Studio обнаруживает метку порядка следования байтов, чтобы определить, имеет ли исходный файл формат в кодировке Юникод, например UTF-16 или. UTF-8 Если метка порядка байтов не найдена, предполагается, что исходный файл кодируется с помощью кодовой страницы текущего пользователя, если не указана кодовая страница с помощью **`/utf-8`** или **`/source-charset`** параметра. Visual Studio позволяет сохранить исходный код C++ с помощью любой из нескольких кодировок символов. Сведения о кодировках исходного кода и выполнения см. в разделе [наборы символов](../../cpp/character-sets.md) в документации по языку.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Установка параметра в Visual Studio или программным способом

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства** > конфигурации**C/C++** > **Командная строка** .

1. В окне **Дополнительные параметры**добавьте **`/utf-8`** параметр, чтобы указать предпочтительную кодировку.

1. Выберите **ОК** для сохранения внесенных изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[/Execution-charset (Задание кодировки выполнения)](execution-charset-set-execution-character-set.md)<br/>
[указаны кодировки/Source-charset (задание исходной кодировки)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (проверка совместимости символов)](validate-charset-validate-for-compatible-characters.md)
