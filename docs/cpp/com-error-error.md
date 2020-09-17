---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 8e2c52d10b15822703329dcea18944773f5784ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180762"
---
# <a name="_com_errorerror"></a>_com_error::Error

**Блок, относящийся только к системам Microsoft**

Извлекает значение HRESULT, передаваемое конструктору.

## <a name="syntax"></a>Синтаксис

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Необработанный элемент HRESULT, переданный в конструктор.

## <a name="remarks"></a>Примечания

Извлекает инкапсулированный элемент HRESULT в объект `_com_error`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
