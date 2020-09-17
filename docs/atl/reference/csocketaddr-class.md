---
title: Класс CSocketAddr
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: 66d33d62212389a2b0f318250c1c16a99167c6eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330683"
---
# <a name="csocketaddr-class"></a>Класс CSocketAddr

Этот класс предоставляет методы преобразования имен хостов для размещения адресов, поддерживая форматы IPv4 и IPV6.

## <a name="syntax"></a>Синтаксис

```
class CSocketAddr
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSocketAddr::CSocketAddr](#csocketaddr)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSocketAddr:FindAddr](#findaddr)|Вызовите этот метод, чтобы преобразовать указанное имя узла в адрес хоста.|
|[CSocketAddr:FindINET4Addr](#findinet4addr)|Вызовите этот метод для преобразования имени узла IPv4 в адрес хоста.|
|[CSocketAddr:FindINET6Addr](#findinet6addr)|Вызовите этот метод для преобразования имени узла IPv6 в адрес хоста.|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Вызовите этот метод, чтобы вернуть указатель к определенному элементу в списке. `addrinfo`|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Вызовите этот метод, чтобы `addrinfo` вернуть указатель в список.|

## <a name="remarks"></a>Примечания

Этот класс обеспечивает агностик IP-версии для поиска сетевых адресов для использования с функциями API разъемов Windows и обертками розетки в библиотеках.

Члены этого класса, которые используются для поиска сетевых адресов, используют функцию Win32 API [getaddrinfo.](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) Версия функции ANSI или UNICODE называется в зависимости от того, компилируется ли ваш код для ANSI или UNICODE.

Этот класс поддерживает как iPv4, так и IPv6 сетевые адреса.

## <a name="requirements"></a>Требования

**Заголовок:** atlsocket.h

## <a name="csocketaddrcsocketaddr"></a><a name="csocketaddr"></a>CSocketAddr::CSocketAddr

Конструктор.

```
CSocketAddr();
```

### <a name="remarks"></a>Примечания

Создает новый `CSocketAddr` объект и инициализирует связанный список, содержащий информацию об ответе о хосте.

## <a name="csocketaddrfindaddr"></a><a name="findaddr"></a>CSocketAddr:FindAddr

Вызовите этот метод, чтобы преобразовать указанное имя узла в адрес хоста.

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>Параметры

*szHost*<br/>
Имя хоста или пунктирный IP-адрес.

*szPortOrServiceName*<br/>
Номер порта или название службы на хосте.

*nPortNo*<br/>
номер порта.

*Флаги*<br/>
0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.

*addr_family*<br/>
Адрес семьи (например, PF_INET).

*sock_type*<br/>
Тип розетки (например, SOCK_STREAM).

*ai_proto*<br/>
Протокол (например, IPPROTO_IP или IPPROTO_IPV6).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль, если адрес вычисляется успешно. Возвращает ненулевой код ошибки Windows Socket при сбое. В случае успеха расчетный адрес хранится в связанном `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo`списке, на который можно ссылаться с использованием и .

### <a name="remarks"></a>Примечания

Параметр имени хоста может быть в формате IPv4 или IPv6. Этот метод вызывает функцию Win32 API [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) для выполнения преобразования.

## <a name="csocketaddrfindinet4addr"></a><a name="findinet4addr"></a>CSocketAddr:FindINET4Addr

Вызовите этот метод для преобразования имени узла IPv4 в адрес хоста.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Параметры

*szHost*<br/>
Имя хоста или пунктирный IP-адрес.

*nPortNo*<br/>
номер порта.

*Флаги*<br/>
0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.

*sock_type*<br/>
Тип розетки (например, SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль, если адрес вычисляется успешно. Возвращает ненулевой код ошибки Windows Socket при сбое. В случае успеха расчетный адрес хранится в связанном `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo`списке, на который можно ссылаться с использованием и .

### <a name="remarks"></a>Примечания

Этот метод вызывает функцию Win32 API [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) для выполнения преобразования.

## <a name="csocketaddrfindinet6addr"></a><a name="findinet6addr"></a>CSocketAddr:FindINET6Addr

Вызовите этот метод для преобразования имени узла IPv6 в адрес хоста.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Параметры

*szHost*<br/>
Имя хоста или пунктирный IP-адрес.

*nPortNo*<br/>
номер порта.

*Флаги*<br/>
0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.

*sock_type*<br/>
Тип розетки (например, SOCK_STREAM).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль, если адрес вычисляется успешно. Возвращает ненулевой код ошибки Windows Socket при сбое. В случае успеха расчетный адрес хранится в связанном `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo`списке, на который можно ссылаться с использованием и .

### <a name="remarks"></a>Примечания

Этот метод вызывает функцию Win32 API [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) для выполнения преобразования.

## <a name="csocketaddrgetaddrinfo"></a><a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo

Вызовите этот метод, чтобы вернуть указатель к определенному элементу в списке. `addrinfo`

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Ссылка на конкретный элемент в списке [addrinfo.](/windows/win32/api/ws2def/ns-ws2def-addrinfow)

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `addrinfo` структуру, на которую ссылается *nIndex,* в связанном списке, содержащем информацию об ответе о хостеле.

## <a name="csocketaddrgetaddrinfolist"></a><a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList

Вызовите этот метод, чтобы `addrinfo` вернуть указатель в список.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на связанный список `addrinfo` одной или нескольких структур, содержащих информацию об ответных мерах о хостеле. Для получения дополнительной информации [см.](/windows/win32/api/ws2def/ns-ws2def-addrinfow)

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
