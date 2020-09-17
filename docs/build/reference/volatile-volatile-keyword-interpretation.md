---
title: /volatile (интерпретация ключевого слова volatile)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 7c2c1cd477b424f56e66bd9246e7bde76ad06120
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223789"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (интерпретация ключевого слова volatile)

Указывает, как должно интерпретироваться ключевое слово [volatile](../../cpp/volatile-cpp.md) .

## <a name="syntax"></a>Синтаксис

> **/volatile:**{**ISO** | **MS**}

## <a name="arguments"></a>Аргументы

**/volatile: ISO**<br/>
Выбирается **`volatile`** определенная семантика в соответствии с языком C++, стандартом ISO. Семантика получения и освобождения не гарантируется при неизменяемых обращениях. Если компилятор обращается к ARM, это интерпретация по умолчанию **`volatile`** .

**/volatile: МС**<br/>
Выбирается Расширенная **`volatile`** семантика Майкрософт, которая добавляет гарантии порядка в память за пределами языка C++, используемого в стандарте ISO. Семантика получения и освобождения гарантирована при неизменяемых обращениях. Однако этот параметр также заставляет компилятор создавать барьеры аппаратной памяти, что может значительно увеличить нагрузку на ARM и другую слабую архитектуру упорядочивания памяти. Если компилятор предназначен для любой платформы, кроме ARM, это интерпретация по умолчанию **`volatile`** .

## <a name="remarks"></a>Примечания

Настоятельно рекомендуется использовать **/volatile: ISO** вместе с явными примитивами синхронизации и встроенными функциями компилятора при работе с памятью, которая совместно используется в потоках. Дополнительные сведения см. в разделе [volatile](../../cpp/volatile-cpp.md).

Если вы переносите существующий код или изменяете этот параметр в середине проекта, может быть полезно включить предупреждение [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) , чтобы определять местоположения кода, затрагиваемые разностью в семантике.

`#pragma`Для управления этим параметром нет эквивалента.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>Установка параметра компилятора/volatile в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. В поле **Дополнительные параметры** добавьте **/volatile: ISO** или **/volatile: MS** , а затем нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также статью

[volatile](../../cpp/volatile-cpp.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
