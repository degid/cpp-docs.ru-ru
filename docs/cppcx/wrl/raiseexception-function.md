---
title: RaiseException - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 3270057bf5b1b27a98bef1ab236291eab15d27ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213633"
---
# <a name="raiseexception-function"></a>RaiseException - функция

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>Параметры

*кадров*<br/>
Код исключения вызванного исключения; то есть значение HRESULT невыполненной операции.

*двексцептионфлагс*<br/>
Флаг, указывающий на непрерывное исключение (значение флага равно нулю) или непостоянное исключение (значение флага не равно нулю). По умолчанию исключение недоступно.

## <a name="remarks"></a>Примечания

Вызывает исключение в вызывающем потоке.

Дополнительные сведения см. в описании функции Windows `RaiseException`.

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)
