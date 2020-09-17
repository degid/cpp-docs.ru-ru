---
title: Предупреждение компилятора (уровень 3) C4996
description: Объясняет, почему происходит предупреждение компилятора C4996, и описывает, что делать с ним делать.
ms.date: 07/09/2020
f1_keywords:
- C4996
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
ms.openlocfilehash: 9f834c548b2a6b291304bdbf0082659577bfd694
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180985"
---
# <a name="compiler-warning-level-3-c4996"></a>Предупреждение компилятора (уровень 3) C4996

В коде используется функция, член класса, переменная или typedef, помеченные как *устаревшие*. Символы являются устаревшими с помощью [`__declspec(deprecated)`](../../cpp/deprecated-cpp.md) модификатора или атрибута c++ 14 [`[[deprecated]]`](../../cpp/attributes.md) . Фактическое предупреждающее сообщение C4996 указывается `deprecated` модификатором или атрибутом объявления.

> [!IMPORTANT]
> Это предупреждение всегда является преднамеренным сообщением от автора файла заголовка, объявляющего символ. Не используйте нерекомендуемый символ, не зная последствий.

## <a name="remarks"></a>Примечания

Многие функции, функции элементов, функции шаблонов и глобальные переменные в библиотеках Visual Studio являются *устаревшими*. Некоторые, такие как функции POSIX и Microsoft, являются устаревшими, так как теперь они имеют другое предпочтительное имя. Некоторые функции библиотеки времени выполнения C являются устаревшими, так как они являются небезопасными и имеют более безопасный вариант. Другие являются устаревшими, так как они устарели. Сообщения об устаревании обычно содержат предлагаемую замену устаревшей функции или глобальной переменной.

## <a name="turn-off-the-warning"></a>Отключить предупреждение

Чтобы устранить проблему C4996, обычно рекомендуется изменить код. Вместо этого используйте предложенные функции и глобальные переменные. Если необходимо использовать существующие функции или переменные по соображениям переносимости, можно отключить предупреждение.

### <a name="turn-off-the-warning-for-a-specific-line-of-code"></a>Отключение предупреждения для определенной строки кода

Чтобы отключить предупреждение для определенной строки кода, используйте [`warning`](../../preprocessor/warning.md) директиву pragma, `#pragma warning(suppress : 4996)` .

### <a name="turn-off-the-warning-within-a-file"></a>Отключение предупреждения в файле

Чтобы отключить предупреждение в файле для всех элементов, которые следуют за ним, используйте прагма-директиву warning, `#pragma warning(disable : 4996)` .

### <a name="turn-off-the-warning-in-command-line-builds"></a>Отключение предупреждения в сборках из командной строки

Чтобы отключить предупреждение глобально в сборках командной строки, используйте [`/wd4996`](../../build/reference/compiler-option-warning-level.md) параметр командной строки.

### <a name="turn-off-the-warning-for-a-project-in-visual-studio"></a>Отключение предупреждения для проекта в Visual Studio

Чтобы отключить предупреждение для всего проекта в интегрированной среде разработки Visual Studio, сделайте следующее:

1. Откройте диалоговое окно **страницы свойств** для проекта. Сведения об использовании диалогового окна страницы свойств см. в разделе [страницы свойств](../../build/reference/property-pages-visual-cpp.md).

1. Выберите страницу свойств свойства **конфигурации**  >  **C/C++**  >  **Дополнительно** .

1. Измените свойство **Отключить определенные предупреждения** , чтобы добавить *`4996`* . Нажмите кнопку **ОК** , чтобы применить изменения.

### <a name="disable-the-warning-using-preprocessor-macros"></a>Отключение предупреждения с помощью макросов препроцессора

Вы также можете использовать макросы препроцессора, чтобы отключить некоторые определенные классы предупреждений об устаревании, используемых в библиотеках. Эти макросы описаны ниже.

Чтобы определить макрос препроцессора в Visual Studio, выполните следующие действия.

