---
title: FILE_TYPE_CODE enum
description: Ссылка на SDK Build Insights sDK FILE_TYPE_CODE.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dea603a072d7b2f472112a75b2e9ccded78399a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325567"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE enum

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В `FILE_TYPE_CODE` enum описывается тип файла.

## <a name="members"></a>Участники

| name | Значение | Описание |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x0000000000) | Тип файла, не указанный в этом списке. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Файл объекта\*(.obj). |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Исполняемый (.exe)\*или DLL (.dll)\*файл. |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Статический файл библиотеки. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x000000004) | Библиотека импорта (к.либ) |
| `FILE_TYPE_CODE_EXP` | 5 (0x000000005) | Экспортный файл( файл. |

## <a name="remarks"></a>Примечания

::: moniker-end
