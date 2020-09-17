---
title: Перечисление Буфферкомманд
description: 'Описывает перечисление Буфферкомманд, которое используется для работы с файлами памяти с помощью Кмемфиле:: Жетбуфферптр ().'
ms.date: 07/23/2020
f1_keywords:
- afx/buffercommand
helpviewer_keywords:
- buffercommand enumeration [MFC]
ms.openlocfilehash: f2f553df56fadd99b65b04cce9a97917425ed70b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212082"
---
# <a name="buffercommand-enumeration"></a>Перечисление Буфферкомманд

Используется функцией [кмемфиле:: жетбуфферптр](cmemfile-class.md#getbufferptr) , чтобы определить, какое действие следует предпринять в буфере памяти, поддерживаемом файлом.

## <a name="syntax"></a>Синтаксис

``` cpp
public enum BufferCommand
{
   bufferRead,
   bufferWrite,
   bufferCommit,
   bufferCheck
};
```

## <a name="members"></a>Участники

|Имя|Описание|
|-|-|
| `bufferRead` | Чтение буфера памяти, доступного в файле. |
| `bufferWrite` | Запись в буфер памяти, записанный в файле. |
| `bufferCommit` | Изменяет текущую позицию в буфере памяти, сохраненном в файле, до конца выделенного буфера. |
| `bufferCheck` | Определите, может ли размер буфера памяти, поддерживающего передачу файлов, увеличиваться. |

## <a name="requirements"></a>Требования

**Заголовок:** афксвинформс.h (определяется в atlmfc\lib\mfcmifc80.dll сборки)
