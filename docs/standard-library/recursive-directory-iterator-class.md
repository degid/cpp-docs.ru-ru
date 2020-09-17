---
title: Класс recursive_directory_iterator
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 0f9bdc3edd7f5798afaa8d170adc35708a6aafa2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217627"
---
# <a name="recursive_directory_iterator-class"></a>Класс recursive_directory_iterator

Описывает итератор ввода, который помещает через имена файлов в каталоге, возможно, по убыванию в подкаталогах рекурсивно. Для итератора `X` `*X` результатом выражения является объект класса `directory_entry` , который заключает в оболочку имя файла и все известные сведения о его состоянии.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Примечания

В шаблоне класса хранятся:

1. Объект типа `stack<pair<directory_iterator, path>>` , вызываемый `mystack` здесь в целях демонстрации, который представляет вложенность каталогов для упорядочения

1. Объект типа `directory_entry` , вызываемый `myentry` здесь, который представляет текущее имя файла в последовательности каталогов.

1. Объект типа **`bool`** , который вызывается `no_push` здесь, который записывает, отключен ли рекурсивный спуск в подкаталогах

1. Объект типа `directory_options` , который вызывается `myoptions` здесь, в котором записываются параметры, созданные при создании

Созданный по умолчанию объект типа `recursive_directory_entry` имеет итератор конца последовательности в `mystack.top().first` и представляет итератор конца последовательности. Например, при наличии каталога `abc` с записями `def` (каталог), `def/ghi` и `jkl` , код:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

выполнит вызов Visit с аргументами `path("abc/def/ghi")` и `path("abc/jkl")` . Можно определить последовательность через поддерево каталога двумя способами.

1. Каталог символьную ссылку будет проверяться только при создании `recursive_directory_iterator` с `directory_options` аргументом, значение которого равно `directory_options::follow_directory_symlink` .

1. При вызове `disable_recursion_pending` следующий каталог, обнаруженный во время инкремента, не будет рекурсивно проверен.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Создает документ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[depth](#depth)|Возвращает `mystack.size() - 1` , поэтому `pval` имеет нулевую глубину.|
|[disable_recursion_pending](#disable_recursion_pending)|Сохраняет **`true`** в `no_push` .|
|[increment](#increment)|Переходит к следующему имени файла в последовательности.|
|[options](#options)|Возвращает `myoptions`.|
|[pор](#pop)|Возвращает следующий объект.|
|[recursion_pending](#recursion_pending)|Возвращает `!no_push`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Возвращает `!(*this == right)`.|
|[operator=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[operator==](#op_eq)|Возвращает, **`true`** только если оба **`*this`** и *право* являются итераторами конца последовательности или оба являются итераторами конца последовательности.|
|[operator*](#op_multiply)|Возвращает `myentry`.|
|[operator->](#op_cast)|Возвращает `&**this`.|
|[operator++](#op_increment)|Увеличивает значение `recursive_directory_iterator` .|

## <a name="requirements"></a>Требования

**Заголовок:**\<filesystem>

**Пространство имен:** std::tr2::sys

## <a name="recursive_directory_iteratordepth"></a><a name="depth"></a>recursive_directory_iterator::depth

Возвращает `mystack.size() - 1` , поэтому `pval` имеет нулевую глубину.

```cpp
int depth() const;
```

## <a name="recursive_directory_iteratordisable_recursion_pending"></a><a name="disable_recursion_pending"></a>recursive_directory_iterator::disable_recursion_pending

Сохраняет **`true`** в `no_push` .

```cpp
void disable_recursion_pending();
```

## <a name="recursive_directory_iteratorincrement"></a><a name="increment"></a>recursive_directory_iterator::Increment

Переходит к следующему имени файла в последовательности.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Параметры

*контроллер*\
Указанный код ошибки.

### <a name="remarks"></a>Примечания

Функция пытается перейти к имени следующего файла во вложенной последовательности. В случае успеха файл сохраняется в; в `myentry` противном случае — итератор конца последовательности.

## <a name="recursive_directory_iteratoroperator"></a><a name="op_neq"></a>recursive_directory_iterator::operator!=

Возвращает `!(*this == right)`.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="recursive_directory_iteratoroperator"></a><a name="op_as"></a>recursive_directory_iterator::operator=

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*recursive_directory_iterator*\
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) , копируемый в `recursive_directory_iterator` .

## <a name="recursive_directory_iteratoroperator"></a><a name="op_eq"></a>recursive_directory_iterator::operator==

Возвращает, **`true`** только если оба **`*this`** и *право* являются итераторами конца последовательности или оба являются итераторами конца последовательности.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="recursive_directory_iteratoroperator"></a><a name="op_multiply"></a>recursive_directory_iterator::operator*

Возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="recursive_directory_iteratoroperator-"></a><a name="op_cast"></a>recursive_directory_iterator::operator->

Возвращает `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="recursive_directory_iteratoroperator"></a><a name="op_increment"></a>recursive_directory_iterator::operator++

Увеличивает значение `recursive_directory_iterator` .

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

*int*\
Указанное приращение.

### <a name="remarks"></a>Примечания

Первая функция – член вызывает `increment()` , а затем возвращает **`*this`** . Вторая функция-член создает копию объекта, вызывает `increment()` , а затем возвращает копию.

## <a name="recursive_directory_iteratoroptions"></a><a name="options"></a>recursive_directory_iterator::options

Возвращает `myoptions`.

```cpp
directory_options options() const;
```

## <a name="recursive_directory_iteratorpop"></a><a name="pop"></a>recursive_directory_iterator::p Op

Возвращает следующий объект.

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

`depth() == 0`Значение, если объект преобразуется в итератор конца последовательности. В противном случае функция-член завершает проверку текущего (самого глубокого) каталога и возобновляет ее на следующем нижнем уровне глубины.

## <a name="recursive_directory_iteratorrecursion_pending"></a><a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

Возвращает `!no_push`.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iteratorrecursive_directory_iterator"></a><a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

Создает документ `recursive_directory_iterator`.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*Pval*\
Заданный путь.

*error_code*\
Указанный код ошибки.

*решает*\
Указанные параметры каталога.

*recursive_directory_iterator*\
`recursive_directory_iterator`, копией которого будет создаваемый `recursive_directory_iterator`.

### <a name="remarks"></a>Примечания

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы хранятся **`false`** в `no_push` и `directory_options::none` в, а `myoptions` затем пытаются открыть и прочитать *Pval* как каталог. В случае успеха они инициализируются `mystack` и `myentry` назначают первое имя файла, не являющегося каталогом, во вложенной последовательности. в противном случае они создают итератор конца последовательности.

Четвертый и пятый конструкторы ведут себя так же, как во втором и третьем, за исключением того, что они *сначала сохраняют в* `myoptions` . Установленные по умолчанию конструкторы работают корректно.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)
