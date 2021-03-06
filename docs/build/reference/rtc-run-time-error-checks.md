---
title: /RTC (проверки ошибок во время выполнения)
ms.date: 07/31/2020
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
ms.openlocfilehash: eefec0956bebe9f72324f3cbc61fccbc5e2e24d7
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520542"
---
# <a name="rtc-run-time-error-checks"></a>`/RTC`(Проверки ошибок во время выполнения)

Используется для включения и отключения функции проверки ошибок во время выполнения в сочетании с директивой pragma [runtime_checks](../../preprocessor/runtime-checks.md) .

## <a name="syntax"></a>Синтаксис

> **`/RTC1`**\
> **`/RTCc`**\
> **`/RTCs`**\
> **`/RTCu`**

## <a name="arguments"></a>Аргументы

**`/RTC1`**<br/>
Эквивалентно **`/RTCsu`** .

**`/RTCc`**<br/>
Сообщает, когда значение присвоено меньшему типу данных и приводит к потери данных. Например, он возвращает значение, если **`short`** тип `0x0101` присваивается переменной типа **`char`** .

Этот параметр может сообщать о ситуациях, в которых предполагается усечение. Например, если требуется, чтобы первые 8 битов **`int`** возвращались как **`char`** . Так как **`/RTCc`** вызывает ошибку во время выполнения, если назначение вызывает потери данных, сначала необходимо скрыть сведения, чтобы избежать ошибки во время выполнения. Пример:

```C
#include <crtdbg.h>

char get8bits(unsigned value, int position) {
   _ASSERT(position < 32);
   return (char)(value >> position);
   // Try the following line instead:
   // return (char)((value >> position) & 0xff);
}

int main() {
   get8bits(12341235,3);
}
```

Поскольку **`/RTCc`** отклоняет код, который соответствует стандарту, он не поддерживается стандартной библиотекой C++. Код, использующий **`/RTCc`** и стандартную библиотеку C++, может вызвать ошибку компилятора [C1189](../../error-messages/compiler-errors-1/fatal-error-c1189.md). Вы можете определить, чтобы не выводить `_ALLOW_RTCc_IN_STL` предупреждение и использовать **`/RTCc`** параметр.

**`/RTCs`**<br/>
Включает проверку ошибок во время выполнения кадра стека следующим образом.

- Инициализация локальных переменных для ненулевого значения. Этот параметр позволяет выявить ошибки, которые не отображаются при работе в режиме отладки. Существует большая вероятность того, что переменные стека по-прежнему имеют нулевое значение в отладочной сборке по сравнению с построением выпуска. Это обусловлено оптимизацией компилятором переменных стека в сборке выпуска. Когда программа использует область своего стека, компилятор никогда не сбрасывает его в 0. Это означает, что все неинициализированные переменные стека, которые применяют одну и ту же область стека позже, могут возвращать значения, оставшиеся раньше использования этой памяти стека.

- Обнаружение перезапусков и неполных запусков локальных переменных, таких как массивы. **`/RTCs`** не обнаруживает переполнения при доступе к памяти, полученной в результате заполнения компилятора в структуре. Заполнение может произойти с помощью [`align`](../../cpp/align-cpp.md) , [ `/Zp` (выравнивание членов структуры)](zp-struct-member-alignment.md)или [`pack`](../../preprocessor/pack.md) , или, если упорядочить элементы структуры таким образом, чтобы требовать от компилятора добавления заполнения.

- Проверка указателя стека, которая обнаруживает повреждение указателя стека. Повреждение указателя стека может быть вызвано несоответствием соглашения о вызовах. Например, с помощью указателя функции вы вызываете функцию в библиотеке DLL, которая экспортируется как, [`__stdcall`](../../cpp/stdcall.md) но указатель на функцию будет объявлен как [`__cdecl`](../../cpp/cdecl.md) .

**`/RTCu`**<br/>
Сообщает, когда переменная используется без инициализации. Например, инструкция, создающая предупреждение C4701, может также формировать ошибку времени выполнения в **`/RTCu`** . Любая инструкция, создающая [Предупреждение компилятора (уровень 1 и уровень 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) , создает ошибку времени выполнения в **`/RTCu`** .

Однако рассмотрим следующий фрагмент кода:

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

Если переменная могла быть инициализирована, она не сообщается во время выполнения **`/RTCu`** . Например, после присвоения псевдонима переменной через указатель компилятор не будет фиксировать переменную и отчет неинициализированные использования. По сути, можно инициализировать переменную, используя ее адрес. **`&`** В этом случае оператор работает как оператор присваивания.

## <a name="remarks"></a>Примечания

Проверки ошибок во время выполнения — это способ поиска проблем в выполняемом коде; Дополнительные сведения см. [в разделе инструкции. Использование проверок во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks).

В командной строке можно указать несколько **`/RTC`** параметров. Аргументы параметра могут быть объединены; Например, **`/RTCcu`** имеет то же значение, что и **`/RTCc /RTCu`** .

Если вы компилируете программу из командной строки с помощью любого из **`/RTC`** параметров компилятора, все инструкции директивы pragma [`optimize`](../../preprocessor/optimize.md) в коде автоматически завершаются ошибкой. Это обусловлено тем, что проверки ошибок во время выполнения не являются допустимыми в сборке выпуска (оптимизированной).

Используется **`/RTC`** для сборок разработки; Не используйте **`/RTC`** для сборки выпуска. **`/RTC`** не может использоваться с оптимизацией компилятора ([ `/O` Параметры (оптимизация кода)](o-options-optimize-code.md)). Образ программы, созданный с помощью **`/RTC`** , немного больше и немного медленнее, чем образ, созданный с помощью **`/Od`** (до 5% медленнее, чем **`/Od`** Сборка).

`__MSVC_RUNTIME_CHECKS`Директива препроцессора будет определена при использовании любого **`/RTC`** параметра или [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства "**  >  **Создание кода** **C/C++**".  

1. Измените одно или оба из следующих свойств: **Обычная проверка времени выполнения** или **Проверка типа меньшего размера**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Практическое руководство. Проверки времени выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks)
