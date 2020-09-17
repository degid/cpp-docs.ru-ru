---
title: idl_module (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 651d2e133d7ef08fce48feded1b7a5aff458adb1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845228"
---
# <a name="idl_module"></a>idl_module

Задает точку входа в DLL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Параметры

*name*<br/>
Определяемое пользователем имя для блока кода, которое будет отображаться в IDL-файле.

*dllname*<br/>
Используемых DLL-файл, содержащий экспорт.

*uuid*<br/>
Используемых Уникальный идентификатор.

*helpstring*<br/>
Используемых Символьная строка, используемая для описания библиотеки типов.

*helpstringcontext*<br/>
Используемых ИДЕНТИФИКАТОР раздела справки в файле.hlp или. chm.

*helpcontext*<br/>
Используемых Идентификатор справки для этой библиотеки типов.

*служеб*<br/>
Используемых Параметр, который предотвращает отображение библиотеки. Дополнительные сведения см. в описании атрибута MIDL [hidden](/windows/win32/Midl/hidden) .

*зона*<br/>
Используемых Члены библиотеки не могут вызываться произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](/windows/win32/Midl/restricted) .

*объявление функции*<br/>
Функция, которая будет определена.

## <a name="remarks"></a>Примечания

Атрибут **idl_module** C++ позволяет указать точку входа в DLL-файле, которая позволяет импортировать из DLL-файла.

Атрибут **idl_module** имеет функциональные возможности, аналогичные атрибуту MIDL [модуля](/windows/win32/Midl/module) .

Вы можете экспортировать содержимое из COM-объекта, который можно экспортировать из файла DLL, поместив точку входа DLL в блок библиотеки IDL-файла.

Необходимо использовать **idl_module** в двух шагах. Во-первых, необходимо определить пару имя/DLL. Затем при использовании **idl_module** для указания точки входа укажите имя и все дополнительные атрибуты.

## <a name="example"></a>Пример

В следующем коде показано, как использовать атрибут **idl_module** :

```cpp
// cpp_attr_ref_idl_module.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];
[idl_module(name="MyLib"), entry(4), usesgetlasterror]
void FuncName(int i);
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|В любом месте|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[операции](entry.md)
