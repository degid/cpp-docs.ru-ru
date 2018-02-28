---
title: "Выключенные по умолчанию предупреждения компилятора | Документы Microsoft"
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 619e2c517305246937ed7428eadbcf40be31fe5b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Выключенные по умолчанию предупреждения компилятора

Компилятор включает в себя предупреждения, отключенные по умолчанию, так как многие разработчики не хотят видеть их. В некоторых случаях они представления стилистических выбора, являются общих идиом в старом коде или воспользоваться расширением Microsoft для языка. В других случаях они указывают на область, где программисты часто делать неверные предположения, что может привести к неожиданным или неопределенное поведение. Некоторые из предупреждений могут быть очень часто срабатывает в заголовков библиотеки.

Эти предупреждения можно включить с помощью одного из следующих вариантов:

- **#pragma warning (по умолчанию:** *warning_number* **)**  
   Указанное предупреждение (*warning_number*) включается на соответствующем уровне по умолчанию. Документация по предупреждениям содержит уровень предупреждения по умолчанию.

- **#pragma warning(** *warning_level* **:** *warning_number* **)**  
   Указанное предупреждение (*warning_number*) включены на заданном уровне (*порог_предупреждения*).

- [/Wall](../build/reference/compiler-option-warning-level.md)  
   **/ Wall** включает все предупреждения, отключенные по умолчанию. При использовании этого параметра, можно отключить отдельные предупреждения с помощью [/wd](../build/reference/compiler-option-warning-level.md) параметр.

- [/w*lnnnn*](../build/reference/compiler-option-warning-level.md)  
   Это позволяет предупреждение  *nnnn*  на уровне *l*.

