---
title: Класс directory_iterator
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: a7ccc2a941da079e14092af5b81dc537db4a48c0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215781"
---
# <a name="directory_iterator-class"></a>Класс directory_iterator

Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге. Для итератора `X` `*X` результатом выражения является объект класса `directory_entry` , который заключает в оболочку имя файла и все известные сведения о его состоянии.

Класс сохраняет объект типа `path` , вызываемый `mydir` здесь в целях демонстрации, который представляет имя каталога для упорядочения, и объект типа `directory_entry` `myentry` , который вызывается здесь, который представляет текущее имя файла в последовательности каталогов. Созданный по умолчанию объект типа `directory_entry` имеет пустой `mydir` путь и представляет итератор конца последовательности.

Например, при наличии каталога `abc` с записями `def` и `ghi` , код:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

будет вызывать `visit` с аргументами `path("abc/def")` и `path("abc/ghi")` .

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[directory_iterator](#directory_iterator)|Конструирует входной итератор, подающий последовательность по именам файлов в каталоге.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[increment](#increment)|Пытается перейти к следующему имени файла в каталоге.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Возвращает `!(*this == right)`.|
|[operator=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[operator==](#op_eq)|Возвращает, **`true`** только если оба **`*this`** и *право* являются итераторами конца последовательности или оба являются итераторами конца последовательности.|
|[operator*](#op_star)|Возвращает `myentry`.|
|[operator->](#op_cast)|Возвращает `&**this`.|
|[operator++](#op_increment)|Вызывает `increment()` , затем возвращает **`*this`** или создает копию объекта, вызывает `increment()` , а затем возвращает копию.|

## <a name="requirements"></a>Требования

**Заголовок:**\<experimental/filesystem>

**Пространство имен:** std::experimental::filesystem

## <a name="directory_iteratordirectory_iterator"></a><a name="directory_iterator"></a>directory_iterator::d irectory_iterator

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы хранят *Pval* в `mydir` , а затем пытаются открыть и прочитать в `mydir` виде каталога. В случае успеха они сохраняют первое имя файла в каталоге в `myentry` ; в противном случае они создают итератор конца последовательности.

Установленные по умолчанию конструкторы работают корректно.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь к сохраненному имени файла.

*контроллер*\
Код ошибки состояния.

*directory_iterator*\
Сохраненный объект.

## <a name="directory_iteratorincrement"></a><a name="increment"></a>directory_iterator:: Increment

Функция пытается перейти к следующему файлу в каталоге. В случае успеха файл сохраняется в; в `myentry` противном случае — итератор конца последовательности.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="directory_iteratoroperator"></a><a name="op_neq"></a>directory_iterator::operator!=

Оператор-член возвращает `!(*this == right)`.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
[Directory_iterator](../standard-library/directory-iterator-class.md) сравнивается с `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_as"></a>directory_iterator::operator=

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*right*\
[Directory_iterator](../standard-library/directory-iterator-class.md) , копируемый в `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_eq"></a>directory_iterator::operator==

Оператор-член возвращает, **`true`** только если оба **`*this`** и *право* являются итераторами конца последовательности или оба являются итераторами конца последовательности.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
[Directory_iterator](../standard-library/directory-iterator-class.md) сравнивается с `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_star"></a>directory_iterator::operator*

Оператор-член возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="directory_iteratoroperator-"></a><a name="op_cast"></a>directory_iterator::operator->

Функция-член возвращает значение `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="directory_iteratoroperator"></a><a name="op_increment"></a>directory_iterator::operator++

Первая функция – член вызывает `increment()` , а затем возвращает **`*this`** . Вторая функция-член создает копию объекта, вызывает `increment()` , а затем возвращает копию.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

*int*\
Число приращений.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)
