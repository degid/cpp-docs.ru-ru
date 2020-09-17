---
title: Улучшение соответствия C++
ms.date: 08/04/2020
description: Microsoft C++ в Visual Studio развивается в сторону полного соответствия стандарту языка C++20.
ms.technology: cpp-language
ms.openlocfilehash: 3a0e21bf08fcf7861feedd3fd43666bd3768deee
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042125"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Улучшения соответствия C++ в Visual Studio

В каждом выпуске Microsoft C++ добавляются улучшения соответствия и исправления ошибок. В этой статье перечислены улучшения в разбивке по основным выпускам и версиям системы. Также здесь перечислены основные исправления ошибок в разбивке по версиям. Чтобы перейти непосредственно к изменениям в конкретной версии, используйте список из **этой статьи**.

::: moniker range="vs-2019"

## <a name="conformance-improvements-in-visual-studio-2019-rtw-version-160"></a><a name="improvements_160"></a> Улучшения соответствия в Visual Studio 2019 RTW (версия 16.0)

Visual Studio 2019 RTW содержит следующие улучшения соответствия, исправления ошибок и изменения в поведении в компиляторе Microsoft C++ (MSVC)

**Примечание.** Возможности C++ 20 будут доступны в режиме **`/std:c++latest`** до завершения реализации C++20 для компилятора и IntelliSense. На этом этапе будет введен режим компилятора **`/std:c++20`** .

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Улучшенные модули поддерживают шаблоны и обнаружение ошибок

