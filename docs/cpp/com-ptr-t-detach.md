---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190018"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Блок, относящийся только к системам Microsoft**

Извлекает и возвращает инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Примечания

Извлекает и возвращает инкапсулированный указатель на интерфейс, а затем очищает область хранения инкапсулированного указателя, присваивая ему значение NULL. Поэтому указатель на интерфейс удаляется из инкапсуляции. Вы должны вызвать `Release` в возвращенном указателе интерфейса.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
