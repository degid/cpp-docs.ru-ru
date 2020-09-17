---
title: Класс CCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: d79199a332f6930619e6b4995b04bc590b6ea580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369366"
---
# <a name="ccriticalsection-class"></a>Класс CCriticalSection

Представляет собой "критический раздел" - объект синхронизации, который позволяет одному потоку одновременно получить доступ к ресурсу или разделу кода.

## <a name="syntax"></a>Синтаксис

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Формирует объект `CCriticalSection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[КритическаяСекция::Блокировка](#lock)|Используйте для получения `CCriticalSection` доступа к объекту.|
|[CCriticalSection::Разблокировать](#unlock)|Освобождает объект `CCriticalSection`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CCriticalSection::оператор CRITICAL_SECTION](#operator_critical_section_star)|Извлекает указатель на внутренний объект CRITICAL_SECTION.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|Объект CRITICAL_SECTION.|

## <a name="remarks"></a>Примечания

Критические разделы полезны, когда только один поток в то время может быть разрешено изменять данные или другой контролируемый ресурс. Например, добавление узлов в связанный список — это процесс, который должен быть разрешен только одним потоком за раз. С помощью `CCriticalSection` объекта для управления связанным списком доступ к списку может получить только один поток.

> [!NOTE]
> Функциональность `CCriticalSection` класса обеспечивается фактическим CRITICAL_SECTION объектом Win32.

Критические разделы используются вместо mutexes (см. [CMutex),](../../mfc/reference/cmutex-class.md)когда скорость имеет решающее значение и ресурс не будет использоваться через границы процесса.

Существует два способа использования `CCriticalSection` объекта: автономный и встроенный в класс.

- Автономный метод для использования отдельного `CCriticalSection` объекта, `CCriticalSection` построить объект, когда это необходимо. После успешного возвращения от конструктора явно заблокируйте объект вызовом в [блокировку.](#lock) Позвоните [разблокировать,](#unlock) когда вы сделали доступ к критическим разделом. Этот метод, в то время как яснее для кого-то читать ваш исходный код, является более склоннык к ошибкам, как вы должны помнить, чтобы заблокировать и разблокировать критический раздел до и после доступа.

   Более предпочтительным методом является использование класса [CSingleLock.](../../mfc/reference/csinglelock-class.md) Он также `Lock` имеет `Unlock` и метод, но вам не придется беспокоиться о разблокировке ресурса, если происходит исключение.

- Встроенный метод Вы также можете поделиться классом с несколькими потоками, добавив в класс член данных типа a `CCriticalSection`-type и при необходимости заблокировав член данных.

Для получения дополнительной `CCriticalSection` информации об [Multithreading: How to Use the Synchronization Classes](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)использовании объектов см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>CCriticalSection::CCriticalSection

Формирует объект `CCriticalSection`.

```
CCriticalSection();
```

### <a name="remarks"></a>Примечания

Чтобы получить доступ `CCriticalSection` к объекту или освободить объект, создайте объект [CSingleLock](../../mfc/reference/csinglelock-class.md) и позвоните в его функции [lock](../../mfc/reference/csinglelock-class.md#lock) and [Unlock.](../../mfc/reference/csinglelock-class.md#unlock) Если `CCriticalSection` объект используется автономно, позвоните в функцию члена [Unlock,](#unlock) чтобы освободить его.

Если конструктор не выделяет требуемую память системы, автоматически выбрасывается исключение памяти (типа [CMemoryException).](../../mfc/reference/cmemoryexception-class.md)

### <a name="example"></a>Пример

  Смотрите пример [cCriticalSection::Lock](#lock).

## <a name="ccriticalsectionlock"></a><a name="lock"></a>КритическаяСекция::Блокировка

Вызовите эту функцию участника, чтобы получить доступ к объекту критических секций.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
`Lock`игнорирует значение этого параметра.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lock`— это блокирующий вызов, который не вернется до тех пор, пока не будет сигнализирован критический объект раздела (становится доступным).

Если время ожидания необходимы, вы можете использовать объект [CMutex](../../mfc/reference/cmutex-class.md) вместо `CCriticalSection` объекта.

Если `Lock` не удается выделить необходимую память системы, автоматически выбрасывается исключение памяти (типа [CMemoryException).](../../mfc/reference/cmemoryexception-class.md)

### <a name="example"></a>Пример

Этот пример демонстрирует вложенный критический подход к разделу, контролируя доступ к общему ресурсу (статическому `_strShared` объекту) с помощью общего `CCriticalSection` объекта. Функция `SomeMethod` демонстрирует безопасное обновление общего ресурса.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a>CCriticalSection::m_sect

Содержит критический объект раздела, `CCriticalSection` который используется всеми методами.

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a>CCriticalSection::оператор CRITICAL_SECTION

Извлекает CRITICAL_SECTION объект.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Примечания

Вызов ими функции для получения указателя на внутренний объект CRITICAL_SECTION.

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Разблокировать

Выпускает `CCriticalSection` объект для использования другим потоком.

```
BOOL Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CCriticalSection` если объект принадлежал потоку и выпуск был успешным; в противном случае 0.

### <a name="remarks"></a>Примечания

Если `CCriticalSection` используется автономный, `Unlock` необходимо вызываться сразу же после завершения использования ресурса, контролируемого критическим разделом. Если используется объект [CSingleLock,](../../mfc/reference/csinglelock-class.md) `CCriticalSection::Unlock` он будет вызываться функцией члена объекта блокировки. `Unlock`

### <a name="example"></a>Пример

  Смотрите пример [cCriticalSection::Lock](#lock).

## <a name="see-also"></a>См. также раздел

[Класс CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMutex](../../mfc/reference/cmutex-class.md)
