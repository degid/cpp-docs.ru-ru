---
title: Поддержка многобайтовой кодировки MBCS в Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
ms.openlocfilehash: 404fcee5e48d8db28e56a005f24f8cac5892240e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375791"
---
# <a name="mbcs-support-in-visual-c"></a>Поддержка многобайтовой кодировки MBCS в Visual C++

При запуске на версии Windows с поддержкой MBCS система разработки Visual C''а (включая интегрированный редактор исходного кода, отладчик и инструменты командной строки) включается с поддержкой MBCS, за исключением окна памяти.

Окно памяти не интерпретирует байты данных как символы MBCS, даже если они могут интерпретировать их как символы ANSI или Unicode. Символы ANSI всегда 1 байт по размеру, а символы Unicode - 2 байта по размеру. С MBCS символы могут быть размером 1 или 2 байта, и их интерпретация зависит от того, какая страница кода используется. Из-за этого в окне памяти трудно надежно отображать символы MBCS. Окно памяти не может знать, какой байт является началом персонажа. Разработчик может просматривать значения байта в окне памяти и искать значение в таблицах для определения представления символов. Это возможно, поскольку разработчик знает начальный адрес строки на основе исходного кода.

Визуальный C' принимает символы с двойным байтом, где это уместно. Это включает имена путей и имена файлов в диалоговых коробках и текстовые записи в редакторе ресурсов Visual C '(например, статический текст в редакторе диалогов и статические текстовые записи в редакторе значка). Кроме того, препроцессор признает некоторые директивы с двойным байтом `#include` - например, имена `code_seg` `data_seg` файлов в заявлениях, а также в качестве аргументов в пользу прагмей. В редакторе исходного кода принимаются двасимволы в комментариях и буквах строки, хотя и не в элементах языка C/C е (например, переменные имена).

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>Поддержка редактора метода ввода (IME)

Приложения, написанные для восточноазиатских рынков, которые используют MBCS (например, Япония), обычно поддерживают Windows IME для ввода как одно-, так и двойного байт-символа. Среда разработки Visual C' содержит полную поддержку IME.

Японские клавиатуры напрямую не поддерживают персонажей Kanji. IME преобразует фонетическую строку, введенную в одном из других японских алфавитов (Ромаджи, Катакана, или Хирагана) в возможные представления Кандзи. Если есть двусмысленность, вы можете выбрать из нескольких альтернатив. Когда вы выбрали предполагаемый символ Kanji, IME передает два `WM_CHAR` сообщения в контролирующий приложение.

IME, активированный комбинацией\` ключов АЛТЗ, отображается как набор кнопок (индикатор) и окно преобразования. Приложение позиционирует окно в точке вставки текста. Приложение должно `WM_MOVE` обрабатывать `WM_SIZE` и сообщения, перемещая окно преобразования в соответствие с новым местоположением или размером целевого окна.

Если вы хотите, чтобы пользователи вашего приложения имели возможность вводить символы Kanji, приложение должно обрабатывать сообщения Windows IME. Для получения дополнительной информации [Input Method Manager](/windows/win32/intl/input-method-manager)о программировании IME см.

## <a name="visual-c-debugger"></a>Визуальный СЕ Дебудгер

Отладка Visual C''предоставляет возможность устанавливать точки разрыва на сообщениях IME. Кроме того, в окне Памяти могут отображаться символы с двойным байтом.

## <a name="command-line-tools"></a>Программы командной строки

Инструменты командной строки Visual C', включая компилятор, NMAKE и компилятор ресурсов (RC. EXE), с поддержкой MBCS. Можно использовать опцию компилятора ресурсов /c для изменения страницы кода по умолчанию при компиляции ресурсов приложения.

Чтобы изменить локаль по умолчанию во время компилирования исходного кода, используйте [#pragma setlocale.](../preprocessor/setlocale.md)

## <a name="graphical-tools"></a>Графические инструменты

Инструменты на базе Windows, такие как «Шпион» и инструменты редактирования ресурсов, полностью поддерживают строки IME.

## <a name="see-also"></a>См. также раздел

[Поддержка многобайтовых кодировок](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)
