---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: d5b05cd4e26f89d42ea23b605f5e6560795a0cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180645"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetGUID`.

## <a name="syntax"></a>Синтаксис

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetGUID` для объекта `IErrorInfo`, записанного в объекте `_com_error`. Если `IErrorInfo` объект не записан, он возвращает `GUID_NULL`.

## <a name="remarks"></a>Примечания

Любой сбой при вызове метода `IErrorInfo::GetGUID` игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
