---
title: Интерфейс Исреадпулконфиг
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: cba82055c292fc966dc2328773cce4aa64d45a64
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835432"
---
# <a name="ithreadpoolconfig-interface"></a>Интерфейс Исреадпулконфиг

Этот интерфейс предоставляет методы для настройки пула потоков.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[GetSize](#getsize)|Вызовите этот метод, чтобы получить количество потоков в пуле.|
|[Время ожидания](#gettimeout)|Вызовите этот метод, чтобы получить максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.|
|[SetSize](#setsize)|Вызовите этот метод, чтобы задать количество потоков в пуле.|
|[SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.|

## <a name="remarks"></a>Примечания

Этот интерфейс реализуется с помощью [ксреадпул](../../atl/reference/cthreadpool-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a> Исреадпулконфиг:: DataSize

Вызовите этот метод, чтобы получить количество потоков в пуле.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Параметры

*пннумсреадс*<br/>
заполняет Адрес переменной, которая в случае успешного выполнения получает количество потоков в пуле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a> Исреадпулконфиг:: не истечение времени

Вызовите этот метод, чтобы получить максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Параметры

*пдвмаксваит*<br/>
заполняет Адрес переменной, которая в случае успешного выполнения получает максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

См. раздел [исреадпулконфиг:: DataSize](#getsize).

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a> Исреадпулконфиг:: SetSize

Вызовите этот метод, чтобы задать количество потоков в пуле.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Параметры

*ннумсреадс*<br/>
Запрошенное число потоков в пуле.

Если *ннумсреадс* является отрицательным, его абсолютное значение будет умножено на число процессоров на компьютере, чтобы получить общее число потоков.

Если *ннумсреадс* равен нулю, ATLS_DEFAULT_THREADSPERPROC будут умножены на количество процессоров на компьютере, чтобы получить общее число потоков.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

См. раздел [исреадпулконфиг:: DataSize](#getsize).

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a> Исреадпулконфиг:: SetTimeout

Вызовите этот метод, чтобы задать максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Параметры

*двмаксваит*<br/>
Запрошенное максимальное время в миллисекундах, в течение которого пул потоков будет ожидать завершения работы потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

См. раздел [исреадпулконфиг:: DataSize](#getsize).

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс Ксреадпул](../../atl/reference/cthreadpool-class.md)
