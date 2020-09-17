---
title: Класс CSocketFile
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 83810a05925e5c8302240b61d95c131fdd78b426
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318160"
---
# <a name="csocketfile-class"></a>Класс CSocketFile

Объект `CFile` , используемый для отправки и получения сведений по сети с помощью Windows Sockets.

## <a name="syntax"></a>Синтаксис

```
class CSocketFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|Формирует объект `CSocketFile`.|

## <a name="remarks"></a>Примечания

Для этой `CSocketFile` цели можно `CSocket` прикрепить объект к объекту. Вы также можете и обычно `CSocketFile` прикреплять объект к объекту `CArchive` для упрощения отправки и получения данных с помощью сериализации MFC.

Для сериализации (отправки) данных вы вставляете их в архив, который вызывает `CSocketFile` функции участника для записи данных на `CSocket` объект. Для десеризанизации (получения) данных вы извлекаете из архива. Это приводит к `CSocketFile` тому, что архив `CSocket` вызывает функции членов для чтения данных с объекта.

> [!TIP]
> Помимо `CSocketFile` использования, как описано здесь, вы можете использовать его в `CFile`качестве автономного объекта файла, так же, как вы можете с , его базовый класс. Вы также `CSocketFile` можете использовать с любыми функциями сериализации MFC на основе архива. Поскольку `CSocketFile` не поддерживает `CFile`сятвия всех функций, некоторые функции `CSocketFile`сериализации MFC по умолчанию не совместимы с . Особенно это касается `CEditView` класса. Не следует пытаться `CEditView` сериализовать `CArchive` данные через `CSocketFile` объект, прилагаемый к объекту с помощью; `CEditView::SerializeRaw` вместо `CEditView::Serialize` этого. Функция `SerializeRaw` ожидает, что объект файла `Seek`будет `CSocketFile` иметь функции, такие как , который не имеет.

`CArchive` При использовании `CSocketFile` `CSocket`с и, вы `CSocket::Receive` можете столкнуться с `PumpMessages(FD_READ)`ситуацией, когда входит в цикл (по ) ждет запрошенное количество байтов. Это связано с тем, что розетки Windows `CSocketFile` позволяют вызвать только один вызов recv в FD_READ уведомления, но и `CSocket` разрешают несколько вызовов recv в FD_READ. Если вы получаете FD_READ, когда нет данных для чтения, приложение зависает. Если вы никогда не получите другой FD_READ, приложение перестает общаться через розетку.

Эту проблему можно решить следующим образом. В `OnReceive` методе вашего класса гнезда `CAsyncSocket::IOCtl(FIONREAD, ...)` звоните `Serialize` перед вызовом метода класса сообщений, когда ожидаемые данные, которые будут считываться из гнезда, превышают размер одного пакета TCP (максимальная трансмиссия сетевой среды, обычно не менее 1096 байтов). Если размер имеющихся данных меньше, чем требуется, подождите, пока все данные будут получены, и только после этого начните операцию чтения.

В следующем примере — приблизительное количество байтов, `m_dwExpected` которые пользователь ожидает получить. Предполагается, что вы объявите об этом в другом месте вашего кода.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Для получения дополнительной информации [см. Windows Розетки в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows розетки: Использование розетки с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), а также [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a>CSocketFile::CSocketFile

Формирует объект `CSocketFile`.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Параметры

*pSocket*<br/>
Розетка для крепления `CSocketFile` к объекту.

*bArchiveCompatible*<br/>
Определяет, предназначен ли объект файла для `CArchive` использования с объектом. Пройдите FALSE только в `CSocketFile` том случае, если вы хотите использовать объект `CFile` в автономном порядке, как вы бы автономный объект, с определенными ограничениями. Этот флаг изменяет способ `CArchive` управления `CSocketFile` объектом, прикрепленным к объекту, для чтения.

### <a name="remarks"></a>Примечания

Разрушатель объекта отсаживается от объекта розетки, когда объект выходит из области или удаляется.

> [!NOTE]
> A `CSocketFile` также может использоваться в качестве `CArchive` (ограниченного) файла без объекта. По умолчанию `CSocketFile` параметр *bArchiveCompatible* конструктора является правдой. Это указывает на то, что объект файла предназначен для использования в архиве. Чтобы использовать объект файла без архива, передайте FALSE в параметре *bArchiveCompatible.*

В режиме «архивной совместимости» `CSocketFile` объект обеспечивает лучшую производительность и снижает опасность «замка». Взаимоблокировка возникает, когда как отправка, так и получение розетки ждут друг от друга, или для общего ресурса. Эта ситуация может `CArchive` возникнуть, `CSocketFile` если объект работает `CFile` с тем, как он работает с объектом. С `CFile`помощью архива можно предположить, что если он получает меньше байтов, чем он просил, конец файла был достигнут.

С `CSocketFile`, однако, данные основаны сообщения; буфер может содержать несколько сообщений, поэтому получение меньшего количества запрошенных байтов не означает конец файла. Приложение не блокирует в этом случае, `CFile`как это может быть с, и он может продолжать чтение сообщений из буфера, пока буфер пуст. Функция [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) полезна для мониторинга состояния буфера архива в таком случае.

Для получения дополнительной информации об использовании `CSocketFile`, см. статьи Windows [розетки: Использование розетки с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md) и Windows [розетки: Пример розетки с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>См. также раздел

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)
