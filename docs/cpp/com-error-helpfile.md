---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 775adfa7d5dd5aca098edcd793c2164d65fe7efa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190226"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetHelpFile`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetHelpFile` для объекта `IErrorInfo`, записанного в объекте `_com_error`. Результирующая строка BSTR инкапсулируется в объект `_bstr_t`. Если `IErrorInfo` не записано, возвращается пустая `_bstr_t`.

## <a name="remarks"></a>Примечания

Любой сбой при вызове метода `IErrorInfo::GetHelpFile` игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
