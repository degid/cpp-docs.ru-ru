---
title: Справочник по средствам проверки C++ Core Guidelines
ms.date: 03/22/2018
ms.topic: reference
helpviewer_keywords:
- code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
ms.openlocfilehash: e85ce8baed9a1ef39e0ab759ab86a5b570a42fa6
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87389952"
---
# <a name="c-core-guidelines-checker-reference"></a>Справочник по средствам проверки C++ Core Guidelines

В этом разделе перечислены предупреждения средства проверки C++ Core Guidelines. Дополнительные сведения об анализе кода см. в разделе [ `/analyze` (анализ кода)](/cpp/build/reference/analyze-code-analysis) и [быстрое начало: анализ кода для C/C++](../code-quality/quick-start-code-analysis-for-c-cpp.md).

> [!NOTE]
> Некоторые предупреждения относятся к более чем одной группе, а не ко всем предупреждениям — полный справочный раздел.

## <a name="owner_pointer-group"></a>Группа OWNER_POINTER

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
Возврат объекта с заданной областью вместо выделения кучи, если он содержит конструктор перемещения. См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26403 RESET_OR_DELETE_OWNER](C26403.md)\
Сброс или явное удаление \<T> указателя владельца "*variable*". См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26404 DONT_DELETE_INVALID](C26404.md)\
Не удаляйте владельца \<T> , который может находиться в недопустимом состоянии. См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)\
Не присваивайте владельцу \<T> , который может находиться в допустимом состоянии. См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)\
Не присваивайте необработанный указатель владельцу \<T> . См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)\
Предпочитать объекты с заданной областью, не выделяйте кучу без необходимости. См. [C++ Core Guidelines R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26429 USE_NOTNULL](C26429.md)\
Символ "*symbol*" никогда не проверяется на значения NULL, его можно пометить как NOT_NULL. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
Символ "*symbol*" не проверяется на допустимость значений NULL для всех путей. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md)\
Тип выражения "*expr*" уже gsl::not_null. Не проверяйте его на допустимость значений NULL. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

## <a name="raw_pointer-group"></a>Группа RAW_POINTER

