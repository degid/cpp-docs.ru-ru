---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: b5e884956b5a51d3c714f1a81dc6945409f74f4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180671"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Блок, относящийся только к системам Microsoft**

Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.

## <a name="syntax"></a>Синтаксис

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает строковое сообщение для HRESULT, записанного в объекте `_com_error`. Если HRESULT является сопоставленным 16-битным [wCode](../cpp/com-error-wcode.md), возвращается универсальное сообщение "`IDispatch error #<wCode>`". Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`". В зависимости от состояния макроса _UNICODE, возвращается строка Юникода или многобайтовая строка.

## <a name="remarks"></a>Примечания

Извлекает соответствующий системный текст сообщения для HRESULT, записанный в объекте `_com_error`. Текст системного сообщения получается путем вызова функции "Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) ". Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