Модули теперь официально соответствуют стандарту C ++20. Улучшенная поддержка была добавлена в Visual Studio 2017 версии 15.9. Дополнительные сведения см. в разделе [Улучшенная поддержка шаблонов и обнаружение ошибок в модулях C++ MSVC 2017 версии 15.9](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Изменена спецификация типа агрегата

Спецификация типа агрегата была изменена в C++20 (см. раздел [Запрет агрегатов с объявленными пользователем конструкторами](https://wg21.link/p1008r1)). В Visual Studio 2019 в **`/std:c++latest`** класс с любым конструктором, объявленным пользователем (например, конструктор, объявленный `= default` или `= delete`), не является агрегатом. Ранее только предоставленные пользователем конструкторы запрещали классу быть агрегатом. Это изменение накладывает дополнительные ограничения на способ инициализации таких типов.

Следующий код компилируется без ошибок в Visual Studio 2017, но вызывает ошибки C2280 и C2440 в Visual Studio 2019 в **`/std:c++latest`** :

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>Частичная поддержка для `operator <=>`

[P0515R3](https://wg21.link/p0515r3) C++20 вводит трехсторонний оператор сравнения `<=>`, также известный как "оператор — космический корабль". Visual Studio 2019 в режиме **`/std:c++latest`** вводит частичную поддержку оператора, вызывая ошибки синтаксиса, который сейчас запрещен. Например, следующий код компилируется без ошибок в Visual Studio 2017, но вызывает различные ошибки в Visual Studio 2019 в **`/std:c++latest`** :

```cpp
struct S
{
    bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };

int main(int argc, char** argv)
{
    U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

Чтобы избежать этих ошибок, добавьте символ пробела в строку, вызывающую ошибку, перед последней скобкой: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Ссылки на типы с несоответствием cv-квалификаторов

Ранее MSVC допускал прямую привязку ссылки из типа с несоответствием cv-квалификаторов ниже верхнего уровня. Это делало возможным изменение предположительно постоянных данных, на которые указывала ссылка. Теперь компилятор создает временные данные согласно требованиям стандарта. В Visual Studio 2017 следующий код компилировался без предупреждений. В Visual Studio 2019 компилятор вызывает предупреждение C4172: `<func:#1 "?PData@X@@QBEABQBXXZ"> returning address of local variable or temporary.`.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast` из перегруженной функции

Аргумент **`reinterpret_cast`** не входит в число контекстов, в которых разрешен адрес перегруженной функции. Следующий код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 вызывает ошибку C2440: `cannot convert from 'overloaded-function' to 'fp'`.

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Чтобы избежать этой ошибки, используйте допустимые приведения для этого сценария:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Замыкания лямбда-выражений

В C++14 типы замыкания лямбда-выражений не являются литералами. Основное следствие этого правила заключается в том, что лямбда-выражение не может назначаться переменной **`constexpr`** . Следующий код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 вызывает ошибку C2127: `'l': illegal initialization of 'constexpr' entity with a non-constant expression`.

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Чтобы избежать этой ошибки, удалите квалификатор **`constexpr`** или измените режим совместимости на **`/std:c++17`** .

### <a name="stdcreate_directory-failure-codes"></a>Коды сбоя `std::create_directory`

Безусловная реализация [P1164](https://wg21.link/p1164r1) из C ++ 20. Это изменяет `std::create_directory`, чтобы проверить, был ли целевой объект уже каталогом со сбоем. Ранее все ошибки типа ERROR_ALREADY_EXISTS были включены в коды "Выполнено успешно, но каталог не создан".

### `operator<<(std::ostream, nullptr_t)`

Для [LWG 2221](https://cplusplus.github.io/LWG/issue2221) добавлен `operator<<(std::ostream, nullptr_t)` для записи nullptrs в потоки.

### <a name="additional-parallel-algorithms"></a>Дополнительные параллельные алгоритмы

Новые параллельные версии `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` и `is_heap_until`.

### <a name="atomic-initialization"></a>Атомарная инициализация

[P0883 "Устранение атомарной инициализации"](https://wg21.link/p0883r1) меняет `std::atomic`, чтобы инициализировать T по значению, а не по умолчанию. Это исправление включается при использовании Clang/LLVM со стандартной библиотекой Майкрософт. Сейчас оно отключено для компилятора Microsoft C++ в качестве обходного решения для ошибки с обработкой **`constexpr`** .

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` и `remove_cvref_t`

Реализация признаков типа `remove_cvref` и `remove_cvref_t` из [P0550](https://wg21.link/p0550r2). Они удаляют ссылочность и cv-квалификацию из типа без ограничения функций и массивов до указателей (в отличие от `std::decay` и `std::decay_t`).

### <a name="feature-test-macros"></a>Макросы тестирования функций

[P0941R2 — макросы тестирования функций](https://wg21.link/p0941r2) завершены с поддержкой `__has_cpp_attribute`. Макросы тестирования функций поддерживаются во всех стандартных режимах.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Запрет агрегирования с объявленными пользователем конструкторами

[C++ 20 P1008R1 — запрет агрегирования с объявленными пользователем конструкторами](https://wg21.link/p1008r1) завершен.

## <a name="conformance-improvements-in-161"></a><a name="improvements_161"></a> Улучшения соответствия C++ в 16.1

### <a name="char8_t"></a>char8_t

[P0482r6](https://wg21.link/p0482r6). C ++ 20 добавляет новый тип символа, который используется для представления частей кода UTF-8. Строковые литералы `u8` в C++20 имеют тип `const char8_t[N]`, а не `const char[N]`, как было раньше. Аналогичные изменения предложены для стандарта C в [N2231](https://wg14.link/n2231). Рекомендации по обеспечению обратной совместимости для **`char8_t`** приведены в [P1423r3](https://wg21.link/p1423r3). Компилятор Microsoft C++ добавляет поддержку типа **`char8_t`** в Visual Studio 2019 версии 16.1, если вы укажете параметр компилятора **`/Zc:char8_t`** . В будущем он будет поддерживаться с [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md), который можно отменить, чтобы восстановить поведение C++17 с помощью **`/Zc:char8_t-`** . Компилятор EDG, лежащий в основе IntelliSense, пока не поддерживает эту возможность. Вы можете видеть ложные ошибки для IntelliSense, которые не влияют на фактическую компиляцию.

#### <a name="example"></a>Пример

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>Метафункция std::type_identity и объект функции std::identity

[P0887R1 type_identity](https://wg21.link/p0887r1). Устаревшее расширение класса шаблонов `std::identity` было удалено и заменено на метафункцию `std::type_identity` и объект функции `std::identity` в C++20. Они доступны только в [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md).

В следующем примере становится устаревшим предупреждение C4996 для `std::identity` (определено в \<type_traits>) в Visual Studio 2017:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

В следующем примере показано, как использовать новый `std::identity` (определено в \<functional>) вместе с новым `std::type_identity`:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Проверка синтаксиса для универсальных лямбда-выражений

Новый обработчик лямбда-выражений включает некоторые проверки синтаксиса режима совместимости в универсальных лямбда-выражениях в [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) или в другом режиме языка с **`/experimental:newLambdaProcessor`** .

В Visual Studio 2017 этот код компилируется без предупреждений, но в Visual Studio 2019 вызывает ошибку C2760 `syntax error: unexpected token '\<id-expr>', expected 'id-expression'`:

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

В следующем примере показан правильный синтаксис, который теперь применяется компилятором принудительно:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>Зависящий от аргументов поиск вызовов функций

[P0846R0](https://wg21.link/p0846r0) (C++20). Улучшена возможность поиска шаблонов функций с помощью поиска, учитывающего аргументы, выражений вызова функции с явно заданными аргументами шаблона. Требует использования **`/std:c++latest`** .

### <a name="designated-initialization"></a>Назначенная инициализация

[P0329R4](https://wg21.link/p0329r4) (C++20). *Назначенная инициализация* позволяет выбирать определенные элементы в агрегатной инициализации с помощью синтаксиса `Type t { .member = expr }`. Требует использования **`/std:c++latest`** .

### <a name="new-and-updated-standard-library-functions-c20"></a>Новые и обновленные функции стандартной библиотеки (C++20)

- `starts_with()` и `ends_with()` для `basic_string` и `basic_string_view`.
- `contains()` для ассоциативных контейнеров;
- `remove()`, `remove_if()` и `unique()` для `list` и `forward_list` теперь возвращают `size_type`;
- `shift_left()`и `shift_right()` добавлены в \<algorithm>.

## <a name="conformance-improvements-in-162"></a><a name="improvements_162"></a> Улучшения соответствия C++ в 16.2

### <a name="noexcept-constexpr-functions"></a>Функции `noexcept` `constexpr`

Функции **`constexpr`** больше не считаются **`noexcept`** по умолчанию при использовании в константном выражении. Это изменение в поведении обусловлено разрешением [CWG 1351](https://wg21.link/cwg1351) и включено в [`/permissive-`](../build/reference/permissive-standards-conformance.md). Следующий пример компилируется в Visual Studio 2019 версии 16.1 и более ранних версиях, но вызывает C2338 в Visual Studio 2019 версии 16.2:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Чтобы устранить эту ошибку, добавьте выражение **`noexcept`** в объявление функции:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Двоичные выражения с различными типами перечисления

В C++20 не рекомендуется использовать обычные арифметические преобразования к операндам, где:

- один операнд имеет тип перечисления, а

- другой — другой тип перечисления или числовой тип с плавающей запятой.

Дополнительные сведения о P1120R0 см. [здесь](https://wg21.link/p1120r0).

В Visual Studio 2019 версии 16.2 и более поздних в следующем примере кода создается предупреждение уровня 4, если включен параметр компилятора [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md):

```cpp
enum E1 { a };
enum E2 { b };
int main() {
    int i = a | b; // warning C5054: operator '|': deprecated between enumerations of different types
}
```

Чтобы избежать этого предупреждения, используйте [static_cast](../cpp/static-cast-operator.md) для преобразования второго операнда:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
  int i = a | static_cast<int>(b);
}
```

При использовании двоичной операции между типом перечисления и типом с плавающей запятой теперь возникает предупреждение, если включен параметр компилятора [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md):

```cpp
enum E1 { a };
int main() {
  double i = a * 1.1;
}
```

Чтобы избежать этого предупреждения, используйте [static_cast](../cpp/static-cast-operator.md) для преобразования второго операнда:

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>Равенство и реляционные сравнения массивов

Равенство и сравнение отношений между двумя операндами типа массива являются устаревшими в C++ 20 ([P1120R0](https://wg21.link/p1120r0)). Иными словами, операция сравнения двух массивов (несмотря на схожесть приоритета и экстента) теперь вызвает предупреждение. Начиная с Visual Studio 2019 версии 16.2, следующий код вызывает ошибку C5056 `operator '==': deprecated for array types`, если включен параметр компилятора [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md).

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (a == b) { return 1; }
}
```

Чтобы избежать этого предупреждения, можно сравнить адреса первых элементов:

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (&a[0] == &b[0]) { return 1; }
}
```

Чтобы определить, равно ли содержимое двух массивов, используйте функцию [std::equal](../standard-library/algorithm-functions.md#equal):

```cpp
std::equal(std::begin(a), std::end(a), std::begin(b), std::end(b));
```

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>Результат определения оператора трехстороннего сравнения в `==` и `!=`

Определение оператора трехстороннего сравнения ( **`<=>`** ) больше не будет переписывать выражения, включающие **`==`** или **`!=`** , если оператор не помечен как **`= default`** ([P1185R2](https://wg21.link/p1185r2)). Следующий пример компилируется в Visual Studio 2019 RTW и версии 16.1, но вызывает C2678 в Visual Studio 2019 версии 16.2:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Чтобы избежать этой ошибки, определите оператор == или объявите его по умолчанию:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
  bool operator==(const S&) const = default;
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

### <a name="standard-library-improvements"></a>Улучшения стандартной библиотеки

- \<charconv> `to_chars()` с фиксированной или научной точностью. (Общая точность в настоящее время запланирована на версию 16.4.)
- [P0020R6](https://wg21.link/p0020r6): atomic\<float>, atomic\<double>, atomic\<long double>
- [P0463R1](https://wg21.link/p0463r1): endian
- [P0482R6](https://wg21.link/p0482r6): Поддержка библиотек для char8_t
- [P0600R1](https://wg21.link/p0600r1): [\[nodiscard]] для STL, часть 1
- [P0653R2](https://wg21.link/p0653r2): to_address()
- [P0754R2](https://wg21.link/p0754r2): \<version>
- [P0771R1](https://wg21.link/p0771r1): noexcept для конструктора перемещения std::function

## <a name="conformance-improvements-in-visual-studio-2019-version-163"></a><a name="improvements_163"></a> Улучшения соответствия в Visual Studio 2019 версии 16.3

### <a name="stream-extraction-operators-for-char-removed"></a>Операторы извлечения потока для char* удалены

Операторы извлечения потока для указателей на символы были удалены и заменены операторами извлечения для массивов символов (в соответствии с [P0487R1](https://wg21.link/p0487r1)). WG21 считает удаленные перегрузки небезопасными. В режиме [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) следующий пример теперь вызывает ошибку C2679 `binary '>>': no operator found which takes a right-hand operand of type 'char*' (or there is no acceptable conversion)`.

```cpp
   char x[42];
   char* p = x;
   std::cin >> std::setw(42);
   std::cin >> p;
```

Чтобы избежать этой ошибки, используйте оператор извлечения с переменной char[]:

```cpp
char x[42];
std::cin >> x;
```

### <a name="new-keywords-requires-and-concept"></a>Новые ключевые слова `requires` и `concept`

В компилятор Microsoft C++ добавлены новые ключевые слова: **`requires`** и **`concept`** . Если вы попытаетесь использовать одно из них как идентификатор в режиме [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md), компилятор выдаст ошибку C2059 `syntax error`.

### <a name="constructors-as-type-names-disallowed"></a>Конструкторы в качестве имен типов запрещены

В этом случае компилятор больше не считает имена конструкторов внедренными именами классов, когда они появляются в полном имени после псевдонима для специализации шаблона класса. Для объявления других сущностей ранее конструкторы использовались в качестве имени типа. Но теперь следующий пример приводит к возникновению ошибки C3646: `'TotalDuration': unknown override specifier`.

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{};
};

```

Чтобы избежать этой ошибки, объявите `TotalDuration`, как показано ниже:

```cpp
#include <chrono>

class Foo {
  std::chrono::milliseconds TotalDuration {};
};
```

### <a name="stricter-checking-of-extern-c-functions"></a>Более строгая проверка функций `extern "C"`

Если функция **`extern "C"`** была объявлена в разных пространствах имен, предыдущие версии компилятора Microsoft C++ не проверяли, совместимы ли объявления. Начиная с Visual Studio 2019 версии 16.3 компилятор проверяет на совместимость. В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) следующий код вызывает ошибки C2371 `redefinition; different basic types` и C2733 `you cannot overload a function with C linkage`.

```cpp
using BOOL = int;

namespace N
{
   extern "C" void f(int, int, int, bool);
}

void g()
{
   N::f(0, 1, 2, false);
}

extern "C" void f(int, int, int, BOOL){}
```

Чтобы избежать ошибок в предыдущем примере, используйте **`bool`** вместо `BOOL` в обоих объявлениях `f`.

### <a name="standard-library-improvements"></a>Улучшения стандартной библиотеки

Нестандартные заголовки \<stdexcpt.h> и \<typeinfo.h> были удалены. Код, который содержит их, должен включать стандартные заголовки \<exception> и \<typeinfo> соответственно.

## <a name="conformance-improvements-in-visual-studio-2019-version-164"></a><a name="improvements_164"></a> Улучшения соответствия в Visual Studio 2019 версии 16.4

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>Улучшенное принудительное двухэтапное разрешение имени для идентификаторов qualified-id в `/permissive-`

Для двухэтапного поиска имен нужно, чтобы независимые имена, используемые в тексте шаблона, отображались в шаблоне во время определения. Ранее такие имена можно было встретить при создании экземпляра шаблона. Это изменение упрощает написание переносимого и соответствующего требованиям кода в MSVC с флагом [`/permissive-`](../build/reference/permissive-standards-conformance.md).

В Visual Studio 2019 версии 16.4 с установленным флагом **`/permissive-`** в следующем примере поступает сообщение об ошибке, так как при определении шаблона `f<T>` не отображается `N::f`:

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

Как правило, эту ошибку можно исправить, добавив недостающие заголовки или функции либо переменные с опережающим объявлением, как показано в следующем примере:

```cpp
namespace N {
    int f();
}

template <class T>
int f() {
    return N::f() + T{};
}

namespace N {
    int f() { return 42; }
}
```

### <a name="implicit-conversion-of-integral-constant-expressions-to-null-pointer"></a>Неявное преобразование целочисленных константных выражений в пустой указатель

Компилятор MSVC теперь реализует [проблему CWG 903](https://wg21.link/cwg903) в режиме соответствия ( **`/permissive-`** ). Это правило запрещает неявное преобразование целочисленных константных выражений (за исключением целочисленного литерала 0) в константы пустого указателя. В следующем примере поступает сообщение об ошибке C2440 в режиме соответствия:

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

Для устранения этой ошибки используйте **`nullptr`** вместо **`false`** . Литерал 0 по-прежнему можно использовать:

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>Стандартные правила для типов целочисленных литералов

В режиме соответствия (реализуется с помощью [`/permissive-`](../build/reference/permissive-standards-conformance.md)) MSVC использует стандартные правила для типов целочисленных литералов. Десятичным литералам, которые были слишком велики для **`signed int`** , ранее присваивался тип **`unsigned int`** . Теперь таким литералам присваивается следующий самый большой тип целого числа **`signed`** , то есть **`long long`** . Кроме того, литералам с суффиксом ll, которые слишком велики для типа **`signed`** , присваивается тип **`unsigned long long`** .

Это изменение может привести к возникновению разных предупреждений системы диагностики и нестандартному поведению при выполнении арифметических операций над литералами.

В приведенном ниже примере показано новое поведение в Visual Studio 2019 версии 16.4. Переменная `i` теперь имеет тип **`unsigned int`** . Поэтому возникает предупреждение. Старшие разряды переменной `j` имеют значение 0.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

В следующем примере показано, как сохранить прежнее поведение и избежать появления предупреждений и изменений в поведении во время выполнения:

```cpp
void f(int r) {
int i = 2964557531u; // OK
long long j = (long long)0x8000000000000000ll >> r; // shift will keep high-order bits
}
```

### <a name="function-parameters-that-shadow-template-parameters"></a>Параметры функции, которые затемняют параметры шаблона

При использовании компилятора MSVC теперь происходит ошибка, когда параметр функции затемняет параметр шаблона:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T(&buffer)[Size], int& Size) // error C7576: declaration of 'Size' shadows a template parameter
{
    return f(buffer, Size, Size);
}
```

Чтобы устранить эту ошибку, измените имя одного из параметров:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T (&buffer)[Size], int& size_read)
{
    return f(buffer, Size, size_read);
}
```

### <a name="user-provided-specializations-of-type-traits"></a>Определяемые пользователем специализации признаков типов

В соответствии с подпунктом *meta.rqmts* стандартного определения при использовании компилятора MSVC теперь поступает сообщение об ошибке при обнаружении пользовательской специализации одного из указанных шаблонов `type_traits` в пространстве имен `std`. Если не указано иное, такие специализации приводят к неопределенному поведению. В следующем примере наблюдается неопределенное поведение, так как нарушено правило. Поэтому выполнение **`static_assert`** завершается с ошибкой C2338.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

Чтобы избежать этой ошибки, определите структуру, которая наследуется от предпочитаемого `type_trait`, и используйте специализацию:

```cpp
#include <type_traits>

struct S;

template<typename T>
struct my_is_fundamental : std::is_fundamental<T> {};

template<>
struct my_is_fundamental<S> : std::true_type { };

static_assert(my_is_fundamental<S>::value, "fail");
```

### <a name="changes-to-compiler-provided-comparison-operators"></a>Изменения в предоставленных компилятором операторах сравнения

Компилятор MSVC теперь реализует следующие изменения для операторов сравнения ([P1630R1](https://wg21.link/p1630r1)), когда включен параметр [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md):

Компилятор больше не перезаписывает выражения с помощью `operator==`, если они относятся к типу возвращаемого значения, отличному от **`bool`** . Следующий код теперь вызывает ошибку C2088: `'!=': illegal for struct`.

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Чтобы избежать этой ошибки, необходимо явно определить необходимый оператор:

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
    U operator!=(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Компилятор больше не определяет оператор сравнения по умолчанию, если он является членом класса, подобного объединению. Следующий пример теперь приводит к возникновению ошибки C2120: `'void' illegal with all types`.

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const = default;
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

Чтобы избежать этой ошибки, определите текст для оператора:

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const { ... }
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

Компилятор больше не будет определять оператор сравнения по умолчанию, если класс содержит ссылочный элемент. Следующий код теперь вызывает ошибку C2120: `'void' illegal with all types`.

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const = default;
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

Чтобы избежать этой ошибки, определите текст для оператора:

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const { ... };
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

## <a name="conformance-improvements-in-visual-studio-2019-version-165"></a><a name="improvements_165"></a> Улучшения соответствия в Visual Studio 2019 версии 16.5

### <a name="explicit-specialization-declaration-without-an-initializer-isnt-a-definition"></a>Явное объявление специализации без инициализатора не является определением

В `/permissive-` MSVC теперь применяет стандартное правило о том, что явные объявления специализации без инициализаторов не являются определениями. Ранее объявление рассматривалось как определение с инициализатором по умолчанию. Этот эффект можно наблюдать во время компоновки, так как программа, зависимая от этого поведения, теперь может иметь неразрешенные символы. Теперь такой пример приводит к ошибке:

```cpp
template <typename> struct S {
    static int a;
};

// In permissive-, this declaration isn't a definition, and the program won't link.
template <> int S<char>::a;

int main() {
    return S<char>::a;
}
```

```Output
error LNK2019: unresolved external symbol "public: static int S<char>::a" (?a@?$S@D@@2HA) referenced in function _main
at link time.
```

Чтобы устранить эту проблему, добавьте инициализатор:

```cpp
template <typename> struct S {
    static int a;
};

// Add an initializer for the declaration to be a definition.
template <> int S<char>::a{};

int main() {
    return S<char>::a;
}
```

### <a name="preprocessor-output-preserves-newlines"></a>Выходные данные препроцессора сохраняют символы новой строки

Экспериментальный препроцессор теперь сохраняет символы новой строки и пробелы при использовании **`/P`** или **`/E`** с **`/experimental:preprocessor`** .

Если рассматривать этот пример исходного кода:

```cpp
#define m()
line m(
) line
```

Предыдущие выходные данные **`/E`** имели вид:

```Output
line line
#line 2
```

Новые выходные данные **`/E`** имеют вид:

```Output
line
 line
```

### <a name="import-and-module-keywords-are-context-dependent"></a>Ключевые слова "import" и "module" являются контекстно-зависимыми

Согласно P1857R1, директивы препроцессора import и module имеют дополнительные ограничения синтаксиса. Этот пример больше не компилируется:

```cpp
import // Invalid
m;
```

Он возвращает следующее сообщение об ошибке:

```Output
error C2146: syntax error: missing ';' before identifier 'm'
```

Чтобы устранить эту проблему, оставьте import в той же строке:

```cpp
import m; // OK
```

### <a name="removal-of-stdweak_equality-and-stdstrong_equality"></a>Удаление std::weak_equality и std::strong_equality

Для объединения P1959R0 требуется, чтобы компилятор удалил поведение и ссылки на типы `std::weak_equality` и `std::strong_equality`.

Код в этом примере больше не компилируется:

```cpp
#include <compare>

struct S {
    std::strong_equality operator<=>(const S&) const = default;
};

void f() {
    nullptr<=>nullptr;
    &f <=> &f;
    &S::operator<=> <=> &S::operator<=>;
}
```

Теперь этот пример приводит к следующим ошибкам:

```Output
error C2039: 'strong_equality': is not a member of 'std'
error C2143: syntax error: missing ';' before '<=>'
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C7546: binary operator '<=>': unsupported operand types 'nullptr' and 'nullptr'
error C7546: binary operator '<=>': unsupported operand types 'void (__cdecl *)(void)' and 'void (__cdecl *)(void)'
error C7546: binary operator '<=>': unsupported operand types 'int (__thiscall S::* )(const S &) const' and 'int (__thiscall S::* )(const S &) const'
```

Чтобы устранить эту проблему, внесите обновления, чтобы предпочитать встроенные реляционные операторы и заменить удаленные типы:

```cpp
#include <compare>

struct S {
    std::strong_ordering operator<=>(const S&) const = default; // prefer 'std::strong_ordering'
};

void f() {
    nullptr != nullptr; // use pre-existing builtin operator != or ==.
    &f != &f;
    &S::operator<=> != &S::operator<=>;
}
```

### <a name="tls-guard-changes"></a>Изменения TLS Guard

Ранее локальные по отношению к потоку переменные в библиотеках DLL не инициализировались должным образом. За исключением потока, загрузившего библиотеку DLL, они не инициализировались до их первого использования в потоках, существовавших до загрузки библиотеки DLL. Теперь эта ошибка устранена. Локальные по отношению к потоку переменные в подобной библиотеке DLL инициализируются непосредственно перед их первым использованием в таких потоках.

Это новое поведение проверки инициализации при использовании локальных по отношению к потоку переменных можно отключить с помощью параметра компилятора **`/Zc:tlsGuards-`** . Кроме того, можно добавить атрибут `[[msvc:no_tls_guard]]` к конкретным локальным по отношению к потоку переменным.

### <a name="better-diagnosis-of-call-to-deleted-functions"></a>Улучшенная диагностика вызовов удаленных функций

Наш компилятор был менее строгим по отношению к вызовам удаленных функций. Например, если вызовы происходили в контексте тела шаблона, вызов не диагностировался. Кроме того, если существовало несколько экземпляров вызовов удаленных функций, выводилась только одна запись диагностики. Теперь запись диагностики выводится для каждого из них.

Одно из последствий такого нового поведения может привести к небольшому критическому изменению: Код, вызвавший удаленную функцию, не будет диагностирован, если он никогда не требовался для создания кода. Теперь мы выполняем диагностику заранее.

В этом примере показан код, который теперь выдает ошибку:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s{};
};

U u{ 0 };
```

```Output
error C2280: 'S::S(void)': attempting to reference a deleted function
note: see declaration of 'S::S'
note: 'S::S(void)': function was explicitly deleted
```

Чтобы устранить эту проблему, удалите вызовы удаленных функций:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s;  // Do not call the deleted ctor of 'S'.
};

U u{ 0 };
```

## <a name="conformance-improvements-in-visual-studio-2019-version-166"></a><a name="improvements_166"></a> Улучшения соответствия в Visual Studio 2019 версии 16.6

### <a name="standard-library-streams-reject-insertions-of-mis-encoded-character-types"></a>Потоки стандартной библиотеки отклоняют вставки типов символов с неправильным кодированием

Обычно в результате вставки **`wchar_t`** в `std::ostream` и вставки **`char16_t`** или **`char32_t`** в `std::ostream` или `std::wostream` выводится целочисленное значение. При вставке указателей на эти типы символов выводится значение указателя. Оба варианта не являются интуитивно понятными для программистов. Чаще всего ожидается, что стандартная библиотека перекодирует символ или строку символов, оканчивающуюся нулем, и выведет результат.

Предложение C++20 [P1423R3](https://wg21.link/p1423r3) реализует добавление перегрузок операторов вставки удаленных потоков для этих сочетаний потоков и символов или символьных указателей. В режиме **`/std:c++latest`** перегрузки делают эти вставки неправильно сформированными, а не вызывают то, что, скорее всего, является нежелательным поведением. При обнаружении компилятор выдает ошибку C2280. Вы можете определить макрос типа "escape hatch" `_HAS_STREAM_INSERTION_OPERATORS_DELETED_IN_CXX20` равным `1`, чтобы восстановить предыдущее поведение. (Предложение также реализует удаление операторов вставки потока для **`char8_t`** . Наша стандартная библиотека реализовывала аналогичные перегрузки, когда мы добавили поддержку **`char8_t`** , так что неправильное поведение для **`char8_t`** никогда не возникало.)

В следующем примере показано поведение при этом изменении:

```cpp
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << cw << ' ' << pw << '\n';
    std::cout << c16 << ' ' << p16 << '\n';
    std::cout << c32 << ' ' << p32 << '\n';
    std::wcout << c16 << ' ' << p16 << '\n';
    std::wcout << c32 << ' ' << p32 << '\n';
}
```

Теперь код вызывает следующие диагностические сообщения:

```Output
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,wchar_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char32_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char32_t)': attempting to reference a deleted function
```

Вы можете вернуть старое поведение во всех режимах языка, преобразуя типы символов в **`unsigned int`** или типы указателей на символы в `const void*`:

```c++
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << (unsigned)cw << ' ' << (const void*)pw << '\n'; // Outputs "120 0052B1C0"
    std::cout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::cout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
    std::wcout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::wcout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
}
```

### <a name="changed-return-type-of-stdpow-for-stdcomplex"></a>Изменен тип возвращаемого значения `std::pow()` для `std::complex`

Ранее реализация MSVC правил повышения для типа возвращаемого значения шаблона функции `std::pow()` была неправильной. Например, раньше функция `pow(complex<float>, int)` возвращала тип `complex<float>`. Теперь она правильно возвращает тип `complex<double>`. Исправление было реализовано безусловно для всех режимов соответствия стандартам в Visual Studio 2019 версии 16.6.

Это изменение может привести к ошибкам компилятора. Например, ранее можно было умножить `pow(complex<float>, int)` на **`float`** . Поскольку `complex<T> operator*` ожидает аргументы одинакового типа, следующий пример теперь вызывает ошибку компилятора C2676: `binary '*': 'std::complex<double>' does not define this operator or a conversion to a type acceptable to the predefined operator`.

```cpp
// pow_error.cpp
// compile by using: cl /EHsc /nologo /W4 pow_error.cpp
#include <complex>

int main() {
    std::complex<float> cf(2.0f, 0.0f);
    (void) (std::pow(cf, -1) * 3.0f);
}
```

Существует множество способов исправления.

- Измените тип множимого **`float`** на **`double`** . Этот аргумент можно преобразовать непосредственно в `complex<double>`, чтобы обеспечить соответствие типу, возвращаемому `pow`.

- Ограничьте результат `pow` типом `complex<float>`, выполнив `complex<float>{pow(ARG, ARG)}`. Затем можно будет умножить этот результат на значение с типом **`float`** .

- Передайте в `pow` тип **`float`** , а не **`int`** . Эта операция может занять больше времени.

- В некоторых случаях можно вообще не использовать `pow`. Например, `pow(cf, -1)` можно заменить на операцию деления.

### <a name="switch-related-warnings-for-c"></a>Предупреждения в C, связанные с оператором switch

Начиная с Visual Studio 2019 версии 16.6, компилятор реализует некоторые существовавшие ранее предупреждения C++ для кода, скомпилированного как код C. На разных уровнях теперь включены следующие предупреждения: C4060, C4061, C4062, C4063, C4064, C4065, C4808 и C4809. Предупреждения C4065 и C4060 по умолчанию отключены в C.

Предупреждения активируются, если отсутствуют операторы **`case`** , не определены **`enum`** или определены неверные параметры типа **`bool`** (то есть тех, что содержат слишком много операторов case). Пример:

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
        default: break; // C4809: switch statement has redundant 'default' label;
                        // all possible 'case' labels are given
    }
}
```

Чтобы исправить этот код, удалите лишний оператор case **`default`** :

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
    }
}
```

### <a name="unnamed-classes-in-typedef-declarations"></a>Безымянные классы в объявлениях `typedef`

Начиная с Visual Studio 2019 версии 16.6, поведение объявлений **`typedef`** ограничено для соответствия предложению [P1766R1](https://wg21.link/P1766R1). В этом обновлении безымянные классы в объявлении **`typedef`** могут содержать только следующие элементы:

- нестатические элементы данных;
- классов-элементов;
- перечисления элементов;
- инициализаторы элементов по умолчанию.

Те же ограничения применяются рекурсивно к каждому вложенному классу. Ограничение должно обеспечить простоту структур с именами **`typedef`** для связывания. Они должны быть достаточно простыми, чтобы не нужно было вычислять связывания до того, как компилятор дойдет до имени **`typedef`** для связывания.

Это изменение влияет на все режимы соответствия стандартам компилятора. В режиме по умолчанию ( **`/std:c++14`** ) и режиме **`/std:c++17`** компилятор выдает предупреждение C5208 для кода, который не соответствует стандартам. Если указан параметр **`/permissive-`** , компилятор выдает предупреждение C5208 как ошибку в режиме **`/std:c++14`** , а в режиме **`/std:c++17`** выдает ошибку C7626. Компилятор выдает ошибку C7626 для кода, не соответствующего требованиям, если указан параметр **`/std:c++latest`** .

В приведенном ниже примере показаны конструкции, которые теперь нельзя использовать в безымянных структурах. В зависимости от указанного режима соответствия стандартам, выдаются ошибки или предупреждения C5208 или C7626:

```cpp
struct B { };
typedef struct : B { // inheriting from 'B'; ill-formed
    void f(); // ill-formed
    static int i; // ill-formed
    struct U {
        void f(); // nested class has non-data member; ill-formed
    };
    int j = 10; // default member initializer; ill-formed
} S;
```

Приведенный выше код можно исправить, присвоив безымянному классу имя:

```cpp
struct B { };
typedef struct S_ : B {
    void f();
    static int i;
    struct U {
        void f();
    };
    int j = 10;
} S;
```

### <a name="default-argument-import-in-ccli"></a>Импорт аргументов по умолчанию в C++/CLI

Растущее число интерфейсов API имеет в .NET Core аргументы по умолчанию. Вот почему теперь поддерживается импорт аргументов по умолчанию в C++/CLI. Это изменение может нарушить работу существующего кода, в котором объявлено несколько перегрузок, как показано в следующем примере:

```cpp
public class R {
    public void Func(string s) {}   // overload 1
    public void Func(string s, string s2 = "") {} // overload 2;
}
```

При импорте этого класса в C++/CLI вызов одной из перегрузок приводит к ошибке:

```cpp
    (gcnew R)->Func("abc"); // error C2668: 'R::Func' ambiguous call to overloaded function
```

Компилятор выдает ошибку C2668, потому что обе перегрузки соответствуют этому списку аргументов. Во второй перегрузке второй аргумент заполняется аргументом по умолчанию. Чтобы обойти эту проблему, удалите избыточную перегрузку (1). Также можно использовать полный список аргументов и явно указать аргументы по умолчанию.

## <a name="conformance-improvements-in-visual-studio-2019-version-167"></a><a name="improvements_167"></a> Улучшения соответствия в Visual Studio 2019 версии 16.7

### <a name="definition-of-is-trivially-copyable"></a>Определение *is trivially copyable*

В C++20 изменилось определение *is trivially copyable*. Если у класса есть нестатический элемент данных, имеющий тип с квалификатором **`volatile`** , то этот элемент больше не подразумевает, что создаваемые компилятором конструкторы копирования или перемещения или соответствующий оператор присваивания являются нетривиальными. Комитет по стандартизации C++ применил это изменение в виде отчета об ошибках, имеющего обратное действие. В MSVC поведение компилятора не меняется в разных языковых режимах, таких как **`/std:c++14`** или **`/std:c++latest`** .

Вот пример этого нового поведения:

```cpp
#include <type_traits>

struct S
{
    volatile int m;
};

static_assert(std::is_trivially_copyable_v<S>, "Meow!");
```

Этот код не компилируется в версиях MSVC до Visual Studio 2019 версии 16.7. Существует предупреждение компилятора, отключенного по умолчанию, которое можно использовать для обнаружения этого изменения. Если вы компилируете приведенный выше код с помощью **`cl /W4 /w45220`** , вы увидите следующее предупреждение:

предупреждение C5220 `'S::m': a non-static data member with a volatile qualified type no longer implies that compiler generated copy/move constructors and copy/move assignment operators are non trivial`

### <a name="pointer-to-member-and-string-literal-conversions-to-bool-are-narrowing"></a>Сужающие преобразования указателя на элемент и строкового литерала в `bool`

Комитет по стандартизации C++ недавно применил отчет об ошибках [P1957R2](https://wg21.link/p1957r2), который считает `T*` ->  **`bool`** сужающим преобразованием. Компилятор MSVC устранил ошибку в реализации, которая ранее выполняла диагностику `T*` ->  **`bool`** на предмет сужения, но не обнаруживала преобразования строкового литерала в **`bool`** или указателя на элемент в **`bool`** .

Следующая программа с неправильным форматом в Visual Studio 2019 версии 16.7:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" }); // error: conversion from 'const char [8]' to 'bool' requires a narrowing conversion

    int (X::* p) = nullptr;
    f(X { p }); // error: conversion from 'int X::*' to 'bool' requires a narrowing conversion
}
```

Чтобы исправить этот код, либо добавьте явные сравнения для **`nullptr`** , либо избегайте контекстов, в которых сужающие преобразования имеют неправильный формат:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" != nullptr }); // Absurd, but OK

    int (X::* p) = nullptr;
    f(X { p != nullptr }); // OK
}
```

### <a name="nullptr_t-is-only-convertible-to-bool-as-a-direct-initialization"></a>`nullptr_t` можно преобразовать только в `bool` как прямую инициализацию

В C++11 **`nullptr`** можно преобразовать только в **`bool`** в качестве *прямого преобразования* (например, при инициализации **`bool`** с помощью заключенного в фигурные скобки списка инициализаторов). Это ограничение никогда принудительно не применялось к MSVC. MSVC теперь реализует правило в [`/permissive-`](../build/reference/permissive-standards-conformance.md). Неявные преобразования теперь диагностируются как с неправильным форматом. Контекстное преобразование в **`bool`** по-прежнему разрешено, так как `bool b(nullptr)` прямой инициализации является допустимым.

В большинстве случаев ошибку можно исправить, заменив **`nullptr`** на **`false`** , как показано в этом примере:

```cpp
struct S { bool b; };
void g(bool);
bool h() { return nullptr; } // error, should be 'return false;'

int main() {
    bool b1 = nullptr; // error: cannot convert from 'nullptr' to 'bool'
    S s { nullptr }; // error: cannot convert from 'nullptr' to 'bool'
    g(nullptr); // error: cannot convert argument 1 from 'nullptr' to 'bool'

    bool b2 { nullptr }; // OK: Direct-initialization
    if (!nullptr) {} // OK: Contextual conversion to bool
}
```

### <a name="conforming-initialization-behavior-for-array-initializations-with-missing-initializers"></a>Согласование поведения инициализации для инициализаций массива с отсутствующими инициализаторами

Ранее в MSVC было не согласованное поведение для инициализаций массива с отсутствующими инициализаторами. MSVC всегда называется конструктором по умолчанию для каждого элемента массива, который не имеет инициализатора. Стандартным поведением является инициализация каждого элемента с помощью пустого списка инициализаторов, заключенных в фигурные скобки ( **`{}`** ). Контекст инициализации для пустого списка инициализаторов, заключенных в фигурные скобки, — это инициализация копии, которая не допускает вызовов явных конструкторов. Также могут возникнуть различия в среде выполнения, так как использование `{}` для инициализации может вызвать конструктор, который принимает `std::initializer_list`, а не конструктор по умолчанию. Такое поведение согласования включается в [`/permissive-`](../build/reference/permissive-standards-conformance.md).

Вот пример этого измененного поведения:

```cpp
struct B {
    explicit B() {}
};

void f() {
    B b1[1]{}; // Error in /permissive-, because aggregate init calls explicit ctor
    B b2[1]; // OK: calls default ctor for each array element
}
```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a><a name="update_160"></a> Исправления ошибок и изменения в поведении в Visual Studio 2019

### <a name="reinterpret_cast-in-a-constexpr-function"></a>`reinterpret_cast` в функции `constexpr`

**`reinterpret_cast`** нельзя использовать в функции **`constexpr`** . Компилятор Microsoft C++ раньше отклонял **`reinterpret_cast`** , только если он использовался в контексте **`constexpr`** . В Visual Studio 2019 во всех стандартных режимах языка компилятор правильно выполняет диагностику **`reinterpret_cast`** в определении функции **`constexpr`** . Следующий код теперь вызывает ошибку C3615: `constexpr function 'f' cannot result in a constant expression`.

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

Чтобы избежать этой ошибки, удалите модификатор **`constexpr`** из объявления функции.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Правильная диагностика для конструктора диапазонов basic_string

В Visual Studio 2019 конструктор диапазонов `basic_string` больше не подавляет диагностику компилятора с помощью **`static_cast`** . Приведенный ниже код компилируется без предупреждений в Visual Studio 2017, несмотря на возможную потерю данных при преобразовании из **`wchar_t`** в **`char`** при инициализации `out`:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 правильно выдает предупреждение C4244: `'argument': conversion from 'wchar_t' to 'const _Elem', possible loss of data`. Чтобы избежать этого предупреждения, можно инициализировать std::string, как показано в следующем примере:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>Неправильные вызовы `+=` и `-=` в `/clr` или `/ZW` теперь корректно обнаруживаются

В Visual Studio 2017 появилась ошибка, из-за которой компилятор пропускал ошибки без предупреждений и не создавал код для недопустимых вызовов **`+=`** и **`-=`** в **`/clr`** или **`/ZW`** . Следующий код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 корректно вызывает ошибку C2845: `'System::String ^': pointer arithmetic not allowed on this type`.

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Чтобы избежать данной ошибки в этом примере, используйте оператор **`+=`** с методом `ToString()`: `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Инициализаторы для встроенных статических элементов данных

Доступ к недопустимым элементам в инициализаторах **`inline`** и **`static constexpr`** теперь определяется правильно. Следующий пример компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 в режиме **`/std:c++17`** корректно вызывает ошибку C2248: `cannot access private member declared in class 'X'`.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

Чтобы избежать этой ошибки, объявите элемент `X::c` как защищенный:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>Возобновлено использование C4800

В MSVC ранее создавалось предупреждение о производительности C4800 для неявных преобразований в **`bool`** . Это предупреждение было слишком назойливым и его нельзя было подавить, в результате чего мы решили удалить его в Visual Studio 2017. Но за время работы Visual Studio 2017 мы получили множество отзывов о полезности этого предупреждения. В выпуске Visual Studio 2019 мы возвращаем предупреждение C4800, тщательно настроив его и дополнив пояснительным предупреждением C4165. Оба этих предупреждения легко подавить: либо с помощью явного приведения, либо путем сравнения с 0 соответствующего типа. C4800 — это по умолчанию отключенное предупреждение уровня 4, а C4165 — это по умолчанию отключенное предупреждение уровня 3. Их можно обнаружить с помощью параметра компилятора **`/Wall`** .

В следующем примере возникают предупреждения C4800 и C4165 в режиме **`/Wall`** :

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Чтобы избежать предупреждений в предыдущем примере, можно написать следующий код:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Функция-член локального класса не имеет тела

В Visual Studio 2017 предупреждение C4822 `Local class member function doesn't have a body` возникает только в том случае, если явно задан параметр компилятора **`/w14822`** . Оно не отображается, если задан параметр **`/Wall`** . В Visual Studio 2019 C4822 является предупреждением, отключенным по умолчанию, которое можно обнаружить в **`/Wall`** без явного задания **`/w14822`** .

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-if-constexpr-statements"></a>Тела шаблонов функций, содержащие операторы `if constexpr`

Для тел шаблонов функций, содержащих операторы **`if constexpr`** , включены некоторые проверки [`/permissive-`](../build/reference/permissive-standards-conformance.md), связанные с синтаксическим анализом. Например, в Visual Studio 2017 следующий код вызывает ошибку C7510 `'Type': use of dependent type name must be prefixed with 'typename'` только в том случае, если параметр **`/permissive-`** не задан. В Visual Studio 2019 тот же код вызывает ошибки независимо от того, задан ли параметр **`/permissive-`** :

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}
```

Чтобы избежать этой ошибки, добавьте ключевое слово **`typename`** в объявление `a`: `typename T::Type a;`.

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Встроенный код сборки не поддерживается в лямбда-выражении

Недавно команда Microsoft C++ узнала о проблеме безопасности, из-за которой использование встроенного ассемблера в лямбда-выражении могло привести к повреждению `ebp` (регистра обратного адреса) во время выполнения. Злоумышленник может воспользоваться этим сценарием. Встроенный ассемблер поддерживается только на 32-разрядной (x86) платформе и плохо взаимодействует с остальными функциями компилятора. Учитывая эти факты и характер проблемы, самым надежным решением было запретить встроенный ассемблер в лямбда-выражении.

Мы нашли "в реальной жизни" только один вариант применения встроенного ассемблера в лямбда-выражении, а именно получение обратного адреса. В этом сценарии можно получить обратный адрес на всех платформах, просто используя `_ReturnAddress()` в компиляторе.

Следующий код вызывает ошибку C7552 `inline assembler is not supported in a lambda` как в Visual Studio 2017 версии 15.9, так и в Visual Studio 2019:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

Чтобы избежать этой ошибки, переместите код сборки в именованную функцию, как показано в следующем примере:

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmove_iterator"></a>Отладка перечислителя и `std::move_iterator`

Функция отладки итераторов теперь может правильно развертывать `std::move_iterator`. Например, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` теперь использует быстрый путь `memcpy`.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>Исправления для принудительного применения ключевого слова \<xkeycheck.h>

Исправлено принудительное применение стандартной библиотеки в \<xkeycheck.h> для макросов, заменяющих ключевое слово. Теперь библиотека выдает ключевое слово фактически обнаруженной проблемы вместо сообщения общего характера. Также поддерживаются ключевые слова C ++ 20, а IntelliSense не сообщает, что случайные ключевые слова являются макросами.

### <a name="allocator-types-no-longer-deprecated"></a>Типы распределителей теперь не считаются нерекомендуемыми

`std::allocator<void>`, `std::allocator::size_type` и `std::allocator::difference_type` теперь не считаются нерекомендуемыми.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Правильное предупреждение для сужающих преобразований строк

Из `std::string` удален лишний вызов **`static_cast`** , который не соответствовал стандарту и случайно подавлял предупреждения о сужении C4244. Попытка вызвать `std::string::string(const wchar_t*, const wchar_t*)` теперь правильно выдает предупреждение C4244 `narrowing a wchar_t into a char`.

### <a name="various-fixes-for-filesystem-correctness"></a>Различные исправления для правильности \<filesystem>

- Исправлен сбой `std::filesystem::last_write_time` при попытке изменить последнее время записи каталога.
- Теперь конструктор `std::filesystem::directory_entry` сохраняет результат сбоя, а не создает исключение, если задан несуществующий целевой путь.
- Версия `std::filesystem::create_directory` с двумя параметрами была изменена для вызова версии с одним параметром, так как базовая функция `CreateDirectoryExW` использовала бы `copy_symlink`, если бы `existing_p` был символьной ссылкой.
- `std::filesystem::directory_iterator` больше не завершается сбоем при обнаружении неработающей символьной ссылки.
- `std::filesystem::space` теперь принимает относительные пути.
- `std::filesystem::path::lexically_relative` больше не путается из-за конечных знаков косой черты, как сообщалось в [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Найдено обходное решение для проблемы, при которой `CreateSymbolicLinkW` отклонял пути с символами косой черты в `std::filesystem::create_symlink`.
- Найдено обходное решение для проблемы с функцией `delete` удаления режима POSIX, которая существовала в Windows 10 LTSB 1609, но в действительности не удаляла файлы.
- Конструкторы копий `std::boyer_moore_searcher` и `std::boyer_moore_horspool_searcher` и операторы присваивания копий теперь действительно копируют элементы.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Параллельные алгоритмы в Windows 8 и более поздних версий

Библиотека параллельных алгоритмов теперь правильно использует реальное семейство `WaitOnAddress` в Windows 8 и более поздних версий вместо того, чтобы всегда использовать Windows 7 и более ранние фиктивные версии.

### <a name="stdsystem_categorymessage-whitespace"></a>Пробелы в `std::system_category::message()`

`std::system_category::message()` теперь удаляет конечный пробел из возвращенного сообщения.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>Деление на ноль в `std::linear_congruential_engine`

Некоторые условия, приводящие к тому, что `std::linear_congruential_engine` вызывает деление на ноль, были исправлены.

### <a name="fixes-for-iterator-unwrapping"></a>Исправления для распаковывания итератора

Некоторые механизмы распаковывания итератора впервые были представлены для интеграции пользователя и программиста в Visual Studio 2017 версии 15.8. Это описано в записи блога команды разработчиков C++ [о функциях STL и исправлениях ошибок в VS 2017 15.8](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/). Этот механизм больше не выполняет извлечение итераторов из оболочки, основанных на итераторах стандартной библиотеки. Например, пользователь, который происходит от `std::vector<int>::iterator` и пытается настроить поведение, теперь получает настроенное поведение при вызове алгоритмов стандартной библиотеки, а не поведение указателя.

Функция неупорядоченного контейнера `reserve` теперь действительно резервирует N элементов, как описано в [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>Обработка времени

- Ранее некоторые значения времени, которые передавались в библиотеку параллелизма, вызывали переполнение, например `condition_variable::wait_for(seconds::max())`. Эти исправленные переполнения ранее изменяли поведение псевдослучайным образом в течение 29-дневного цикла (когда значение миллисекунд uint32_t принималось с переполнением в базовые API Win32).

- Заголовок \<ctime> теперь правильно объявляет `timespec` и `timespec_get` в пространстве имен `std`, а также в глобальном пространстве имен.

### <a name="various-fixes-for-containers"></a>Различные исправления для контейнеров

- Многие функции внутреннего контейнера стандартной библиотеки стали закрытыми для повышения эффективности IntelliSense. В последующих выпусках MSVC ожидаются дополнительные исправления, которые позволят объявлять элементы закрытыми.

- Проблемы правильности безопасности исключения, при которых контейнеры на основе узла, например `list`, `map` и `unordered_map`, повреждались, теперь исправлены. Во время операции переназначения `propagate_on_container_copy_assignment` или `propagate_on_container_move_assignment` мы освобождаем граничный узел контейнера с помощью старого распределителя, выполняем назначение POCCA/POCMA в старом распределителе, а затем пробуем получить граничный узел из нового распределителя. Если это распределение не удавалось, контейнер становился поврежденным. Он даже не мог быть уничтожен, так как обладание граничным узлом является инвариантной жесткой структурой данных. Этот код был исправлен так, чтобы создавать граничный узел, используя распределитель исходного контейнера перед удалением имеющегося граничного узла.

- Контейнеры были исправлены и всегда копируют, перемещают или меняют распределители согласно `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` и `propagate_on_container_swap` даже для распределителей, объявленных `is_always_equal`.

- Добавлены перегрузки для компонентных функций слияния и извлечения контейнеров, которые принимают контейнеры rvalue. Дополнительные сведения см. в документе [P0083 "Соединение карт и наборов"](https://wg21.link/p0083r3).

### <a name="stdbasic_istreamread-processing-of-rn--n"></a>Обработка `\r\n`` => `\n` в `std::basic_istream::read`

`std::basic_istream::read` исправлен так, чтобы не записывать временные данные в части предоставленного буфера при обработке операции `\r\n` => `\n`. Это изменение несколько нивелирует преимущество в производительности, достигнутое в Visual Studio 2017 15.8 для операций чтения размером более 4 КБ. Но при этом сохраняется повышенная эффективность за счет избавления от трех виртуальных вызовов на каждый символ.

### <a name="stdbitset-constructor"></a>Конструктор `std::bitset`

Конструктор `std::bitset` теперь не считывает единицы и нули в обратном порядке для больших наборов битов.

### <a name="stdpairoperator-regression"></a>Регрессия в `std::pair::operator=`

Исправлена регрессия в операторе присваивания `std::pair`, которая появилась при реализации [LWG 2729 "Отсутствует SFINAE для std::pair::operator="](https://cplusplus.github.io/LWG/issue2729). Теперь снова правильно принимаются типы, которые можно преобразовывать в `std::pair`.

### <a name="non-deduced-contexts-for-add_const_t"></a>Невыводимые контексты для `add_const_t`

Исправлена ошибка признаков дополнительного типа, где `add_const_t` и связанные функции должны быть невыводимым контекстом. Другими словами, `add_const_t` должен быть псевдонимом для `typename add_const<T>::type`, а не `const T`.

## <a name="bug-fixes-and-behavior-changes-in-162"></a><a name="update_162"></a> Исправления ошибок и изменения в поведении в версии 16.2

### <a name="const-comparators-for-associative-containers"></a>Константные блоки сравнения для ассоциативных контейнеров

Код для поиска и вставки в [set](../standard-library/set-class.md), [map](../standard-library/map-class.md), [multiset](../standard-library/multiset-class.md) и [multimap](../standard-library/multimap-class.md) был объединен для уменьшения размера кода. Операции вставки теперь вызывают сравнение "меньше чем" для функтора сравнения **`const`** , как это делали ранее операции поиска. Следующий код компилируется в Visual Studio 2019 версии 16.1 и более ранних версиях, но вызывает C3848 в Visual Studio 2019 версии 16.2:

```cpp
#include <iostream>
#include <map>

using namespace std;

struct K
{
   int a;
   string b = "label";
};

struct Comparer  {
   bool operator() (K a, K b) {
      return a.a < b.a;
   }
};

map<K, double, Comparer> m;

K const s1{1};
K const s2{2};
K const s3{3};

int main() {

   m.emplace(s1, 1.08);
   m.emplace(s2, 3.14);
   m.emplace(s3, 5.21);

}
```

Чтобы избежать этой ошибки, используйте оператор сравнения **`const`** :

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-version-167"></a><a name="updates_167"></a> Исправление ошибок и изменения в поведении в Visual Studio 2019 версии 16.7

### <a name="initialization-of-class-members-with-overloaded-names-is-correctly-sequenced"></a>Инициализация элементов класса с перегруженными именами правильно упорядочена

Мы обнаружили ошибку во внутреннем представлении элементов данных класса, если имя типа также перегружено как имя элемента данных. Эта ошибка привела к несогласованности при агрегатной инициализации и порядке инициализации элементов. Созданный код инициализации теперь является правильным. Однако это изменение может привести к ошибкам или предупреждениям в источнике, который случайно полагался на элементы с неправильным порядком, как показано в следующем примере:

```cpp
// Compiling with /w15038 now gives:
// warning C5038: data member 'Outer::Inner' will be initialized after data member 'Outer::v'
struct Outer {
    Outer(int i, int j) : Inner{ i }, v{ j } {}

    struct Inner { int x; };
    int v;
    Inner Inner; // 'Inner' is both a type name and data member name in the same scope
};
```

В предыдущих версиях конструктор неправильно инициализирует элемент данных `Inner` перед элементом данных `v`. (Стандарт C++ требует, чтобы порядок инициализации совпадал с порядком объявления элементов). Теперь, когда созданный код соответствует стандарту, список инициализации элементов является неупорядоченным. Компилятор выдает предупреждение для этого примера. Чтобы устранить эту проблему, измените порядок в списке инициализации элементов в соответствии с порядком объявления.

### <a name="overload-resolution-involving-integral-overloads-and-long-arguments"></a>Разрешение перегрузки, включающее целочисленные перегрузки и аргументы `long`

Стандарт C++ требует ранжирования **`long`** для преобразования **`int`** в качестве стандартного преобразования. Предыдущие компиляторы MSVC неправильно ранжируют его как целочисленное повышение уровня, ранги которого более высокие для разрешения перегрузки. Это ранжирование может привести к успешному разрешению перегрузки, если оно считается неоднозначным.

Компилятор теперь правильно рассматривает ранг в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md). Недопустимый код диагностируется правильно, как показано в следующем примере:

```cpp
void f(long long);
void f(int);

int main() {
    long x {};
    f(x); // error: 'f': ambiguous call to overloaded function
    f(static_cast<int>(x)); // OK
}
```

Устранить эту проблему можно несколькими способами:

- В месте вызова измените тип переданного аргумента на **`int`** . Вы можете либо изменить тип переменной, либо привести ее.

- Если имеется много мест вызова, можно добавить другую перегрузку, принимающую аргумент **`long`** . В этой функции приведите и переадресуйте аргумент к перегрузке **`int`** .

### <a name="use-of-undefined-variable-with-internal-linkage"></a>Использование неопределенной переменной с внутренней компоновкой

Версии MSVC до принятия Visual Studio 2019 версии 16.7 используют объявленную переменную (не определена) **`extern`** с внутренней компоновкой. Такие переменные не могут быть определены в другой единице трансляции и не могут формировать допустимую программу. Теперь компилятор выполняет диагностику этого случая во время компиляции. Ошибка аналогична ошибке для неопределенных статических функций.

```cpp
namespace {
    extern int x; // Not a definition, but has internal linkage because of the anonymous namespace
}

int main()
{
    return x; // Use of 'x' that no other translation unit can possibly define.
}
```

Эта программа ранее была неправильно скомпилирована и скомпонована, но теперь будет выдавать

ошибку C7631: `'anonymous-namespace'::x': variable with internal linkage declared but not defined`.

Такие переменные должны быть определены в той же единице трансляции, в которой они используются. Для этого можно предоставить явный инициализатор или отдельное определение.

### <a name="type-completeness-and-derived-to-base-pointer-conversions"></a>Заполнение типа и преобразования указателя из производного в базовый

В стандартах C++ до C++20 для преобразования из производного класса в базовый не требовалось, чтобы производный класс был полным типом класса. Комитет по стандартизации C++ утвердил изменение (относится ко всем версиям языка C++) в отчете об ошибках, имеющем обратное действие. Это изменение обеспечивает процесс преобразования с признаками типа, например `std::is_base_of`, который требует, чтобы производный класс был полным типом класса.

Ниже приведен пример:

```cpp
template<typename A, typename B>
struct check_derived_from
{
    static A a;
    static constexpr B* p = &a;
};

struct W { };
struct X { };
struct Y { };

// With this change this code will fail as Z1 is not a complete class type
struct Z1 : X, check_derived_from<Z1, X>
{
};

// This code failed before and it will still fail after this change
struct Z2 : check_derived_from<Z2, Y>, Y
{
};

// With this change this code will fail as Z3 is not a complete class type
struct Z3 : W
{
    check_derived_from<Z3, W> cdf;
};
```

Это изменение в поведении применяется ко всем режимам языка C++ компилятора MSVC, а не только **`/std:c++latest`** .

### <a name="narrowing-conversions-are-more-consistently-diagnosed"></a>Более согласованная проверка сужающих преобразований

MSVC выдает предупреждение для сужающих преобразований в инициализаторе списка в фигурных скобках. Ранее компилятор не проверял сужающие преобразования от больших базовых типов **`enum`** до более узких целочисленных типов. (Компилятор неправильно считает их целочисленным повышением уровня вместо преобразования.) Если сужающее преобразование является преднамеренным, можно избежать предупреждения, используя **`static_cast`** для аргумента инициализатора. Или выберите больший целочисленный тип назначения.

Ниже приведен пример использования явного **`static_cast`** для устранения предупреждения:

```cpp
enum E : long long { e1 };
struct S { int i; };

void f(E e) {
    S s = { e }; // warning: conversion from 'E' to 'int' requires a narrowing conversion
    S s1 = { static_cast<int>(e) }; // Suppress warning with explicit conversion
}
```

::: moniker-end

::: moniker range="vs-2017"

## <a name="conformance-improvements-in-visual-studio-2017-rtw-version-150"></a><a name="improvements_150"></a> Улучшения соответствия в Visual Studio 2017 RTW (версия 15.0)

Благодаря поддержке обобщенного выражения **`constexpr`** и NSDMI (нестатическая инициализация элементов данных) для статистических выражений, компилятор Microsoft C++ в Visual Studio 2017 теперь включает все функции, добавленные в стандарте C++14. Обратите внимание, что в компиляторе по-прежнему отсутствуют несколько функций из стандартов C++11 и C++98. Сведения о текущем состоянии компилятора см. в статье [Таблица соответствия Microsoft Visual C++ стандартам языка](../visual-cpp-language-conformance.md).

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++11 Поддержка выражения SFINAE в большем числе библиотек

Продолжается улучшение поддержки выражения SFINAE в компиляторе. Это требуется для дедукции и подстановки аргументов шаблона, когда выражения **`decltype`** и **`constexpr`** могут отображаться в качестве параметров шаблона. Дополнительные сведения см. в разделе [Усовершенствования выражения SFINAE в версии-кандидате Visual Studio 2017](https://devblogs.microsoft.com/cppblog/expression-sfinae-improvements-in-vs-2015-update-3/).

### <a name="c14-nsdmi-for-aggregates"></a>C++14: NSDMI для статистических выражений

Агрегат — это массив или класс без предоставленного пользователем конструктора, без частных или защищенных нестатических элементов данных, без базовых классов и виртуальных функций. Начиная с версии C++14, агрегаты могут содержать инициализаторы элементов. Дополнительные сведения см. в разделе [Инициализаторы членов и статистические выражения](https://wg21.link/n3605).

### <a name="c14-extended-constexpr"></a>C++14: Расширенный `constexpr`

Выражения, объявленные как **`constexpr`** , теперь могут содержать определенные виды объявлений, операторы if и switch, операторы циклов, а также изменения объектов, время существования которых началось с вычисления выражения **`constexpr`** . Кроме того, теперь не требуется, чтобы нестатическая функция-член **`constexpr`** явным образом была **`const`** . Дополнительные сведения см. в статье [Нестрогие ограничения для функций `constexpr`](https://wg21.link/n3652).

### <a name="c17-terse-static_assert"></a>C++17 Сжатое `static_assert`

Параметр сообщения для **`static_assert`** является необязательным. Дополнительные сведения см. в разделе [Расширение static_assert, v2](https://wg21.link/n3928).

### <a name="c17-fallthrough-attribute"></a>C++17: атрибут `[[fallthrough]]`

В режиме **`/std:c++17`** атрибут `[[fallthrough]]` можно использовать в контексте инструкций switch как указание для компилятора передать управление вниз. Этот атрибут позволит избежать вывода предупреждений компилятора в таких ситуациях. Дополнительные сведения см. в разделе [Формулировка для атрибута `[[fallthrough]]`](https://wg21.link/p0188r0).

### <a name="generalized-range-based-for-loops"></a>Обобщенный цикл for на основе диапазона

Циклы for на основе диапазона больше не требуют, чтобы `begin()` и `end()` возвращали объекты одного типа. Это изменение позволяет `end()` возвращать граничную метку согласно использованию в диапазонах [range-v3](https://github.com/ericniebler/range-v3) и технической спецификации по диапазонам (которая уже готова, но еще не опубликована). Дополнительные сведения см. в разделе [Обобщение цикла `for` на основе диапазона](https://wg21.link/p0184r0).

## <a name="conformance-improvements-in-153"></a><a name="improvements_153"></a> Улучшения соответствия в 15.3

### <a name="constexpr-lambdas"></a>Лямбда-выражения `constexpr`

Лямбда-выражения теперь можно использоваться в константных выражениях. Дополнительные сведения см. в разделе [Лямбда-выражения `constexpr` в C++](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr` в шаблонах функций

Шаблон функции может содержать операторы **`if constexpr`** для поддержки ветвления во время компиляции. Дополнительные сведения см. в статье [Инструкции `if constexpr`](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Операторы выбора с инициализаторами

Оператор **`if`** может включать инициализатор, который вводит переменную в области видимости блока внутри самого оператора. Дополнительные сведения см. в разделе [Операторы `if` с инициализатором](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybe_unused-and-nodiscard-attributes"></a>Атрибуты `[[maybe_unused]]` и `[[nodiscard]]`

Новый атрибут `[[maybe_unused]]` подавляет предупреждения о неиспользовании сущности. Атрибут `[[nodiscard]]` создает предупреждение, если при вызове функции отбрасывается возвращаемое значение. Дополнительные сведения см. в статье [Attributes in C++](../cpp/attributes.md) (Атрибуты в C++).

### <a name="using-attribute-namespaces-without-repetition"></a>Использование пространств имен атрибутов без повторения

Новый синтаксис позволяет включать в список атрибутов всего один идентификатор пространства имен. Дополнительные сведения см. в статье [Attributes in C++](../cpp/attributes.md) (Атрибуты в C++).

### <a name="structured-bindings"></a>Структурированные привязки

Теперь можно одним объявлением сохранить значение с отдельными именами компонентов, когда значение является массивом, `std::tuple` или `std::pair`, либо когда все его нестатические элементы данных являются открытыми. Дополнительные сведения см. в разделах [Структурированные привязки](https://wg21.link/p0144r0) и [Возврат нескольких значений из функции](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Правила создания для значений `enum class`

Теперь происходит неявное преобразование для ограниченных перечислений, которое является не ограничивающим. Преобразование выполняется из базового типа ограниченного перечисления в само перечисление. Преобразование доступно, если его определение не вводит перечислитель и если источник использует синтаксис инициализации списка. Дополнительные сведения см. в разделе [Правила конструкции значений класса перечисления](https://wg21.link/p0138r2) и [Перечисления](../cpp/enumerations-cpp.md#no_enumerators).

### <a name="capturing-this-by-value"></a>Захват `*this` по значению

Теперь лямбда-выражение может обращаться к объекту **`*this`** по значению. Это позволяет использовать лямбда-выражения в сценариях с параллельными и асинхронными операциями, особенно на новых архитектурах компьютеров. Дополнительные сведения см. в документе о [захвате объекта \*this по значению в виде \[=,\*this\] в лямбда-выражении](https://wg21.link/p0018r3).

### <a name="removing-operator-for-bool"></a>Удаление `operator++` для `bool`

`operator++` больше не поддерживается для типов **`bool`** . Дополнительные сведения см. в документе об [удалении устаревшего объекта operator++(bool)](https://wg21.link/p0002r1).

### <a name="removing-deprecated-register-keyword"></a>Удаление нерекомендуемого ключевого слова `register`

Ключевое слово **`register`** , ранее признанное нерекомендуемым (и игнорируемое компилятором), теперь удалено из языка. Дополнительные сведения см. в документе об [удалении нерекомендуемого ключевого слова `register`](https://wg21.link/p0001r1).

## <a name="conformance-improvements-in-155"></a><a name="improvements_155"></a> Улучшения соответствия в 15.5

Функции, отмеченные как \[14], доступны без дополнительных условий даже в режиме **`/std:c++14`** .

### <a name="new-compiler-switch-for-extern-constexpr"></a>Новый параметр компилятора для `extern constexpr`

В более ранних версиях Visual Studio компилятор всегда использовал для переменной **`constexpr`** внутреннюю компоновку, даже если эта переменная была помечена как **`extern`** . В Visual Studio 2017 версии 15.5 новый параметр компилятора ([`/Zc:externConstexpr`](../build/reference/zc-externconstexpr.md)) обеспечивает корректное поведение, соответствующее стандартам. Дополнительные сведения см. в разделе о [компоновке extern constexpr](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Удаление динамических спецификаций исключений

[P0003R5](https://wg21.link/p0003r5): динамические спецификации исключений в C++11 стали нерекомендуемыми. Эта функция удалена из C++17, но (по-прежнему) нерекомендуемая спецификация `throw()` сохраняется исключительно в качестве псевдонима для `noexcept(true)`. Дополнительные сведения см. в разделе [Удаление спецификации динамических исключений и noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](https://wg21.link/p0005r4): `not_fn` является заменой `not1` и `not2`.

### <a name="rewording-enable_shared_from_this"></a>Изменение формулировки для `enable_shared_from_this`

[P0033R1](https://wg21.link/p0033r1): класс `enable_shared_from_this` добавлен в C++11. Стандарт C++17 обновляет спецификацию, чтобы лучше обрабатывать некоторые пограничные случаи. \[14]

### <a name="splicing-maps-and-sets"></a>Соединение карт и наборов

[P0083R3](https://wg21.link/p0083r3). Эта возможность позволяет извлекать узлы из ассоциативных контейнеров (например, `map`, `set`, `unordered_map`, `unordered_set`), а затем изменять их и вставлять обратно в тот же или другой контейнер с тем же типом узла. (Типичный вариант использования — извлечение узла из `std::map`, изменение ключа и повторная вставка.)

### <a name="deprecating-vestigial-library-parts"></a>Нерекомендуемые части библиотек

[P0174R2](https://wg21.link/p0174r2). Со временем несколько функций стандартной библиотеки C++ были заменены новыми, признаны нецелесообразными или проблемными. Эти функции являются официально нерекомендуемыми в C++17.

### <a name="removing-allocator-support-in-stdfunction"></a>Удаление поддержки распределителя в `std::function`

[P0302R1](https://wg21.link/p0302r1). До появления C++17 шаблон класса `std::function` содержал несколько конструкторов, принимающих аргумент распределителя. Однако использование распределителей в данном контексте было проблематичным, а семантика — неясной. Проблема конструкторов теперь устранена.

### <a name="fixes-for-not_fn"></a>Исправления для `not_fn()`

[P0358R1](https://wg21.link/p0358r1). Новая формулировка `std::not_fn` поддерживает передачу категории значения при вызове класса-оболочки.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](https://wg21.link/p0414r2): внесение изменений `shared_ptr` из Library Fundamentals в C++17. \[14]

### <a name="fixing-shared_ptr-for-arrays"></a>Исправление `shared_ptr` для массивов

[P0497R0](https://wg21.link/p0497r0): исправления поддержки shared_ptr для массивов. \[14]

### <a name="clarifying-insert_return_type"></a>Пояснение `insert_return_type`

[P0508R0](https://wg21.link/p0508r0): ассоциативные и неупорядоченные контейнеры с уникальными ключами имеют функцию-член `insert`, возвращающую `insert_return_type` вложенного типа. Тип возвращаемого значения теперь определяется как специализация типа, который параметризуется по итератору и типу узла контейнера.

### <a name="inline-variables-for-the-standard-library"></a>Встроенные переменные для стандартной библиотеки

[P0607R0](https://wg21.link/p0607r0)

### <a name="annex-d-features-deprecated"></a>Нерекомендуемые функции в приложении D

Приложение D стандарта C++ содержит все функции, признанные нерекомендуемыми, включая `shared_ptr::unique()`, `<codecvt>` и `namespace std::tr1`. Если задан параметр компилятора **`/std:c++17`** , почти все функции стандартной библиотеки в приложении D помечаются как нерекомендуемые. Дополнительные сведения см. в [этой статье](#annex_d).

Пространство имен `std::tr2::sys` в `<experimental/filesystem>` теперь по умолчанию выдает предупреждение о нерекомендуемых функциях при использовании **`/std:c++14`** , а при использовании **`/std:c++17`** оно по умолчанию удалено.

Улучшено соответствие в `<iostream>` за счет отказа от нестандартного расширения (явных специализаций в классе).

Стандартная библиотека теперь использует шаблоны переменных внутренним образом.

Стандартная библиотека была обновлена в соответствии с изменениями компилятора C++17. В обновления входит добавление **`noexcept`** в систему типов, а также удаление спецификаций динамических исключений.

## <a name="conformance-improvements-in-156"></a><a name="improvements_156"></a> Улучшения соответствия в 15.6

### <a name="c17-library-fundamentals-v1"></a>C++17. Основы работы с библиотеками V1

[P0220R1](https://wg21.link/p0220r1) включает технические спецификации основ библиотек для C++17 в стандарт. Содержит обновления для \<experimental/tuple>, \<experimental/optional>, \<experimental/functional>, \<experimental/any>, \<experimental/string_view>, \<experimental/memory>, \<experimental/memory_resource> и \<experimental/algorithm>.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++17 Улучшение выведения аргументов шаблонов класса для стандартной библиотеки

[P0739R0](https://wg21.link/p0739r0). Переместите `adopt_lock_t` в начало списка параметров, чтобы `scoped_lock` разрешил согласованное использование `scoped_lock`. Разрешите конструктору `std::variant` участвовать в разрешении перегрузки в большем числе случаев, чтобы поддерживать присваивание копированием.

## <a name="conformance-improvements-in-157"></a><a name="improvements_157"></a> Улучшения соответствия в 15.7

### <a name="c17-rewording-inheriting-constructors"></a>C++17 Изменение формулировки наследуемых конструкторов

[P0136R1](https://wg21.link/p0136r1) указывает, что объявление **`using`** , которое указывает конструктор, теперь делает соответствующие конструкторы базового класса видимыми для инициализаций производного класса, поэтому можно не объявлять дополнительные конструкторы для производного класса. Это является изменением формулировки по сравнению с C++14. В Visual Studio 2017 версии 15.7 и более поздних в режиме **`/std:c++17`** может оказаться недопустимым или иметь иную семантику код, который нормально работает в C++14 с использованием наследуемых конструкторов.

В следующем примере показана реакция на событие в C++14:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

В следующем примере показана реакция на событие **`/std:c++17`** в Visual Studio 15.7:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

Дополнительные сведения см. в разделе [Конструкторы](../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C++17 Расширенная агрегатная инициализация

[P0017R1](https://wg21.link/p0017r1)

Если конструктор базового класса не является открытым, но доступен производному классу, то в режиме **`/std:c++17`** в Visual Studio 2017 версии 15.7 больше нельзя использовать пустые фигурные скобки для инициализации объекта производного типа.
В следующем примере показана соответствующая реакция на событие в C++14:

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

В C++17 `Derived` теперь считается агрегатным типом. Это означает, что инициализация `Base` через закрытый конструктор по умолчанию происходит непосредственно как часть расширенного правила агрегатной инициализации. Закрытый конструктор `Base` ранее вызывался через конструктор `Derived`, и это работало успешно благодаря объявлению дружественных отношений.
В следующем примере показано поведение C++17 в Visual Studio версии 15.7 в режиме **`/std:c++17`** :

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};
struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17 Объявление параметров шаблона, не являющихся типами, с использованием auto

[P0127R2](https://wg21.link/p0127r2)

В режиме **`/std:c++17`** компилятор теперь может выводить тип аргумента шаблона, не являющегося типом и объявленного с помощью **`auto`** :

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

В результате код C++14 может быть недопустимым или иметь другую семантику. Например, стали допустимыми некоторые перегрузки, которые ранее были недопустимыми. В следующем примере показан код C++14, который компилируется, поскольку вызов `example(p)` привязан к `example(void*);`. В Visual Studio 2017 версии 15.7 в режиме **`/std:c++17`** оптимальным решением будет шаблон функции `example`.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

В следующем примере показан код C++17 в Visual Studio 15.7 в режиме **`/std:c++17`** :

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17 Простые преобразования строк (частично)

[P0067R5](https://wg21.link/p0067r5). Независимые от языкового стандарта функции низкого уровня для преобразования между целыми числами и строками и между числами с плавающей запятой и строками.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20. Отказ от лишнего вырождения (частично)

[P0777R1](https://wg21.link/p0777r1). Проводит различие между концепцией "вырождения" и простым удалением константы или квалификаторов ссылки.  Новый признак типа `remove_reference_t` заменяет `decay_t` в некоторых контекстах. В Visual Studio 2019 реализована поддержка `remove_cvref_t`.

### <a name="c17-parallel-algorithms"></a>C++17 Параллельные алгоритмы

[P0024R2](https://wg21.link/p0024r2). Технические спецификации параллелизма включены в стандарт с небольшими изменениями.

### <a name="c17-hypotx-y-z"></a>C++17: `hypot(x, y, z)`

[P0030R1](https://wg21.link/p0030r1). Добавлены три новые перегрузки в `std::hypot` для типов **`float`** , **`double`** и **`long double`** , у каждой из которых есть три входных параметра.

### <a name="c17-filesystem"></a>C++17: \<filesystem>

[P0218R1](https://wg21.link/p0218r1). Включает технические спецификации файловой системы в стандарт с некоторыми изменениями формулировок.

### <a name="c17-mathematical-special-functions"></a>C++17 Специальные математические функции

[P0226R1](https://wg21.link/p0220r1). Включает предыдущие технические спецификации для специальных математических функций в стандартный заголовок \<cmath>.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++17 Рекомендации по удержанию для стандартной библиотеки

[P0433R2](https://wg21.link/p0433r2). Обновляет до STL, чтобы воспользоваться преимуществами внедрения в C++17 [P0091R3](https://wg21.link/p0091r3), который добавляет поддержку для выведения аргумента шаблона класса.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17 Исправление простых преобразований строк

[P0682R1](https://wg21.link/p0682r1). Перемещение новых функций по простому преобразованию строк из P0067R5 в новый заголовок \<charconv> и другие усовершенствования, включая изменение обработки ошибок для использования `std::errc` вместо `std::error_code`.

### <a name="c17-constexpr-for-char_traits-partial"></a>C++17: `constexpr` для `char_traits` (частично)

[P0426R1](https://wg21.link/p0426r1). Изменения в функциях-членах `length`, `compare` и `find` типа `std::traits_type`, позволяющие использовать `std::string_view` в константных выражениях. (В Visual Studio 2017 версии 15.6 поддерживается только для Clang/LLVM. В версии 15.7, предварительная версия 2, почти полная поддержка и для ClXX.)

## <a name="conformance-improvements-in-159"></a><a name="improvements_159"></a> Улучшения соответствия в 15.9

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>Порядок вычисления слева направо для операторов `->*`, `[]`, `>>` и `<<`

Начиная с C++17, операнды операторов `->*`, `[]`, `>>` и `<<` должны обрабатываться в порядке слева направо. Есть два случая, в которых компилятор не может обеспечить этот порядок:

- если одно из выражений операндов является объектом, передаваемым по значению, или содержит объект, передаваемый по значению;

- при компиляции с использованием **`/clr`** , когда один из операндов является полем объекта или элемента массива.

Компилятор выдает предупреждение [C4866](../error-messages/compiler-warnings/c4866.md), когда он не может обеспечить вычисление слева направо. Компилятор создает это предупреждение только в том случае, если указан режим **`/std:c++17`** или более поздней версии, так как в C++17 добавлено требование обработки этих операторов в порядке слева направо.

Чтобы устранить это предупреждение, сначала определите, требуется ли вычисление операндов слева направо. Например, это может быть необходимо, если вычисление операндов может привести к побочным эффектам, зависящим от порядка. Во многих случаях порядок вычисления операндов не имеет никакого значения. Если порядок вычисления должен быть слева направо, попробуйте передать операнды с использованием ссылки на константу. Это изменение устраняет предупреждение в следующем примере кода.

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="bug-fixes-in-visual-studio-2017-rtw-version-150"></a><a name="update_150"></a> Исправления ошибок в Visual Studio 2017 RTW (версии 15.0)

### <a name="copy-list-initialization"></a>Инициализация копии списка

Visual Studio 2017 правильно вызывает ошибки компилятора, связанные с созданием объектов с помощью списков инициализатора. Эти ошибки не перехватывались в Visual Studio 2015 и могли привести к сбоям или неопределенному поведению среды выполнения. Согласно N4594 13.3.1.7p1 в инициализации копии списка компилятор должен учитывать явный конструктор для разрешения перегрузки. Но он должен выдавать ошибку, если выбирается конкретно эта перегрузка.

Следующие два примера кода компилируются в Visual Studio 2015, но не в Visual Studio 2017.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Чтобы исправить эту ошибку, следует использовать прямую инициализацию:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

В Visual Studio 2015 компилятор ошибочно интерпретировал инициализацию копии списка так же, как обычную инициализацию копии. Он рассматривал только преобразование конструкторов для разрешения перегрузки. В следующем примере Visual Studio 2015 выбирает `MyInt(23)`. Visual Studio 2017 правильно выводит ошибку.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Этот пример аналогичен предыдущему, но выводит другую ошибку. Он выполняется успешно в Visual Studio 2015, а в Visual Studio 2017 с C2668 завершается ошибкой.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Нерекомендуемые определения типов

Теперь Visual Studio 2017 выдает правильное предупреждение для нерекомендуемых определений типов, объявленных в классе или структуре. В следующем примере показана компиляция без предупреждений в Visual Studio 2015. Но в Visual Studio 2017 выводится предупреждение C4996.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### `constexpr`

Visual Studio 2017 правильно выдает ошибку, если левый операнд в операции условного вычисления является недопустимым в контексте constexpr. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017, где он вызывает ошибку C3615`constexpr function 'f' cannot result in a constant expression`:

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

Чтобы исправить эту ошибку, объявите функцию `array::size()` как **`constexpr`** или удалите квалификатор **`constexpr`** из `f`.

### <a name="class-types-passed-to-variadic-functions"></a>Типы классов, передаваемые в функции с переменным числом аргументов

В Visual Studio 2017 классы и структуры, передаваемые в вариадическую функцию, например `printf`, должны быть доступны для простого копирования. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Чтобы исправить эту ошибку, можно вызвать функцию-член, возвращающую тип, доступный для простого копирования,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

или выполнить статическое приведение для преобразования объекта перед его передачей:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Для строк, созданных и управляемых с помощью `CString`, следует использовать предоставленный `operator LPCTSTR()` для приведения объекта `CString` к указателю C, ожидаемому строкой формата.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы в конструкторах класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Эта проблема может привести к сбою или непредсказуемому поведению среды выполнения. Следующий пример компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Чтобы исправить эту ошибку, объявите `operator int()` как **`const`** .

### <a name="access-checking-on-qualified-names-in-templates"></a>Проверка доступа к полным именам в шаблонах

В предыдущих версиях компилятора не выполнялась проверка доступа к полным именам в некоторых контекстах шаблонов. Эта проблема могла помешать ожидаемой работе SFINAE там, где подстановка должна завершиться ошибкой из-за отсутствия доступа к имени. Это могло приводить к сбою или неожиданному поведению среды выполнения из-за того, что компилятор ошибочно вызывал неверную перегрузку оператора. В Visual Studio 2017 выводится ошибка компилятора. Могут возникать разные ошибки, но чаще всего возникает ошибка C2672 `no matching overloaded function found`. Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017:

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>Отсутствующие списки аргументов шаблона

В Visual Studio 2015 и более ранних версиях компилятор не обнаруживал все отсутствующие списки аргументов шаблона. Он не заметил бы, если бы отсутствующий шаблон отобразился в списке параметров шаблона (например, когда аргумент шаблона по умолчанию или параметр шаблона, не являющийся типом, отсутствовали). Эта проблема может привести к непредсказуемому поведению, включая сбои компилятора или непредсказуемое поведение среды выполнения. Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Выражение SFINAE

Чтобы реализовать поддержку выражения SFINAE, компилятор теперь анализирует аргументы **`decltype`** при объявлении шаблонов, а не при создании их экземпляров. Это означает, что независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания. Она обрабатывается немедленно и в этот же момент проверяется на все возможные ошибки.

В следующем примере показана такая ошибка компилятора, возникающая во время объявления.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>Классы, объявляемые в анонимных пространствах имен

Согласно стандарту C++, объявленный внутри анонимного пространства имен класс имеет внутреннюю компоновку и не может быть экспортирован. В Visual Studio 2015 и более ранних версиях это правило не применялось. В Visual Studio 2017 это правило применяется частично. В Visual Studio 2017 в следующем примере возникает ошибка C2201 `const anonymous namespace::S1::vftable: must have external linkage in order to be exported/imported.`.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Инициализаторы по умолчанию для членов класса значения (C++/CLI)

В Visual Studio 2015 и более ранних версиях компилятор допускал (но игнорировал) инициализатор членов по умолчанию для члена класса значений. Инициализатор по умолчанию для класса значений всегда инициализирует члены нулевым значением. Конструктор по умолчанию не допускается. В Visual Studio 2017 инициализаторы членов по умолчанию вызывают ошибку компилятора, как показано в следующем примере:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Индексаторы по умолчанию (C++/CLI)

В Visual Studio 2015 и более ранних версиях в некоторых случаях компилятор неправильно определял свойство по умолчанию как индексатор по умолчанию. Эту проблему удавалось решить благодаря использованию идентификатора **`default`** для доступа к свойству. Это обходное решение само стало создавать проблемы после того, как значение **`default`** было введено как ключевое слово в C++11. В Visual Studio 2017 исправлены ошибки, которые требовали обходного решения. Теперь компилятор выдает ошибку, если для доступа к свойству по умолчанию для класса используется **`default`** .

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

В Visual Studio 2017 оба свойства значения доступны по их именам:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="bug-fixes-in-153"></a><a name="update_153"></a> Исправления ошибок в 15.3

### <a name="calls-to-deleted-member-templates"></a>Вызовы шаблонов удаленного элемента

В предыдущих версиях Visual Studio компилятор в некоторых случаях не сообщал об ошибках при некорректных вызовах шаблона удаленного элемента. Эти вызовы могли вызвать сбои во время выполнения. Следующий код теперь возвращает ошибку C2280 `'int S<int>::f<int>(void)': attempting to reference a deleted function`.

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

Чтобы устранить эту ошибку, объявите элемент `i` как **`int`** .

### <a name="pre-condition-checks-for-type-traits"></a>Проверки предварительных условий для признаков типов

В Visual Studio 2017 версии 15.3 улучшены проверки предварительных условий для признаков типов на более строгое следование стандарту. Одна из проверок проверяет присвоение. Для следующего кода создается ошибка C2139 в Visual Studio 2017 версии 15.3:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Новое предупреждение компилятора и проверки среды выполнения для маршалинга между собственными и управляемыми функциями

Вызов собственных функций из управляемых функций требует маршалинга. Среда CLR выполняет такой маршалинг, но не понимает семантику C++. Если вы передадите собственный объект по значению, CLR вызовет конструктор копии объекта или применит функцию `BitBlt`, что может привести к непредсказуемому поведению в среде выполнения.

Теперь компилятор выдает предупреждение, если во время компиляции находит ошибку, что через границу собственной и управляемой функции передается по значению собственный объект с удаленным конструктором копии. Если компилятор во время компиляции не может получить такую информацию, он внедряет проверку времени выполнения, чтобы программа немедленно вызвала `std::terminate` в случае некорректного маршалинга. В Visual Studio 2017 версии 15.3 следующий код вызывает предупреждение C4606: `'A': passing argument by value across native and managed boundary requires valid copy constructor. Otherwise, the runtime behavior is undefined.`

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshaling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Чтобы устранить такую ошибку, удалите директиву `#pragma managed`, чтобы вызывающая функция стала собственной. Это позволит избежать маршалинга.

### <a name="experimental-api-warning-for-winrt"></a>Экспериментальные предупреждения API для WinRT

API-интерфейсы WinRT, выпускаемые для экспериментов и обратной связи, обозначаются атрибутом `Windows.Foundation.Metadata.ExperimentalAttribute`. В Visual Studio 2017 версии 15.3 при обнаружении этого атрибута компилятор выдает предупреждение C4698. Некоторые API-интерфейсы в предыдущих версиях Windows SDK уже помечены этим атрибутом, поэтому обращения к этим API теперь вызывают указанное выше предупреждение. В новых пакетах SDK для Windows атрибут удален из всех поставляемых типов. Если вы используете более раннюю версию пакета SDK, необходимо подавить эти предупреждения для всех вызовов к поставляемым типам.

Следующий код теперь вызывает предупреждение C4698: `'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' is for evaluation purposes only and is subject to change or removal in future updates`.

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Чтобы отключить это предупреждение, добавьте атрибут #pragma.

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Определение функции-члена шаблона вне строки

В Visual Studio 2017 версии 15.3 появляется сообщение об ошибке, если обнаруживается внешнее определение компонентной функции шаблона, не объявленное в классе. Следующий код теперь вызывает ошибку C2039: `'f': is not a member of 'S'`.

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Чтобы исправить такую ошибку, добавьте в класс следующее объявление:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Попытка получить адрес для указателя `this`

В C++ **`this`** является значением prvalue с типом указателя для X. Вы не можете получить адрес **`this`** или привязать его к ссылке на lvalue. В предыдущих версиях Visual Studio компилятор позволял обойти это ограничение, выполнив приведение типов. В Visual Studio 2017 версии 15.3 компилятор выдает ошибку C2664.

### <a name="conversion-to-an-inaccessible-base-class"></a>Преобразование в недоступный базовый класс

Visual Studio 2017 версии 15.3 выводит сообщение об ошибке при попытке преобразовать тип в недоступный базовый класс. Теперь компилятор вызывает ошибку C2243: `'type cast': conversion from 'D *' to 'B *' exists, but is inaccessible`. Следующий код является некорректным и может привести к сбою в среде выполнения. Теперь компилятор создает ошибку C2243 для такого кода:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Аргументы по умолчанию не допускаются во внешних определениях функций-членов

Аргументы по умолчанию не допускаются во внешних определениях функций-членов в классах шаблонов. Компилятор выдаст предупреждение в режиме **`/permissive`** и критическую ошибку в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md).

В предыдущих версиях Visual Studio следующий некорректный код может вызвать сбой среды выполнения. В Visual Studio 2017 версии 15.3 возникает предупреждение C5034: `'A\<T>::f': an out-of-line definition of a member of a class template cannot have default arguments`.

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

Чтобы устранить такую ошибку, удалите аргумент по умолчанию `= false`.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Использование `offsetof` с обозначением составного члена

Если используется `offsetof(T, m)`, где *m* является "обозначением составного элемента", в Visual Studio 2017 версии 15.3 появится предупреждение при компиляции с параметром **`/Wall`** . Следующий код является некорректным и может привести к сбою во время выполнения. В Visual Studio 2017 версии 15.3 возникает предупреждение C4841: `non-standard extension used: compound member designator in offsetof`.

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Чтобы исправить этот код, отключите предупреждение с помощью директивы pragma или уберите из кода `offsetof`.

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Использование `offsetof` со статическим элементом данных или функцией-членом

Если используется `offsetof(T, m)`, где *m* ссылается на статические данные-член или на функцию-член, Visual Studio 2017 версии 15.3 выдает ошибку. Следующий код вызывает ошибку C4597 `undefined behavior: offsetof applied to member function 'example'` и ошибку C4597 `undefined behavior: offsetof applied to static data member 'sample'`.

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Этот код является некорректным и может привести к сбою во время выполнения. Чтобы устранить такую ошибку, измените код так, чтобы он не создавал неопределенное поведение. Это код не является переносимым и запрещен стандартом C++.

### <a name="new-warning-on-__declspec-attributes"></a><a name="declspec"></a> Новое предупреждение для атрибутов `__declspec`

В Visual Studio 2017 версии 15.3 компилятор больше не игнорирует атрибуты, если `__declspec(...)` применяется перед спецификацией компоновки `extern "C"`. В прошлом компилятор игнорировал такой атрибут, что могло повлиять на работу в среде выполнения. Если установлены параметры **`/Wall`** и **`/WX`** , следующий код вызывает предупреждение C4768: `__declspec attributes before linkage specification are ignored`.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Чтобы устранить это предупреждение, переместите `extern "C"` вперед:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

В версии 15.3 это предупреждение по умолчанию отключено, а в 15.5 — включено. Оно влияет только на код, скомпилированный с параметрами **`/Wall`** **`/WX`** .

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` и вызовы удаленных деструкторов

В предыдущих версиях Visual Studio компилятор не отслеживал возникновение вызовов удаленных деструкторов в контексте выражений, связанных с **`decltype`** . В Visual Studio 2017 версии 15.3 следующий код вызывает ошибку C2280: `'A<T>::~A(void)': attempting to reference a deleted function`.

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>Неинициализированные переменные const

В выпуске Visual Studio 2017 RTW использовалась регрессия, из-за которой компилятор C++ не выдавал диагностических сообщений о том, что переменная **`const`** не инициализирована. Эта регрессия была устранена в Visual Studio 2017 версии 15.3. Следующий код теперь вызывает предупреждение C4132: `'Value': const object should be initialized`.

```cpp
const int Value; //C4132
```

Чтобы исправить эту ошибку, присвойте значение переменной `Value`.

### <a name="empty-declarations"></a>Пустые объявления

Теперь Visual Studio 2017 версии 15.3 предупреждает о пустых объявлениях для всех типов, а не только для встроенных. Теперь для следующего кода создаются предупреждения C4091 уровня 2 для всех четырех объявлений:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Чтобы устранить эти предупреждения, закомментируйте или удалите все пустые объявления. В случаях, когда объекты без имен созданы специально для побочных эффектов (например, RAII), им следует присвоить имена.

Это предупреждение отключено при использовании **`/Wv:18`** и включено по умолчанию на уровне предупреждений W2.

### <a name="stdis_convertible-for-array-types"></a>`std::is_convertible` для типов массивов

В предыдущих версиях компилятора класс [std::is_convertible](../standard-library/is-convertible-class.md) выдавал неверные результаты для типов массива. Из-за этого разработчикам библиотек необходимо было особым образом обрабатывать в компиляторе Microsoft C++ признаки типа `std::is_convertible<...>`. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` проверяет, правильно ли сформировано определение мнимой функции.

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>Частные деструкторы и `std::is_constructible`

Предыдущие версии компилятора не проверяли, является ли деструктор закрытым, при получении результата [std::is_constructible](../standard-library/is-constructible-class.md). Теперь это принимается во внимание. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

Закрытые деструкторы могут сделать тип неконструируемым. При вычислении `std::is_constructible<T, Args...>` подразумевается следующее объявление.

```cpp
   T obj(std::declval<Args>()...)
```

Этот вызов подразумевает вызов деструктора.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: неоднозначное разрешение перегрузки

Предыдущим версиям компилятора иногда не удавалось обнаружить неоднозначность, если при использовании объявлений и при поиске функций по аргументам выявлялись различные кандидаты. Эта ошибка может привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. В следующем примере Visual Studio 2017 версии 15.3 правильно выдает ошибку C2668 `'f': ambiguous call to overloaded function`:

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

Чтобы исправить код, удалите оператор using `N::f`, если вы намереваетесь вызвать `::f()`.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: локальные объявления функций и проверка по аргументам

При локальном объявлении функции скрываются внутри области, поэтому поиск по аргументам не осуществляется. Однако в этом случае предыдущие версии компилятора всегда выполняли поиск с учетом аргументов. Это могло привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. Как правило, такая ошибка связана с ошибкой в сигнатуре локального объявления функции. В следующем примере Visual Studio 2017 версии 15.3 правильно выдает ошибку C2660 `'f': function does not take two arguments`:

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Чтобы устранить эту проблему, измените сигнатуру `f(S)` или удалите ее.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: порядок инициализации в списках инициализатора

Элементы класса инициализируются в порядке их объявления, а не в порядке отображения в списках инициализаторов. В предыдущих версиях компилятора, когда порядок списка инициализаторов отличался от порядка объявления, никакого предупреждения не выводилось. Эта проблема могла приводить к неопределенному поведению среды выполнения, если инициализация одного элемента зависела от другого элемента, инициализированного в списке. В следующем примере Visual Studio 2017 версии 15.3 (с **`/Wall`** ) выдает предупреждение C5038: `data member 'A::y' will be initialized after data member 'A::x'`.

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Чтобы устранить проблему, список инициализатора должен иметь тот же порядок, что и объявления. Похожее предупреждение возникает, когда один инициализатор или оба ссылаются на члены базового класса.

Это предупреждение по умолчанию отключено и относится только к коду, скомпилированному с параметром **`/Wall`** .

## <a name="bug-fixes-and-other-behavior-changes-in-155"></a><a name="update_155"></a> Исправления ошибок и другие изменения в поведении в версии 15.5

### <a name="partial-ordering-change"></a>Частичное упорядочение изменений

Компилятор теперь правильно отклоняет следующий код и выводит нужное сообщение об ошибке:

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

Проблема в приведенном выше примере заключается в том, что имеется два различия в типах (const и non-const и pack и non-pack). Чтобы устранить ошибку компилятора, удалите одно из различий. Затем компилятор может однозначно упорядочить функции.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>Обработчики исключений

Обработчики ссылок на тип массива или функции никогда не соответствуют никаким объектам исключений. Теперь компилятор правильно учитывает это правило и создает предупреждение уровня 4. Он также больше не соответствует обработчику `char*` или `wchar_t*` в строковом литерале, если используется **`/Zc:strictStrings`** .

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

Следующий код позволяет избежать этой ошибки:

```cpp
catch (int (*)[1]) {}
```

### <a name="stdtr1-namespace-is-deprecated"></a><a name="tr1"></a> Пространство имен `std::tr1` является нерекомендуемым

Нестандартное пространство имен `std::tr1` теперь помечается как нерекомендуемое в режимах C++14 и C++17. В Visual Studio 2017 версии 15.5 приведенный ниже код вызывает предупреждение C4996:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Чтобы исправить ошибку, удалите ссылку на пространство имен `tr1`.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="standard-library-features-in-annex-d-are-marked-as-deprecated"></a><a name="annex_d"></a> Функции стандартной библиотеки в приложении D помечены как нерекомендуемые

Если задан параметр режима компилятора **`/std:c++17`** , почти все функции стандартной библиотеки в приложении D помечаются как нерекомендуемые.

В Visual Studio 2017 версии 15.5 приведенный ниже код вызывает предупреждение C4996:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Чтобы устранить ошибку, следуйте инструкциям в тексте предупреждения, как показано в следующем коде:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Неиспользуемые локальные переменные

В Visual Studio версии 15.5 предупреждение C4189 создается в большинстве случаев, как показано в следующем коде:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Чтобы устранить ошибку, удалите неиспользуемую переменную.

### <a name="single-line-comments"></a>Однострочные комментарии

В Visual Studio 2017 версии 15.5 компилятор C больше не создает предупреждения C4001 и C4179. Ранее они создавались только при использовании параметра компилятора **`/Za`** .  Эти предупреждения больше не нужны, так как однострочные комментарии входят в стандарт C, начиная с версии C99.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Если код не должен поддерживать обратную совместимость, вы можете избежать этих предупреждений, удалив подавление предупреждений C4001 и C4179. Если код должен поддерживать обратную совместимость, подавите вывод только предупреждения C4619.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>Атрибуты `__declspec` с компоновкой `extern "C"`

В более ранних версиях Visual Studio компилятор игнорировал атрибуты `__declspec(...)`, когда `__declspec(...)` был применен перед спецификацией компоновки `extern "C"`. Это поведение приводило к созданию кода, который не планировался пользователем, с возможными последствиями для среды выполнения. Это предупреждение было добавлено в Visual Studio версии 15.3, но было отключено по умолчанию. В Visual Studio 2017 версии 15.5 предупреждение включено по умолчанию.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Чтобы устранить ошибку, поместите спецификацию компоновки перед атрибутом __declspec:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Это новое предупреждение C4768 выдается для некоторых заголовков Windows SDK, которые поставлялись с Visual Studio 2017 15.3 или более ранними версиями (например, с версией 10.0.15063.0, также известной как пакет SDK для RS2). Однако в более поздних версиях заголовков Windows SDK (в частности в ShlObj.h и ShlObj_core.h) внесены исправления, чтобы это предупреждение не создавалось. При появлении этого предупреждения от заголовков Windows SDK можно выполнить следующие действия:

1. Переключитесь на последнюю версию Windows SDK, поставляемую вместе с выпуском Visual Studio 2017 версии 15.5.

1. Отключите предупреждение вокруг #include инструкции заголовка пакета Windows SDK:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern-constexpr-linkage"></a><a name="extern_linkage"></a> Компоновка `extern constexpr`

В более ранних версиях Visual Studio компилятор всегда использовал для переменной **`constexpr`** внутреннюю компоновку, даже если эта переменная была помечена как **`extern`** . В Visual Studio 2017 версии 15.5 новый параметр компилятора ( **`/Zc:externConstexpr`** ) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это поведение будет использоваться по умолчанию.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную, объявленную как **`extern constexpr`** , она должна быть помечена как `__declspec(selectany)` для правильного объединения повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid` нельзя использовать с неполным типом класса

В более ранних версиях Visual Studio компилятор неправильно разрешал выполнение следующего кода, что приводило к выводу потенциально неверных сведений о типе. В Visual Studio 2017 версии 15.5 компилятор правильно выдает сообщение об ошибке:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>Тип целевого объекта `std::is_convertible`

Для `std::is_convertible` необходимо, чтобы целевой тип был допустимым возвращаемым типом. В более ранних версиях Visual Studio компилятор неправильно разрешал использование абстрактных типов, что могло приводить к неверному разрешению перегрузки и непредусмотренному поведению среды выполнения.  Следующий код теперь правильно выводит предупреждение C2338:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Чтобы избежать этой ошибки, при использовании `is_convertible` следует сравнить типы указателей, поскольку сравнение типа, отличного от указателя, может завершиться неудачно, если один тип является абстрактным:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="dynamic-exception-specification-removal-and-noexcept"></a><a name="noexcept_removal"></a> Удаление спецификации динамических исключений и `noexcept`

В C++17 `throw()` является псевдонимом для **`noexcept`** , `throw(<type list>)` и `throw(...)` удалены, а определенные типы могут включать **`noexcept`** . Это изменение может привести к проблемам совместимости для исходного кода, который соответствует C++14 или более ранней версии. Параметр **`/Zc:noexceptTypes-`** можно использовать для возврата к **`noexcept`** версии C++14 при использовании режима C++17 в целом. Это позволяет обновить исходный код для соответствия C++17, не переписывая весь код `throw()`.

Компилятор теперь также проверяет дополнительные спецификации несоответствующих исключений в объявлениях в режиме C++17 или с параметром [`/permissive-`](../build/reference/permissive-standards-conformance.md) с новым предупреждением C5043.

Следующий код вызывает ошибки C5043 и C5040 в Visual Studio 2017 версии 15.5 при использовании параметра **`/std:c++17`** :

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

Чтобы исправить ошибки и продолжать использовать **`/std:c++17`** , добавьте параметр **`/Zc:noexceptTypes-`** в командную строку или обновите код для использования **`noexcept`** , как показано в следующем примере:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>Встроенные переменные

Статические элементы данных **`constexpr`** теперь являются неявными **`inline`** . Это означает, что объявления в пределах класса теперь являются их определениями. Использование внешних определений для элементов данных **`static constexpr`** избыточно и не рекомендуется. В Visual Studio 2017 версии 15.5 при применении параметра **`/std:c++17`** следующий код теперь вызывает предупреждение C5041 `'size': out-of-line definition for constexpr static data member is not needed and is deprecated in C++17`:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>Теперь предупреждение C4768 `extern "C" __declspec(...)` включено по умолчанию

Это предупреждение было добавлено в Visual Studio 2017 версии 15.3, но было отключено по умолчанию. В Visual Studio 2017 версии 15.5 предупреждение включено по умолчанию. Дополнительные сведения см. в разделе [Новое предупреждение для атрибутов \_\_declspec](#declspec).

### <a name="defaulted-functions-and-__declspecnothrow"></a>Заданные по умолчанию функции и `__declspec(nothrow)`

Компилятор ранее разрешал объявление установленных по умолчанию функций с `__declspec(nothrow)`, если соответствующие базовые функции или функции-члены разрешали исключения. Это противоречит стандарту C++ и может привести к неопределенному поведению во время выполнения. Согласно стандарту, такие функции должны быть определены как удаленные, если имеется несовпадение спецификации исключений.  В режиме **`/std:c++17`** следующий код вызывает ошибку C2280 `attempting to reference a deleted function. Function was implicitly deleted because the explicit exception specification is incompatible with that of the implicit declaration.`

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Чтобы исправить этот код, удалите __declspec(nothrow) из функции по умолчанию или удалите `= default` и предоставьте определение функции вместе с любой необходимой обработкой исключений:

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>`noexcept` и частичные специализации

При наличии **`noexcept`** в системе типов частичные специализации для сопоставления отдельных вызываемых типов могут мешать компиляции или выбору основного шаблона из-за отсутствия частичной специализации для указателей на функции noexcept.

В таких случаях может потребоваться добавить дополнительные частичные специализации для обработки указателей на функции **`noexcept`** и указателей **`noexcept`** на функции-члены. Эти перегрузки допустимы только в режиме **`/std:c++17`** . Если вам необходимо поддерживать обратную совместимость с C++14 и вы создаете код, который будут использовать другие разработчики, следует защитить эти новые перегрузки внутри директив `#ifdef`. Если вы работаете в автономном модуле, то вместо использования условий `#ifdef` можно просто выполнять компиляцию с параметром **`/Zc:noexceptTypes-`** .

Приведенный ниже код компилируется при использовании режима **`/std:c++14`** , но не при использовании **`/std:c++17`** с `error C2027: use of undefined type 'A<T>'`:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Следующий код компилируется при указании параметра **`/std:c++17`** , так как компилятор выбирает новую частичную специализацию `A<void (*)() noexcept>`:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="bug-fixes-and-other-behavior-changes-in-157"></a><a name="update_157"></a> Исправления ошибок и другие изменения в поведении в версии 15.7

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17 Аргумент по умолчанию в шаблоне основного класса

Это изменение в поведении является обязательным условием для [выведения аргумента шаблона для шаблонов класса — P0091R3](https://wg21.link/p0091r3).

Ранее компилятор игнорировал аргумент по умолчанию в шаблоне основного класса.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

В Visual Studio 2017 версии 15.7 в режиме **`/std:c++17`** аргумент по умолчанию не игнорируется:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Разрешение имен зависимых объектов

Это изменение в поведении является обязательным условием для [выведения аргумента шаблона для шаблонов класса — P0091R3](https://wg21.link/p0091r3).

В следующем примере компилятор в Visual Studio 15.6 и более ранних версий разрешает `D::type` для `B<T>::type` в шаблоне основного класса.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

Visual Studio 2017 версии 15.7 в режиме **`/std:c++17`** требует указать ключевое слово **`typename`** в инструкции **`using`** из D. Без **`typename`** компилятор создает предупреждение C4346 (`'B<T*>::type': dependent name is not a type`) и ошибку C2061 (`syntax error: identifier 'type'`):

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++17. Атрибут `[[nodiscard]]` — повышение порога предупреждения

В Visual Studio 2017 версии 15.7 в режиме **`/std:c++17`** уровень предупреждений для C4834 `discarding return value of function with 'nodiscard' attribute` увеличивается с W3 до W1. Вы можете отключить это предупреждение путем приведения к **`void`** или путем передачи **`/wd:4834`** компилятору.

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Список инициализации для базового класса конструктора шаблонов с переменным числом аргументов

В предыдущих версиях Visual Studio список инициализации для базового класса конструктора шаблонов с переменным числом аргументов мог не содержать аргументов шаблона (что недопустимо), и при этом не выдавалась ошибка. В Visual Studio 2017 версии 15.7 компилятор выдает ошибку.

В следующем примере кода в Visual Studio 2017 версии 15.7 возникает ошибка C2614: `D<int>: illegal member initialization: 'B' is not a base or member`.

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

Чтобы устранить ошибку, измените выражение B() на B\<T>().

### <a name="constexpr-aggregate-initialization"></a>Агрегатная инициализация `constexpr`

Предыдущие версии компилятора C++ неправильно обрабатывали агрегатную инициализацию **`constexpr`** . Компилятор принимал недопустимый код, в котором выражение aggregate-init-list содержало слишком много элементов, и создавал для него неверный codegen. Примером является следующий код:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

В Visual Studio 2017 версии 15.7 с обновлением 3 и более поздних версий в предыдущем примере теперь возникает ошибка C2078 `too many initializers`. В приведенном ниже примере показано, как исправить код. При инициализации `std::array`, когда используются вложенные списки инициализации в скобках, укажите для внутреннего массива собственный вложенный список в скобках:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="bug-fixes-and-behavior-changes-in-158"></a><a name="update_158"></a> Исправления ошибок и изменения в поведении в версии 15.8

Все изменения в работе компилятора в Visual Studio 2017 версии 15.8 — исправления ошибок и изменения в поведении. Они перечислены ниже:

### <a name="typename-on-unqualified-identifiers"></a>`typename` для неквалифицированных идентификаторов

В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) компилятор больше не принимает ложные ключевые слова **`typename`** в неквалифицированных идентификаторах в определениях шаблонов псевдонимов. Следующий код теперь вызывает ошибку C7511 `'T': 'typename' keyword must be followed by a qualified name`:

```cpp
template <typename T>
using  X = typename T;
```

Чтобы исправить эту ошибку, измените вторую строку на `using  X = T;`.

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` справа от определений шаблонов псевдонимов

Ключевое слово [__declspec](../cpp/declspec.md) теперь запрещено указывать справа от определения шаблона псевдонима. Ранее компилятор принимал этот код, но игнорировал его. Это не приводило к появлению предупреждения о нерекомендуемом элементе при использовании псевдонима.

Вместо этого можно использовать стандартный атрибут C++ [\[\[deprecated\]\]](../cpp/attributes.md). Он учитывается в Visual Studio, начиная с выпуска 2017 версии 15.6. Следующий код теперь вызывает ошибку C2760 `syntax error: unexpected token '__declspec', expected 'type specifier'`:

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Чтобы исправить эту ошибку, измените код на следующий (укажите атрибут перед знаком "=" определения псевдонима).

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>Диагностика двухэтапного поиска имен

Для двухэтапного поиска имен нужно, чтобы независимые имена, используемые в тексте шаблона, отображались в шаблоне во время определения. Ранее компилятор Microsoft C++ мог не искать ненайденное имя до момента создания экземпляров. Теперь ему требуется, чтобы независимые имена привязывались уже в тексте шаблона.

Ошибка может возникать при поиске в зависимых базовых классах. Ранее компилятор позволял использовать имена, определенные в зависимых базовых классах. Это связано с тем, выполнялся поиск имен во время создания экземпляра при разрешении всех типов. Теперь такой код считается ошибкой. В этом случае вы можете принудительно использовать поиск переменной во время создания экземпляров, задав ей в качестве квалификатора тип базового класса или другим образом сделав ее зависимой, например с помощью указателя `this->`.

В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) следующий код теперь вызывает ошибку C3861 `'base_value': identifier not found`.

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

Чтобы исправить эту ошибку, измените инструкцию **`return`** на `return this->base_value;`.

**Примечание.** В Python-библиотеке Boost существовало относящееся к MSVC обходное решение для опережающего объявления шаблона в [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp). В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md), начиная с Visual Studio 2017 версии 15.8 (\_MSC\_VER=1915), компилятор MSVC правильно выполняет поиск имен с учетом аргументов. Теперь процесс согласуется с другими компиляторами, что делает это обходное решение ненужным. Чтобы избежать ошибки C3861 `'unwind_type': identifier not found`, см. запрос на вытягивание [PR 229](https://github.com/boostorg/python/pull/229) в репозитории Boost, где приведены сведения об обновлении файла заголовка. Мы уже исправили пакет Boost [vcpkg](../build/vcpkg.md), поэтому при получении или обновлении источника Boost из vcpkg не нужно применять отдельное исправление.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>Прямые объявления и определения в пространстве имен `std`

Стандарт C++ запрещает пользователю добавлять опережающие объявления и определения в пространство имен `std`. Добавление объявлений или определений в пространство имен `std` или в пространство имен, вложенное в `std`, теперь приводит к неопределенному поведению.

В дальнейшем корпорация Майкрософт изменит место определения для некоторых типов стандартной библиотеки. Это изменение нарушит работу существующего кода, который добавляет прямые объявления в пространство имен `std`. Новое предупреждение C4643 помогает выявить такие проблемы с источником. Предупреждение можно включить в режиме **`/default`** . По умолчанию оно отключено. Оно повлияет на программы, которые компилируются с параметром **`/Wall`** или **`/WX`** .

Следующий код теперь вызывает ошибку C4643: `Forward declaring 'vector' in namespace std is not permitted by the C++ Standard`.

```cpp
namespace std {
    template<typename T> class vector;
}
```

Чтобы исправить эту ошибку, используйте директиву **include** вместо опережающего объявления.

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Конструкторы, делегирующие самим себе

Стандарт C++ предполагает, что компилятор должен породить диагностическое сообщение, если делегирующий конструктор делегирует самому себе. Компилятор Microsoft C++ в режимах [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) и [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) теперь выдает ошибку C7535 `'X::X': delegating constructor calls itself`.

Без этой ошибки следующая программа скомпилируется, но создаст бесконечный цикл.

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

Чтобы избежать этого, делегируйте в другой конструктор.

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>Постоянные выражения для `offsetof`

Макрос [offsetof](../c-runtime-library/reference/offsetof-macro.md) обычно реализовывался с помощью макроса, требующего [reinterpret_cast](../cpp/reinterpret-cast-operator.md). Такое использование недопустимо в контекстах, требующих константного выражения, но обычно компилятор Microsoft C++ разрешал его. Макрос `offsetof`, входящий в состав стандартной библиотеки, правильно использует встроенную конструкцию компилятора ( **__builtin_offsetof**), но многие разработчики применяли эту особенность для определения собственных `offsetof`.

В Visual Studio 2017 версии 15.8 компилятор ограничивает области, в которых можно использовать операторы **`reinterpret_cast`** в режиме по умолчанию, чтобы поведение кода лучше соответствовало стандарту C++. В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) ограничения еще строже. Использование результата `offsetof` в тех случаях, когда требуются константные выражения, может привести к тому, что код вызовет предупреждение C4644 `usage of the macro-based offsetof pattern in constant expressions is non-standard; use offsetof defined in the C++ standard library instead` или C2975 `invalid template argument, expected compile-time constant expression`.

Следующий код вызывает ошибку C4644 в режимах **`/default`** и **`/std:c++17`** , а также ошибку C2975 в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md):

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

Чтобы исправить эту ошибку, используйте `offsetof`, определенный через \<cstddef>.

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>Квалификаторы cv-qualifier в базовых классах, участвующих в раскрытии пакета

Компиляторы Microsoft C++ предыдущих версий не обнаруживали квалификаторы cv-qualifier в базовом классе, если он также участвовал в раскрытии пакета.

В Visual Studio 2017 версии 15.8 в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) следующий код вызывает ошибку C3770 `'const S': is not a valid base class`:

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>Ключевое слово `template` и вложенные описатели имен

В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) компилятор теперь требует, чтобы ключевое слово **`template`** предшествовало имени шаблона, если оно стоит после зависимого вложенного описателя имен.

В режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) следующий код теперь вызывает ошибку C7510 `'example': use of dependent template name must be prefixed with 'template'. note: see reference to class template instantiation 'X<T>' being compiled`.

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        Base<T>::example<int>();
    }
};
```

Чтобы исправить эту ошибку, добавьте ключевое слово **`template`** в инструкцию `Base<T>::example<int>();`, как показано в следующем примере.

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        // Add template keyword here:
        Base<T>::template example<int>();
    }
};
```

## <a name="bug-fixes-and-behavior-changes-in-159"></a><a name="update_159"></a> Исправления ошибок и изменения в поведении в версии 15.9

### <a name="identifiers-in-member-alias-templates"></a>Идентификаторы в шаблонах псевдонимов членов

Идентификатор, используемый в определении шаблона псевдонима члена, должен быть объявлен до использования.

В предыдущих версиях компилятора допускался следующий код:

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

В Visual Studio 2017 версии 15.9 в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md) компилятор выдает ошибку C3861: `'from_template': identifier not found`.

Чтобы устранить эту ошибку, объявите `from_template_t` перед `from_template`.

### <a name="modules-changes"></a>Изменения модулей

В Visual Studio 2017 версии 15.9 компилятор выводит ошибку C5050, если на сторонах создания и потребления используются несогласованные параметры командной строки для модулей. В следующем примере показаны две проблемы:

- на стороне потребления (файл main.cpp) не указан параметр **`/EHsc`** ;

- на стороне создания используется версия C++ **`/std:c++17`** , а на стороне потребления — **`/std:c++14`** .

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

В обоих случаях компилятор выдает предупреждение C5050: `warning C5050: Possible incompatible environment while importing module 'm': mismatched C++ versions.  Current "201402" module version "201703"`.

Компилятор также выдает ошибку C7536 при каждом изменении IFC-файла. Заголовок интерфейса модуля содержит хэш SHA2 содержимого. При импорте IFC-файл хэшируется и проверяется на соответствие хэшу в заголовке. Если они не совпадают, возникает ошибка C7536: `ifc failed integrity checks.  Expected SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'`.

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Частичное упорядочение с использованием псевдонимов и невыведенных контекстов

Существует расхождение реализации в правилах частичного упорядочения, использующих псевдонимы в невыведенных контекстах. В следующем примере GCC и компилятор Microsoft C++ (в режиме [`/permissive-`](../build/reference/permissive-standards-conformance.md)) выдают ошибку, тогда как Clang принимает код.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

В предыдущем примере выводится ошибка C2668:

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

Расхождение реализаций связано с регрессией в формулировках стандарта C++. Для устранения ошибки 2235 потребовалось удалить часть текста, который позволял упорядочивать эти перегрузки. В текущем стандарте C++ отсутствует механизм для частичного упорядочения этих функций, поэтому они считаются неоднозначными.

В качестве обходного решения мы рекомендуем не применять частичное упорядочение. Вместо этого используйте SFINAE для удаления конкретной перегрузки. В следующем примере используется вспомогательный класс `IsA`, позволяющий удалять первую перегрузку, если `Alloc` является специализацией `A`:

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Недопустимые выражения и типы, не являющиеся литералами, в определениях функций на основе шаблона

Недопустимые выражения и типы, не являющиеся литералами, теперь правильно выявляются в определениях шаблонных функций, которые специализируются явным образом. Ранее такие ошибки не возникали для определения функции. Тем не менее недопустимое выражение или нелитеральный тип будут по-прежнему диагностироваться при вычислении как часть константного выражения.

В предыдущих версиях Visual Studio следующий код компилировался без предупреждений:

```cpp
void g();

template<typename T>
struct S
{
    constexpr void f();
};

template<>
constexpr void S<int>::f()
{
    g(); // C3615 in 15.9
}
```

В Visual Studio 2017 версии 15.9 этот код вызывает такую ошибку:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Чтобы избежать этой ошибки, удалите квалификатор **`constexpr`** из явного создания экземпляра функции `f()`.

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Улучшения соответствия стандарту C++ в Visual Studio 2015

Мы предлагаем полный список улучшений соответствия вплоть до Visual Studio 2015 с обновлением 3. Дополнительные сведения см. в статье [Visual C++ What's New 2003 through 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015) (Новые возможности Visual C++ 2003–2015).

::: moniker-end

## <a name="see-also"></a>См. также

[Таблица соответствия Microsoft Visual C++ стандартам языка](visual-cpp-language-conformance.md)
