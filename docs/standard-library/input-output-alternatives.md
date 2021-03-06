---
title: Варианты ввода-вывода
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: b46ff242fc263be5069eb691dd0ea9e8fb00b0f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455288"
---
# <a name="inputoutput-alternatives"></a>Альтернативные варианты ввода и вывода

Компилятор Майкрософт C++ предоставляет несколько альтернативных вариантов программирования ввода-вывода:

- Прямой ввод-вывод без буферизации на основе библиотеки времени выполнения С.

- Потоковый ввод-вывод на основе библиотеки времени выполнения ANSI C.

- Прямой ввод-вывод на консоль и в порт.

- Библиотека MFC.

- Стандартная библиотека Microsoft C++.

Классы iostream полезны для ввода-вывода форматированного текста с буферизацией. Они также могут использоваться для ввода-вывода без буферизации или двоичного ввода-вывода, если требуется интерфейс программирования C++ и принято решение отказаться от использования библиотеки Microsoft Foundation Class (MFC). Классы iostream — это объектно-ориентированная альтернатива вводу-выводу с помощью функций времени выполнения С.

Классы iostream можно использовать с операционной системой Microsoft Windows. Потоки строк и файлов работают без ограничений, но объекты потока символьного режима `cin`, `cout`, `cerr`, и `clog` не совместимы с графическим интерфейсом пользователя Windows. Также можно получать производные пользовательские классы потоков, которые взаимодействуют непосредственно со средой Windows.

## <a name="see-also"></a>См. также

[Что такое поток](../standard-library/what-a-stream-is.md)
