---
title: Классы поддержки компилятора COM
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: a8b0845fdfa96c1cb4b8b67e9d39169d9f4d3737
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189706"
---
# <a name="compiler-com-support-classes"></a>Классы поддержки компилятора COM

**Блок, относящийся только к системам Microsoft**

Стандартные классы используются для поддержки некоторых типов модели COM. Классы определяются в \<comdef.h > и файлы заголовков, созданные из библиотеки типов.

|Class|Назначение|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|
|[_com_error](../cpp/com-error-class.md)|Определяет объект Error, вызываемый [_com_raise_error](../cpp/com-raise-error.md) в большинстве сбоев.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели на COM-интерфейсы и автоматизирует необходимые вызовы `AddRef`, `Release`и `QueryInterface`.|
|[_variant_t](../cpp/variant-t-class.md)|Создает программу оболочку для типа `VARIANT`, предоставляя полезные операторы и методы.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Поддержка COM компилятора](../cpp/compiler-com-support.md)<br/>
[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)
