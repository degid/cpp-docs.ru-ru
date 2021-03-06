---
title: Ошибка компилятора C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: dc13829a267deea1f412eb2d8f86057f01dc0e1c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752422"
---
# <a name="compiler-error-c2011"></a>Ошибка компилятора C2011

identifier: повторное определение типа type

Идентификатор ранее был определен как `type`. Проверьте переопределения идентификатора.

Ошибка C2011 также может возникнуть при импорте файла заголовков или библиотеки типов более одного раза в один файл. Чтобы предотвратить множественные включения типов, определенных в файле заголовка, используйте директиву include или `#pragma`[Once](../../preprocessor/once.md) в файле заголовка.

Если необходимо найти исходное объявление переопределенного типа, можно использовать флаг " [/p](../../build/reference/p-preprocess-to-a-file.md) компилятора" для создания предварительно обработанных выходных данных, переданных компилятору. Вы можете воспользоваться средствами поиска текста для поиска экземпляров переопределенного идентификатора в выходном файле.

В следующем примере показано возникновение ошибки C2011 и приводятся сведения по ее устранению.

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
