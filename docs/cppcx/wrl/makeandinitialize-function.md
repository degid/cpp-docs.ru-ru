---
title: Функция MakeAndInitialize
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
ms.openlocfilehash: 28d9e586a766a131e7ab6280859845810c1d9814
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213802"
---
# <a name="makeandinitialize-function"></a>Функция MakeAndInitialize

Инициализирует указанный класс среда выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename T,
    typename I,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9>
HRESULT MakeAndInitialize(
    _Outptr_result_nullonfailure_ I** ppvObject,
    TArg1 &&arg1,
    TArg2 &&arg2,
    TArg3 &&arg3,
    TArg4 &&arg4,
    TArg5 &&arg5,
    TArg6 &&arg6,
    TArg7 &&arg7,
    TArg8 &&arg8,
    TArg9 &&arg9) throw()
```

### <a name="parameters"></a>Параметры

*T*<br/>
Определяемый пользователем класс, наследуемый от `WRL::RuntimeClass`.

*TArg1*<br/>
Тип аргумента 1, который передается указанному классу среды выполнения.

*TArg2*<br/>
Тип аргумента 2, который передается указанному классу среды выполнения.

*TArg3*<br/>
Тип аргумента 3, который передается указанному классу среды выполнения.

*TArg4*<br/>
Тип аргумента 4, который передается указанному классу среды выполнения.

*TArg5*<br/>
Тип аргумента 5, который передается указанному классу среды выполнения.

*TArg6*<br/>
Тип аргумента 6, который передается указанному классу среды выполнения.

*TArg7*<br/>
Тип аргумента 7, который передается указанному классу среды выполнения.

*TArg8*<br/>
Тип аргумента 8, который передается указанному классу среды выполнения.

*TArg9*<br/>
Тип аргумента 9, который передается указанному классу среды выполнения.

*arg1*<br/>
Аргумент 1, передаваемый в указанный класс среды выполнения.

*arg2*<br/>
Аргумент 2, передаваемый в указанный класс среды выполнения.

*arg3*<br/>
Аргумент 3, передаваемый в указанный класс среды выполнения.

*arg4*<br/>
Аргумент 4, передаваемый в указанный класс среды выполнения.

*arg5*<br/>
Аргумент 5, передаваемый в указанный класс среды выполнения.

*arg6*<br/>
Аргумент 6, передаваемый в указанный класс среды выполнения.

*arg7*<br/>
Аргумент 7, передаваемый в указанный класс среды выполнения.

*arg8*<br/>
Аргумент 8, передаваемый в указанный класс среды выполнения.

*arg9*<br/>
Аргумент 9, передаваемый в указанный класс среды выполнения.

## <a name="return-value"></a>Возвращаемое значение

Значение HRESULT.

## <a name="remarks"></a>Примечания

См. раздел [как напрямую создавать экземпляры компонентов WRL](how-to-instantiate-wrl-components-directly.md) , чтобы узнать о различиях между этой функцией и [Microsoft:: WRL:: make](make-function.md), а также в качестве примера.

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)
