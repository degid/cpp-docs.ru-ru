---
title: ArgTraits - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: 16c44d861ebbbc98fa1bffb62a00d1989c0c803c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377161"
---
# <a name="argtraits-structure"></a>ArgTraits - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
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
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Параметры

*TMemberFunction*<br/>
Параметр тигимен для структуры ArgTraits, который не может соответствовать ни одной `Invoke` подписи метода.

*TDelegateИнтерфейс*<br/>
Интерфейс делегата.

*TArg1*<br/>
Тип первого аргумента `Invoke` метода.

*TArg2*<br/>
Тип второго аргумента `Invoke` метода.

*TArg3*<br/>
Тип третьего аргумента `Invoke` метода.

*TArg4*<br/>
Тип четвертого аргумента `Invoke` метода.

*TArg5*<br/>
Тип пятого аргумента `Invoke` метода.

*TArg6*<br/>
Тип шестого аргумента `Invoke` метода.

*TArg7*<br/>
Тип седьмого аргумента `Invoke` метода.

*TArg8*<br/>
Тип восьмого аргумента `Invoke` метода.

*TArg9*<br/>
Тип девятого аргумента `Invoke` метода.

## <a name="remarks"></a>Примечания

Структура `ArgTraits` объявляет указанный интерфейс делегата и анонимную функцию-член, которая принимает указанное число параметров.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя       | Описание
---------- | ----------------------
`Arg1Type` | Typedef для TArg1.
`Arg2Type` | Typedef для TArg2.
`Arg3Type` | Typedef для TArg3.
`Arg4Type` | Typedef для TArg4.
`Arg5Type` | Typedef для TArg5.
`Arg6Type` | Typedef для TArg6.
`Arg7Type` | Typedef для TArg7.
`Arg8Type` | Typedef для TArg8.
`Arg9Type` | Typedef для TArg9.

### <a name="public-constants"></a>Открытые константы

Имя                     | Описание
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits::args](#args) | Ведется подсчет количества параметров `Invoke` на методе интерфейса делегата.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ArgTraits`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="argtraitsargs"></a><a name="args"></a>ArgTraits::args

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Примечания

Ведется подсчет количества параметров `Invoke` на методе интерфейса делегата. Когда `args` равен -1, не может `Invoke` быть соответствия для подписи метода.
