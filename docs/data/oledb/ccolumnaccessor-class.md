---
title: Класс CColumnAccessor
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2a3b1dac51a8300a915a7177c36f15512b583fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212114"
---
# <a name="ccolumnaccessor-class"></a>Класс CColumnAccessor

Создает код для внедренного потребителя.

## <a name="syntax"></a>Синтаксис

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Примечания

В введенном коде каждый столбец привязан как отдельный метод доступа. Следует иметь в виду, что этот класс используется во внедренном коде (например, при отладке), но обычно его не нужно использовать напрямую или непосредственно с его методами.

`CColumnAccessor` реализует следующие методы-заглушки, каждый из которых соответствует функциональным возможностям другим методам класса методов доступа:

- `CColumnAccessor` конструкторе; создает и инициализирует объект `CColumnAccessor`.

- `CreateAccessor` выделяет память для структур привязки столбцов и инициализирует элементы данных столбца.

- `BindColumns` привязывает столбцы к методы доступа.

- `SetParameterBuffer` выделяет буферы для параметров.

- `AddParameter` добавляет запись параметра в структуры записи параметра.

- `HasOutputColumns` определяет, содержит ли метод доступа выходные столбцы

- `HasParameters` определяет, имеет ли метод доступа параметры.

- `BindParameters` привязывает созданные параметры к столбцам.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