[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)\
Не присваивайте результат выделения или вызова функции с \<T> возвращаемым значением owner необработанному указателю; \<T> вместо этого используйте owner. См. [C++ Core Guidelines I. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26401 DONT_DELETE_NON_OWNER](c26401.md)\
Не удаляйте необработанный указатель, который не является владельцем \<T> . См. [C++ Core Guidelines I. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
Возврат объекта с заданной областью вместо выделения кучи, если он содержит конструктор перемещения. См. [C++ Core Guidelines R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26408 NO_MALLOC_FREE](C26408.md)\
Избегайте функции malloc() и free(), предпочитать версию new с delete. См. [C++ Core Guidelines R. 10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree).

[C26409 NO_NEW_DELETE](C26409.md)\
Старайтесь не вызывать метод new и delete явным образом, вместо этого используйте std::make_unique \<T> . См. статью [C++ Core Guidelines R. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete).

[C26429 USE_NOTNULL](C26429.md)\
Символ "*symbol*" никогда не проверяется на значения NULL, его можно пометить как NOT_NULL. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
Символ "*symbol*" не проверяется на допустимость значений NULL для всех путей. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md)\
Тип выражения "*expr*" уже gsl::not_null. Не проверяйте его на допустимость значений NULL. См. [C++ Core Guidelines F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
Не используйте арифметические операции с указателями. Вместо этого используйте span. См [. раздел C++ Core Guidelines boundss. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
Выражение "*expr*": нет массива для Decay указателя. См [. раздел C++ Core Guidelines boundss. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

## <a name="unique_pointer-group"></a>Группа UNIQUE_POINTER

[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)\
Параметр "*параметр*" является ссылкой на `const` уникальный указатель, вместо этого используйте const t * или const t&. См. [C++ Core Guidelines R. 32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).

[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)\
Параметр "*параметр*" является ссылкой на уникальный указатель, и он никогда не переназначается или не сбрасывается. вместо этого используйте t * или t&. См. [C++ Core Guidelines R. 33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat).

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
Перемещение, копирование, повторное присвоение или сброс локального смарт-указателя "*symbol*". См. [C++ Core Guidelines R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
Параметр интеллектуального указателя "*symbol*" используется только для доступа к содержащему указателю. Вместо этого используйте T * или T&. См. [C++ Core Guidelines R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

## <a name="shared_pointer-group"></a>Группа SHARED_POINTER

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
Перемещение, копирование, повторное присвоение или сброс локального смарт-указателя "*symbol*". См. [C++ Core Guidelines R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
Параметр интеллектуального указателя "*symbol*" используется только для доступа к содержащему указателю. Вместо этого используйте T * или T&. См. [C++ Core Guidelines R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)\
Параметр общего указателя "*symbol*" передан ссылкой rvalue. Вместо этого передается значение. См. [C++ Core Guidelines R. 34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner).

[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)\
Параметр общего указателя "*symbol*" передается по ссылке, а не сбрасывается или не переназначается. Вместо этого используйте T * или T&. См. [C++ Core Guidelines R. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam).

[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)\
Параметр общего указателя "*symbol*" не копируется или не перемещается. Вместо этого используйте T * или T&. См. [C++ Core Guidelines R. 36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const).

## <a name="declaration-group"></a>Группа объявлений

[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)\
Глобальный инициализатор вызывает функцию "*symbol*", не относящуюся к constexpr. См. [C++ Core Guidelines I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)\
Глобальный инициализатор обращается к внешнему объекту "*symbol*". См. [C++ Core Guidelines I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md)\
Избегайте использования неименованных объектов с пользовательскими конструкциями и уничтожениями. См. раздел [ES. 84: не (попробуйте) объявить локальную переменную без имени](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="class-group"></a>Группа классов

[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)\
Если вы определяете или удаляете любую операцию по умолчанию в типе "*symbol*", определите или удалите их все. См. [C++ Core Guidelines C. 21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all).

[C26433 OVERRIDE_EXPLICITLY](c26433.md)\
Функция "*символ*" должна быть помечена модификатором "override". См. раздел [C. 128. виртуальные функции должны указывать только один из виртуальных, переопределений или конечных](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26434 DONT_HIDE_METHODS](C26434.md)\
Функция "*symbol_1*" скрывает невиртуальную функцию "*symbol_2*". См. раздел [C++ Core Guidelines C. 128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md)\
В функции "*символ*" должно быть указано только одно из "Virtual", "override" или "Final". См. раздел [C. 128. виртуальные функции должны указывать только один из виртуальных, переопределений или конечных](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

[C26436 NEED_VIRTUAL_DTOR](C26436.md)\
Тип "*symbol*" с виртуальной функцией должен иметь открытый виртуальный или защищенный невиртуальный деструктор. См. [C++ Core Guidelines C. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual).

[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md)\
Переопределяющий деструктор не должен использовать явные спецификаторы "override" или "Virtual". См. раздел [C. 128. виртуальные функции должны указывать только один из виртуальных, переопределений или конечных](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="style-group"></a>Группа стилей

[C26438 NO_GOTO](C26438.md)\
Избегайте образования `goto`. См. [C++ Core GUIDELINES ES. 76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto).

## <a name="function-group"></a>Группа функций

[C26439 SPECIAL_NOEXCEPT](C26439.md)\
Этот тип функции может не вызывать исключение. Объявите его **`noexcept`** . См. [C++ Core Guidelines F. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26440 DECLARE_NOEXCEPT](C26440.md)\
Функция "*символ*" может быть объявлена **`noexcept`** . См. [C++ Core Guidelines F. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26447 DONT_THROW_IN_NOEXCEPT](c26447.md)\
Функция объявлена, **`noexcept`** но вызывает функцию, которая может вызывать исключения.
См. раздел [C++ Core Guidelines: F. 6. Если функция не может создавать исключение, объявите ее без](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

## <a name="concurrency-group"></a>Группа ПАРАЛЛЕЛИЗМа

[C26441 NO_UNNAMED_GUARDS](C26441.md)\
Объекты Guard должны иметь имена. См. [C++ Core Guidelines CP. 44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks).

## <a name="const-group"></a>Группа CONST

[C26460 USE_CONST_REFERENCE_ARGUMENTS](c26460.md)\
Ссылочный аргумент "*аргумент*" для функции "*функция*" может быть помечен как `const` . См. раздел [C++ Core Guidelines Con. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26461 USE_CONST_POINTER_ARGUMENTS](c26461.md): \
Аргумент-указатель "*аргумент*" для функции "*функция*" может быть помечен как указатель на `const` . См. раздел [C++ Core Guidelines Con. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26462 USE_CONST_POINTER_FOR_VARIABLE](c26462.md)\
Значение, на которое указывает "*variable*", присваивается только один раз. пометьте его как указатель на `const` . См. раздел [C++ Core Guidelines Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26463 USE_CONST_FOR_ELEMENTS](c26463.md)\
Элементы массива "*array*" назначаются только один раз. Пометьте элементы `const` . См. раздел [C++ Core Guidelines Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26464 USE_CONST_POINTER_FOR_ELEMENTS](c26464.md)\
Значения, на которые указывают элементы массива "*array*", присваиваются только один раз. Пометьте элементы как указатели на `const` . См. раздел [C++ Core Guidelines Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26496 USE_CONST_FOR_VARIABLE](c26496.md)\
Переменная "*переменная*" назначается только один раз, пометьте ее как `const` . См. раздел [C++ Core Guidelines Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26497 USE_CONSTEXPR_FOR_FUNCTION](c26497.md)\
Эта *функция* функции может быть помечена `constexpr` , если требуется вычисление во время компиляции. См. [C++ Core Guidelines F. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr).

[C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL](c26498.md)\
Эта *функция* вызова функции может использоваться, `constexpr` Если требуется вычисление во время компиляции. См. раздел [C++ Core Guidelines Con. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr).

## <a name="type-group"></a>Группа типов

[C26437 DONT_SLICE](C26437.md)\
Не фрагментировать. См. [C++ Core GUIDELINES ES. 63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice).

[C26465 NO_CONST_CAST_UNNECESSARY](c26465.md)\
Не используйте `const_cast` для приведения `const` . `const_cast`не является обязательным; Константа или изменчивости не удаляется этим преобразованием. См. [C++ Core Guidelines Type. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).

[C26466 NO_STATIC_DOWNCAST_POLYMORPHIC](c26466.md)\
Не используйте `static_cast` образования производных типов. Приведение из полиморфизма типа должно использовать dynamic_cast. См. раздел [тип C++ Core Guidelines. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast).

[C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR](c26471.md)\
Не используйте `reinterpret_cast` . Приведение из void * может использовать `static_cast` . См. [C++ Core Guidelines Type. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)\
Не используйте `static_cast` для арифметических преобразований. Используйте скобки для инициализации, gsl::narrow_cast или gsl::narrow. См. [C++ Core Guidelines Type. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26473 NO_IDENTITY_CAST](C26473.md)\
Не применяйте типы указателей, где исходный и конечный типы совпадают. См. [C++ Core Guidelines Type. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26474 NO_IMPLICIT_CAST](C26474.md)\
Не применяйте тип указателя, если преобразование может быть неявным. См. [C++ Core Guidelines Type. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)\
Не используйте приведение типов C в стиле функции. См. [C++ Core GUIDELINES ES. 49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast).

[C26490 NO_REINTERPRET_CAST](c26490.md)\
Не используйте `reinterpret_cast` . См. [C++ Core Guidelines Type. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26491 NO_STATIC_DOWNCAST](c26490.md)\
Не используйте `static_cast` образования производных типов. См. раздел [тип C++ Core Guidelines. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26492 NO_CONST_CAST](c26492.md)\
Не используйте `const_cast` для приведения `const` . См. [C++ Core Guidelines Type. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26493 NO_CSTYLE_CAST](c26493.md)\
Не используйте приведения в стиле C. См. [C++ Core Guidelines Type. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26494 VAR_USE_BEFORE_INIT](c26494.md)\
Переменная "*variable*" не инициализирована. Всегда инициализируйте объект. См. [C++ Core Guidelines Type. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26495 MEMBER_UNINIT](c26495.md)\
Переменная "*variable*" не инициализирована. Всегда инициализируйте переменную-член. См. [C++ Core Guidelines Type. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

## <a name="bounds-group"></a>Группа границ

[C26446 USE_GSL_AT](c26446.md)\
Предпочитать использовать `gsl::at()` вместо непроверенного оператора индекса. См. раздел [C++ Core Guidelines: boundss. 4. не используйте функции и типы стандартной библиотеки, которые не имеют установленных ограничений](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
Не используйте арифметические операции с указателями. Вместо этого используйте span. См [. раздел C++ Core Guidelines Bounds. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26482 NO_DYNAMIC_ARRAY_INDEXING](c26482.md)\
Индексировать в массивы следует только с помощью константных выражений. См [. раздел C++ Core Guidelines Bounds. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26483 STATIC_INDEX_OUT_OF_RANGE](c26483.md)\
Значение *находится вне* границ (0, *с границей*) переменной "*variable*". Индексировать в массивы следует только с помощью константных выражений, находящихся в границах массива. См [. раздел C++ Core Guidelines Bounds. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
Выражение "*expr*": нет массива для Decay указателя. См [. раздел C++ Core Guidelines Bounds. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

## <a name="gsl-group"></a>Группа GSL

[C26445 NO_SPAN_REF](c26445.md)\
Ссылка на `gsl::span` или `std::string_view` может быть указанием проблемы времени существования.
См [. раздел C++ Core GUIDELINES GSL. View: views.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)

[C26446 USE_GSL_AT](c26446.md)\
Предпочитать использовать `gsl::at()` вместо непроверенного оператора индекса. См. раздел [C++ Core Guidelines: boundss. 4. не используйте функции и типы стандартной библиотеки, которые не имеют установленных ограничений](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26448 USE_GSL_FINALLY](c26448.md)\
Рассмотрите возможность использования `gsl::finally` , если планируется финальное действие. См. раздел [C++ Core Guidelines: GSL. util: Utilities](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-utilities).

[C26449 NO_SPAN_FROM_TEMPORARY](c26449.md)\
`gsl::span`или `std::string_view` создается из временной папки, если временная проверка становится недействительной. См. раздел [C++ Core Guidelines: GSL. View: views](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views).

## <a name="deprecated-warnings"></a>Устаревшие предупреждения

Следующие предупреждения представлены в раннем экспериментальном наборе правил средства проверки основных правил, но теперь являются устаревшими и могут быть спокойно пропущены. Предупреждения заменяются предупреждениями из приведенного выше списка.

- 26412 DEREF_INVALID_POINTER
- 26413 DEREF_NULLPTR
- 26420 ASSIGN_NONOWNER_TO_EXPLICIT_OWNER
- 26421 ASSIGN_VALID_OWNER
- 26422 VALID_OWNER_LEAVING_SCOPE
- 26423 ALLOCATION_NOT_ASSIGNED_TO_OWNER
- 26424 VALID_ALLOCATION_LEAVING_SCOPE
- 26425 ASSIGNING_TO_STATIC
- 26499 NO_LIFETIME_TRACKING

## <a name="see-also"></a>См. также

[Использование средств проверки C++ Core Guidelines](using-the-cpp-core-guidelines-checkers.md)
