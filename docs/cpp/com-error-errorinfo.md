---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: cedb9ccadc63166c43d980333d93a195254700d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180710"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Блок, относящийся только к системам Microsoft**

Получает объект `IErrorInfo`, переданный конструктору.

## <a name="syntax"></a>Синтаксис

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Необработанный элемент `IErrorInfo`, переданный в конструктор.

## <a name="remarks"></a>Примечания

Извлекает инкапсулированный `IErrorInfo` элемент в объекте `_com_error` или значение NULL, если элемент `IErrorInfo` не записывается. Вызывающий объект должен вызвать `Release` для возвращенного объекта, когда он завершил использовать его.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
