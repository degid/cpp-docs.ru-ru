---
title: Класс CRestrictions
ms.date: 11/04/2016
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
ms.openlocfilehash: a380f1ba00dcc444099f186071b7d55c9db71291
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844968"
---
# <a name="crestrictions-class"></a>Класс CRestrictions

Универсальный класс, позволяющий задавать ограничения для наборов строк схемы.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, short nRestrictions, const GUID* pguid>
class CRestrictions :
   public CSchemaRowset <T, nRestrictions>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, используемый для метода доступа.

*нрестриктионс*<br/>
Число столбцов ограничений для набора строк схемы.

*пгуид*<br/>
Указатель на идентификатор GUID для схемы.

## <a name="requirements"></a>Требования

**Заголовок:** атлдбсч.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Открыть](#open)|Возвращает результирующий набор в соответствии с предоставленными пользователем ограничениями.|

## <a name="crestrictionsopen"></a><a name="open"></a> CRestrictions:: Open

Возвращает результирующий набор в соответствии с предоставленными пользователем ограничениями.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CSession& session,
   LPCTSTR lpszParam 1 = NULL,
   LPCTSTR lpszParam 2 = NULL,
   LPCTSTR lpszParam 3 = NULL,
   LPCTSTR lpszParam 4 = NULL,
   LPCTSTR lpszParam 5 = NULL,
   LPCTSTR lpszParam 6 = NULL,
   LPCTSTR lpszParam 7 = NULL,
   bool bBind = true);
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
окне Указывает существующий объект сеанса, используемый для подключения к источнику данных.

*лпсзпарам*<br/>
окне Задает ограничения для набора строк схемы.

*ббинд*<br/>
окне Указывает, следует ли автоматически привязывать карту столбцов. Значение по умолчанию равно **`true`** , что приводит к автоматическому связыванию таблицы столбцов. Установка параметра *ббинд* для **`false`** предотвращения автоматической привязки схемы столбца, чтобы можно было выполнить привязку вручную. (Ручная привязка особенно интересна для пользователей OLAP.)

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

В наборе строк схемы можно указать не более семи ограничений.

Сведения об определенных ограничениях для каждого набора строк схемы см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) .

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Классы наборов строк схемы и классы typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)
