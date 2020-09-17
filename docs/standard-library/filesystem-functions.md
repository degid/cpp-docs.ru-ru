---
title: Функции &lt;filesystem&gt;
ms.date: 03/27/2019
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.openlocfilehash: c637c4893a13df577fd6c083c8a4f2380c9c4cad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219161"
---
# <a name="ltfilesystemgt-functions"></a>Функции &lt;filesystem&gt;

Эти бесплатные функции в [\<filesystem>](../standard-library/filesystem.md) заголовке выполняют изменения и запрашивают операции с путями, файлами, символических ссылок, каталогами и томами. Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="absolute"></a><a name="absolute"></a>минималь

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Функция возвращает абсолютный путь, соответствующий *Pval* , относительно пути `base` :

1. Если `pval.has_root_name() && pval.has_root_directory()` функция возвращает *Pval*.

1. `pval.has_root_name() && !pval.has_root_directory()`Значение, если функция возвращает значение `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  /  `pval.relative_path()` .

1. Если `!pval.has_root_name() && pval.has_root_directory()` функция возвращает `absolute(base).root_name()`  /  *Pval*.

1. Если `!pval.has_root_name() && !pval.has_root_directory()` функция возвращает `absolute(base)`  /  *Pval*.

## <a name="begin"></a><a name="begin"></a> begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Обе функции возвращают *iter*.

## <a name="canonical"></a><a name="canonical"></a>формат

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Все функции формируют абсолютный путь `pabs = absolute(pval, base)` (или `pabs = absolute(pval)` для перегрузки без базового параметра), а затем сокращают их до канонической формы в следующей последовательности шагов:

1. Каждый компонент пути, `X` для `is_symlink(X)` которого **`true`** заменяется `read_symlink(X)` .

1. Каждый компонент пути `.` (точка — это текущий каталог, установленный предыдущими компонентами пути) удаляется.

1. Каждая пара компонентов пути `X` / `..` (точка-точка — это родительский каталог, установленный предыдущими компонентами пути), удаляется.

Затем функция возвращает `pabs` .

## <a name="copy"></a><a name="copy"></a>копии

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Все функции, возможно, копируют или связывают один или несколько файлов *с* в *в* , под контролем прав *, которое*принимается `copy_options::none` для перегрузок с параметром без *opts* параметров. *направо должен содержать* не более одного из следующих элементов:

- `skip_existing`, `overwrite_existing` или `update_existing`

- `copy_symlinks` или `skip_symlinks`

- `directories_only`, `create_symlinks` или `create_hard_links`

Функции сначала определяют file_status значения `f` для *from* и `t` для: *to*

- Если `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)` , путем вызова метода`symlink_status`

- в противном случае путем вызова метода`status`

- в противном случае передается ошибка.

Если `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)` значение равно, они сообщают об ошибке (и не выполняют никаких других действий).

В противном случае —, если `is_symlink(f)` :

- Если `options & copy_options::skip_symlinks` значение равно, ничего делать не нужно.

- В противном случае, если `!exists(t)&& options & copy_options::copy_symlinks` , то `copy_symlink(from, to, opts)` .

- В противном случае сообщите об ошибке.

В противном случае, если `is_regular_file(f)` , то:

- Если `opts & copy_options::directories_only` значение равно, ничего делать не нужно.

- В противном случае, если `opts & copy_options::create_symlinks` , то `create_symlink(to, from)` .

- В противном случае, если `opts & copy_options::create_hard_links` , то `create_hard_link(to, from)` .

- В противном случае, если `is_directory(f)` , то `copy_file(from, to`  /  `from.filename(), opts)` .

- В противном случае — значение `copy_file(from, to, opts)`.

В противном случае, если `is_directory(f) && (opts & copy_options::recursive || !opts)` , то:

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

В противном случае не выполнять никаких действий.

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Все функции, возможно, копируют файл *из* в в *в* , под контролем прав *, которое*принимается `copy_options::none` для перегрузок с параметром без *opts* параметров. *должно содержать* не более одного из `skip_existing` , `overwrite_existing` или `update_existing` .

Если задано `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))` значение, то выводится сообщение о том, что файл уже существует.

В противном случае, если `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))` , то попытается скопировать содержимое и атрибуты файла *из* в файл *в*. Передать как ошибку в случае сбоя попытки копирования.

Функции возвращают значение **`true`** , если копия пытается выполнить операцию, в противном случае — значение **`false`** .

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Если `is_directory(from)` значение равно, функция вызывает `create_directory_symlink(from, to)` . В противном случае он вызывает `create_symlink(from, to)` .

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Для пути, например a \/ b \/ c, функция создает каталоги a и \/ b в соответствии с требованиями, чтобы при необходимости можно было создать каталог a \/ b \/ c. Он возвращает **`true`** , только если на самом деле он создает каталог *Pval*.

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

При необходимости функция создает каталог *Pval* . Он возвращает значение true только в том случае, если фактически создает каталог *Pval*. в этом случае он копирует разрешения из существующего атрибута *attr*или использует `perms::all` для перегрузок без параметра *attr* .

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку в качестве символьную ссылку *для каталога.*

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку как жесткую ссылку на каталог или файл *в*.

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает *ссылку* в качестве символьную ссылку *для файла.*

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Функции без параметров *Pval* возвращают путь к текущему каталогу. Оставшиеся функции задают для текущего каталога значение *Pval*.

## <a name="end"></a><a name="end"></a> end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

Первая функция возвращает `directory_iterator()` , а вторая возвращает`recursive_directory_iterator()`

## <a name="equivalent"></a>Эквивалент <a name="equivalent"></a>

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

Функции возвращают **`true`** только в том случае, если *Left* и *right* выбирают одну и ту же сущность FileSystem.

## <a name="exists"></a><a name="exists"></a>существующем

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `status_known && stat.type() != file_not_found`. Вторая и третья функции возвращают значение `exists(status(pval))` .

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Функции возвращают размер в байтах файла, выбранного параметром *Pval*, если `exists(pval) && is_regular_file(pval)` и размер файла можно определить. В противном случае они сообщают об ошибке и возвращают ошибку `uintmax_t(-1)` .

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

Функция возвращает число жестких связей для *Pval*или значение \- 1, если возникает ошибка.

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

Функция возвращает хэш-значение для `pval.native()` .

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::block`. Остальные функции возвращают значение `is_block_file(status(pval))` .

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::character`. Остальные функции возвращают значение `is_character_file(status(pval))` .

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::directory`. Остальные функции возвращают значение `is_directory_file(status(pval))` .

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Если `is_directory(pval)` , то функция возвращает значение `directory_iterator(pval) == directory_iterator()` ; в противном случае возвращается значение `file_size(pval) == 0` .

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::fifo`. Остальные функции возвращают значение `is_fifo(status(pval))` .

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::other`. Остальные функции возвращают значение `is_other(status(pval))` .

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::regular`. Остальные функции возвращают значение `is_regular_file(status(pval))` .

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::socket`. Остальные функции возвращают значение `is_socket(status(pval))` .

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::symlink`. Остальные функции возвращают значение `is_symlink(status(pval))` .

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

Первые две функции возвращают время последнего изменения данных для *Pval*или `file_time_type(-1)` при возникновении ошибки. Последние две функции устанавливают время последнего изменения данных для *Pval* на *New_Time*.

## <a name="permissions"></a><a name="permissions"></a>чтение

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

Функции устанавливают разрешения для пути, выбранном параметром *Pval* , в значение `mask & perms::mask` под контролем `perms & (perms::add_perms | perms::remove_perms)` . *Маска* должна содержать не более одного элемента `perms::add_perms` и `perms::remove_perms` .

Если `mask & perms::add_perms` задано значение, то функции устанавливают разрешения в `status(pval).permissions() | mask & perms::mask` . В противном случае, если `mask & perms::remove_perms` функции задают для разрешений значение `status(pval).permissions() & ~(mask & perms::mask)` . В противном случае функции устанавливают разрешения в `mask & perms::mask` .

## <a name="proximate"></a><a name="proximate"></a>проксимате

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a><a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Функции сообщают об ошибке и возвращают значение, `path()` Если `!is_symlink(pval)` . В противном случае функции возвращают объект типа `path`, содержащий символьную ссылку.

## <a name="relative"></a><a name="relative"></a>относительный

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>отменит

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Функции возвращают, **`true`** только если `exists(symlink_status(pval))` и файл успешно удалены. Символьную ссылку сам удаляется, а не файл, который он выбирает.

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Если *Pval* является каталогом, функции рекурсивно удаляют все записи каталога, а затем саму запись. В противном случае функции вызывают `remove` . Они возвращают число всех успешно удаленных элементов.

## <a name="rename"></a><a name="rename"></a>имени

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

Функции переименованы *из* *в в.* Сам символьную ссылку переименовывается, а не в файл, который он выбирает.

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Функции изменяют размер файла таким, что`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>модуль

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

