---
title: Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR
ms.date: 11/04/2016
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ASSERTE
- ASSERTE
- _ASSERT_EXPR
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: d07fbe5de7afdc62f952727660447c5e4f0b78aa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232642"
---
# <a name="_assert-_asserte-_assert_expr-macros"></a>Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR

Вычисление выражения и создание отчета об отладке, если результат равен **false** (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Параметры

*булеанекспрессион*<br/>
Скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (true) или 0 (false).

*message*<br/>
Расширенная строка, отображаемая в составе отчета.

## <a name="remarks"></a>Примечания

Макросы **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** предоставляют приложению четкий и простой механизм для проверки допущений во время процесса отладки. Пользоваться ими очень удобно: их не нужно заключать в операторы `#ifdef` , чтобы они не вызывались в окончательной сборке приложения. Эта гибкость обеспечивается использованием макроса [_DEBUG](../../c-runtime-library/debug.md) . **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** доступны только в том случае, если **_DEBUG** определен во время компиляции. Если **_DEBUG** не определен, вызовы этих макросов удаляются во время предварительной обработки.

**_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** оценить свой аргумент *булеанекспрессион* и, когда результат равен **`false`** (0), они выводят диагностическое сообщение и вызывают [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) для создания отчета об отладке. Макрос **_ASSERT** выводит простое диагностическое сообщение, **_ASSERTE** содержит строковое представление выражения Failed в сообщении, а **_ASSERT_EXPR** включает строку *сообщения* в диагностическое сообщение. Эти макросы не выполняют никаких действий, если *булеанекспрессион* имеет ненулевое значение.

**_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** вызвать **_CrtDbgReportW**, в результате чего все выходные данные будут в расширенных символах. **_ASSERTE** правильно выводит символы Юникода в *булеанекспрессион* и **_ASSERT_EXPR** выводит символы Юникода в *сообщении*.

Так как макрос **_ASSERTE** задает выражение Failed, а **_ASSERT_EXPR** позволяет указать сообщение в созданном отчете, они позволяют пользователям определить проблему без обращения к исходному коду приложения. Однако недостаток заключается в том, что каждое *сообщение* , печатаемое **_ASSERT_EXPR** , и каждое выражение, вычисляемое **_ASSERTE** , включается в выходной файл (отладочная версия) приложения в виде строковой константы. Таким образом, если для **_ASSERT_EXPR** или **_ASSERTE**выполняется большое количество вызовов, эти выражения могут значительно увеличить размер выходного файла.

Если иное не задано с помощью функций [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) , сообщения отображаются во всплывающем диалоговом окне, что эквивалентно следующей настройке:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** создает отчет об отладке и определяет его назначение или назначения на основе текущего режима или режимов отчета, а также файла, определенного для **_CRT_ASSERTного** типа отчета. По умолчанию ошибки и сбои проверочных утверждений направляются в окно сообщений отладчика. Функции [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.

Если назначение является окном сообщения об отладке и пользователь нажимает кнопку **повторить** , **_CrtDbgReportW** возвращает значение 1, что приводит к тому, что макросы **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** запускают отладчик при включении JIT-отладки.

Дополнительные сведения о процессе формирования отчетов см. в описании функций [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) . Дополнительные сведения о разрешении сбоев проверочных утверждений и использовании этих макросов в качестве отладочных механизмов обработки ошибок см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).

Помимо макросов **_ASSERT** , макрос [Assert](assert-macro-assert-wassert.md) можно использовать для проверки логики программы. Этот макрос доступен и в отладочной, и в окончательной версиях библиотек. Для формирования отчетов об отладке также предусмотрены отладочные макросы [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) , однако они не вычисляют выражение. Макросы **_RPT** создают простой отчет. Макросы **_RPTF** включают исходный файл и номер строки, в которой был вызван макрос отчета в созданном отчете. Доступны версии этих макросов для расширенных символов (**_RPTW**, **_RPTFW**). Версии для расширенных символов идентичны версиям для узких символов, за исключением того, что для всех строковых параметров и вывода используются строки расширенных символов.

Хотя **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** являются макросами и доступны, включая \<crtdbg.h> , приложение должно связываться с отладочной версией библиотеки времени выполнения C, когда определен **_DEBUG** , так как эти макросы вызывают другие функции времени выполнения.

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT** **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>Пример

В этой программе выполняется вызов макросов **_ASSERT** и **_ASSERTE** для проверки условия `string1 == string2` . Если условие не выполняется, эти макросы выводят диагностическое сообщение. **_RPT** и **_RPTF** группа макросов также используется в этой программе в качестве альтернативы функции **printf** .

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>См. также статью

[Отладочные подпрограммы](../../c-runtime-library/debug-routines.md)<br/>
[Макрос assert, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
[Макросы _RPT, _RPTF, _RPTW, _RPTFW](rpt-rptf-rptw-rptfw-macros.md)<br/>