1. Откройте диалоговое окно **страницы свойств** для проекта. Сведения об использовании диалогового окна страницы свойств см. в разделе [страницы свойств](../../build/reference/property-pages-visual-cpp.md).

1. Разверните **Свойства конфигурации > препроцессора > C/C++**.

1. В свойстве **определения препроцессора** добавьте имя макроса. Нажмите кнопку **ОК** для сохранения изменений, а затем выполните повторную сборку проекта.

Чтобы определить макрос только в определенных исходных файлах, добавьте строку `#define EXAMPLE_MACRO_NAME` , например перед любой строкой, содержащей файл заголовка.

Ниже приведены некоторые из распространенных источников предупреждений и ошибок C4996:

## <a name="posix-function-names"></a>Имена функций POSIX

**`The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name:`** _`new-name.`_ **`See online help for details.`**

Корпорация Майкрософт переименовала некоторые библиотечные функции POSIX и Microsoft в CRT, чтобы они соответствовали ограничениям C99 и C++ 03 в зарезервированных и глобальных именах, определяемых реализацией. *Только имена являются устаревшими, а не сами функции*. В большинстве случаев в имя функции добавляется символ подчеркивания для создания имени. Компилятор выдает предупреждение об устаревании для имени исходной функции и предлагает предпочтительное имя.

Чтобы устранить эту проблему, обычно рекомендуется изменить код так, чтобы вместо него использовались предлагаемые имена функций. Однако обновленные имена относятся только к Microsoft. Если необходимо использовать имена существующих функций по соображениям переносимости, можно отключить эти предупреждения. Функции по-прежнему доступны в библиотеке с их исходными именами.

Чтобы отключить предупреждения об устаревании для этих функций, определите макрос препроцессора **`_CRT_NONSTDC_NO_WARNINGS`** . Этот макрос можно определить в командной строке, включив параметр `/D_CRT_NONSTDC_NO_WARNINGS` .

## <a name="unsafe-crt-library-functions"></a>Небезопасные функции библиотеки CRT

**`This function or variable may be unsafe. Consider using`** _`safe-version`_ **`instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.`**

Корпорация Майкрософт не имеет устаревших функций и глобальных библиотек CRT и C++, так как доступны более безопасные версии. Большинство устаревших функций допускают непроверенный доступ на чтение или запись к буферам. Их неправильное использование может привести к серьезным проблемам безопасности. Компилятор выдает предупреждение об устаревании для этих функций и предлагает предпочтительную функцию.

Чтобы устранить эту проблему, рекомендуется вместо этого использовать функцию или переменную *`safe-version`* . Иногда вы не можете обеспечить переносимость или обратную совместимость. Тщательно проверьте, не возможно ли перезапись или Пересчитывание буфера в коде. После этого предупреждение можно отключить.

Чтобы отключить предупреждения об устаревании для этих функций в CRT, определите **`_CRT_SECURE_NO_WARNINGS`** .

Чтобы отключить предупреждения о нерекомендуемых глобальных переменных, определите **`_CRT_SECURE_NO_WARNINGS_GLOBALS`** .

Дополнительные сведения об этих устаревших функциях и глобальных параметрах см. [в разделе функции безопасности в](../../c-runtime-library/security-features-in-the-crt.md) библиотеках CRT и [безопасные: Стандартная библиотека C++](../../standard-library/safe-libraries-cpp-standard-library.md).

## <a name="unsafe-standard-library-functions"></a>Ненадежные функции стандартной библиотеки

**`'std::`** *`function_name`* **`::_Unchecked_iterators::_Deprecate' Call to std::`** *`function_name`* **`with parameters that may be unsafe - this call relies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'`**

В Visual Studio 2015 это предупреждение появляется в отладочных сборках, поскольку некоторые функции шаблона стандартной библиотеки C++ не проверяют правильность параметров. Часто это обусловлено тем, что функции не хватает информации для проверки границ контейнера. Или, так как итераторы могут неправильно использоваться функцией. Это предупреждение помогает понять эти функции, так как они могут быть источником серьезных брешей в системе безопасности в программе. Дополнительные сведения см. в разделе [проверенные итераторы](../../standard-library/checked-iterators.md).

