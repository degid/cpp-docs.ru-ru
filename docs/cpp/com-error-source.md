---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 43dd21297ddd54863d535402dddd59243d589eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180528"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetSource`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetSource` для объекта `IErrorInfo`, записанного в объекте `_com_error`. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если `IErrorInfo` не записано, возвращается пустая `_bstr_t`.

## <a name="remarks"></a>Примечания

Любой сбой при вызове метода `IErrorInfo::GetSource` игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
