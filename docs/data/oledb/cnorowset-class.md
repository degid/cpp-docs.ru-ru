---
title: Класс CNoRowset
ms.date: 11/04/2016
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
ms.openlocfilehash: 19a1e01fd29c74cf1c44081c24bf384704cf2acd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211477"
---
# <a name="cnorowset-class"></a>Класс CNoRowset

Может использоваться в качестве аргумента шаблона (`TRowset`) для [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Класс метода доступа. Значение по умолчанию — `CAccessorBase`.

## <a name="remarks"></a>Примечания

Используйте `CNoRowset` в качестве аргумента шаблона, если команда не возвращает набор строк.

`CNoRowset` реализует следующие методы-заглушки, каждый из которых соответствует другим методам класса метода доступа:

- `BindFinished` — указывает, когда привязка завершена (Возвращает значение `S_OK`).

- `Close`-выпуски строк и текущего интерфейса IRowset.

- `GetIID` — получает идентификатор интерфейса точки подключения.

- `GetInterface` — Извлекает интерфейс.

- `GetInterfacePtr` — получает указатель инкапсулированного интерфейса.

- `SetAccessor` — задает указатель на метод доступа.

- `SetupOptionalRowsetInterfaces` — настраивает дополнительные интерфейсы для набора строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