Следующие предупреждения по умолчанию отключены.

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (уровень 4)|Перечислитель "*идентификатор*«в операторе switch для перечисления»*перечисления*" не обрабатывается явно меткой выбора|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (уровень 4)|Перечислитель "*идентификатор*«в операторе switch для перечисления»*перечисления*" не обрабатывается|
|C4191 (уровень 3)|"*оператор*": небезопасное преобразование из "*type_of_expression*«to»*type_required*"|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (уровень 4)|"*идентификатор*": преобразование из "*тип1*«to»*тип2*", возможна потеря данных|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (уровень 4)|"*оператор*": преобразование из "*тип1*«to»*тип2*", возможна потеря данных|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (уровень 4)|"*функция*": не представлен прототип функции: преобразование «()» в «(void)»|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (уровень 4)|"*функция*": функция-член не переопределяет ни одной функции виртуальный член базового класса|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (уровень 1)|"*virtual_function*": нет доступного переопределения для виртуальной функции-члена из базового "*класс*"; функция скрыта|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (уровень 3)|"*класс*": класс имеет виртуальные функции, но деструктор не является виртуальным|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (уровень 4)|"*функция*": нет доступного переопределения для виртуальной функции-члена из базового "*типа*"; функция скрыта|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (уровень 3)|"*оператор*": без учета знака несовпадение отрицательной константы и константы|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (уровень 4)|использовано нестандартное расширение: "*var*": переменная управления циклом, объявленная в цикле for, используется вне области цикла for|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (уровень 4)|"*оператор*": выражение всегда имеет значение false|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (уровень 4)|"*типа*": обнаружено использование неопределенного типа в метаданных CLR - применение этого типа может привести к исключению среды выполнения|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (уровень 1)|Изменение поведения: "*функция*" вызван, но в предыдущих версиях был вызван оператор-член|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (уровень 1)|Изменение поведения: "*член1*«вызван вместо»*member2*"|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this': используется в основном списке инициализации членов|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (уровень 4)|"*действия*": преобразование из "*тип_1*«to»*тип_2*", несоответствие со знаком и без|
|C4370 (уровень 3)|размещение класса изменилось по сравнению с предыдущей версией компилятора из-за улучшенной упаковки|
|[C4371](../error-messages/compiler-warnings/c4371.md) (уровень 3)|"*classname*": размещение класса могло измениться с предыдущей версии компилятора из-за улучшенной упаковки члена "*член*"|
|C4388 (уровень 4)|несоответствие типов со знаком и без знака|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (уровень 2)|"*функция*": подпись функции содержит тип "*тип*'; Объекты C++ небезопасно передавать между чистый код и смешанного или машинного|
|C4426 нахождения неправильного (уровень 1)|Флаги оптимизации изменены после включения заголовка, может быть связано с #pragma optimize()|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (уровень 4)|"*class1*": структура объекта в/vd2 изменится из-за виртуального базового "*class2*"|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (уровень 4)|приведение dynamic_cast из виртуального базового "*class1*«to»*class2*" может завершиться ошибкой в некоторых контекстах|
|C4444 (уровень 3)|директива верхнего уровня "__unaligned" не реализована в этом контексте|
|C4464 (уровень 4)|относительный путь включения содержит ".."|
|C4472 (уровень 1)|"*идентификатор*" является собственным перечислением: добавьте спецификатор доступа (private/public), чтобы объявить управляемое перечисление|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (уровень 4)|"*функция*": неиспользуемая встроенная функция была удалена|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (уровень 4)|«имя_типа»: имя типа превышает ограничение метаданных "*ограничение*" знаков|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (уровень 1)|вычисление выражения перед запятой дает функцию, в которой отсутствует список аргументов|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (уровень 1)|в вызове функции перед запятой отсутствует список аргументов|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (уровень 1)|"*оператор*": оператор перед запятой не имеет результата; требуется оператор с побочным действием|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (уровень 1)|выражение перед запятой не имеет результата; требуется выражение с побочным действием|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (уровень 1)|"*operator1*": оператор перед запятой не имеет результата; возможно, планировалось "*operator2*"?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (уровень 1)|выражение не имеет результата; требуется выражение с побочным действием|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (уровень 3)|«__assume» содержит эффект "*эффект*"|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (уровень 4)|Информация: семантика catch(...) изменилась, начиная с версии Visual C++ 7.1; структурированные исключения (SEH) более не перехватываются|
|C4574 (уровень 4)|"*идентификатор*«определяется как" 0": имелось в виду использование" #if *идентификатор*"?|
|C4582 (уровень 4)|"*типа*": конструктор не вызывается неявно|
|C4583 (уровень 4)|"*типа*": деструктор не вызывается неявно|
|C4587 (уровень 1)|"*anonymous_structure*": изменение поведения: конструктор имеет больше не вызывается неявно|
|C4588 (уровень 1)|"*anonymous_structure*": изменение поведения: деструктор больше не вызывается неявно|
|C4598 (уровень 1 и уровень 3)|"#include"*заголовок*«": номер заголовка *номер* в предкомпилированный заголовок не соответствует текущей компиляции в этой позиции|
|C4599 (уровень 3)|"*параметр* *путь*": номер аргумента командной строки *номер* не соответствует предварительно скомпилированного заголовка|
|C4605 (уровень 1)|"/D*макрос*" указан в текущей командной строке, но не был указан, если предкомпилированный заголовок был построен|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (уровень 3)|предупреждение #pragma: нет предупреждения с номером "*номер*"|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (уровень 4)|"derived class": не удалось создать конструктор по умолчанию, так как конструктор по умолчанию для базового класса недоступен|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (уровень 4)|"derived class": не удалось создать конструктор копии, так как конструктор копии для базового класса недоступен|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (уровень 4)|"derived class": не удалось создать оператор присваивания, так как оператор присваивания для базового класса недоступен|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (уровень 1)|диграфы не поддерживаются при наличии параметра -Ze. Последовательность символов "*диграф*«не преобразована в альтернативный маркер для»*char*"|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (уровень 3)|"*экземпляр*": создание в конструкторе локального статического объекта не является потокобезопасной|
|C4647 (уровень 3)|Изменение поведения: __is_pod (*типа*) имеет другое значение в предыдущих версиях|
|C4654 (уровень 4)|Код, помещенный перед включают предкомпилированного заголовка строки будут пропущены. Добавьте код для предкомпилированного заголовка.|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (уровень 4)|"*символ*«не определен в качестве макроса препроцессора и будет заменен"0"в»*директивы*"|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (уровень 4)|"*символ*": не указан атрибут параметра направления, по умолчанию принимается [in]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (уровень 3)|"*определяемого пользователем типа*": возможное изменение поведения, изменение возвращаемого значения UDT соглашение о вызовах|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (уровень 1)|"*функция*": подпись не частного члена содержит частный собственный тип сборки "*частныйТип*"|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (уровень 4)|"*функция*": функция не является встроенной|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (уровень 3)|хранение результатов в памяти в 32-разрядном формате с плавающей запятой, возможно снижение производительности|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|переменное обращение "*выражение*" определяется параметром/volatile:\<iso &#124; ms >; попробуйте использовать встроенные функции __iso_volatile_load/store|
|C4749 (уровень 4)|условно поддерживается: нестандартное применение offsetof к non standard макет типа "*типа*"|
|C4767 (уровень 4)|Имя раздела '*символ*"длиннее, чем 8 символов и будет усечено компоновщиком|
|C4768 (уровень 3)|атрибуты __declspec перед спецификация компоновки учитываются.|
|C4774 (уровень 4)|"*строка*": ожидаемая в аргументе строки формата *номер* не является строковым литералом|
|C4786 (уровень 3)|"*символ*": имя объекта было усечено до "*номер*" символов в отладочной информации|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (уровень 4)|"*байт*«-байтовые поля добавлены после конструкции»*member_name*"|
|C4826 (уровень 2)|Преобразование из "*тип1*«to»*тип2*" выполняется с расширением знака. Это может вызвать непредвиденное поведение.|
|C4837 (уровень 4)|Обнаруженный триграф: "?? *символ*«заменить»*символ*"|
|C4841 (уровень 4)|использовано нестандартное расширение: обозначение составной элемент, используемый в offsetof|
|C4842 (уровень 4)|результат offsetof применяется к типу, использование множественного наследования не обязательно быть согласованы между версиями компилятора|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (уровень 4)|"_файл_(*номер_строки*)" компилятор не может принудительно применить порядок вычисления слева направо в списке инициализации в фигурных скобках|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (уровень 1)|приведение двухбайтового строкового литерала к "LPSTR"|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (уровень 1)|строковой литерал приведен к "LPWSTR"|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (уровень 1)|"*декларатор*": идентификатор GUID может быть связан только с классом, интерфейсом или пространством имен|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (уровень 1)|недопустимая инициализация копии; неявно применено несколько пользовательских преобразований|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (уровень 4)|предполагается, что при построении библиотека типов была рассчитана на "число"-разрядные указатели|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (уровень 1)|reinterpret_cast между связанными классами: "*class1*«и»*class2*"|
|C4962|"*функция*": Профильная оптимизация отключена, поскольку операции оптимизации приводят к несогласованности данных профиля|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (уровень 4)|"*символ*": спецификация исключения не соответствует предыдущему объявлению|
|C4987 (уровень 4)|используется нестандартное расширение: throw (...)|
|C4988 (уровень 4)|"*символ*": переменная объявлена вне области класса или функции|
|C5022|"*типа*": указано несколько конструкторов перемещения|
|C5023|"*типа*": заданы несколько операторов присваивания перемещения|
|C5024 (уровень 4)|"*типа*": переместите конструктор неявно определен как удаленный|
|C5025 (уровень 4)|"*типа*": переместите оператор присваивания неявно определен как удаленный|
|C5026 (уровень 1 и уровень 4)|"*типа*": переместите конструктор неявно определен как удаленный|
|C5027 (уровень 1 и уровень 4)|"*типа*": переместите оператор присваивания неявно определен как удаленный|
|C5029 (уровень 4)|использовано нестандартное расширение: атрибуты выравнивания в C++ применяются к переменным, элементам данных и только к типам тегов|
|C5031 (уровень 4)|#pragma warning(pop): возможное несоответствие, состояние всплывающего предупреждения передано в другой файл|
|C5032 (уровень 4)|Обнаружено #pragma warning(push) без соответствующего выражения #pragma warning(pop)|
|C5035|Использование функции "*компонент*" вызывает функцию *функция* будет компилироваться как Гость кода|
|C5036 (уровень 1)|varargs преобразование указателя функции, при компиляции с /hybrid:x86arm64 "*тип1*«to»*тип2*"|
|[C5038](../error-messages/compiler-warnings/c5038.md)|элемент данных "*member1*«будет инициализирована после элемента данных»*member2*"|

Эти предупреждения, отключены, если не [/ разрешительным-](../build/reference/permissive-standards-conformance.md) задан параметр компилятора:

|||
|-|-|
|[C4471 (уровень 4)](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md)|у прямого объявления неограниченного перечисления должен быть базовый тип (предполагается тип int)|
|[C4608 (уровень 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|"*union_member*«уже инициализирован другим членом объединения в списке инициализаторов»*union_member*"|

Эти предупреждения были в версиях до Visual Studio 2015 компилятора по умолчанию:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (уровень 2)|"*преобразования*": усечение из "*тип1*«to»*тип2*"|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (уровень 1)|"*переменной*": усечение указателя из "*тип*«to»*типа*"|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (уровень 1)|"*операции*": преобразование из "*тип1*«to»*тип2*" большего размера|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (уровень 1)|"*оператор*": нулевое расширение "*тип1*«to»*тип2*" большего размера|

Эти предупреждения были в версиях до Visual Studio 2012 компилятора по умолчанию:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (уровень 4)|отсутствует спецификатор типа — предполагается int. Примечание. C++ не поддерживает тип int по умолчанию|

## <a name="see-also"></a>См. также

[warning](../preprocessor/warning.md)