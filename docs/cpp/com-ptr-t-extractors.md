---
title: Средства извлечения _com_ptr_t
description: Описывает операторы извлечения для класса _com_ptr_t.
ms.date: 07/07/2020
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
ms.openlocfilehash: fb5441d87dc35ec6fbb495bc38d9041c1f2d2f33
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220578"
---
# <a name="_com_ptr_t-extractors"></a>`_com_ptr_t`Средства извлечения

**Специально для систем Майкрософт**

Извлекают инкапсулированный указатель на COM-интерфейс.

## <a name="syntax"></a>Синтаксис

```c++
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>Примечания

- **`operator Interface*`** Возвращает указатель инкапсулированного интерфейса, который может иметь значение NULL.

- **`operator Interface&`** Возвращает ссылку на инкапсулированный указатель интерфейса и выдает ошибку, если указатель имеет значение NULL.

- **`operator*`** Позволяет объекту интеллектуального указателя действовать так, будто он был фактически инкапсулированным интерфейсом при разыменовании.

- **`operator->`** Позволяет объекту интеллектуального указателя действовать так, будто он был фактически инкапсулированным интерфейсом при разыменовании.

- **`operator&`** Освобождает любой инкапсулированный указатель интерфейса, заменяя его значением NULL, и возвращает адрес инкапсулированного указателя. Этот оператор позволяет передать смарт-указатель по адресу в функцию с параметром *out* , через который он возвращает указатель интерфейса.

- **`operator bool`** Позволяет использовать объект интеллектуального указателя в условном выражении. Этот оператор возвращает **`true`** , если указатель не имеет значение null.

  > [!NOTE]
  > Поскольку не **`operator bool`** объявлен как **`explicit`** , неявно преобразуется `_com_ptr_t` в, которое преобразуется **`bool`** в любой скалярный тип. Это может привести к непредвиденным последствиям в коде. Включите [Предупреждение компилятора (уровень 4) C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md) , чтобы предотвратить непреднамеренное использование этого преобразования.

## <a name="see-also"></a>См. также раздел

[_com_ptr_t - класс](../cpp/com-ptr-t-class.md)
