---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: cb5950e311711dd489b3cab223714b1840773f60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220591"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Блок, относящийся только к системам Microsoft**

Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.

## <a name="syntax"></a>Синтаксис

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Параметры

*пинтерфаце*<br/>
Необработанный указатель на интерфейс.

*фаддреф*<br/>
Если это так **`true`** , то `AddRef` вызывается. Если это так **`false`** , `_com_ptr_t` объект принимает владение указателем необработанного интерфейса без вызова `AddRef` .

## <a name="remarks"></a>Примечания

- **Attach (**  *пинтерфаце*  **)** `AddRef` не вызывается. Право на владение интерфейсом передается данному объекту `_com_ptr_t`. `Release`метод вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя.

- **Attach (**  *пинтерфаце* **,**  *фаддреф*  **)** Если *фаддреф* имеет значение **`true`** , `AddRef` вызывается метод для увеличения числа ссылок для указателя инкапсулированного интерфейса. Если *фаддреф* имеет значение **`false`** , этот `_com_ptr_t` объект берет на себя владение указателем необработанного интерфейса без вызова `AddRef` . `Release`метод вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
