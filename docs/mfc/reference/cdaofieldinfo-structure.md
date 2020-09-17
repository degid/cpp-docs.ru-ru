---
title: Структура CDaoFieldInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 9466386fefc6e5ab8fcf89bf497c1d5219e3e807
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368400"
---
# <a name="cdaofieldinfo-structure"></a>Структура CDaoFieldInfo

Структура `CDaoFieldInfo` содержит информацию об объекте поля, определяемом для объектов доступа к данным (DAO).

DAO поддерживается через Office 2013. DAO 3.6 является окончательной версией, и он считается устаревшим.

## <a name="syntax"></a>Синтаксис

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Уникально называет объект поля. Подробнее об этом читайте в теме «Название собственности» в справке DAO.

*m_nType*<br/>
Значение, указывавщее тип поля данных. Подробнее о том, как "Тип собственности", читайте в справке DAO. Стоимость этого свойства может быть одной из следующих:

- `dbBoolean`Да/Нет, так же, как TRUE/FALSE

- `dbByte`Байт

- `dbInteger`Короткие

- `dbLong`Длинные

- `dbCurrency`Валюта; см. MFC класса [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle`Одного

- `dbDouble`Двухместный

- `dbDate`Дата/время; см. MFC класс [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText`Текст; см. [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary`Длинные двоичные (OLE объект); Вы можете использовать MFC класса [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса, `CLongBinary` как `CByteArray` богаче и проще в использовании.

- `dbMemo`Памятка; см. класс MFC`CString`

- `dbGUID`Глобально уникальный идентификатор/универсально уникальный идентификатор, используемый с удаленными вызовами процедур. Для получения дополнительной информации, см.

> [!NOTE]
> Не используйте типы строк данных для двоичных данных. Это приводит к тому, что ваши данные проходят через слой перевода Unicode/ANSI, что приводит к увеличению накладных расходов и, возможно, неожиданному переводу.

*m_lSize*<br/>
Значение, указывавщее максимальный размер в байтах объекта поля DAO, содержащего текст, или фиксированный размер объекта поля, содержащего текстовые или числовые значения. Подробнее о том, как "Размер собственности", читайте в справке DAO. Размеры могут быть одним из следующих значений:

|Тип|Размер (байт)|Описание|
|----------|--------------------|-----------------|
|`dbBoolean`|1 байт|Да/Нет (так же, как True/False)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Целое число|
|`dbLong`|4|Long|
|`dbCurrency`|8|Валюта[(COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Один|
|`dbDouble`|8|Double|
|`dbDate`|8|Дата/время[(COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Текст ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Длинные двоичные (OLE объект; [CByteArray](../../mfc/reference/cbytearray-class.md); использовать вместо `CLongBinary`)|
|`dbMemo`|0|Памятка ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Глобально уникальный идентификатор/универсально уникальный идентификатор, используемый с удаленными вызовами процедур.|

*m_lAttributes*<br/>
Определяет характеристики объекта поля, содержащегося в объекте таблицы, записи, querydef или объекте индекса. Возвратное значение может быть суммой этих констант, созданных с помощью оператора C'bitwise-OR** (&#124;): **

- `dbFixedField`Размер поля фиксируется (по умолчанию для численных полей).

- `dbVariableField`Размер поля является переменным (только текстовые поля).

- `dbAutoIncrField`Значение поля для новых записей автоматически приравнивается к уникальному длинному целыку, который нельзя изменить. Поддерживается только для таблиц баз данных Microsoft Jet.

- `dbUpdatableField`Значение поля может быть изменено.

- `dbDescending`Поле сортируется по нисходящей (я - A или 100 - 0) порядку (применяется только к объекту поля в коллекции Полей объекта индекса; в MFC объекты индекса сами содержатся в объектах таблицы). Если вы опустите эту константу, поле сортируется в восходящем порядке (A - No или 0 - 100) (по умолчанию).

При проверке настройки этого свойства можно использовать оператора C'wise-AND ()**&** для проверки на наличие определенного атрибута. При настройке нескольких атрибутов их можно комбинировать, комбинируя соответствующие константы с оператором bitwise-OR** (&#124;). ** Подробнее о том, как "Недвижимость атрибутов", читайте в справке DAO.

*m_nOrdinalPosition*<br/>
Значение, окоторомывающее числовой порядок, в котором требуется отображение поля, представленного объектом поля DAO, по сравнению с другими полями. Вы можете установить это свойство с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Подробнее об этом читайте в теме "OrdinalPosition Property" в справке DAO.

*m_bRequired*<br/>
Указывает, требуется ли объект поля DAO значение, не являющееся нулем. Если это свойство является правдой, поле не позволяет значение Null. При наборе требуемого значения FALSE поле может содержать значения Null, а также значения, отвечающие условиям, указанным в настройках свойства Allow'ero Length и ValidationRule. Подробнее о ней читайте в теме "Требуемая недвижимость" в справке DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Указывает, является ли пустая строка («) допустимым значением объекта поля DAO с типом данных текста или памятки. Если это свойство является правдой, пустая строка является допустимым значением. Можно настроить это свойство на FALSE, чтобы убедиться, что вы не можете использовать пустую строку для установки значения поля. Подробнее об этом читайте в теме «Недвижимость «Разрешить»»В помощи DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Определяет последовательность порядка сортировки в тексте для сравнения строк или сортировки. Подробнее о настройках данных для доступа к данным читайте в справке DAO. Список возможных возвращенных значений `m_lCollatingOrder` можно узнать см. [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Значение, которое в зависимости от этого определяет название объекта поля DAO в иностранной таблице, которое соответствует полю в основной таблице. Подробнее о том, как "Недвижимость иностранных имен", читайте в справке DAO.

*m_strSourceField*<br/>
Указывается имя поля, которое является исходным источником данных для объекта поля DAO, содержащегося в объекте таблицы, записи или объекта запроса. Это свойство указывает исходное имя поля, связанное с объектом поля. Например, это свойство можно использовать для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Подробнее о том, как "ИсточникФилд, Источник свойства" читайте в справке DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Указывается имя таблицы, которая является исходным источником данных для объекта поля DAO, содержащегося в объекте таблицы, записи или объекта запроса. Это свойство указывает исходное имя таблицы, связанное с объектом поля. Например, это свойство можно использовать для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Подробнее о том, как "ИсточникФилд, Источник свойства" читайте в справке DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Значение, которое проверяет данные в поле при изменении или добавлении в таблицу. Подробнее о том, как валидация Rule Property, читайте в справке DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

Для получения соответствующей информации `m_strValidationRule` о таблицах см. [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)

*m_strValidationText*<br/>
Значение, определяющее текст сообщения, отображается приложением, если значение объекта поля DAO не соответствует правилу проверки, указанному параметром свойства Валидации. Подробнее о том, как "ВалидацияТекст собственности", читайте в справке DAO. Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
Значение по умолчанию объекта поля DAO. При создании новой записи параметр свойства DefaultValue автоматически вводится в качестве значения для поля. Подробнее о ней читайте в справке DAO". Вы можете установить это свойство для таблицы с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Примечания

Ссылки на Первоначальное, Среднее, и все выше `GetFieldInfo` перечисление, как информация возвращается функцией участника в классах [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDao-КуириDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Полевые объекты не представлены классом MFC. Вместо этого, объекты DAO, лежащие в основе объектов MFC следующих классов, содержат коллекции полевых объектов: [CDaoTableDef,](../../mfc/reference/cdaotabledef-class.md) [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)и [CDao-EryDef](../../mfc/reference/cdaoquerydef-class.md). Эти классы предоставляют функции члена для доступа к некоторым отдельным элементам `CDaoFieldInfo` полевой информации, или вы можете получить к ним доступ к всем сразу с объектом, позвонив функции `GetFieldInfo` элемента containing object.

Помимо использования для изучения свойств объектов, можно также использовать `CDaoFieldInfo` для построения вхнужного параметра для создания новых полей в таблице. Для этой задачи доступны более простые варианты, но если требуется более тонкий `CDaoFieldInfo` контроль, можно использовать версию [CDaoTableDef::CreateField,](../../mfc/reference/cdaotabledef-class.md#createfield) которая занимает параметр.

Информация, полученная функцией `GetFieldInfo` участника (класса, содержащего `CDaoFieldInfo` поле), хранится в структуре. Вызов `GetFieldInfo` функции члена содержащего объекта, в котором хранится объект поля Полей. `CDaoFieldInfo`также определяет `Dump` функцию члена в сборках отладок. Содержимое `CDaoFieldInfo` `Dump` объекта можно использовать.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также раздел

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDao КуириДеф::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
