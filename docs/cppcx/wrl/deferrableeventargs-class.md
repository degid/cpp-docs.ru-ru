---
title: Класс DeferrableEventArgs
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 066918bf2c76b17f06871ee08be674be9b36c161
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032464"
---
# <a name="deferrableeventargs-class"></a>Класс DeferrableEventArgs

Класс шаблона, используемый для типов аргументов событий для задержек.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Параметры

*TEventArgsИнтерфейс*<br/>
Тип интерфейса, который объявляет аргументы для отложенного события.

*TEventArgsClass*<br/>
Класс, который реализует *TEventArgsInterface*.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

| Имя | Описание |
|--|--|
| [DeferrableEventArgs::GetDeferral](#getdeferral) | Получает ссылку на объект [отсрочки,](/uwp/api/windows.foundation.deferral) представляющий отложенное событие. |
| [DeferrableEventArgs::InvokeAllFinished](#invokeallfinished) | Вызывается, чтобы указать, что вся обработка для отложенного события завершена. |

## <a name="remarks"></a>Примечания

Экземпляры этого класса передаются в обработчики событий для отложенных событий. Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.

Класс отображается как первый аргумент обработчика событий для отложенного события. Вы можете позвонить в метод [GetDeferral,](#getdeferral) чтобы получить объект [отсрочки,](/uwp/api/windows.foundation.deferral) из которого вы можете получить всю информацию об отложенном событии. После завершения обработки событий необходимо вызвать завершение в объекте «Задержка». Затем необходимо вызвать [InvokeAllFinished](#invokeallfinished) в конце метода обработчика событий, который гарантирует, что завершение всех отложенных событий будет сообщено должным образом.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

Получает ссылку на объект [отсрочки,](/uwp/api/windows.foundation.deferral) представляющий отложенное событие.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Параметры

*Результат*<br/>
Указатель, который будет ссылаться на объект [отсрочки,](/uwp/api/windows.foundation.deferral) когда вызов завершается.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a>DeferrableEventArgs::InvokeAllFinished

Вызывается, чтобы указать, что вся обработка для отложенного события завершена.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Примечания

Этот метод следует позвонить после вызова источника событий [InvokeAll.](eventsource-class.md#invokeall) Вызов этого метода предотвращает ввод последующих задержек и вызывает принудительное выполнение обработчика завершения, если задержки отсутствовали.
