---
title: Структура CDaoDatabaseInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoDatabaseInfo
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
ms.openlocfilehash: 60972aa3ecaef4d38c9a0d0ecc70477796aa37aa
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304254"
---
# <a name="cdaodatabaseinfo-structure"></a>Структура CDaoDatabaseInfo

Структура `CDaoDatabaseInfo` содержит сведения об объекте базы данных, определенном для объектов доступа к данным (DAO). Версия DAO 3,6 является окончательной и считается устаревшей.

## <a name="syntax"></a>Синтаксис

```
struct CDaoDatabaseInfo
{
    CString m_strName;       // Primary
    BOOL m_bUpdatable;       // Primary
    BOOL m_bTransactions;    // Primary
    CString m_strVersion;    // Secondary
    long m_lCollatingOrder;  // Secondary
    short m_nQueryTimeout;   // Secondary
    CString m_strConnect;    // All
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Уникально именует объект базы данных. Чтобы напрямую получить это свойство, вызовите [CDaoDatabase:: Name](../../mfc/reference/cdaodatabase-class.md#getname). Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_bUpdatable*<br/>
Указывает, можно ли вносить изменения в базу данных. Чтобы напрямую получить это свойство, вызовите метод [CDaoDatabase:: канупдате](../../mfc/reference/cdaodatabase-class.md#canupdate). Дополнительные сведения см. в разделе "обновляемое свойство" справки DAO.

*m_bTransactions*<br/>
Указывает, поддерживает ли источник данных транзакции — запись ряда изменений, которые впоследствии можно откатить (отменить) или зафиксировать (сохранить). Если база данных основана на ядре СУБД Microsoft Jet, свойство Transactions не равно нулю и можно использовать транзакции. Другие ядра СУБД могут не поддерживать транзакции. Чтобы напрямую получить это свойство, вызовите метод [CDaoDatabase:: кантрансакт](../../mfc/reference/cdaodatabase-class.md#cantransact). Дополнительные сведения см. в разделе "свойства транзакций" справки DAO.

*m_strVersion*<br/>
Указывает версию ядра СУБД Microsoft Jet. Чтобы получить значение этого свойства напрямую, вызовите [функцию члена GetObject объекта базы](../../mfc/reference/cdaodatabase-class.md#getversion) данных. Дополнительные сведения см. в разделе "свойство Version" справки DAO.

*m_lCollatingOrder*<br/>
Задает последовательность порядка сортировки в тексте для сравнения строк или сортировки. Возможные значения:

- `dbSortGeneral` использовать общие (английский, французский, немецкий, португальский, итальянский и современный испанский) порядок сортировки.

- `dbSortArabic` использовать порядок сортировки для арабского языка.

- `dbSortCyrillic` использовать русский порядок сортировки.

- `dbSortCzech` использовать чешский порядок сортировки.

- `dbSortDutch` использовать нидерландский порядок сортировки.

- `dbSortGreek` использовать греческий порядок сортировки.

- `dbSortHebrew` использовать порядок сортировки для иврита.

- `dbSortHungarian` использовать Венгерский порядок сортировки.

- `dbSortIcelandic` использовать порядок сортировки Исландский.

- `dbSortNorwdan` использовать норвежский или датский порядок сортировки.

- `dbSortPDXIntl` использовать международный порядок сортировки Paradox.

- `dbSortPDXNor` использовать порядок сортировки Paradox норвежский или датский.

- `dbSortPDXSwe` использовать порядок сортировки Paradox шведский или финский.

- `dbSortPolish` использовать польский порядок сортировки.

- `dbSortSpanish` использовать Испанский порядок сортировки.

- `dbSortSwedFin` использовать шведский или Финский порядок сортировки.

- `dbSortTurkish` использовать порядок сортировки для турецкого языка.

- `dbSortUndefined` порядок сортировки не определен или неизвестен.

Дополнительные сведения см. в разделе «Настройка параметров реестра Windows для доступа к данным» справки DAO.

*m_nQueryTimeout*<br/>
Количество секунд, в течение которых ядро СУБД Microsoft Jet ждет возникновения ошибки времени ожидания при выполнении запроса в базе данных ODBC. Значение времени ожидания по умолчанию — 60 секунд. Когда параметр QueryTimeout имеет значение 0, время ожидания не возникает; Это может привести к тому, что программа перестает отвечать на запросы. Чтобы получить значение этого свойства напрямую, вызовите функцию члена [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) объекта базы данных. Дополнительные сведения см. в разделе "свойство QueryTimeout" справки DAO.

*m_strConnect*<br/>
Предоставляет сведения об источнике открытой базы данных. Сведения о строках соединения и сведения о получении значения этого свойства напрямую см. в описании функции члена [CDaoDatabase::](../../mfc/reference/cdaodatabase-class.md#getconnect) . Дополнительные сведения см. в подразделе «свойство Connect» справки DAO.

## <a name="remarks"></a>Примечания

База данных — это объект DAO, лежащий в основе объекта MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Ссылки на первичный, вторичный и все вышеперечисленное указывают, как эта информация возвращается функцией-членом [кдаоворкспаце:: жетдатабасеинфо](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) .

Сведения, получаемые функцией-членом [кдаоворкспаце:: жетдатабасеинфо](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) , хранятся в структуре `CDaoDatabaseInfo`. Вызовите `GetDatabaseInfo` для объекта `CDaoWorkspace`, в коллекции баз данных которого хранится объект базы данных. `CDaoDatabaseInfo` также определяет функцию-член `Dump` в отладочных сборках. Для дампа содержимого объекта `CDaoDatabaseInfo` можно использовать `Dump`.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао.h

## <a name="see-also"></a>См. также:

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
