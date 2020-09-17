---
title: Макросы агрегирования и фабрики классов
ms.date: 08/12/2020
f1_keywords:
- ATLCOM/ATL::DECLARE_AGGREGATABLE
- ATLCOM/ATL::DECLARE_CLASSFACTORY
- ATLCOM/ATL::DECLARE_CLASSFACTORY_EX
- ATLCOM/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLCOM/ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATLCOM/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATLCOM/ATL::DECLARE_NOT_AGGREGATABLE
- ATLCOM/ATL::DECLARE_ONLY_AGGREGATABLE
- ATLCOM/ATL::DECLARE_POLY_AGGREGATABLE
- ATLCOM/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLCOM/ATL::DECLARE_VIEW_STATUS
- ATLDEF/ATL::DECLARE_AGGREGATABLE
- ATLDEF/ATL::DECLARE_CLASSFACTORY
- ATLDEF/ATL::DECLARE_CLASSFACTORY_EX
- ATLDEF/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLDEF/ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATLDEF/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATLDEF/ATL::DECLARE_NOT_AGGREGATABLE
- ATLDEF/ATL::DECLARE_ONLY_AGGREGATABLE
- ATLDEF/ATL::DECLARE_POLY_AGGREGATABLE
- ATLDEF/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLDEF/ATL::DECLARE_VIEW_STATUS
- ATLCOM/DECLARE_AGGREGATABLE
- ATLCOM/DECLARE_CLASSFACTORY
- ATLCOM/DECLARE_CLASSFACTORY_EX
- ATLCOM/DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLCOM/DECLARE_CLASSFACTORY_SINGLETON
- ATLCOM/DECLARE_GET_CONTROLLING_UNKNOWN
- ATLCOM/DECLARE_NOT_AGGREGATABLE
- ATLCOM/DECLARE_ONLY_AGGREGATABLE
- ATLCOM/DECLARE_POLY_AGGREGATABLE
- ATLCOM/DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLCOM/DECLARE_VIEW_STATUS
- ATL::DECLARE_AGGREGATABLE
- ATL::DECLARE_CLASSFACTORY
- ATL::DECLARE_CLASSFACTORY_EX
- ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATL::DECLARE_NOT_AGGREGATABLE
- ATL::DECLARE_ONLY_AGGREGATABLE
- ATL::DECLARE_POLY_AGGREGATABLE
- ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATL::DECLARE_VIEW_STATUS
- DECLARE_AGGREGATABLE
- DECLARE_CLASSFACTORY
- DECLARE_CLASSFACTORY_EX
- DECLARE_CLASSFACTORY_AUTO_THREAD
- DECLARE_CLASSFACTORY_SINGLETON
- DECLARE_GET_CONTROLLING_UNKNOWN
- DECLARE_NOT_AGGREGATABLE
- DECLARE_ONLY_AGGREGATABLE
- DECLARE_POLY_AGGREGATABLE
- DECLARE_PROTECT_FINAL_CONSTRUCT
- DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
- ATL::DECLARE_AGGREGATABLE
- ATL::DECLARE_CLASSFACTORY
- ATL::DECLARE_CLASSFACTORY_EX
- ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATL::DECLARE_NOT_AGGREGATABLE
- ATL::DECLARE_ONLY_AGGREGATABLE
- ATL::DECLARE_POLY_AGGREGATABLE
- ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATL::DECLARE_VIEW_STATUS
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 5fdf330cfc69ea68720666eae5952be356cad314
ms.sourcegitcommit: 50db6d0a0d640155c9347c1914bc8859efaadd90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "88197334"
---
# <a name="aggregation-and-class-factory-macros"></a>Макросы агрегирования и фабрики классов

Эти макросы предоставляют способы управления статистической обработкой и объявлением фабрик классов.

