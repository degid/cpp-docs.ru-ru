---
title: '&lt;cstdalign&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 603a590190c50495aa80f1b41a574149eb8f760a
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68342843"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign&gt;

В некоторых C++ реализациях стандартной библиотеки этот заголовок включает заголовок \<стандартной библиотеки C стдалигн.h > и добавляет `std` связанные имена в пространство имен. Поскольку этот заголовок не реализован в компилятором MSVC, \<заголовок cstdalign > определяет макросы `__alignas_is_defined` совместимости и `__alignof_is_defined`.

> [!NOTE]
> Так как заголовок C++ стдалигн.h>определяетмакросы,которыеявляютсяключевымисловамив,втомчисленеоказываетникакого\<влияния. В C++рекомендуется использовать заголовок стдалигн.h\<>. Заголовок \<cstdalign > является устаревшим в c++ 17 и удаляется в черновом стандарте c++ 20.

## <a name="requirements"></a>Требования

**Заголовок:** \<cstdalign >

**Пространство имен:** std

## <a name="macros"></a>Макросы

| Макрос | Описание |
| - | - |
| `__alignas_is_defined` | Макрос совместимости C, который разворачивается до целочисленной константы 1. |
| `__alignof_is_defined` | Макрос совместимости C, который разворачивается до целочисленной константы 1. |

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[C++Общие сведения о стандартной библиотеке](cpp-standard-library-overview.md)\
[Безопасность потоков в C++ стандартной библиотеке](thread-safety-in-the-cpp-standard-library.md)
