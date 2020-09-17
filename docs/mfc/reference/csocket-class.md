---
title: Класс CSocket
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: 730bea34354b008d641ecc28e7368f79efad12a7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751152"
---
# <a name="csocket-class"></a>Класс CSocket

Получает от `CAsyncSocket`, наследует его инкапсуляции Windows Sockets API, и представляет собой `CAsyncSocket` более высокий уровень абстракции, чем у объекта.

## <a name="syntax"></a>Синтаксис

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|Формирует объект `CSocket`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSocket::Прикрепите](#attach)|Прикрепляет ручку SOCKET к объекту. `CSocket`|
|[CSocket::ОтменаБлокировкаКолл](#cancelblockingcall)|Отменяет блокировку вызова, который в настоящее время выполняется.|
|[CSocket::Создание](#create)|Создает розетку.|
|[CSocket::FromHandle](#fromhandle)|Возвращает указатель на `CSocket` объект с учетом ручки SOCKET.|
|[CSocket::Блокирование](#isblocking)|Определяет, выполняется ли блокировка вызова.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CSocket::OnMessage](#onmessagepending)|Вызывается для обработки ожидающих сообщений в ожидании завершения блокировки вызова.|

## <a name="remarks"></a>Примечания

`CSocket`работает с `CSocketFile` `CArchive` классами и управляет отправкой и получением данных.

Объект `CSocket` также обеспечивает блокировку, которая имеет важное `CArchive`значение для синхронной работы. Блокирующие функции, `Send` `ReceiveFrom`такие `SendTo`как `Accept` `Receive`, , `CAsyncSocket`, и (все унаследованные от), не возвращают ошибку `WSAEWOULDBLOCK` в `CSocket`. Вместо этого эти функции ждут завершения операции. Кроме того, исходный вызов завершается с ошибкой `CancelBlockingCall` WSAEINTR, если он вызывается во время блокировки одной из этих функций.

Чтобы использовать `CSocket` объект, позвоните в `Create` конструктор, а затем позвоните для создания основной ручки SOCKET (тип SOCKET). Параметры по умолчанию `Create` создают разъем потока, но если вы не `CArchive` используете розетку с объектом, можно указать параметр для создания разъема datagram или привязать к определенному порту для создания разъема сервера. Подключайтесь к клиентской розетке, используя `Connect` на стороне клиента и `Accept` на стороне сервера. Затем создайте `CSocketFile` объект и `CSocket` присваивайте его к объекту в конструкторе. `CSocketFile` Затем создайте `CArchive` объект для отправки и один для получения данных (по мере необходимости), а затем связать их с объектом `CSocketFile` `CArchive` в конструкторе. Когда связь завершена, `CArchive` `CSocketFile`уничтожить `CSocket` , и объекты. Тип данных SOCKET описан в статье [Windows Sockets: Background](../../mfc/windows-sockets-background.md).

`CArchive` При использовании `CSocketFile` `CSocket`с и, вы `CSocket::Receive` можете столкнуться с `PumpMessages(FD_READ)`ситуацией, когда входит в цикл (по ) ждет запрошенное количество байтов. Это связано с тем, что розетки Windows `CSocketFile` позволяют вызвать только один вызов recv в FD_READ уведомления, но и `CSocket` разрешают несколько вызовов recv в FD_READ. Если вы получаете FD_READ, когда нет данных для чтения, приложение зависает. Если вы никогда не получите другой FD_READ, приложение перестает общаться через розетку.

Эту проблему можно решить следующим образом. В `OnReceive` методе вашего класса гнезда `CAsyncSocket::IOCtl(FIONREAD, ...)` звоните `Serialize` перед вызовом метода класса сообщений, когда ожидаемые данные, которые будут считываться из гнезда, превышают размер одного пакета TCP (максимальная трансмиссия сетевой среды, обычно не менее 1096 байтов). Если размер имеющихся данных меньше, чем требуется, подождите, пока все данные будут получены, и только после этого начните операцию чтения.

В следующем примере — приблизительное количество байтов, `m_dwExpected` которые пользователь ожидает получить. Предполагается, что вы объявите об этом в другом месте вашего кода.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> При использовании разъемов MFC во вторичных потоках в `AfxSocketInit` статично связанном приложении MFC необходимо вызвать каждый поток, который использует розетки для инициализации библиотек розетки. По умолчанию, `AfxSocketInit` называется только в основном потоке.

Для получения дополнительной информации, см [Windows розетки в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows розетки: Использование розетки с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows розетки: Как розетки с архивами работы](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows розетки: Последовательность операций](../../mfc/windows-sockets-sequence-of-operations.md), [Windows розетки: Пример разъемы С использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

## <a name="csocketattach"></a><a name="attach"></a>CSocket::Прикрепите

Вызов эту функцию `hSocket` участника, `CSocket` чтобы прикрепить ручку к объекту.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит ручку к розетке.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно.

### <a name="remarks"></a>Примечания

Ручка SOCKET хранится в [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) члена данных объекта.

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a>CSocket::ОтменаБлокировкаКолл

Вызов этой функции участника, чтобы отменить блокировку вызова в настоящее время в процессе.

```cpp
void CancelBlockingCall();
```

### <a name="remarks"></a>Примечания

Эта функция отменяет любую выдающуюся операцию блокировки для этой розетки. Первоначальный блокирующий вызов завершится как можно скорее с ошибкой WSAEINTR.

В случае операции `Connect` блокировки реализация Windows Sockets завершает блокировку вызова как можно скорее, но это может быть невозможно для ресурсов розетки, которые будут выпущены до завершения соединения (а затем был сдан) или приурочен. Это, вероятно, будет заметно только в том случае, если приложение немедленно попытается открыть новую розетку (если розетки отсутствуют), или подключиться к тому же одноранговому усту.

Отмена любой `Accept` операции, кроме может оставить гнездо в неопределенном состоянии. Если приложение отменяет операцию блокировки на розетке, единственной операцией, которую приложение может зависеть от возможности выполнить на `Close`розетке, является вызов, хотя другие операции могут работать на некоторых реализациях Windows Sockets. Если вы желаете максимальной переносимости приложения, вы должны быть осторожны, чтобы не зависеть от выполнения операций после отмены.

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketcreate"></a><a name="create"></a>CSocket::Создание

Вызов функции **члена Create** после построения объекта розетки для создания разъема Windows и прикрепите ее.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Параметры

*nSocketPort*<br/>
Конкретный порт, который будет использоваться с розеткой, или 0, если вы хотите, чтобы MFC выбрать порт.

*nSocketType*<br/>
SOCK_STREAM или SOCK_DGRAM.

*lpszSocketАдрес*<br/>
Указатель на строку, содержащую сетевой адрес подключенной розетки, пунктирный номер, такой как "128.56.22.8". Прохождение строки NULL для `CSocket` этого параметра указывает на то, что экземпляр должен прослушивать активность клиента на всех сетевых интерфейсах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, и определенный `GetLastError`код ошибки может быть извлечен, позвонив .

### <a name="remarks"></a>Примечания

`Create`затем `Bind` вызывает привязать розетку к указанному адресу. Поддерживаются следующие типы розетки:

- SOCK_STREAM обеспечивает секвенированные, надежные, двусторонние, основанные на подключении потоки байт. Использует протокол управления передачей (TCP) для семейства адресов Интернета.

- SOCK_DGRAM поддерживает данные, которые являются ненадежными, ненадежными буферами фиксированной (обычно небольшой) максимальной длины. Использует протокол пользовательской datagram (UDP) для семейства адресов Интернета. Чтобы использовать эту опцию, вы не должны `CArchive` использовать розетку с объектом.

    > [!NOTE]
    >  Функция `Accept` члена берет в качестве параметра ссылку на новый пустой `CSocket` объект. Вы должны построить этот `Accept`объект, прежде чем вы звоните. Имейте в виду, что если этот объект розетки выходит за рамки, соединение закрывается. Не вызывайте `Create` этот новый объект розетки.

Для получения дополнительной информации о потоке и [Windows Sockets: Background](../../mfc/windows-sockets-background.md) [Windows Sockets: Ports and Socket Addresses](../../mfc/windows-sockets-ports-and-socket-addresses.md) [разъемах](../../mfc/windows-sockets-using-sockets-with-archives.md)для диаграмм, см.

## <a name="csocketcsocket"></a><a name="csocket"></a>CSocket::CSocket

Формирует объект `CSocket`.

```
CSocket();
```

### <a name="remarks"></a>Примечания

После построения необходимо `Create` позвонить в функцию участника.

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketfromhandle"></a><a name="fromhandle"></a>CSocket::FromHandle

Возвращает указатель объекту. `CSocket`

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Параметры

*hSocket*<br/>
Содержит ручку к розетке.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CSocket` объект, или NULL, `CSocket` если нет объекта, прикрепленного к *hSocket*.

### <a name="remarks"></a>Примечания

При приведении ручки SOCKET, если `CSocket` объект не прикреплен к ручке, функция участника возвращает NULL и не создает временный объект.

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketisblocking"></a><a name="isblocking"></a>CSocket::Блокирование

Вызов этой функции участника, чтобы определить, выполняется ли блокировка вызова.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если розетка блокирует; в противном случае 0.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a>CSocket::OnMessage

Переопределить эту функцию участника, чтобы искать определенные сообщения из Windows и отвечать на них в гнезде.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было обработано; в противном случае 0.

### <a name="remarks"></a>Примечания

Это передовой overridable.

Платформа вызывает `OnMessagePending` вызовы, пока розетка накачивает сообщения Windows, чтобы дать вам возможность иметь дело с сообщениями, представляющими интерес для вашего приложения. Для примеров того, `OnMessagePending`как вы могли бы использовать, смотрите статью [Windows Sockets: Получение из разъема классов](../../mfc/windows-sockets-deriving-from-socket-classes.md).

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>См. также раздел

[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
