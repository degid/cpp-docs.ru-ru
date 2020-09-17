---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: de2275f096fe2fde96e64cbc3034602a1fde5e88
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180775"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetDescription`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetDescription` для объекта `IErrorInfo`, записанного в объекте `_com_error`. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если `IErrorInfo` не записано, возвращается пустая `_bstr_t`.

## <a name="remarks"></a>Примечания

Вызывает функцию `IErrorInfo::GetDescription` и извлекает `IErrorInfo`, записанные в объекте `_com_error`. Любой сбой при вызове метода `IErrorInfo::GetDescription` игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
