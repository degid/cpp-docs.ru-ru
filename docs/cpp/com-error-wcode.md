---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: 92dffbdbe034ef55be04c1b7d204be6880d8d4b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190200"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Блок, относящийся только к системам Microsoft**

Извлекает 16-разрядный код ошибки, сопоставленный с инкапсулированным значением HRESULT.

## <a name="syntax"></a>Синтаксис

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Если значение HRESULT находится в диапазоне от 0x80040200 до 0x8004FFFF, то метод `WCode` возвращает значение HRESULT минус 0x80040200. в противном случае возвращается ноль.

## <a name="remarks"></a>Примечания

Метод `WCode` используется для отмены сопоставления, происходящего в коде поддержки COM. Оболочка для `dispinterface` свойства или метода вызывает подпрограмму поддержки, которая упаковывает аргументы и вызывает `IDispatch::Invoke`. При возврате, если возвращается ошибка HRESULT `DISP_E_EXCEPTION`, сведения об ошибке извлекаются из структуры `EXCEPINFO`, передаваемой `IDispatch::Invoke`. Код ошибки может представлять собой 16-разрядное значение, хранящееся в `wCode` элемента структуры `EXCEPINFO` или полное 32-разрядное значение в `scode` элемента структуры `EXCEPINFO`. Если возвращается 16-разрядный `wCode`, он сначала должен быть сопоставлен со значением HRESULT 32-разрядного сбоя.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[Класс _com_error](../cpp/com-error-class.md)
