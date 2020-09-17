---
title: Указание оптимизации компилятора для проекта ATL
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: c3b00823cb33be952451c3cc9e370c99140acc3c
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630617"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Указание оптимизации компилятора для проекта ATL

По умолчанию [Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md) создает новые классы с помощью макроса ATL_NO_VTABLE следующим образом:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

Затем ATL определяет _ATL_NO_VTABLE следующим образом:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

Если не определить _ATL_DISABLE_NO_VTABLE, макрос ATL_NO_VTABLE расширяется до `declspec(novtable)`. Использование `declspec(novtable)`в объявлении класса предотвращает инициализацию указателя vtable в конструкторе и деструкторе класса. При сборке проекта компоновщик удаляет таблицы vtable и все функции, на которые указывает vtable.

Необходимо использовать ATL_NO_VTABLE и, следовательно `declspec(novtable)`, только базовые классы, которые не могут быть созданы напрямую. `declspec(novtable)` Не следует использовать в проекте с наиболее производным классом, так как этот класс (обычно [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md)или [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) инициализирует указатель vtable для проекта.

Не следует вызывать виртуальные функции из конструктора любого объекта, использующего `declspec(novtable)`. Необходимо переместить эти вызовы в метод [финалконструкт](ccomobjectrootex-class.md#finalconstruct) .

Если вы не уверены, следует ли использовать `declspec(novtable)` модификатор, можно удалить макрос ATL_NO_VTABLE из любого определения класса или глобально отключить его, указав

```
#define _ATL_DISABLE_NO_VTABLE
```

в файле *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях) перед включением всех остальных файлов заголовков ATL.

## <a name="see-also"></a>См. также

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов C++ в Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
