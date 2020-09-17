---
title: Функция Make
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
ms.openlocfilehash: 0f2e81e3cd757214805817af2a355a93c1cfd096
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220474"
---
# <a name="make-function"></a>Функция Make

Инициализирует указанный класс среда выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8,
   TArg9 &&arg9
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3
);
template <
   typename T,
   typename TArg1,
   typename TArg2
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2
);
template <
   typename T,
   typename TArg1
>
ComPtr<T> Make(
   TArg1 &&arg1
);
template <
   typename T
>
ComPtr<T> Make();
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

`ComPtr<T>`Объект в случае успеха; в противном случае — значение **`nullptr`** .

## <a name="remarks"></a>Примечания

См. статью [как создать экземпляры компонентов WRL напрямую](how-to-instantiate-wrl-components-directly.md) , чтобы узнать о различиях между этой функцией и [Microsoft:: WRL::D состояния:: MakeAndInitialize](makeandinitialize-function.md), а также в качестве примера.

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
