---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: b3c79bb069ef504680e83359d6ec90c803f16d9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180593"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetHelpContext`.

## <a name="syntax"></a>Синтаксис

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetHelpContext` для объекта `IErrorInfo`, записанного в объекте `_com_error`. Если объект `IErrorInfo` не записан, возвращается ноль.

## <a name="remarks"></a>Примечания

Любой сбой при вызове метода `IErrorInfo::GetHelpContext` игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
