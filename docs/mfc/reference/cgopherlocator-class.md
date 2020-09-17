---
title: Класс CGopherLocator
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: d23ef3dad68c62e74ec64454953ca372b8c31114
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373667"
---
# <a name="cgopherlocator-class"></a>Класс CGopherLocator

Получает суслика "локатор" от суслика сервера, определяет тип локатора, и делает локатор доступным [для CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
> Классы `CGopherConnection` `CGopherFile`, `CGopherFileFind` `CGopherLocator` , и их члены были уволены, потому что они не работают на платформе Windows XP, но они будут продолжать работать на более ранних платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator:CGopherLocator](#cgopherlocator)|Формирует объект `CGopherLocator`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|Парсирует суслика локатора и определяет его атрибуты.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator:оператор LPCTSTR](#operator_lpctstr)|Непосредственно получает доступ к `CGopherLocator` символам, хранящимся в объекте в виде строки C-стиля.|

## <a name="remarks"></a>Примечания

Приложение должно получить локатор сервера суслика, прежде чем он сможет получить информацию с этого сервера. После того, как он имеет локатор, он должен относиться к локатору как к непрозрачному токену.

Каждый локатор суслика имеет атрибуты, которые определяют тип найденного файла или сервера. Список типов локаторов сусликов читайте в [GetLocatorType.](#getlocatortype)

Приложение обычно использует локатор для звонков на [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения определенной части информации.

Чтобы узнать `CGopherLocator` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator:CGopherLocator

Эта функция члена называется `CGopherLocator` для создания объекта.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Параметры

*ref*<br/>
Ссылка на `CGopherLocator` постоянный объект.

### <a name="remarks"></a>Примечания

Вы никогда `CGopherLocator` не создаете объект напрямую. Вместо этого позвоните [в CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) для `CGopherLocator` создания и возврата указателя на объект.

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::GetLocatorType

Вызов исвызывайте эту функцию участника, чтобы получить тип локатора.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Параметры

*dwRef*<br/>
Ссылка на DWORD, который получит тип локатора. Смотрите **Замечания** для таблицы типов локатора.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Примечания

Возможные типы следующие:

|Значение|Значение|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Текстовый файл ASCII.|
|GOPHER_TYPE_DIRECTORY|Каталог дополнительных элементов Gopher.|
|GOPHER_TYPE_CSO|Сервер телефонной книги CSO.|
|GOPHER_TYPE_ERROR|Указывает условие ошибки.|
|GOPHER_TYPE_MAC_BINHEX|Файл Macintosh в формате BINHEX.|
|GOPHER_TYPE_DOS_ARCHIVE|Архивный файл DOS.|
|GOPHER_TYPE_UNIX_UUENCODED|Файл UUENCODED.|
|GOPHER_TYPE_INDEX_SERVER|Сервер индекса.|
|GOPHER_TYPE_TELNET|Сервер Telnet.|
|GOPHER_TYPE_BINARY|Двоичный файл.|
|GOPHER_TYPE_REDUNDANT|Дублированный сервер. Информация, содержащаяся внутри, является дубликатом основного сервера. Основной сервер — это последняя запись каталога, которая не имеет GOPHER_TYPE_REDUNDANT типа.|
|GOPHER_TYPE_TN3270|Сервер TNN3270.|
|GOPHER_TYPE_GIF|Графический файл GIF.|
|GOPHER_TYPE_IMAGE|Файл изображения.|
|GOPHER_TYPE_BITMAP|Файл бит-карты.|
|GOPHER_TYPE_MOVIE|Файл фильма.|
|GOPHER_TYPE_SOUND|Звуковой файл.|
|GOPHER_TYPE_HTML|Документ HTML.|
|GOPHER_TYPE_PDF|Файл PDF.|
|GOPHER_TYPE_CALENDAR|Файл календаря.|
|GOPHER_TYPE_INLINE|Вонючий файл.|
|GOPHER_TYPE_UNKNOWN|Тип элемента неизвестен.|
|GOPHER_TYPE_ASK|Элемент Ask.|
|GOPHER_TYPE_GOPHER_PLUS|Элемент Gopher.|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>CGopherLocator:оператор LPCTSTR

Этот полезный оператор литья предоставляет эффективный метод доступа к `CGopherLocator` нулевой строке C, содержащейся в объекте.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символов к данным строки.

### <a name="remarks"></a>Примечания

Символы не копируются; возвращается только указатель.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)
