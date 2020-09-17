---
title: /openmp (Включить поддержку OpenMP)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: d3454650bfaaacd756e5cfc73df056441a39f5ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336197"
---
# <a name="openmp-enable-openmp-support"></a>/openmp (Включить поддержку OpenMP)

Вызывает обработку компилятора [`#pragma omp`](../../preprocessor/omp.md) директив в поддержку OpenMP.

## <a name="syntax"></a>Синтаксис

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__экспериментальный__

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>Примечания

`#pragma omp`используется для указания [Директив и](../../parallel/openmp/reference/openmp-directives.md) [оговорок.](../../parallel/openmp/reference/openmp-clauses.md) Если **/openmp** не указан в компиляции, компилятор игнорирует положения и директивы OpenMP. Звонки [OpenMP Function](../../parallel/openmp/reference/openmp-functions.md) обрабатываются компилятором, даже если **/openmp** не указан.

::: moniker range=">= vs-2019"

В настоящее время компилятор СЗ поддерживает стандарт OpenMP 2.0. Тем не менее, Visual Studio 2019 также теперь предлагает функциональность SIMD. Чтобы использовать SIMD, компилировать с помощью **/openmp:экспериментальный** вариант. Эта опция позволяет как обычным функциям OpenMP, так и дополнительным функциям OpenMP SIMD, недоступным при использовании коммутатора **/openmp.**

::: moniker-end

Приложения, компилированные с помощью **обоих /openmp** и **/clr,** могут быть запущены только в процессе одного домена приложения. Несколько доменов приложений не поддерживаются. То есть, когда конструктор`.cctor`модуля () запущен, он обнаруживает, если процесс компилируется с помощью **/openmp**, и если приложение загружается в непо умолчанию время выполнения. Для получения дополнительной информации [см. appdomain](../../cpp/appdomain.md) [, /clr (Общий язык Runtime Compilation)](clr-common-language-runtime-compilation.md), и [инициализация смешанных собраний](../../dotnet/initialization-of-mixed-assemblies.md).

Если вы попытаетесь загрузить приложение, компилированное с помощью **как /openmp** и **/clr,** в домен приложения без дефолта, <xref:System.TypeInitializationException> за пределами отладчика выбрасывается исключение, и `OpenMPWithMultipleAppdomainsException` в отладчик выбрасывается исключение.

Эти исключения также могут быть подняты в следующих ситуациях:

- Если ваше приложение компилируется с помощью **/clr,** но не **/openmp,** и загружается в домен приложения без дефолта, где процесс включает в себя приложение, составленное с помощью **/openmp.**

- Если вы передаете ваше **приложение /clr** утилите, например [regasm.exe,](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)которая загружает свои целевые сборки в домен приложения без дефолта.

Безопасность доступа к коду общего времени выполнения языка не работает в регионах OpenMP. Если вы применяете атрибут безопасности доступа кода CLR за пределами параллельной области, он не будет действовать в параллельной области.

Корпорация Майкрософт не рекомендует писать **/openmp** приложения, которые позволяют частично доверенных абонентов. Не используйте <xref:System.Security.AllowPartiallyTrustedCallersAttribute>или какие-либо атрибуты безопасности доступа к коду CLR.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Расширьте страницу свойств **configuration Properties** > **C/C'.** > **Язык.**

1. Измените свойство **поддержки OpenMP.**

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Пример

Следующий пример показывает некоторые из эффектов запуска пула потоков по сравнению с использованием пула потоков после его начала. Предполагая, что x64, одноядро, двойной процессор, пул потоков занимает около 16 мс, чтобы запустить. После этого, есть небольшая дополнительная плата для потока пула.

При компилировании с помощью **/openmp,** второй вызов test2 никогда не выполняется дольше, чем если вы компилируете с помощью **/openmp-**, так как нет запуска пула потоков. На миллион итераций, **/ openmp** версия быстрее, чем **/ openmp-версия** для второго вызова для test2. На 25 итераций, как **/ openmp-** и **/ Openmp** версии регистрируются меньше, чем часы детализации.

Если у вас есть только один цикл в приложении, и он работает менее чем за 15 мс (с поправкой на приблизительные накладные расходы на вашей машине), **/ openmp** не может быть целесообразным. Если он выше, вы можете рассмотреть возможность использования **/openmp**.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md) \
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md) \
[OpenMP в MSVC](../../parallel/openmp/openmp-in-visual-cpp.md)
