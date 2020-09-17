---
title: Интерфейс Иворкерсреадклиент
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: aa72f090a006d6936339582a919b0faf5cab6b03
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835354"
---
# <a name="iworkerthreadclient-interface"></a>Интерфейс Иворкерсреадклиент

`IWorkerThreadClient` — Это интерфейс, реализуемый клиентами класса [кворкерсреад](../../atl/reference/cworkerthread-class.md) .

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[CloseHandle](#closehandle)|Реализуйте этот метод, чтобы закрыть маркер, связанный с этим объектом.|
|[Execute](#execute)|Реализуйте этот метод для выполнения кода, когда дескриптор, связанный с этим объектом, получает сигнал.|

## <a name="remarks"></a>Примечания

Реализуйте этот интерфейс, если у вас есть код, который должен выполняться в рабочем потоке в ответ на то, что дескриптор становится сигнальным.

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> Иворкерсреадклиент:: CloseHandle

Реализуйте этот метод, чтобы закрыть маркер, связанный с этим объектом.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Параметры

*ххандле*<br/>
Закрываемый обработчик.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK об успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Маркер, переданный этому методу, был ранее связан с этим объектом посредством вызова [кворкерсреад:: аддхандле](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

В следующем коде показана простая реализация `IWorkerThreadClient::CloseHandle` .

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> Иворкерсреадклиент:: Execute

Реализуйте этот метод для выполнения кода, когда дескриптор, связанный с этим объектом, получает сигнал.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Параметры

*двпарам*<br/>
Параметр User.

*хобжект*<br/>
Дескриптор, который стал сигнальным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK об успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Маркер и DWORD или указатель, переданный этому методу, ранее были связаны с этим объектом посредством вызова [кворкерсреад:: аддхандле](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

В следующем коде показана простая реализация `IWorkerThreadClient::Execute` .

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс Кворкерсреад](../../atl/reference/cworkerthread-class.md)
