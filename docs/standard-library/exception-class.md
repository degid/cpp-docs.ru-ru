---
title: Класс exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: fd3fb3c48e9501b7aaf90bca14ea98530b245ec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228275"
---
# <a name="exception-class"></a>Класс exception

Этот класс служит базовым классом для всех исключений, создаваемых определенными выражениями и стандартной библиотекой C++.

## <a name="syntax"></a>Синтаксис

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>Примечания

В частности, этот базовый класс является корнем стандартных классов исключений, определенных в [\<stdexcept>](../standard-library/stdexcept.md) . Значение строки в C, возвращаемое объектом `what`, не указывается конструктором по умолчанию, но может быть определено конструкторами для некоторых производных классов как строка C для заданной реализации. Ни одна из функций-членов не создает исключение.

**`int`** Параметр позволяет указать, что память не должна выделяться. Значение параметра **`int`** игнорируется.

> [!NOTE]
> Конструкторы `exception(const char* const &message)` и `exception(const char* const &message, int)` являются расширениями Майкрософт для стандартной библиотеки C++.

## <a name="example"></a>Пример

Примеры использования стандартных классов исключений, которые наследуются от `exception` класса, см. в разделе любые классы, определенные в [\<stdexcept>](../standard-library/stdexcept.md) .
