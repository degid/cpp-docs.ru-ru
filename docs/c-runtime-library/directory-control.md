---
title: Управление каталогами
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
ms.openlocfilehash: 640ce8a8665936b604c6e8e6270e358a200c880a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438535"
---
# <a name="directory-control"></a>Управление каталогами

Эти подпрограммы имеют доступ к структуре каталогов, изменяют ее и получают о ней сведения.

## <a name="directory-control-routines"></a>Подпрограммы управления каталогами

|Подпрограмма|Использование|
|-------------|---------|
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Изменение текущей рабочей папки|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Изменение текущего диска|
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Получение текущей рабочей папки для диска по умолчанию|
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Получение текущей рабочей папки для выбранного диска|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Заполняет структуру **_diskfree_t** сведениями о диске.|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Получение текущего диска (по умолчанию)|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Возвращает битовую маску, которая представляет доступные в данный момент диски.|
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Создание нового каталога|
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Удалить каталог|
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Поиск выбранного файла в указанных папках|

## <a name="see-also"></a>См. также раздел

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Обработка файлов](../c-runtime-library/file-handling.md)<br/>
[Системные вызовы](../c-runtime-library/system-calls.md)<br/>
