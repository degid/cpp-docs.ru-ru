---
title: Класс CComObjectRoot
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 98868e67fd14899a75f86837034ba540d22039e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224244"
---
# <a name="ccomobjectroot-class"></a>Класс CComObjectRoot

Это определение типа [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) преобразованный в потоковой модели сервера по умолчанию.

## <a name="syntax"></a>Синтаксис

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>Примечания

`CComObjectRoot`— Это **`typedef`** [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) преобразованный в потоковой модели сервера по умолчанию. Таким же [ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel) будет ссылаться либо на [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) , либо на [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md).

`CComObjectRootEx`обрабатывает управление счетчиком ссылок на объекты для неагрегированных и агрегированных объектов. Он содержит счетчик ссылок на объекты, если объект не выполняет статистическую обработку, и содержит указатель на внешнюю неизвестную функцию, если выполняется статистическая обработка объекта. Для агрегированных объектов `CComObjectRootEx` методы можно использовать для обработки сбоя внутреннего объекта, а также для защиты внешнего объекта от удаления при освобождении внутренних интерфейсов или при удалении внутреннего объекта.

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="see-also"></a>См. также статью

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