Функция возвращает сведения о томе, выбранном параметром *Pval*, в структуре типа `space_info` . Структура содержит `uintmax_t(-1)` любое значение, которое не может быть определено.

## <a name="status"></a><a name="status"></a>состояние

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

Функции возвращают состояние пути, тип файла и разрешения, связанные с *Pval*. Символьную ссылку сам по себе не тестируется, а файл выбирается.

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

Функция возвращает`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>позиции

```cpp
void swap(path& left, path& right) noexcept;
```

Функция меняет местами содержимое *слева* и *справа*.

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, error_code& ec) noexcept;
```

Функции возвращают путь символьную ссылку, тип файла и разрешения, связанные с *Pval*. Функции ведут себя так же, как `status(pval)` за исключением того, что сам символьную ссылку тестируется, а не в выбранном файле.

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

Функции возвращают абсолютный путь, который учитывает (при необходимости) текущий каталог, связанный с его корневым именем. \(Для POSIX функции возвращают `absolute(pval)` .\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

Функции возвращают путь к каталогу, подходящему для хранения временных файлов.

## <a name="u8path"></a><a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

Первая функция ведет себя так же, как `path(source)` и вторая функция ведет себя так же, как `path(first, last)` за исключением того, что выбранный источник в каждом случае принимается как последовательность элементов char, закодированных как UTF-8, независимо от файловой системы.

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
