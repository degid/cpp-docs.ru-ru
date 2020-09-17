---
title: Module (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: b6cde0baaae9901258e90ededf05c60cb13a7dc1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833976"
---
# <a name="module-c"></a>module (C++)

Определяет блок библиотеки в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Параметры

*type*<br/>
Используемых Может быть одним из следующих:

- `dll` Добавляет функции и классы, которые позволяют результирующей библиотеке DLL функционировать как внутрипроцессный COM-сервер. Это значение по умолчанию.

- `exe` Добавляет функции и классы, которые позволяют результирующему исполняемому файлу работать как сервер COM вне процесса.

- `service` Добавляет функции и классы, позволяющие результирующему исполняемому файлу функционировать как служба NT.

- `unspecified` Отключает внедрение кода ATL, связанного с атрибутом Module: внедрение класса модуля ATL, _AtlModule глобальных экземпляров и функций точки входа. Не отключает внедрение кода ATL из-за других атрибутов в проекте.

*name*<br/>
Используемых Имя блока библиотеки.

*version*<br/>
Используемых Номер версии, который необходимо назначить блоку библиотеки. Значение по умолчанию — 1,0.

*uuid*<br/>
Уникальный идентификатор для библиотеки. Если этот параметр опущен, идентификатор для библиотеки будет создан автоматически. Может потребоваться получить значение *uuid* для блока библиотеки, что можно сделать с помощью идентификатора **__uuidof(** *имя_библиотеки* **)**.

*lcid*<br/>
Параметр локализации. Дополнительные сведения см. в описании [lcid](/windows/win32/Midl/lcid) .

*control*<br/>
Используемых Указывает, что все коклассы в библиотеке являются элементами управления.

*helpstring*<br/>
Указывает библиотеку типов.

*helpstringdll*<br/>
Используемых Задает имя DLL-файла, используемого для выполнения поиска строки документа. Дополнительные сведения см. в описании [helpstringdll](/windows/win32/Midl/helpstringdll) .

*helpfile*<br/>
Используемых Имя файла **справки** для библиотеки типов.

*helpcontext*<br/>
Используемых **Идентификатор справки** для этой библиотеки типов.

*helpstringcontext*<br/>
Используемых Дополнительные сведения см. в разделе [хелпстрингконтекст](helpstringcontext.md) .

*служеб*<br/>
Используемых Предотвращает отображение всей библиотеки. Этот режим предназначен для использования с элементами управления. Узлы должны создать новую библиотеку типов, инкапсулирующую элемент управления с расширенными свойствами. Дополнительные сведения см. в описании атрибута MIDL [hidden](/windows/win32/Midl/hidden) .

*зона*<br/>
Используемых Члены библиотеки не могут вызываться произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](/windows/win32/Midl/restricted) .

*настройки*<br/>
Используемых Один или несколько атрибутов; Это похоже на [Пользовательский](custom-cpp.md) атрибут. Первым параметром для *Custom* является идентификатор GUID атрибута. Пример:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
Идентификатор строкового ресурса RGS-файла, используемый для регистрации идентификатора приложения для библиотеки DLL, исполняемого файла или службы. Если модуль имеет тип service, этот аргумент также используется для получения идентификатора строки, содержащей имя службы.

> [!NOTE]
> Как RGS-файл, так и строка с именем службы должны содержать одинаковое числовое значение.

## <a name="remarks"></a>Примечания

Если не указать параметр *restricted* для [emitidl](emitidl.md), **module** требуется в любой программе, использующей атрибуты C++.

Блок библиотеки создается, если в дополнение к атрибуту **module** исходный код также использует [dispinterface](dispinterface.md), [dual](dual.md), [object](object-cpp.md)либо атрибут, подразумевающий [coclass](coclass.md).

В IDL-файле разрешен один блок библиотеки. Несколько записей module в исходном коде будут объединены с применением самых последних значений параметров.

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанного выше поведения, атрибут также вставляет глобальный объект (с именем `_AtlModule` ) правильного типа и дополнительный код поддержки. Если атрибут является автономным, он вставляет класс, производный от правильного типа module. Если атрибут применяется к классу, он добавляет базовый класс правильного типа module. Правильный тип определяется значением параметра *типа* :

- `type` = **компоновки**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) используется в качестве базового класса и стандартных точек входа библиотеки DLL, необходимых для COM-сервера. Это точки входа: [DllMain](/windows/win32/Dlls/dllmain), [DllRegisterServer](/windows/win32/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/win32/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)и [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- `type` = **программы**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/win32/api/winbase/nf-winbase-winmain).

- `type` = **служеб**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/win32/api/winbase/nf-winbase-winmain).

- `type` = **Unspecified**

   Отключает внедрение кода ATL, связанного с атрибутом module.

## <a name="example"></a>Пример

В следующем коде показано, как создать блок библиотеки в сформированном IDL-файле.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

В следующем коде показано, что можно предоставить собственную реализацию функции, которая будет отображаться в коде, внедренном в результате применения **module**. Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../../build/reference/fx-merge-injected-code.md) . Чтобы переопределить одну из функций, вставленных атрибутом **module** , создайте класс, который будет содержать реализацию функции, и примените к этому классу атрибут **module** .

```cpp
// cpp_attr_ref_module2.cpp
// compile with: /LD /link /OPT:NOREF
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

// no semicolon after attribute block
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]
// module attribute now applies to this class
class CMyClass {
public:
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {
   // add your own code here
   return __super::DllMain(dwReason, lpReserved);
   }
};
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
[Атрибуты класса](class-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Библиотечная](/windows/win32/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[version](version-cpp.md)
