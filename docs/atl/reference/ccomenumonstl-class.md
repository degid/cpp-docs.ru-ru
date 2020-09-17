---
title: Класс Ккоменумонстл
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: b0674d64b471318d972d209373e0d74af0fa77f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226598"
---
# <a name="ccomenumonstl-class"></a>Класс Ккоменумонстл

Этот класс определяет объект перечислителя COM на основе коллекции стандартной библиотеки C++.

## <a name="syntax"></a>Синтаксис

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
T,
    Copy,
CollType>,
    public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Перечислитель COM. Пример см. в разделе [иенумстринг](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, предоставляемого интерфейсом перечислителя.

*Копировать*<br/>
Класс [политики копирования](../../atl/atl-copy-policy-classes.md) .

*коллтипе*<br/>
Класс контейнера стандартной библиотеки C++.

## <a name="remarks"></a>Примечания

`CComEnumOnSTL`Определяет объект перечислителя COM на основе коллекции стандартной библиотеки C++. Этот класс можно использовать самостоятельно или в сочетании с [иколлектиононстлимпл](../../atl/reference/icollectiononstlimpl-class.md). Ниже приведены типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Чтобы использовать этот класс с Иколлектиононстлимпл:

- **`typedef`** Специализация этого класса.

- Используйте в **`typedef`** качестве окончательного аргумента шаблона в специализации `ICollectionOnSTLImpl` .

Пример см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md) .

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Использование этого класса независимо от Иколлектиононстлимпл:

- **`typedef`** Специализация этого класса.

- Используйте в **`typedef`** качестве аргумента шаблона в специализации `CComObject` .

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя путем вызова [иенумонстлимпл:: init](../../atl/reference/ienumonstlimpl-class.md#init).

- Возврат интерфейса перечислителя клиенту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="example"></a>Пример

Приведенный ниже код предоставляет универсальную функцию для управления созданием и инициализацией объекта перечислителя.

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Эта функция шаблона может использоваться для реализации `_NewEnum` Свойства интерфейса коллекции, как показано ниже:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Этот код создает объект **`typedef`** для `CComEnumOnSTL` , который предоставляет вектор из с `CComVariant` помощью `IEnumVariant` интерфейса. `CVariantCollection`Класс просто специализируется `CreateSTLEnumerator` на работе с объектами перечислителя этого типа.

## <a name="see-also"></a>См. также статью

[иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)<br/>
[Пример Атлколлектионс. Демонстрация классов политик Иколлектиононстлимпл, Ккоменумонстл и пользовательских копий](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс Иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)
