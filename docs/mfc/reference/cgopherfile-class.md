---
title: Класс CGopherFile
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: e157a4509fe30b814a1834690a675906ac82afe7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373695"
---
# <a name="cgopherfile-class"></a>Класс CGopherFile

Обеспечивает возможность поиска и чтения файлов на сервере gopher.

> [!NOTE]
> Классы `CGopherConnection` `CGopherFile`, `CGopherFileFind` `CGopherLocator` , и их члены были уволены, потому что они не работают на платформе Windows XP, но они будут продолжать работать на более ранних платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGopherFile::CGopherFile](#cgopherfile)|Формирует объект `CGopherFile`.|

## <a name="remarks"></a>Примечания

Служба сусликов не позволяет пользователям записывать данные в файл суслика, потому что эта служба функционирует главным образом как интерфейс, управляемый меню для поиска информации. Функциями `CGopherFile` `Write` `WriteString`участника, `Flush` и не `CGopherFile`реализованы для . Вызов этих функций `CGopherFile` на объект, возвращает [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Чтобы узнать `CGopherFile` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a>CGopherFile::CGopherFile

Эта функция члена называется `CGopherFile` для построения объекта.

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Ручка к файлу HINTERNET.

*рефЛокатор*<br/>
Ссылка на объект [CGopherLocator.](../../mfc/reference/cgopherlocator-class.md)

*pConnection*<br/>
Указатель на объект [CGopherConnection.](../../mfc/reference/cgopherconnection-class.md)

*hСессия*<br/>
Ручка для текущей сессии Интернета.

*pstrLocator*<br/>
Указатель на строку, используемую для поиска сервера сусликов. Подробнее о [локаторах gopher Sessions](cgopherlocator-class.md) читайте в сообщении.

*dwLocLen*<br/>
DWORD, содержащий количество байтов в *pstrLocator*.

*Dwcontext*<br/>
Указатель на идентификатор контекста открываемого файла.

### <a name="remarks"></a>Примечания

Вам нужен объект для `CGopherFile` чтения из файла во время сессии Суслик Интернет.

Вы никогда `CGopherFile` не создаете объект напрямую. Вместо этого позвоните [cGopherConnection::OpenFile,](../../mfc/reference/cgopherconnection-class.md#openfile) чтобы открыть файл на сервере сусликов.

## <a name="see-also"></a>См. также раздел

[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)
