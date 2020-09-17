---
title: Класс CUtlProps
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 46fa266c5a8328bbcf7cfd1257ce1ff3e38ed2bb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845670"
---
# <a name="cutlprops-class"></a>Класс CUtlProps

Реализует свойства для различных интерфейсов свойств OLE DB (например,, `IDBProperties` `IDBProperties` и `IRowsetInfo` ).

## <a name="syntax"></a>Синтаксис

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, содержащий `BEGIN_PROPSET_MAP` .

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[жетпропвалуе](#getpropvalue)|Возвращает свойство из набора свойств.|
|[исвалидвалуе](#isvalidvalue)|Используется для проверки значения перед установкой свойства.|
|[онинтерфацерекуестед](#oninterfacerequested)|Обрабатывает запросы для необязательного интерфейса, когда потребитель вызывает метод для интерфейса создания объекта.|
|[OnPropertyChanged](#onpropertychanged)|Вызывается после задания свойства для управления связанными свойствами.|
|[сетпропвалуе](#setpropvalue)|Задает свойство в наборе свойств.|

## <a name="remarks"></a>Примечания

Большая часть этого класса является подробным описанием реализации.

`CUtlProps` содержит два элемента для внутреннего задания свойств: [жетпропвалуе](../../data/oledb/cutlprops-getpropvalue.md) и [сетпропвалуе](../../data/oledb/cutlprops-setpropvalue.md).

Дополнительные сведения о макросах, используемых в схеме набора свойств, см. в разделе [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) и [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).

## <a name="cutlpropsgetpropvalue"></a><a name="getpropvalue"></a> CUtlProps:: Жетпропвалуе

Возвращает свойство из набора свойств.

### <a name="syntax"></a>Синтаксис

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Параметры

*пгуидпропсет*<br/>
окне Идентификатор GUID для набора свойств.

*dwPropId*<br/>
окне Индекс свойства.

*пввалуе*<br/>
заполняет Указатель на вариант, который содержит новое значение свойства.

### <a name="return-value"></a>Возвращаемое значение

`Failure` в случае сбоя и S_OK в случае успеха.

## <a name="cutlpropsisvalidvalue"></a><a name="isvalidvalue"></a> CUtlProps:: Исвалидвалуе

Используется для проверки значения перед установкой свойства.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Параметры

*икурсет*<br/>
Индекс в массиве наборов свойств; нуль, если имеется только один набор свойств.

*пдбпроп*<br/>
Идентификатор свойства и новое значение в структуре [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Возвращаемое значение по умолчанию — S_OK.

### <a name="remarks"></a>Примечания

Если у вас есть подпрограммы проверки, которые необходимо использовать для задания значения свойства, следует переопределить эту функцию. Например, можно проверить DBPROP_AUTH_PASSWORD для таблицы паролей, чтобы определить допустимое значение.

## <a name="cutlpropsoninterfacerequested"></a><a name="oninterfacerequested"></a> CUtlProps:: Онинтерфацерекуестед

Обрабатывает запросы для необязательного интерфейса, когда потребитель вызывает метод для одного из интерфейсов создания объекта.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>Параметры

*riid*<br/>
окне IID запрошенного интерфейса. Дополнительные сведения см. в описании параметра *riid* `ICommand::Execute` в *справочнике программиста OLE DB* (в *пакете SDK для MDAC*).

### <a name="remarks"></a>Примечания

`OnInterfaceRequested` обрабатывает запросы потребителей для необязательного интерфейса, когда потребитель вызывает метод для одного из интерфейсов создания объекта (например `IDBCreateSession` ,, `IDBCreateCommand` `IOpenRowset` или `ICommand` ). Он устанавливает соответствующее свойство OLE DB для запрошенного интерфейса. Например, если потребитель запрашивает `IID_IRowsetLocate` , `OnInterfaceRequested` задает `DBPROP_IRowsetLocate` интерфейс. Это позволит поддерживать правильное состояние во время создания набора строк.

Этот метод вызывается, когда потребитель вызывает `IOpenRowset::OpenRowset` или `ICommand::Execute` .

Если потребитель открывает объект и запрашивает дополнительный интерфейс, поставщик должен установить свойство, связанное с этим интерфейсом, для VARIANT_TRUE. Чтобы разрешить обработку для конкретного свойства, `OnInterfaceRequested` вызывается до `Execute` вызова метода поставщика. По умолчанию `OnInterfaceRequested` обрабатывает следующие интерфейсы:

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

Если вы хотите обрабатывать другие интерфейсы, переопределите эту функцию в источнике данных, сеансе, команде или классе набора строк для обработки функций. Переопределение должно пройти через обычные интерфейсы set/get Properties, чтобы убедиться, что свойства настройки также устанавливают все связанные свойства (см. [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).

## <a name="cutlpropsonpropertychanged"></a><a name="onpropertychanged"></a> CUtlProps:: OnPropertyChanged

Вызывается после задания свойства для управления связанными свойствами.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Параметры

*икурсет*<br/>
Индекс в массиве наборов свойств; нуль, если имеется только один набор свойств.

*пдбпроп*<br/>
Идентификатор свойства и новое значение в структуре [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Возвращаемое значение по умолчанию — S_OK.

### <a name="remarks"></a>Примечания

Если требуется управлять связанными свойствами, такими как закладки или обновления, значения которых зависят от значения другого свойства, следует переопределить эту функцию.

### <a name="example"></a>Пример

В этой функции пользователь получает идентификатор свойства из `DBPROP*` параметра. Теперь можно сравнить идентификатор со свойством с цепочкой. При обнаружении свойства `SetProperties` вызывается со свойством, которое теперь будет задано вместе с другим свойством. В этом случае, если один из них `DBPROP_IRowsetLocate` получает `DBPROP_LITERALBOOKMARKS` свойство, или `DBPROP_ORDEREDBOOKMARKS` , одно из них может `DBPROP_BOOKMARKS` установить свойство.

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="cutlpropssetpropvalue"></a><a name="setpropvalue"></a> CUtlProps:: Сетпропвалуе

Задает свойство в наборе свойств.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Параметры

*пгуидпропсет*<br/>
окне Идентификатор GUID для набора свойств.

*dwPropId*<br/>
окне Индекс свойства.

*пввалуе*<br/>
окне Указатель на вариант, который содержит новое значение свойства.

### <a name="return-value"></a>Возвращаемое значение

`Failure` в случае сбоя и S_OK в случае успеха.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
