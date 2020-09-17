---
title: Класс CSyncObject
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: ebfbc185cdca2effc96ce2e6d96d05f997c52bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365970"
---
# <a name="csyncobject-class"></a>Класс CSyncObject

Чисто виртуальный класс, обеспечивающий общую функциональность объектов синхронизации Win32.

## <a name="syntax"></a>Синтаксис

```
class CSyncObject : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Формирует объект `CSyncObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::Lock](#lock)|Получает доступ к объекту синхронизации.|
|[CSyncObject::Разблокировка](#unlock)|Получает доступ к объекту синхронизации.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::оператор HANDLE](#operator_handle)|Обеспечивает доступ к объекту синхронизации.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|Ручка к базовому объекту синхронизации.|

## <a name="remarks"></a>Примечания

Библиотека класса Фонда Майкрософт предоставляет `CSyncObject`несколько классов, полученных из . Это [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CSemaphore](../../mfc/reference/csemaphore-class.md).

Информацию об использовании объектов синхронизации можно узнать в статье [«Многопоточность: как использовать классы синхронизации».](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a>CSyncObject::CSyncObject

Строит объект синхронизации с поставляемым именем.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Параметры

*pstrName*<br/>
Имя объекта. Если NULL, *pstrName* будет нулевым.

## <a name="csyncobjectlock"></a><a name="lock"></a>CSyncObject::Lock

Вызовите эту функцию, чтобы получить доступ к ресурсу, контролируемому объектом синхронизации.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
Определяет количество времени в миллисекундах для ожидания объекта синхронизации (сигнализируется). Если INFINITE, будет ждать, `Lock` пока объект сигнализируется перед возвращением.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Если объект синхронизации сигнализируется, вернется успешно, `Lock` и теперь поток владеет объектом. Если объект синхронизации не сигнализирован (недоступен), `Lock` будет ждать, пока объект синхронизации станет сигналом до количества миллисекунд, указанного в параметре *dwTimeOut.* Если объект синхронизации не стал сигналом в указанное `Lock` время, возвращается сбой.

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a>CSyncObject::m_hObject

Ручка к базовому объекту синхронизации.

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a>CSyncObject::оператор HANDLE

Используйте этот оператор, чтобы `CSyncObject` получить ручку объекта.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка объекта синхронизации; в противном случае, NULL.

### <a name="remarks"></a>Примечания

Ручку можно использовать для прямого вызова AA Windows.

## <a name="csyncobjectunlock"></a><a name="unlock"></a>CSyncObject::Разблокировка

Декларация `Unlock` без параметров является чистой виртуальной функцией и должна быть `CSyncObject`перекрыта всеми классами, вытекающими из .

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Не используется по умолчанию реализации.

*lpPrevCount*<br/>
Не используется по умолчанию реализации.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Примечания

Реализация декларации по умолчанию с двумя параметрами всегда возвращает TRUE. Эта функция призвана освободить доступ к объекту синхронизации, принадлежащему потоку вызовов. Вторая декларация предусмотрена для объектов синхронизации, таких как семафоры, которые позволяют более чем одному доступу к контролируемому ресурсу.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
