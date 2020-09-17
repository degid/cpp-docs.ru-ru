---
title: Справочник по XDCMake
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: 9970470d1feb471f9e0b8c9284a08337dac7ef0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335859"
---
# <a name="xdcmake-reference"></a>Справочник по XDCMake

xdcmake.exe — это программа, которая компилирует XDC-файлы в XML-файл. Файл .xdc создается компилятором MSVC для каждого исходного кода, когда исходный код компилируется с [/doc](doc-process-documentation-comments-c-cpp.md) и когда файл исходного кода содержит комментарии к документации, отмеченные тегами XML.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Использование xdcmake.exe в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **Свойства конфигурации**.

1. Выберите страницу свойств **Комментарии XML-документа**.

> [!NOTE]
> Параметры xdcmake.exe в командной строке отличаются от параметров, доступных при использовании xdcmake.exe из среды разработки (страницы свойств). Сведения об использовании xdcmake.exe в среде разработки см. в разделе [Страницы свойств средства создания XML-документов](xml-document-generator-tool-property-pages.md).

## <a name="syntax"></a>Синтаксис

xdcmake `input_filename options`

## <a name="parameters"></a>Параметры

*input_filename*<br/>
Имя для XDC-файлов, используемых в качестве входных для xdcmake.exe. Укажите один или несколько XDC-файлов или значение *.xdc, чтобы использовать все XDC-файлы в текущем каталоге.

*Параметры*<br/>
От нуля до нескольких следующих параметров:

|Параметр|Описание|
|------------|-----------------|
|/?, /help|Отображает справку для xdcmake.exe.|
|/assembly:*имя_файла*|Позволяет задать значение тега \<assembly> в XML-файле.  По умолчанию значение тега \<assembly> совпадает с именем XML-файла.|
|/nologo|Позволяет запретить вывод сообщения об авторских правах.|
|/out:*имя_файла*|Позволяет указать имя XML-файла.  По умолчанию именем XML-файла является имя первого XDC-файла, обработанного xdcmake.exe.|

## <a name="remarks"></a>Примечания

Visual Studio вызовет xdcmake.exe автоматически при сборке проекта. Кроме того, xdcmake.exe можно вызвать из командной строки.

Дополнительные сведения о добавлении комментариев документации в файлы исходного кода см. в разделе [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments-visual-cpp.md).

## <a name="see-also"></a>См. также раздел

[Документация XML](xml-documentation-visual-cpp.md)
