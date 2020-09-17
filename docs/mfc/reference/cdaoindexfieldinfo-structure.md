---
title: Структура CDaoIndexFieldInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: 10c786ef4fed9ecb3bbbb93526cd68a11e18d58c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303626"
---
# <a name="cdaoindexfieldinfo-structure"></a>Структура CDaoIndexFieldInfo

Структура `CDaoIndexFieldInfo` содержит сведения об объекте поля индекса, определенном для объектов доступа к данным (DAO).

DAO поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей.

## <a name="syntax"></a>Синтаксис

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Уникально именует объект поля индекса. Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_bDescending*<br/>
Указывает порядок индексов, определенный объектом index. Значение TRUE, если порядок сортировки по убыванию.

## <a name="remarks"></a>Примечания

Объект индекса может иметь несколько полей, указывающих, в каких полях будет индексироваться объект tabledef (или набор записей, основанный на таблице). Ссылки на основные выше сведения указывают, как данные возвращаются в `m_pFieldInfos` члене объекта [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) , полученного путем вызова функции-члена `GetIndexInfo` класса [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md#getindexinfo) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Объекты индекса и объекты полей индекса не представлены классом MFC. Вместо этого объекты DAO базовых объектов MFC класса [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержат коллекцию объектов index, называемую коллекцией индексов. Каждый объект индекса, в свою очередь, содержит коллекцию объектов Field. Эти классы предоставляют функции-члены для доступа к отдельным элементам сведений об индексах или к ним можно обращаться сразу с помощью объекта `CDaoIndexInfo`, вызывая функцию-член `GetIndexInfo` содержащего объекта. Объект `CDaoIndexInfo`, затем содержит элемент данных `m_pFieldInfos`, указывающий на массив объектов `CDaoIndexFieldInfo`.

Вызовите функцию-член `GetIndexInfo` содержащего объекта tabledef или Recordset, в коллекции индексов которого хранится объект индекса, который вас интересует. Затем перейдите к элементу `m_pFieldInfos` объекта [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) . Длина массива `m_pFieldInfos` хранится в `m_nFields`. `CDaoIndexFieldInfo` также определяет функцию-член `Dump` в отладочных сборках. Для дампа содержимого объекта `CDaoIndexFieldInfo` можно использовать `Dump`.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао.h

## <a name="see-also"></a>См. также:

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Кдаотабледеф:: Жетиндексинфо](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: Жетиндексинфо](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
