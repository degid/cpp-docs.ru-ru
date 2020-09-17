---
title: Класс CMutex
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 2d6f637ab4828b3e70df205ebf359ae45a940d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363283"
---
# <a name="cmutex-class"></a>Класс CMutex

Представляет собой "мутекс" - объект синхронизации, который позволяет одному потоку получить взаимоисключающий доступ к ресурсу.

## <a name="syntax"></a>Синтаксис

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMutex::CMutex](#cmutex)|Формирует объект `CMutex`.|

## <a name="remarks"></a>Примечания

Mutexes полезны, когда только один поток в то время может быть разрешено изменять данные или другой контролируемый ресурс. Например, добавление узлов в связанный список — это процесс, который должен быть разрешен только одним потоком за раз. С помощью `CMutex` объекта для управления связанным списком доступ к списку может получить только один поток.

Чтобы использовать `CMutex` объект, `CMutex` постройте объект, когда это необходимо. Укажите имя mutex, которого вы хотите ждать, и что ваше приложение должно изначально владеть им. Затем вы можете получить доступ к mutex, когда конструктор возвращается. Вызов [CSyncObject::Разблокировать,](../../mfc/reference/csyncobject-class.md#unlock) когда вы сделали доступ к контролируемому ресурсу.

Альтернативным методом `CMutex` использования объектов является `CMutex` добавление переменной типа в качестве члена данных в класс, который вы хотите контролировать. Во время строительства контролируемого объекта позвоните в конструктор анавора `CMutex` данных, указав, является ли mutex изначально принадлежащим, название mutex (если он будет использоваться через границы процесса) и желаемые атрибуты безопасности.

Чтобы получить доступ `CMutex` к ресурсам, контролируемым объектами таким образом, сначала создайте переменную типа [CSingleLock](../../mfc/reference/csinglelock-class.md) или введите [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции члена доступа ресурса. Затем позвоните функции `Lock` члена объекта блокировки (например, [CSingleLock::Lock).](../../mfc/reference/csinglelock-class.md#lock) На этом этапе поток либо получит доступ к ресурсу, либо будет ждать, пока ресурс будет выпущен, и получит доступ, либо будет ждать, пока ресурс будет выпущен и тайм-аут, не получив доступа к ресурсу. В любом случае, доступ к вашему ресурсу был безопасным способом. Чтобы освободить ресурс, используйте функцию `Unlock` члена объекта блокировки (например, [CSingleLock::Unlock),](../../mfc/reference/csinglelock-class.md#unlock)или позвольте объекту блокировки выпасть из сферы охвата.

Для получения дополнительной `CMutex` информации об [Multithreading: How to Use the Synchronization Classes](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)использовании объектов см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

## <a name="cmutexcmutex"></a><a name="cmutex"></a>CMutex::CMutex

Строит названный или `CMutex` неназванный объект.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Параметры

*bInitiallyOwn*<br/>
Определяет, имеет ли поток, `CMutex` создающий объект, доступ к ресурсу, контролируемому mutex.

*lpszName*<br/>
Имя объекта `CMutex`. Если существует другой mutex с тем же именем, *lpszName* должен быть поставлен, если объект будет использоваться через границы процесса. Если **NULL**, mutex будет безымянным. Если имя совпадает с существующим mutex, конструктор `CMutex` создает новый объект, который ссылается на mutex этого имени. Если имя совпадает с существующим объектом синхронизации, который не является mutex, конструкция выйдет из строя.

*lpsaAttribute*<br/>
Атрибуты безопасности для объекта mutex. Полное описание этой структуры [можно](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) SECURITY_ATTRIBUTES в SDK Windows.

### <a name="remarks"></a>Примечания

Чтобы получить доступ `CMutex` к объекту или освободить объект, создайте объект [CMultiLock](../../mfc/reference/cmultilock-class.md) или [CSingleLock](../../mfc/reference/csinglelock-class.md) и позвоните [в](../../mfc/reference/csinglelock-class.md#lock) его функции lock and [Unlock.](../../mfc/reference/csinglelock-class.md#unlock) Если `CMutex` объект используется автономно, позвоните `Unlock` его функции-члена, чтобы освободить его.

> [!IMPORTANT]
> После создания `CMutex` объекта используйте [GetLastError,](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) чтобы убедиться, что mutex еще не существует. Если mutex действительно существовал неожиданно, это может означать, что процесс изгоев приседает на корточках и может быть намерен использовать mutex злонамеренно. В этом случае рекомендуемая процедура, связанная с безопасностью, заключается в том, чтобы закрыть ручку и продолжить, как если бы произошел сбой в создании объекта.

## <a name="see-also"></a>См. также раздел

[Класс CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
