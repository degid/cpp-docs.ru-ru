---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 4ac902f0fda90f77526ef53139ef0d523d8c22e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180788"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Блок, относящийся только к системам Microsoft**

Конструирует объект **_com_error** .

## <a name="syntax"></a>Синтаксис

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Параметры

*кадров*<br/>
Сведения HRESULT.

*перринфо*<br/>
Объект `IErrorInfo`.

*фаддреф*<br/>
По умолчанию конструктор вызывает AddRef для интерфейса `IErrorInfo`, отличного от NULL. Это обеспечивает правильный подсчет ссылок в общем случае, когда владение интерфейсом передается в объект **_com_error** , например:

```cpp
throw _com_error(hr, perrinfo);
```

Если вы не хотите, чтобы код переносит владение объекту **_com_error** , а `AddRef` требуется смещение `Release` в деструкторе **_com_error** , создайте объект следующим образом:

```cpp
_com_error err(hr, perrinfo, true);
```

*что*<br/>
Существующий объект **_com_error** .

## <a name="remarks"></a>Примечания

Первый конструктор создает новый объект с заданным значением HRESULT и необязательным `IErrorInfo` объектом. Вторая создает копию существующего объекта **_com_error** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_error](../cpp/com-error-class.md)
