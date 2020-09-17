---
title: Класс Ккоменум
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 7241d903e44329eb8fd50155059355a470fb7b90
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226624"
---
# <a name="ccomenum-class"></a>Класс Ккоменум

Этот класс определяет объект перечислителя COM, основанный на массиве.

## <a name="syntax"></a>Синтаксис

```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
T,
    Copy>,
public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Интерфейс перечислителя COM. Пример см. в разделе [иенумстринг](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, предоставляемого интерфейсом перечислителя.

*Копировать*<br/>
Однородный [класс политики копирования](../../atl/atl-copy-policy-classes.md).

*среадмодел*<br/>
Потоковая модель класса. По умолчанию для этого параметра используется модель потоков глобальных объектов, используемая в проекте.

## <a name="remarks"></a>Примечания

`CComEnum`Определяет объект перечислителя COM на основе массива. Этот класс аналогичен [ккоменумонстл](../../atl/reference/ccomenumonstl-class.md) , который реализует перечислитель на основе контейнера стандартной библиотеки C++. Ниже приведены типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Чтобы использовать этот класс, сделайте следующее:

- **`typedef`** Специализация этого класса.

- Используйте в **`typedef`** качестве аргумента шаблона в специализации `CComObject` .

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя путем вызова [ккоменумимпл:: init](../../atl/reference/ccomenumimpl-class.md#init).

- Возврат интерфейса перечислителя клиенту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[ккоменумимпл](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="example"></a>Пример

Приведенный ниже код предоставляет многократно используемую функцию для создания и инициализации объекта перечислителя.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Эта функция шаблона может использоваться для реализации `_NewEnum` Свойства интерфейса коллекции, как показано ниже:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Этот код создает объект **`typedef`** для `CComEnum` , предоставляющий вектор вариантов через `IEnumVariant` интерфейс. `CVariantArrayCollection`Класс просто специализируется `CreateEnumerator` на работе с объектами перечислителя этого типа и передает необходимые аргументы.

## <a name="see-also"></a>См. также статью

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс Ккоменумимпл](../../atl/reference/ccomenumimpl-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)
