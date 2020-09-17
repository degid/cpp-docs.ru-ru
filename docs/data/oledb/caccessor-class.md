---
title: Класс CAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 2b30cef2baf8c13c5001e44901b984aa1293494d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212307"
---
# <a name="caccessor-class"></a>Класс CAccessor

Представляет один из типов методов доступа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс записей пользователя.

## <a name="remarks"></a>Примечания

Он используется, когда запись статически привязана к источнику данных. Запись содержит буфер. Этот класс поддерживает несколько методов доступа в наборе строк.

Используйте этот тип метода доступа, если известна структура и тип базы данных.

Если метод доступа содержит поля, указывающие на память (например, `BSTR` или интерфейс), которую необходимо освободить, вызовите функцию-член [CAccessorRowset:: фрирекордмемори](../../data/oledb/caccessorrowset-freerecordmemory.md) , прежде чем будет считано следующая запись.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
