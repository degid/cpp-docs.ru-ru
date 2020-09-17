---
title: Класс Катлаутосреадмодулет
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: 7308e3a51c531fbe942e2df326c03273eeb326e2
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168728"
---
# <a name="catlautothreadmodulet-class"></a>Класс Катлаутосреадмодулет

Этот класс предоставляет методы для реализации COM-сервера с контейнерами в пуле потоков.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, который будет реализовывать COM-сервер.

*среадаллокатор*<br/>
Класс, управляющий выбором потока. Значение по умолчанию — [ккомсимплесреадаллокатор](../../atl/reference/ccomsimplethreadallocator-class.md).

*двваит*<br/>
Задает интервал времени ожидания в миллисекундах. Значение по умолчанию — INFINITE, что означает, что интервал времени ожидания метода никогда не истекает.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлаутосреадмодулет:: Жетдефаултсреадс](#getdefaultthreads)|Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля EXE в зависимости от числа процессоров.|

## <a name="remarks"></a>Примечания

Класс [катлаутосреадмодуле](../../atl/reference/catlautothreadmodule-class.md) является производным от `CAtlAutoThreadModuleT` , чтобы реализовать COM-сервер модели подразделения в пуле потоков. Он заменяет устаревший класс [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md).

> [!NOTE]
> Этот класс не следует использовать в библиотеке DLL, так как значение *двваит* по умолчанию, равное бесконечности, вызовет взаимоблокировку при ВЫГРУЗКЕ библиотеки DLL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>Катлаутосреадмодулет:: Жетдефаултсреадс

Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля EXE в зависимости от числа процессоров.

```cpp
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Число потоков, создаваемых в модуле EXE.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если вы хотите использовать другой метод для вычисления числа потоков. По умолчанию количество потоков зависит от количества процессоров.

## <a name="see-also"></a>См. также

[Класс Иатлаутосреадмодуле](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс Иатлаутосреадмодуле](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