Например, это предупреждение отображается в режиме отладки `std::copy` , если вместо простого массива передается указатель на элемент. Чтобы устранить эту проблему, используйте соответствующий объявленный массив, чтобы библиотека могла проверять экстенты массива и проверять границы.

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

Несколько стандартных алгоритмов библиотеки были обновлены в версии C++ 14 с двумя диапазонами. При использовании двух версий диапазона второй диапазон предоставляет необходимые проверки границ:

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

В этом примере показано несколько способов использования стандартной библиотеки для проверки использования итератора, и если непроверенное использование может быть опасным:

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

Если вы проверили, что в коде не может быть ошибки переполнения буфера, это предупреждение можно отключить. Чтобы отключить предупреждения для этих функций, определите **`_SCL_SECURE_NO_WARNINGS`** .

## <a name="checked-iterators-enabled"></a>Проверенные итераторы включены

Предупреждение C4996 также может возникать, если не используется проверяемый итератор, если `_ITERATOR_DEBUG_LEVEL` определен как 1 или 2. По умолчанию для сборок в режиме отладки установлено значение 2, а для розничных сборок — 0. Дополнительные сведения см. в разделе [проверенные итераторы](../../standard-library/checked-iterators.md).

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

## <a name="unsafe-mfc-or-atl-code"></a>Ненадежный код MFC или ATL

Предупреждение C4996 может возникать при использовании функций MFC или ATL, которые являются устаревшими по соображениям безопасности.

Чтобы устранить эту проблему, настоятельно рекомендуется изменить код, чтобы вместо этого использовать обновленные функции.

Сведения о подавлении этих предупреждений см. в разделе [`_AFX_SECURE_NO_WARNINGS`](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) .

## <a name="obsolete-crt-functions-and-variables"></a>Устаревшие функции и переменные CRT

**`This function or variable has been superseded by newer library or operating system functionality. Consider using`** *`new_item`* **`instead. See online help for details.`**

Некоторые функции и глобальные переменные библиотеки устарели. Эти функции и переменные могут быть удалены в будущей версии библиотеки. Компилятор выдает предупреждение об устаревании для этих элементов и предлагает предпочтительную альтернативу.

Чтобы устранить эту проблему, мы рекомендуем изменить код для использования предлагаемой функции или переменной.

Чтобы отключить предупреждения об устаревании для этих элементов, определите **`_CRT_OBSOLETE_NO_WARNINGS`** . Дополнительные сведения см. в документации по устаревшей функции или переменной.

## <a name="marshaling-errors-in-clr-code"></a>Ошибки маршалирования в коде CLR

Предупреждение C4996 также может возникать при использовании библиотеки маршалирования CLR. В этом случае C4996 является ошибкой, а не предупреждением. Эта ошибка возникает при использовании [`marshal_as`](../../dotnet/marshal-as.md) для преобразования между двумя типами данных, для которых требуется [ `marshal_context` класс](../../dotnet/marshal-context-class.md). Эту ошибку также можно получить, когда библиотека упаковки не поддерживает преобразование. Дополнительные сведения о библиотеке упаковки см. [в разделе Общие сведения о маршалировании в C++](../../dotnet/overview-of-marshaling-in-cpp.md).

Этот пример приводит к возникновению предупреждения C4996, поскольку библиотеке маршалирования требуется контекст для преобразования из в `System::String` `const char *` .

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>Пример: определяемая пользователем устаревшая функция

Атрибут можно использовать `deprecated` в собственном коде для предупреждения вызывающих объектов, когда больше не рекомендуется использовать определенные функции. В этом примере C4996 создается в двух местах: по одному для строки, для которой объявлена устаревшая функция, а другая — для строки, в которой используется функция.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

[[deprecated]]
void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
