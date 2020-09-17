---
title: AsyncBase - класс
ms.date: 10/08/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 8684096e76c08456a9c6813b7f04d79b820e41e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211558"
---
# <a name="asyncbase-class"></a>AsyncBase - класс

Реализует асинхронный конечный автомат среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>Параметры

*ткомплете*<br/>
Обработчик событий, который вызывается после завершения асинхронной операции.

*TProgress*<br/>
Обработчик событий, который вызывается, когда выполняющаяся асинхронная операция сообщает о текущем состоянии операции.

*resultType*<br/>
Одно из значений перечисления [асинкресулттипе](asyncresulttype-enumeration.md) . По умолчанию — `SingleResult`.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------
[Метод asyncbase:: метод asyncbase](#asyncbase) | Инициализирует экземпляр класса `AsyncBase`.

### <a name="public-methods"></a>Открытые методы

name                                         | Описание
-------------------------------------------- | -------------------------------------------------------------------------------------
[Метод asyncbase:: Cancel](#cancel)                 | Отменяет асинхронную операцию.
[Метод asyncbase:: Close](#close)                   | Закрывает асинхронную операцию.
[Метод asyncbase:: FireCompletion](#firecompletion) | Вызывает обработчик событий завершения или сбрасывает внутренний делегат хода выполнения.
[Метод asyncbase:: FireProgress](#fireprogress)     | Вызывает текущий обработчик событий процесса выполнения.
[Метод asyncbase:: get_ErrorCode](#get-errorcode)   | Извлекает код ошибки для текущей асинхронной операции.
[Метод asyncbase:: get_Id](#get-id)                 | Получает маркер асинхронной операции.
[Метод asyncbase:: get_Status](#get-status)         | Извлекает значение, указывающее состояние асинхронной операции.
[Метод asyncbase:: GetOnComplete](#getoncomplete)   | Копирует адрес текущего обработчика событий завершения в указанную переменную.
[Метод asyncbase:: GetOnProgress](#getonprogress)   | Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.
[Метод asyncbase::p ut_Id](#put-id)                 | Задает маркер асинхронной операции.
[Метод asyncbase::P Утонкомплете](#putoncomplete)   | Устанавливает в качестве адреса обработчика событий завершения указанное значение.
[Метод asyncbase::P Утонпрогресс](#putonprogress)   | Задает для адреса обработчика событий progress указанное значение.

### <a name="protected-methods"></a>Защищенные методы

Имя                                                                         | Описание
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[Метод asyncbase:: CheckValidStateForDelegateCall](#checkvalidstatefordelegatecall) | Проверяет, можно ли изменять свойства делегата в текущем асинхронном состоянии.
[Метод asyncbase:: CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | Проверяет, можно ли собирать результаты асинхронной операции в текущем асинхронном состоянии.
[Метод asyncbase:: ContinueAsyncOperation](#continueasyncoperation)                 | Определяет, должна ли асинхронная операция продолжать обработку или должна остановиться.
[Метод asyncbase:: CurrentStatus](#currentstatus)                                   | Извлекает состояние текущей асинхронной операции.
[Метод asyncbase:: ErrorCode](#errorcode)                                           | Извлекает код ошибки для текущей асинхронной операции.
[Метод asyncbase:: OnCancel](#oncancel)                                             | При переопределении в производном классе отменяет асинхронную операцию.
[Метод asyncbase:: OnClose](#onclose)                                               | При переопределении в производном классе закрывает асинхронную операцию.
[Метод asyncbase:: OnStart](#onstart)                                               | При переопределении в производном классе запускает асинхронную операцию.
[Метод asyncbase:: Start](#start)                                                   | Запускает асинхронную операцию.
[Метод asyncbase:: TryTransitionToCompleted](#trytransitiontocompleted)             | Указывает, завершена ли текущая асинхронная операция.
[Метод asyncbase:: TryTransitionToError](#trytransitiontoerror)                     | Указывает, может ли указанный код ошибки изменить состояние внутренней ошибки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Требования

**Заголовок:** Async.h

**Пространство имен:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>Метод asyncbase:: метод asyncbase

Инициализирует экземпляр класса `AsyncBase`.

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>Метод asyncbase:: Cancel

Отменяет асинхронную операцию.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию всегда возвращает S_OK.

### <a name="remarks"></a>Примечания

`Cancel()`является реализацией по умолчанию `IAsyncInfo::Cancel` и не выполняет фактическую работу. Чтобы фактически отменить асинхронную операцию, переопределите `OnCancel()` чистый виртуальный метод.

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>Метод asyncbase:: CheckValidStateForDelegateCall

Проверяет, можно ли изменять свойства делегата в текущем асинхронном состоянии.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, можно ли изменять свойства делегата; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>Метод asyncbase:: CheckValidStateForResultsCall

Проверяет, можно ли собирать результаты асинхронной операции в текущем асинхронном состоянии.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, можно ли собирать результаты; в противном случае E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseclose"></a><a name="close"></a>Метод asyncbase:: Close

Закрывает асинхронную операцию.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция закрывается или уже закрыта; в противном случае E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Примечания

`Close()`является реализацией по умолчанию `IAsyncInfo::Close` и не выполняет фактическую работу. Чтобы фактически закрыть асинхронную операцию, переопределите `OnClose()` чистый виртуальный метод.

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>Метод asyncbase:: ContinueAsyncOperation

Определяет, должна ли асинхронная операция продолжать обработку или должна остановиться.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущее состояние асинхронной операции *запускается*, что означает, что операция должна быть продолжена. В противном случае — значение **`false`** , означающее, что операция должна остановиться.

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>Метод asyncbase:: CurrentStatus

Извлекает состояние текущей асинхронной операции.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Параметры

*status*<br/>
Расположение, в котором эта операция сохраняет текущее состояние.

### <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>Метод asyncbase:: ErrorCode

Извлекает код ошибки для текущей асинхронной операции.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Расположение, в котором эта операция хранит текущий код ошибки.

### <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>Метод asyncbase:: FireCompletion

Вызывает обработчик событий завершения или сбрасывает внутренний делегат хода выполнения.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Примечания

Первая версия `FireCompletion()` сбрасывает переменную делегата внутреннего выполнения. Вторая версия вызывает обработчик событий завершения, если асинхронная операция завершена.

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>Метод asyncbase:: FireProgress

Вызывает текущий обработчик событий процесса выполнения.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Параметры

*АРГ*<br/>
Метод обработчика событий для запуска.

### <a name="remarks"></a>Примечания

`ProgressTraits`является производным от [структуры константа argtraitshelper](argtraitshelper-structure.md).

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>Метод asyncbase:: get_ErrorCode

Извлекает код ошибки для текущей асинхронной операции.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Параметры

*errorCode*<br/>
Расположение, в котором хранится текущий код ошибки.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL, если текущая асинхронная операция закрыта.

## <a name="asyncbaseget_id"></a><a name="get-id"></a>Метод asyncbase:: get_Id

Получает маркер асинхронной операции.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
Расположение, в котором должен храниться этот маркер.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Примечания

Этот метод реализует `IAsyncInfo::get_Id`.

## <a name="asyncbaseget_status"></a><a name="get-status"></a>Метод asyncbase:: get_Status

Извлекает значение, указывающее состояние асинхронной операции.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Параметры

*status*<br/>
Расположение, в котором должно храниться состояние. Дополнительные сведения см. в разделе `Windows::Foundation::AsyncStatus` Enumeration.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Примечания

Этот метод реализует `IAsyncInfo::get_Status`.

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>Метод asyncbase:: GetOnComplete

Копирует адрес текущего обработчика событий завершения в указанную переменную.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Параметры

*комплетехандлер*<br/>
Расположение, в котором хранится адрес текущего обработчика событий завершения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>Метод asyncbase:: GetOnProgress

Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Параметры

*прогресшандлер*<br/>
Расположение, в котором сохраняется адрес текущего обработчика событий процесса выполнения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>Метод asyncbase:: OnCancel

При переопределении в производном классе отменяет асинхронную операцию.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>Метод asyncbase:: OnClose

При переопределении в производном классе закрывает асинхронную операцию.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>Метод asyncbase:: OnStart

При переопределении в производном классе запускает асинхронную операцию.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>Метод asyncbase::p ut_Id

Задает маркер асинхронной операции.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
Ненулевой маркер.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_INVALIDARG или E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>Метод asyncbase::P Утонкомплете

Устанавливает в качестве адреса обработчика событий завершения указанное значение.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Параметры

*комплетехандлер*<br/>
Адрес, на который задается обработчик событий завершения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>Метод asyncbase::P Утонпрогресс

Задает для адреса обработчика событий progress указанное значение.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Параметры

*прогресшандлер*<br/>
Адрес, на который задается обработчик событий progress.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasestart"></a><a name="start"></a>Метод asyncbase:: Start

Запускает асинхронную операцию.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция запускается или уже запущена; в противном случае E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Примечания

`Start()`— Это защищенный метод, который не является видимым извне, так как асинхронные операции "горячий запуск" перед возвратом вызывающему объекту.

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>Метод asyncbase:: TryTransitionToCompleted

Указывает, завершена ли текущая асинхронная операция.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если асинхронная операция завершена. в противном случае — **`false`** .

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>Метод asyncbase:: TryTransitionToError

Указывает, может ли указанный код ошибки изменить состояние внутренней ошибки.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Ошибка HRESULT.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если состояние внутренней ошибки было изменено; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже имеет значение S_OK. Эта операция не действует, если состояние ошибки — "ошибка", "отменено", "завершено" или "закрыто".
