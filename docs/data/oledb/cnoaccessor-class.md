---
title: Класс CNoAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: c82d756690c6c2a719cb03f458c471aa44e3d5b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211735"
---
# <a name="cnoaccessor-class"></a>Класс CNoAccessor

Может использоваться в качестве аргумента шаблона (`TAccessor`) для классов шаблонов, таких как `CCommand` и `CTable`, для которых требуется аргумент класса метода доступа.

## <a name="syntax"></a>Синтаксис

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Примечания

Используйте `CNoAccessor` в качестве аргумента шаблона, если не требуется, чтобы класс поддерживал параметры или выходные столбцы.

`CNoAccessor` реализует следующие методы-заглушки, каждый из которых соответствует другим методам класса метода доступа:

- `BindColumns` — привязывает столбцы к методы доступа.

- `BindParameters` — привязывает созданные параметры к столбцам.

- `Bind` — создает привязки.

- `Close` — закрывает метод доступа.

- `ReleaseAccessors` — освобождает методы доступа, созданные классом.

- `FreeRecordMemory` — освобождает все столбцы в текущей записи, которые необходимо освободить.

- `GetColumnInfo` — получает сведения о столбцах из открытого набора строк.

- `GetNumAccessors` — извлекает количество методов доступа, созданных классом.

- `IsAutoAccessor` — возвращает значение true, если данные автоматически извлекаются для метода доступа во время операции перемещения.

- `GetHAccessor` — получает маркер метода доступа для указанного метода доступа.

- `GetBuffer` — получает указатель на буфер закладки.

- `NoBindOnNullRowset` — предотвращает привязку данных к пустым наборам строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
