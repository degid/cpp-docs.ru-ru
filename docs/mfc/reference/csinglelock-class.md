---
title: Класс CSingleLock
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 231397228d94e58665602453b5d377571e24a967
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318268"
---
# <a name="csinglelock-class"></a>Класс CSingleLock

Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.

## <a name="syntax"></a>Синтаксис

```
class CSingleLock
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Формирует объект `CSingleLock`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSingleLock::IsLocked](#islocked)|Определяет, заблокирован ли объект.|
|[CSingleLock::Lock](#lock)|Ожидания на объекте синхронизации.|
|[CSingleLock::Разблокировать](#unlock)|Выпускает объект синхронизации.|

## <a name="remarks"></a>Примечания

`CSingleLock`не имеет базового класса.

Для того, чтобы использовать классы синхронизации [CSemaphore,](../../mfc/reference/csemaphore-class.md) [CMutex,](../../mfc/reference/cmutex-class.md) [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)и `CSingleLock` [CEvent,](../../mfc/reference/cevent-class.md)необходимо создать объект [cMultiLock,](../../mfc/reference/cmultilock-class.md) чтобы подождать и выпустить объект синхронизации. Используйте, `CSingleLock` когда вам нужно только ждать на одном объекте за один раз. Используйте, `CMultiLock` когда есть несколько объектов, которые можно использовать в определенное время.

Чтобы использовать `CSingleLock` объект, позвоните его конструктору внутри функции члена в классе контролируемого ресурса. Затем позвоните в функцию участника [IsLocked,](#islocked) чтобы определить, доступен ли ресурс. Если это так, продолжайте оставшуюся часть функции члена. Если ресурс недоступен, либо подождите определенное время для выпуска ресурса, либо сбой возврата. После завершения использования ресурса либо вызов [функции разблокировки,](#unlock) если `CSingleLock` объект `CSingleLock` будет использован снова, либо позвольте уничтожению объекта.

`CSingleLock`объекты требуют присутствия объекта, полученного из [CSyncObject.](../../mfc/reference/csyncobject-class.md) Обычно это член данных класса контролируемого ресурса. Для получения дополнительной информации о том, как использовать `CSingleLock` объекты, смотрите статью [Многопоточность: Как использовать классы синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CSingleLock`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a>CSingleLock::CSingleLock

Формирует объект `CSingleLock`.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Параметры

*pObject*<br/>
Точки к объекту синхронизации, к нему следует получить доступ. Не может быть NULL.

*bInitialLock*<br/>
Уточняется, следует ли сначала пытаться получить доступ к поставляемому объекту.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается из функции элемента доступа контролируемого ресурса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a>CSingleLock::IsLocked

Определяет, не сигнализируется ли объект с объектом `CSingleLock` (недоступен).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект заблокирован; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a>CSingleLock::Lock

Вызовите эту функцию, чтобы получить доступ к ресурсу, контролируемому объектом синхронизации, поставляемым конструктору. `CSingleLock`

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Параметры

*dwTimeOut*<br/>
Определяетвремя время ожидания объекта синхронизации (сигнал). Если INFINITE, будет ждать, `Lock` пока объект сигнализируется перед возвращением.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Если объект синхронизации сигнализируется, вернется успешно, `Lock` и теперь поток владеет объектом. Если объект синхронизации не сигнализирован (недоступен), `Lock` будет ждать, пока объект синхронизации станет сигналом до количества миллисекунд, указанного в параметре *dwTimeOut.* Если объект синхронизации не стал сигналом в указанное `Lock` время, возвращается сбой.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a>CSingleLock::Разблокировать

Выпускает объект синхронизации, принадлежащий `CSingleLock`.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Количество доступных для выпуска. Должно быть больше 0. Если указанная сумма приведет к тому, что количество объекта превысит его максимальный уклад, количество не изменяется, а функция возвращает FALSE.

*lPrevCount*<br/>
Указывает на перемену для получения предыдущего счета объекта синхронизации. Если NULL, предыдущий подсчет не возвращается.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция называется `CSingleLock`'s destructor.

Если вам нужно освободить несколько пунктов доступа семафора, `Unlock` используйте вторую форму и укажите количество доступных для выпуска.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMultiLock](../../mfc/reference/cmultilock-class.md)
