---
title: Функция обратного вызова (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
ms.openlocfilehash: 8615b92f9b46dcfc6e36867c51eeefdb7a5f5e81
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609086"
---
# <a name="callback-function-wrl"></a>Функция обратного вызова (WRL)

Создает объект, функция-член которого является методом обратного вызова.

## <a name="syntax"></a>Синтаксис

```cpp
template<
   typename TDelegateInterface,
   typename TCallback
>
ComPtr<TDelegateInterface> Callback(
   TCallback callback
);
template<
   typename TDelegateInterface,
   typename TCallbackObject
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)()
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
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
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8,
   TArg9)
);
```

### <a name="parameters"></a>Параметры

*тделегатеинтерфаце*<br/>
Параметр шаблона, определяющий интерфейс делегата, который вызывается при возникновении события.

*ткаллбакк*<br/>
Параметр шаблона, определяющий тип объекта, который представляет объект и его функцию-член обратного вызова.

*ткаллбаккобжект*<br/>
Параметр шаблона, определяющий объект, функция-член которого является методом, вызываемым при возникновении события.

*TArg1*<br/>
Параметр шаблона, который определяет тип первого аргумента метода обратного вызова.

*TArg2*<br/>
Параметр шаблона, который определяет тип второго аргумента метода обратного вызова.

*TArg3*<br/>
Параметр шаблона, который определяет тип третьего аргумента метода обратного вызова.

*TArg4*<br/>
Параметр шаблона, который определяет тип четвертого аргумента метода обратного вызова.

*TArg5*<br/>
Параметр шаблона, который определяет тип пятого аргумента метода обратного вызова.

*TArg6*<br/>
Параметр шаблона, который определяет тип шестого аргумента метода обратного вызова.

*TArg7*<br/>
Параметр шаблона, который определяет тип седьмого аргумента метода обратного вызова.

*TArg8*<br/>
Параметр шаблона, указывающий тип аргумента восьмого метода обратного вызова.

*TArg9*<br/>
Параметр шаблона, который определяет тип девятого аргумента метода обратного вызова.

*обратный вызов*<br/>
Объект, который представляет объект обратного вызова и его функцию-член.

*object*<br/>
Объект, функция-член которого вызывается при возникновении события.

*Method*<br/>
Функция-член, которую необходимо вызвать при возникновении события.

## <a name="return-value"></a>Возвращаемое значение

Объект, функция-член которого является методом обратного вызова.

## <a name="remarks"></a>Примечания

База объекта делегата должна быть `IUnknown` , а не `IInspectable` .

## <a name="requirements"></a>Требования

**Заголовок:** Event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