| Макрос | Описание |
|--|--|
| [DECLARE_AGGREGATABLE](#declare_aggregatable) | Объявляет, что объект может быть агрегирован (по умолчанию). |
| [DECLARE_CLASSFACTORY](#declare_classfactory) | Объявляет фабрику класса для [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md), фабрику классов ATL по умолчанию. |
| [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) | Объявляет объект фабрики класса как фабрику класса. |
| [DECLARE_CLASSFACTORY2](#declare_classfactory2) | Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) как фабрику класса. |
| [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) | Объявляет [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрику класса. |
| [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) | Объявляет [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md) как фабрику класса. |
| [DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown) | Объявляет виртуальную `GetControllingUnknown` функцию. |
| [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) | Объявляет, что объект не может быть агрегирован. |
| [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) | Объявляет, что объект должен быть агрегирован. |
| [DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable) | Проверяет значение внешней неизвестной функции и объявляет статистическую обработку объекта или не подлежит статистической обработке, если это уместно. |
| [DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct) | Защищает внешний объект от удаления во время создания внутреннего объекта. |
| [DECLARE_VIEW_STATUS](#declare_view_status) | Задает флаги ВИЕВСТАТУС для контейнера. |

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a> DECLARE_AGGREGATABLE

Указывает, что объект может быть агрегирован.

```cpp
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя класса, который определяется как статистически обрабатываемый.

### <a name="remarks"></a>Комментарии

[CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит этот макрос для указания статистической модели по умолчанию. Чтобы переопределить это значение по умолчанию, укажите либо макрос [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) , либо [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) в определении класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a> DECLARE_CLASSFACTORY

Объявляет [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) как фабрику класса.

```cpp
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Комментарии

[CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a> Класс Ккомклассфактори

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) .

```cpp
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Комментарии

`CComClassFactory` реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) , который содержит методы для создания объекта определенного идентификатора CLSID, а также блокирует фабрику класса в памяти, чтобы новые объекты могли создаваться быстрее. `IClassFactory` должен быть реализован для каждого класса, регистрируемого в системном реестре и которому назначается идентификатор CLSID.

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` фабрику классов по умолчанию. Чтобы переопределить это значение по умолчанию, укажите один из макросов DECLARE_CLASSFACTORY*xxx* в определении класса. Например, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) макрос использует указанный класс для фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Приведенное выше определение класса указывает, что `CMyClassFactory` будет использоваться в качестве фабрики класса по умолчанию для объекта. `CMyClassFactory` должен быть производным от `CComClassFactory` и переопределять `CreateInstance` .

ATL предоставляет три других макроса, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) Использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который управляет созданием с помощью лицензии.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Использует [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Использует [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md), который конструирует один объект [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) .

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a> DECLARE_CLASSFACTORY_EX

Объявляется как `cf` фабрика класса.

```cpp
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Параметры

*CF*<br/>
окне Имя класса, реализующего объект фабрики класса.

### <a name="remarks"></a>Комментарии

Параметр *CF* должен быть производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и переопределять `CreateInstance` метод.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , который указывает в `CComClassFactory` качестве фабрики классов по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_EX в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a> DECLARE_CLASSFACTORY2

Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) как фабрику класса.

```cpp
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Параметры

*LIC*<br/>
окне Класс, реализующий `VerifyLicenseKey` , `GetLicenseKey` и `IsLicenseValid` .

### <a name="remarks"></a>Комментарии

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , который указывает [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY2 в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a> Класс CComClassFactory2

Этот класс реализует интерфейс [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) .

```cpp
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Параметры

*лицензии*<br/>
Класс, реализующий следующие статические функции:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Комментарии

`CComClassFactory2` реализует интерфейс [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) , который является расширением [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` управляет созданием объектов с помощью лицензии. Фабрика класса, выполняемая на Лицензированном компьютере, может предоставить лицензионный ключ. Этот лицензионный ключ позволяет приложению создавать экземпляры объектов, если лицензия на компьютер не существует.

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), объявляющий [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Чтобы использовать `CComClassFactory2` , укажите [DECLARE_CLASSFACTORY2](#declare_classfactory2) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, параметр шаблона для `CComClassFactory2` должен реализовывать статические функции `VerifyLicenseKey` , `GetLicenseKey` и `IsLicenseValid` . Ниже приведен пример простого класса License:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` является производным от `CComClassFactory2Base` *лицензии*и. `CComClassFactory2Base`, в свою очередь, является производным от `IClassFactory2` и ** \< CComGlobalsThreadModel > CComObjectRootEx**.

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a> DECLARE_CLASSFACTORY_AUTO_THREAD

Объявляет [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрику класса.

```cpp
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Комментарии

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , который указывает [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_AUTO_THREAD в определение класса объекта, вы переопределяете это значение по умолчанию.

При создании объектов в нескольких подразделениях (на сервере вне процесса) добавьте DECLARE_CLASSFACTORY_AUTO_THREAD в класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a> Класс Ккомклассфакторяутосреад

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) и позволяет создавать объекты в нескольких подразделениях.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

```cpp
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Комментарии

`CComClassFactoryAutoThread` аналогичен [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md), но позволяет создавать объекты в нескольких апартаментах. Чтобы воспользоваться этой поддержкой, создайте свой модуль EXE из [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md).

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), объявляющий [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Чтобы использовать `CComClassFactoryAutoThread` , укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a> DECLARE_CLASSFACTORY_SINGLETON

Объявляет [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md) как фабрику класса.

```cpp
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Параметры

*obj*<br/>
окне Имя объекта класса.

### <a name="remarks"></a>Комментарии

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , который указывает [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_SINGLETON в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a> Класс Ккомклассфакторисинглетон

Этот класс является производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и использует [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) для создания одного объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

```cpp
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс.

`CComClassFactorySingleton` является производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и использует [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) для создания одного объекта. Каждый вызов `CreateInstance` метода просто запрашивает этот объект для указателя интерфейса.

### <a name="remarks"></a>Комментарии

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` фабрику классов по умолчанию. Чтобы использовать `CComClassFactorySingleton` , укажите [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a> DECLARE_GET_CONTROLLING_UNKNOWN

Объявляет виртуальную функцию `GetControllingUnknown` .

```cpp
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Комментарии

Добавьте этот макрос в объект, если вы получаете неопределенное сообщение об ошибке компилятора `GetControllingUnknown` (например, в `CComAggregateCreator` ).

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a> DECLARE_NOT_AGGREGATABLE

Указывает, что невозможно выполнить статистическую обработку объекта.

```cpp
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который вы определяете как не подлежащий статистической обработке.

### <a name="remarks"></a>Комментарии

DECLARE_NOT_AGGREGATABLE приводит `CreateInstance` к возвращению ошибки (CLASS_E_NOAGGREGATION), если предпринимается попытка выполнить статистическую обработку на объекте.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос [DECLARE_AGGREGATABLE](#declare_aggregatable) , который указывает, что объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_NOT_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a> DECLARE_ONLY_AGGREGATABLE

Указывает, что объект должен быть агрегирован.

```cpp
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который вы определяете как Статистическое вычисление.

### <a name="remarks"></a>Комментарии

DECLARE_ONLY_AGGREGATABLE вызывает ошибку (E_FAIL) при попытке обращения к объекту в `CoCreate` качестве неагрегированного объекта.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос [DECLARE_AGGREGATABLE](#declare_aggregatable) , который указывает, что объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_ONLY_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a> DECLARE_POLY_AGGREGATABLE

Указывает, что при создании объекта создается экземпляр **CComPolyObject \<** *x* **> ** .

```cpp
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который определяется как агрегированный или не подлежащий статистической обработке.

### <a name="remarks"></a>Комментарии

Во время создания проверяется значение внешней неизвестной. Если он равен NULL, `IUnknown` реализуется для неагрегированного объекта. Если внешнее неизвестное значение не равно NULL, `IUnknown` реализуется для агрегированного объекта.

Преимущество использования DECLARE_POLY_AGGREGATABLE заключается в том, что вы не `CComAggObject` должны использовать и `CComObject` в модуле, чтобы обрабатывать агрегированные и неагрегированные варианты. В `CComPolyObject` обоих случаях обрабатывается один объект. Это означает, что в модуле существует только одна копия таблицы vtable и одна копия функций. Если таблица vtable велика, это может значительно снизить размер модуля. Однако если таблица vtable невелика, использование `CComPolyObject` может привести к тому, что размер модуля будет немного больше, поскольку он не оптимизирован для агрегированного или неагрегированного объекта, как `CComAggObject` и `CComObject` .

Макрос DECLARE_POLY_AGGREGATABLE автоматически объявляется в объекте, если для создания полного доступа используется мастер элементов управления ATL.

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a> DECLARE_PROTECT_FINAL_CONSTRUCT

Защищает объект от удаления, если (во время [финалконструкт](ccomobjectrootex-class.md#finalconstruct)) внутренний агрегированный объект увеличивает число ссылок, а затем уменьшает значение на 0.

```cpp
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a> DECLARE_VIEW_STATUS

Поместите этот макрос в класс элемента управления ActiveX ATL, чтобы указать флаги ВИЕВСТАТУС для контейнера.

```cpp
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Параметры

*статусфлагс*<br/>
окне Флаги ВИЕВСТАТУС. Список флагов см. в разделе [виевстатус](/windows/win32/api/ocidl/ne-ocidl-viewstatus) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
