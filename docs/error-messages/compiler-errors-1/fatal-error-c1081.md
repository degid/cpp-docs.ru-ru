---
title: Неустранимая ошибка C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: b8630a26d14c68a5f1abe45bb0b8d0141d0dedbb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204195"
---
# <a name="fatal-error-c1081"></a>Неустранимая ошибка C1081

"символ": слишком длинное имя файла

Длина пути к файлу превышает `_MAX_PATH` (определяется в STDLIB.h как 260 символов). Сократите имя файла.

При вызове CL. exe с коротким именем файла компилятору может потребоваться создать полный путь. Например, `cl -c myfile.cpp` может вызвать создание компилятором:

```
D:\<very-long-directory-path>\myfile.cpp
```
