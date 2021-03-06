---
title: Структура CDaoIndexInfo
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 55f64fcebc308bd0e63643cfb5447608c4e2e37c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399776"
---
# <a name="cdaoindexinfo-structure"></a>Структура CDaoIndexInfo

`CDaoIndexInfo` Структура содержит сведения об объекте index, определенные для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет объект поля. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_pFieldInfos*<br/>
Указатель на массив [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) объектов, указывающее, какие поля tabledef или набора записей являются ключевые поля в индексе. Каждый объект определяет одно поле в индексе. Сортировка индекса по умолчанию — по возрастанию. Объект индекса, может иметь одно или несколько полей, представляющий ключей индекса для каждой записи. Они могут быть отсортированы по возрастанию, по убыванию, или их комбинацию.

*m_nFields*<br/>
Количество полей, хранящихся в `m_pFieldInfos`.

*m_bPrimary*<br/>
Если основной свойство имеет значение TRUE, объект индекса представляет первичный индекс. Первичный индекс состоит из одного или нескольких полей, которые однозначно определяют все записи из таблицы в предопределенном порядке. Так как поле индекса должно быть уникальным, свойство уникальный индекс объекта также имеет значение TRUE в DAO. Если первичный индекс состоит из нескольких полей, каждое поле может содержать повторяющиеся значения, но каждая комбинация значений всех индексированных полей должно быть уникальным. Первичный индекс состоит из ключа для таблицы и обычно содержит те же поля, что первичный ключ.

При установке первичный ключ для таблицы первичный ключ автоматически определяется как первичный индекс для таблицы. Дополнительные сведения см. в разделах, «Основного свойства» и «Уникальное свойство» в справке DAO.

> [!NOTE]
> Может существовать, максимум один первичный индекс для таблицы.

*m_bUnique*<br/>
Указывает, представляет ли объект индекса уникального индекса для таблицы. Если это свойство имеет значение TRUE, объект индекса представляет индекс, который является уникальным. Уникальный индекс состоит из одного или нескольких полей, которые логически Упорядочить все записи из таблицы в порядке уникальный, предопределенные. Если индекс состоит из одного поля, значения в этом поле должны быть уникальными для всей таблицы. Если индекс состоит из нескольких полей, каждое поле может содержать повторяющиеся значения, но каждая комбинация значений всех индексированных полей должно быть уникальным.

Если первичный и уникальный индекс объекта задано значение TRUE, индекс уникальности и первичности: Однозначно определяет все записи из таблицы в порядке стандартных, логических. Если свойство основной значение FALSE, индекс является вторичным индексом. Вторичные индексы (ключевых и неключевых) логически упорядочить записи в предопределенном порядке без служащее идентификатором для записей в таблице.

Дополнительные сведения см. в разделах, «Основного свойства» и «Уникальное свойство» в справке DAO.

*m_bClustered*<br/>
Указывает, представляет ли объект индекс кластеризованного индекса для таблицы. Если это свойство имеет значение TRUE, объект индекса представляет кластеризованный индекс; в противном случае это не так. Кластеризованный индекс состоит из одного или несколько неключевых полей, взятые вместе, упорядочить все записи из таблицы в предопределенном порядке. С кластеризованным индексом данные в таблице буквально хранятся в порядке, указанном в кластеризованный индекс. Кластеризованный индекс предоставляет эффективный способ доступа к записям в таблице. Дополнительные сведения см. в разделе «Clustered свойство» в справке DAO.

> [!NOTE]
> Свойство Clustered учитывается для баз данных, использующих базы данных Microsoft Jet, так как базы данных Jet не поддерживает кластеризованные индексы.

*m_bIgnoreNulls*<br/>
Указывает, имеются ли записи индекса для записи, имеющие значения Null в полях индекса. Если это свойство имеет значение TRUE, поля со значениями Null нет элемента. Чтобы для записей быстрее с помощью поля поиска, можно определить индекс для поля. Если при предоставлении записи со значением Null в индексированных поле многими из записей, чтобы иметь значение Null, свойство IgnoreNulls для объекта индекса можно задать значение TRUE, чтобы уменьшить объем дискового пространства, которое использует индекс. Параметр IgnoreNulls свойства и значения этого свойства требуется вместе определяют, имеет ли запись со значением Null индекс запись индекса, как показано в следующей таблице.

|IgnoreNulls|Обязательно|Значение NULL, в поле индекса|
|-----------------|--------------|-------------------------|
|True|False|Значение NULL разрешено; не добавлена запись индекса.|
|False|False|Значение NULL разрешено; Индекс добавленного элемента.|
|True или False|True|Значение NULL не допускается; не добавлена запись индекса.|

Дополнительные сведения см. в разделе «IgnoreNulls свойство» в справке DAO.

*m_bRequired*<br/>
Указывает, требует ли объект индекса DAO ненулевое значение. Если это свойство имеет значение TRUE, объект индекса не допускает значение Null. Дополнительные сведения см. в разделе «Требуется свойство» в справке DAO.

> [!TIP]
> При установке этого свойства для объекта DAO индекса или объект поля (содержится tabledef, набор записей или объекта querydef) задана для объекта поля. До этого индекса объекта проверяется допустимость значения этого свойства для объекта поля.

*m_bForeign*<br/>
Указывает, представляет ли объект индекса в таблице внешнего ключа. Если это свойство имеет значение TRUE, индекс представляет внешний ключ в таблице. Внешний ключ состоит из одного или нескольких полей во внешней таблице, которые однозначно определяют строку в таблице первичного. Ядро базы данных Jet (Майкрософт) создает объект индекса для таблицы внешнего и задает свойство внешнего при создании связь, которая позволяет задать целостность ссылок. Дополнительные сведения см. в разделе «Свойство внешнего» в справке DAO.

*m_lDistinctCount*<br/>
Указывает количество уникальных значений для объекта индекса, включенные в связанной таблице. Проверьте свойство DistinctCount для определения количества уникальных значений, или ключи в индексе. Любую клавишу, учитывается только один раз, несмотря на то, что может существовать несколько экземпляров данного значения Если индекс допускает повторяющиеся значения. Эта информация полезна в приложениях, которые предпринимают попытку для оптимизации доступа к данным, оценивая сведений об индексах. Количество уникальных значений, также называется количеством объект индекса. Свойство DistinctCount не всегда будет отражать фактическое число ключей в определенное время. Например, изменение из-за отката транзакции не отразится немедленно в свойстве DistinctCount. Дополнительные сведения см. в разделе «DistinctCount свойство» в справке DAO.

## <a name="remarks"></a>Примечания

Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по `GetIndexInfo` функция-член в классах [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Класс MFC не представлены объектов индекса. Вместо этого DAO объекты базовых объектов MFC класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержать коллекцию объектов индекса, который называется коллекцию индексов. Эти классы предоставлять функции-члены для доступа к отдельным элементам данных индекса, или использовать их все одновременно с `CDaoIndexInfo` путем вызова метода `GetIndexInfo` функция-член края содержащего его объекта.

`CDaoIndexInfo` конструктор и деструктор, чтобы правильно выделять и освобождать данные полей индекса в `m_pFieldInfos`.

Сведений, получаемых методом `GetIndexInfo` функция-член объекта tabledef хранится в `CDaoIndexInfo` структуры. Вызовите `GetIndexInfo` функция-член края вмещающего объекта tabledef, в которых коллекции индексов хранится объект индекса. `CDaoIndexInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoIndexInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
