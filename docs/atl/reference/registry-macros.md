---
title: Макросы реестра
ms.date: 08/19/2019
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: dac1c187bae0eb55b954fc02cd4fb4c981f272f4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834522"
---
# <a name="registry-macros"></a>Макросы реестра

Эти макросы определяют полезные средства библиотеки типов и реестра.

|Имя|Описание|
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Указывает, что код регистрации для объекта должен находиться в объекте, чтобы избежать зависимости от ATL.DLL.|
|[DECLARE_LIBID](#declare_libid)|Предоставляет библиотеке ATL способ получения *идентификатора LIBID* библиотеки типов.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Позволяет избежать регистрации ATL по умолчанию.|
|[DECLARE_REGISTRY](#declare_registry)|Вводит или удаляет запись основного объекта в системном реестре.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Задает сведения, необходимые для автоматической регистрации *AppID*.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Находит именованный ресурс и запускает в нем сценарий реестра.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Находит ресурс, идентифицируемый по ИДЕНТИФИКАЦИОНному номеру, и запускает в нем сценарий реестра.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a> _ATL_STATIC_REGISTRY

Символ, указывающий, что код регистрации для объекта должен находиться в объекте, чтобы избежать зависимости от ATL.DLL.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Примечания

При определении ATL_STATIC_REGISTRY следует использовать следующий код:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a> DECLARE_LIBID

Предоставляет библиотеке ATL способ получения *идентификатора LIBID* библиотеки типов.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Параметры

*ID*<br/>
Идентификатор GUID библиотеки типов.

### <a name="remarks"></a>Примечания

Используйте DECLARE_LIBID в `CAtlModuleT` производном классе.

### <a name="example"></a>Пример

Для созданных мастером проектов ATL, не являющихся атрибутами, будет использоваться пример использования этого макроса.

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a> DECLARE_NO_REGISTRY

Используйте DECLARE_NO_REGISTRY, если необходимо избежать регистрации в библиотеке ATL по умолчанию для класса, в котором этот макрос отображается.

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a> DECLARE_REGISTRY

Вводит стандартную регистрацию класса в системный реестр или удаляет ее из системного реестра.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>Параметры

*class*<br/>
окне Включается для обеспечения обратной совместимости.

*pid*<br/>
окне LPCTSTR, который является идентификатором программы, зависящей от версии.

*впид*<br/>
окне LPCTSTR, который является идентификатором программы, не зависящей от версии.

*NID*<br/>
окне Значение UINT, которое является индексом строки ресурса в реестре для использования в качестве описания программы.

*flags*<br/>
окне Значение типа DWORD, содержащее потоковую модель программы в реестре. Должно иметь одно из следующих значений: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или АУТПРКСФЛАГ.

### <a name="remarks"></a>Примечания

Стандартная регистрация состоит из идентификатора CLSID, идентификатора программы, идентификатора программы, не зависящего от версии, строки описания и модели потока.

При создании объекта или элемента управления с помощью мастера добавления классов ATL мастер автоматически реализует поддержку реестра на основе сценариев и добавляет в файлы макрос [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) . Если не требуется поддержка реестра на основе сценариев, необходимо заменить этот макрос на DECLARE_REGISTRY. DECLARE_REGISTRY только вставляет пять основных ключей, описанных выше, в реестр. Необходимо вручную написать код для вставки других ключей в реестр.

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a> DECLARE_REGISTRY_APPID_RESOURCEID

Задает сведения, необходимые для автоматической регистрации *AppID*.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Параметры

*Resid*<br/>
Идентификатор ресурса RGS файла, содержащего сведения о *AppID*.

*appid*<br/>
Идентификатор GUID.

### <a name="remarks"></a>Примечания

Используйте DECLARE_REGISTRY_APPID_RESOURCEID в `CAtlModuleT` производном классе.

### <a name="example"></a>Пример

Классы, добавленные в проекты ATL с помощью мастера добавления кода класса, будут иметь пример использования этого макроса.

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a> DECLARE_REGISTRY_RESOURCE

Получает именованный ресурс, содержащий файл реестра, и запускает сценарий для ввода объектов в системный реестр или удаления их из системного реестра.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Идентификатор строки ресурса.

### <a name="remarks"></a>Примечания

При создании объекта или элемента управления с помощью мастера проектов ATL мастер автоматически реализует поддержку реестра на основе сценариев и добавляет в файлы макрос [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) , аналогичный DECLARE_REGISTRY_RESOURCE.

Для оптимизированного доступа к реестру можно статически связать с компонентом реестра ATL (регистратором). Чтобы статически связать с кодом регистратора, добавьте следующую строку в файл *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях):

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если необходимо, чтобы в библиотеке ATL заменялись замещающие значения во время выполнения, не указывайте DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структур, где каждая запись содержит заполнитель переменной со значением для замены заполнителя во время выполнения. Затем вызовите [катлмодуле:: упдатерегистрифромресаурцед](catlmodule-class.md#updateregistryfromresourced) или [Катлмодуле:: упдатерегистрифромресаурцес](catlmodule-class.md#updateregistryfromresources), передав массив. При этом все замещающие значения в структурах добавляются в `_ATL_REGMAP_ENTRIES` карту замены регистратора.

Дополнительные сведения о заменяемых параметрах и сценариях см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a> DECLARE_REGISTRY_RESOURCEID

То же, что и [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) за исключением того, что в нем используется формируемый мастером uint для поиска ресурса, а не имя строки.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Идентификатор ресурса, созданный мастером.

### <a name="remarks"></a>Примечания

При создании объекта или элемента управления с помощью мастера проектов ATL мастер автоматически реализует поддержку реестра на основе сценариев и добавляет макрос DECLARE_REGISTRY_RESOURCEID в файлы.

Для оптимизированного доступа к реестру можно статически связать с компонентом реестра ATL (регистратором). Чтобы статически связать с кодом регистратора, добавьте следующую строку в файл *stdafx.h* (*PCH.h* в Visual Studio 2019 и более поздних версиях):

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если необходимо, чтобы в библиотеке ATL заменялись замещающие значения во время выполнения, не указывайте DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структур, где каждая запись содержит заполнитель переменной со значением для замены заполнителя во время выполнения. Затем вызовите [катлмодуле:: упдатерегистрифромресаурцед](catlmodule-class.md#updateregistryfromresourced) или [Катлмодуле:: упдатерегистрифромресаурцес](catlmodule-class.md#updateregistryfromresources), передав массив. При этом все замещающие значения в структурах добавляются в `_ATL_REGMAP_ENTRIES` карту замены регистратора.

Дополнительные сведения о заменяемых параметрах и сценариях см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
