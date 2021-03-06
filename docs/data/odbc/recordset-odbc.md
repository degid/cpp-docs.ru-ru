---
title: Набор записей (ODBC)
ms.date: 05/09/2019
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
ms.openlocfilehash: b7a55621f4875b24cc33a0fd49a5b8b4c88b34cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368634"
---
# <a name="recordset-odbc"></a>Набор записей (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Объект [CRecordset](../../mfc/reference/crecordset-class.md) представляет набор записей, выбранных из источника данных. Возможны следующие источники записей:

- Таблица.

- запрос;

- хранимая процедура, обращающаяся к одной или нескольким таблицам.

Пример набора записей на основе таблицы — "все клиенты" для таблицы "Клиенты". Пример запроса — "все счета от Артема Кузнецова". Пример набора записей на основе хранимой процедуры (иногда называемой предварительно определенным запросом) — набор "все счета с просроченной задолженностью", вызывающий хранимую процедуру во внутренней базе данных. В наборе записей могут объединяться две или несколько таблиц из одного источника данных, но не из разных.

> [!NOTE]
> Некоторые драйверы ODBC поддерживают представления базы данных. В этом смысле представление — это запрос, изначально созданный с помощью инструкции SQL `CREATE VIEW`.

## <a name="recordset-capabilities"></a><a name="_core_recordset_capabilities"></a> Возможности набора записей

Все объекты наборов записей имеют перечисленные ниже возможности.

- Если источник данных доступен не только для чтения, набор записей можно определить как [допускающий обновление](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [допускающий добавление](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md) или доступный только для чтения. Если набор записей допускает обновление, можно выбрать метод пессимистической или оптимистической [блокировки](../../data/odbc/recordset-locking-records-odbc.md) при условии, что он поддерживается драйвером. Если источник данных доступен только для чтения, набор записей также будет доступен только для чтения.

- Путем вызова функций-членов можно [прокручивать](../../data/odbc/recordset-scrolling-odbc.md) выбранные записи.

- Можно [фильтровать](../../data/odbc/recordset-filtering-records-odbc.md) выбираемые записи для их ограничения.

- Записи можно [сортировать](../../data/odbc/recordset-sorting-records-odbc.md) по одному или нескольким столбцам в порядке возрастания или убывания.

- Набор записей можно [параметризовать](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md), чтобы определять выборку во время выполнения.

## <a name="snapshots-and-dynasets"></a><a name="_core_snapshots_and_dynasets"></a> Моментальные снимки и динамические подмножества данных

Существует два основных типа наборов записей: [моментальные снимки](../../data/odbc/snapshot.md) и [динамические подмножества данных](../../data/odbc/dynaset.md). Оба поддерживаются классом `CRecordset`. Каждый из них обладает общими свойствами всех наборов записей, но по-своему расширяет общие возможности. Моментальные снимки обеспечивают статическое представление данных и полезны для отчетов и в других ситуациях, когда нужно получить представление данных на определенный момент времени. Динамические подмножества данных полезны, когда нужно, чтобы изменения, вносимые другими пользователями, отражались в наборе записей без необходимости выполнять повторный запрос или обновление набора. Моментальные снимки и динамические подмножества данных могут допускать обновление или быть доступными только для чтения. Чтобы отразить записи, добавленные или удаленные другими пользователями, вызовите [CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery).

`CRecordset` поддерживает еще два типа наборов записей: динамические и с последовательным доступом. Динамические наборы записей похожи на динамические подмножества данных, однако добавление и удаление записей отражается в них без вызова `CRecordset::Requery`. По этой причине время обработки динамических наборов записей в СУБД, как правило, больше, и многие драйверы ODBC не поддерживают их. Напротив, наборы записей с последовательным доступом обеспечивают наиболее эффективный доступ к данным в случае, если набор записей не требует обновления или обратной прокрутки. Например, такой набор записей можно использовать для переноса данных из одного источника данных в другой с последовательным их перебором. Для использования набора записей с последовательным доступом нужно выполнить два действия.

- Передать параметр `CRecordset::forwardOnly` в качестве параметра *nOpenType* функции-члена [Open](../../mfc/reference/crecordset-class.md#open).

- Указать `CRecordset::readOnly` в параметре *dwOptions* функции-члена `Open`.

    > [!NOTE]
    >  Сведения о требованиях к драйверу ODBC для поддержки динамических подмножеств данных см. в статье [Основы ODBC](../../data/odbc/odbc-basics.md). Список драйверов ODBC, включенных в эту версию Visual C++, и сведения о получении дополнительных драйверов см. в статье [Список драйверов ODBC](../../data/odbc/odbc-driver-list.md).

## <a name="your-recordsets"></a><a name="_core_your_recordsets"></a> Объекты наборов записей

Для каждой таблицы, представления или хранимой процедуры, к которой требуется доступ, обычно определяется класс, производный от `CRecordset`. (Исключением является соединение базы данных, в котором один набор записей представляет столбцы из двух или более таблиц.) При извлечении класса recordset вы включите механизм обмена полями записей (RFX) или механизм обмена полями массового обмена (Bulk RFX), который похож на механизм обмена диалоговыми данными (DDX). RFX и Bulk RFX упрощают передачу данных из источника данных в набор записей. Кроме того, RFX передает данные из набора записей в источник данных. Для получения дополнительной информации см. [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [Recordset: Fetching Records in Bulk (ODBC).](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Объект набора записей предоставляет доступ ко всем выбранным записям. Прокрутка выбранных записей осуществляется с помощью функций-членов `CRecordset`, таких как `MoveNext` и `MovePrev`. В то же время объект набора записей представляет только одну из выбранных записей, которая является текущей. Просматривать поля текущей записи можно путем объявления переменных-членов в классе набора записей, которые соответствуют столбцам таблицы или записей, полученных в результате запроса к базе данных. Для получения информации о членах данных, установленных записьми, [см.](../../data/odbc/recordset-architecture-odbc.md)

В приведенных ниже статьях представлены подробные сведения об использовании объектов наборов записей. Статьи разбиты на функциональные категории и приведены в логическом порядке.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Статьи о принципах открытия, чтения и закрытия наборов записей

- [Рекордсет: Архитектура (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Набор записей. Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Набор записей. Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Набор записей. Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [Набор записей. Закладки и абсолютное позиционирование (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Набор записей. Сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Статьи о принципах изменения наборов записей

- [Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Набор записей: блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Набор записей. Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Статьи о более сложных способах использования

- [Набор записей. Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Набор записей. Объявление класса для предопределенного запроса (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Набор записей. Работа с большими элементами данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Статьи о принципах работы наборов записей

- [Набор записей. Порядок выборки записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Набор записей. Порядок обновления записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>См. также раздел

[Открытая связь с базами данных (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)
