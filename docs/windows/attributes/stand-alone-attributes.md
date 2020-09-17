---
title: Изолированные атрибуты (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: a7df91bbb1c6929b08d8cd867be9f13ce0c35b91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166176"
---
# <a name="stand-alone-attributes"></a>Изолированные атрибуты

Изолированный атрибут не работает с C++ ключевым словом, но более похож на строку кода. В конце строки в качестве изолированных операторов атрибутов требуется точка с запятой.

## <a name="stand-alone-attribute-list"></a>Автономный список атрибутов

|attribute|Description|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Порождает указанную строку без кавычек в созданный файл заголовка.|
|[custom](custom-cpp.md)|Позволяет определить собственный атрибут.|
|[db_command](db-command.md)|Создает команду OLE DB.|
|[emitidl](emitidl.md)|Определяет, будут ли обрабатываться все последующие атрибуты IDL и помещены в созданный IDL-файл.|
|[idl_module](idl-module.md)|Задает точку входа в библиотеке DLL.|
|[idl_quote](idl-quote.md)|Позволяет использовать конструкции IDL, которые не поддерживаются в текущей версии Visual C++ , и передают их в созданный IDL-файл.|
|[import](import.md)|Указывает другой файл. idl,. odl или.h, содержащий определения, на которые вы хотите создать ссылку из основного IDL-файла.|
|[importidl](importidl.md)|Вставляет указанный IDL-файл в созданный IDL-файл|
|[importlib](importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[include](include-cpp.md)|Указывает один или несколько файлов заголовков для включения в созданный IDL-файл.|
|[includelib](includelib-cpp.md)|Вызывает включение IDL-или h-файла в созданный IDL-файл.|
|[library_block](library-block.md)|Помещает конструкцию внутрь блока библиотеки IDL-файла.|
|[module](module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[no_injected_text](no-injected-text.md)|Не позволяет компилятору внедрять код в результате использования атрибута.|
|[pragma](pragma.md)|Порождает указанную строку без кавычек в созданный IDL-файл.|

## <a name="see-also"></a>См. также раздел

[Список атрибутов по использованию](attributes-by-usage.md)
