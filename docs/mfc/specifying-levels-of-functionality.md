---
title: Задание уровней функциональности
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: c3b4ecb38054748f36d75ca43e32d6447d3d2428
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307293"
---
# <a name="specifying-levels-of-functionality"></a>Задание уровней функциональности

В этой статье описывается добавление следующих уровней функциональные возможности для вашего [CObject](../mfc/reference/cobject-class.md)-производный класс:

- Сведения о классе среды выполнения

- Поддержка динамического создания

- Поддержка сериализации

Общее описание `CObject` функциональные возможности, см. в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md).

## <a name="to-add-run-time-class-information"></a>Чтобы добавить сведения о классе среды выполнения

1. Наследование класса из `CObject`, как описано в разделе [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md) статьи.

1. Используйте DECLARE_DYNAMIC-макрос в объявлении класса, как показано ниже:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Использовать implement_dynamic-макрос в файле реализации (. CPP) вашего класса. Этот макрос принимает в качестве аргументов имя класса и его базового класса, следующим образом:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> Всегда помещать IMPLEMENT_DYNAMIC в файле реализации (. CPP) для класса. Implement_dynamic-макрос должно оцениваться только один раз во время компиляции и поэтому не следует использовать в файле интерфейса (. H), потенциально может включаться в более чем одного файла.

## <a name="to-add-dynamic-creation-support"></a>Чтобы добавить поддержку динамического создания

1. Наследование класса из `CObject`.

1. Используйте declare_dyncreate-макрос в объявлении класса.

1. Определяет конструктор без аргументов (конструктор по умолчанию).

1. Используйте implement_dyncreate-макрос в файле реализации класса.

## <a name="to-add-serialization-support"></a>Для добавления поддержки сериализации

1. Наследование класса из `CObject`.

1. Переопределить `Serialize` функция-член.

   > [!NOTE]
   > При вызове метода `Serialize` напрямую, то есть нежелательно для сериализации объекта через указатель полиморфных, пропустите шаги 3 – 5.

1. Используйте declare_serial-макрос в объявлении класса.

1. Определяет конструктор без аргументов (конструктор по умолчанию).

1. Используйте IMPLEMENT_SERIAL-макрос в файле реализации класса.

> [!NOTE]
> «Полиморфных указатель» указывает на объект класса (вызывать его типа) или на объект любого класса, производного от параметр (скажем, B). Для сериализации через указатель полиморфных платформы необходимо определить класс времени выполнения объекта сериализуется (B), так как он может быть объект любого класса, производного от некоторого базового класса (A).

Дополнительные сведения о том, как включить сериализацию, при наследовании от класса `CObject`, см. в статьях [файлы в MFC](../mfc/files-in-mfc.md) и [сериализации](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>См. также

[Наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md)
