---
title: ProgID (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 136c651ec92c78339c2f701804a6a409523dd30f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840002"
---
# <a name="progid"></a>progid

Указывает ProgID для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Параметры

*name*<br/>
Идентификатор ProgID, представляющий объект.

Идентификаторы ProgID представляют собой удобочитаемую для человека версию идентификатора класса (CLSID), используемую для идентификации объектов COM/ActiveX.

## <a name="remarks"></a>Примечания

`progid`Атрибут C++ позволяет указать ProgID для COM-объекта. Идентификатор ProgID имеет форму *name1. имя2. Version*. Если не указать *версию* для ProgID, используется версия по умолчанию 1. Если не указать *name1. имя2*, по умолчанию используется имя *className. ClassName*. Если параметр не указан `progid` и задано `vi_progid` значение, *name1. имя2* берется из `vi_progid` и добавляется версия (следующий последовательный номер).

Если блок атрибута, который использует `progid` , не используется `uuid` , Компилятор проверит наличие в реестре, существует ли объект `uuid` для указанного объекта `progid` . Если `progid` параметр не указан, для создания класса будет использоваться версия (и имя кокласса, если создается coclass) `progid` .

`progid` подразумевает `coclass` атрибут, то есть, если вы указали `progid` , это то же самое, что и указание `coclass` `progid` атрибутов и.

`progid`Атрибут вызывает автоматическую регистрацию класса с указанным именем. Созданный IDL-файл не будет отображать это `progid` значение.

Если этот атрибут используется в проекте, использующем ATL, поведение атрибута изменяется. В дополнение к описанному выше поведению, сведения, указанные с помощью этого атрибута, используются в `GetProgID` функции, внедренной `coclass` атрибутом. Дополнительные сведения см. в описании атрибута [coclass](coclass.md) .

## <a name="example"></a>Пример

Пример использования см. в примере для [coclass](coclass.md) `progid` .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|`class`, `struct`|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Ключ ProgID](/windows/win32/com/-progid--key)
