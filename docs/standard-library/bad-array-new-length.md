---
title: Класс bad_array_new_length
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: c4f4f58f7b28960bbacf695a675fbe4f20a54192
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443701"
---
# <a name="bad_array_new_length-class"></a>Класс bad_array_new_length

Класс описывает исключение, которое указывает, что запрос на выделение не был успешно выполнен из-за того, что размер массива меньше нуля или больше его ограничения.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Примечания

Значение, возвращаемое `what`, является строкой C, определяемой реализацией. Ни одна из функций-членов не создает исключение.

## <a name="requirements"></a>Требования

**Заголовок:** \<New >

## <a name="see-also"></a>См. также раздел

[класс исключения](../standard-library/exception-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
