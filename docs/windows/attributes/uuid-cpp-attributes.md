---
title: uuid (атрибуты C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: 9ff8888c26945d7f118e71002e3b3290217b463c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843044"
---
# <a name="uuid-c-attributes"></a>uuid (атрибуты C++)

Задает уникальный идентификатор класса или интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[ uuid( "uuid" ) ]
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
128-разрядный уникальный идентификатор.

## <a name="remarks"></a>Примечания

Если в определении интерфейса или класса не указан `uuid` Атрибут C++, компилятор Microsoft C++ предоставит его. При указании `uuid` необходимо включить кавычки.

Если не указать `uuid` , компилятор создаст тот же идентификатор GUID для интерфейсов или классов с тем же именем в разных проектах атрибутов на компьютере.

Для создания собственных уникальных идентификаторов можно использовать Uuidgen.exe или Guidgen.exe. (Чтобы запустить любой из этих средств, нажмите кнопку **Пуск** и выберите пункт **выполнить** в меню. Затем введите имя требуемого инструмента.)

При использовании в проекте, который не использует ATL, указание атрибута аналогично `uuid` указанию [uuid](../../cpp/uuid-cpp.md) **`__declspec`** модификатора UUID. Чтобы получить `uuid` класс, можно использовать [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Пример

Пример использования см. в примере с [возможностью привязки](bindable.md) `uuid` .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|`class`, `struct`, `interface`, `union`, `enum`|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)
