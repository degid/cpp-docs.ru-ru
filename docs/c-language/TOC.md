# [Справочник по языку C](c-language-reference.md)
## [Организация справочника по языку C](organization-of-the-c-language-reference.md)
### [Содержание данного руководства](scope-of-this-manual.md)
### [Соответствие ANSI](ansi-conformance.md)
## [Элементы языка C](elements-of-c.md)
### [Токены C](c-tokens.md)
#### [Пробелы](white-space-characters.md)
#### [Комментарии в C](c-comments.md)
#### [Оценка токенов](evaluation-of-tokens.md)
### [Ключевые слова в C](c-keywords.md)
### [Идентификаторы C](c-identifiers.md)
#### [Многобайтовая кодировка и расширенные символы](multibyte-and-wide-characters.md)
#### [Триграфы](trigraphs.md)
### [Константы в C](c-constants.md)
#### [Константы с плавающей запятой в C](c-floating-point-constants.md)
##### [Ограничения на константы с плавающей запятой](limits-on-floating-point-constants.md)
#### [Целочисленные константы в C](c-integer-constants.md)
##### [Целочисленные типы](integer-types.md)
##### [Пределы целых чисел в C++](cpp-integer-limits.md)
#### [Константы символов в C](c-character-constants.md)
##### [Символьные типы](character-types.md)
##### [Набор символов исполнения](execution-character-set.md)
##### [Escape-последовательность](escape-sequences.md)
##### [Спецификации восьмеричных и шестнадцатеричных символов](octal-and-hexadecimal-character-specifications.md)
### [Строковые литералы в C](c-string-literals.md)
#### [Тип для строковых литералов](type-for-string-literals.md)
#### [Хранение строковых литералов](storage-of-string-literals.md)
#### [Объединение строковых литералов](string-literal-concatenation.md)
#### [Максимальная длина строки](maximum-string-length.md)
### [Знаки препинания и специальные символы](punctuation-and-special-characters.md)
## [Структура программы](program-structure.md)
### [Файлы с исходным кодом и исходные программы](source-files-and-source-programs.md)
#### [Директивы препроцессору](directives-to-the-preprocessor.md)
#### [Прагмы C](c-pragmas.md)
#### [Объявления и определения в C](c-declarations-and-definitions.md)
#### [Объявления и определения функций](function-declarations-and-definitions.md)
#### [Блоки](blocks.md)
#### [Пример программы](example-program.md)
### [Функция main и выполнение программ](main-function-and-program-execution.md)
#### [Использование wmain](using-wmain.md)
#### [Описание аргумента](argument-description.md)
#### [Расширение аргументов заполнителей](expanding-wildcard-arguments.md)
#### [Анализ аргументов командной строки C](parsing-c-command-line-arguments.md)
#### [Настройка обработки командной строки C](customizing-c-command-line-processing.md)
### [Время жизни, область, видимость и компоновка](lifetime-scope-visibility-and-linkage.md)
#### [Время существования](lifetime.md)
#### [Область и видимость](scope-and-visibility.md)
#### [Сводка времени существования и видимости](summary-of-lifetime-and-visibility.md)
#### [Компоновка](linkage.md)
##### [Внутренняя компоновка](internal-linkage.md)
##### [Внешняя компоновка](external-linkage.md)
##### [Без компоновки](no-linkage.md)
### [Пространства имен](name-spaces.md)
## [Объявления и типы](declarations-and-types.md)
### [Общие сведения об объявлениях](overview-of-declarations.md)
### [Классы хранения в C](c-storage-classes.md)
#### [Спецификаторы классов хранения для объявлений внешнего уровня](storage-class-specifiers-for-external-level-declarations.md)
#### [Спецификаторы классов хранения для объявлений внутреннего уровня](storage-class-specifiers-for-internal-level-declarations.md)
##### [Спецификатор классов хранения auto](auto-storage-class-specifier.md)
##### [Спецификатор класса хранения register](register-storage-class-specifier.md)
##### [Спецификатор класса хранения static](static-storage-class-specifier.md)
##### [Спецификатор класса хранения extern](extern-storage-class-specifier.md)
#### [Спецификаторы классов хранения с объявлениями функций](storage-class-specifiers-with-function-declarations.md)
### [Спецификаторы типов C](c-type-specifiers.md)
#### [Спецификаторы и эквиваленты типов данных](data-type-specifiers-and-equivalents.md)
### [Квалификаторы типов](type-qualifiers.md)
### [Деклараторы и объявления переменных](declarators-and-variable-declarations.md)
#### [Простые объявления переменных](simple-variable-declarations.md)
#### [Объявления перечислений C](c-enumeration-declarations.md)
#### [Объявления структур](structure-declarations.md)
##### [Битовые поля в C](c-bit-fields.md)
##### [Хранение и выравнивание структур](storage-and-alignment-of-structures.md)
#### [Объявления объединений](union-declarations.md)
##### [Хранение объединений](storage-of-unions.md)
#### [Объявления массивов](array-declarations.md)
##### [Хранение массивов](storage-of-arrays.md)
#### [Объявления указателей](pointer-declarations.md)
##### [Хранение адресов](storage-of-addresses.md)
#### [Основанные указатели (C)](based-pointers-c.md)
#### [Абстрактные деклараторы в C](c-abstract-declarators.md)
### [Интерпретация сложных деклараторов](interpreting-more-complex-declarators.md)
### [Инициализация](initialization.md)
#### [Инициализация скалярных типов](initializing-scalar-types.md)
#### [Инициализация агрегатных типов](initializing-aggregate-types.md)
#### [Инициализация строк](initializing-strings.md)
### [Хранение базовых типов](storage-of-basic-types.md)
#### [Тип char](type-char.md)
#### [Тип int](type-int.md)
#### [Целочисленные типы размеров C](c-sized-integer-types.md)
#### [Тип float](type-float.md)
#### [Тип double](type-double.md)
#### [Тип long double](type-long-double.md)
### [Неполные типы](incomplete-types.md)
### [Объявления typedef](typedef-declarations.md)
### [Расширенные атрибуты классов хранения в C](c-extended-storage-class-attributes.md)
#### [Импорт и экспорт DLL](dll-import-and-export.md)
#### [Naked (C)](naked-c.md)
#### [Локальное хранилище потока](thread-local-storage.md)
## [Выражения и присваивания](expressions-and-assignments.md)
### [Операнды и выражения](operands-and-expressions.md)
#### [Первичные выражения в C](c-primary-expressions.md)
##### [Идентификаторы в первичных выражениях](identifiers-in-primary-expressions.md)
##### [Константы в первичных выражениях](constants-in-primary-expressions.md)
##### [Строковые литералы в первичных выражениях](string-literals-in-primary-expressions.md)
##### [Выражения в скобках](expressions-in-parentheses.md)
#### [Выражения L-Value и R-Value](l-value-and-r-value-expressions.md)
#### [Постоянные выражения в C](c-constant-expressions.md)
#### [Вычисление выражений (C)](expression-evaluation-c.md)
##### [Побочные эффекты](side-effects.md)
##### [Точки следования C](c-sequence-points.md)
### [Операторы в C](c-operators.md)
#### [Приоритет и порядок оценки](precedence-and-order-of-evaluation.md)
#### [Обычные арифметические преобразования](usual-arithmetic-conversions.md)
#### [Постфиксные операторы](postfix-operators.md)
##### [Одномерные массивы](one-dimensional-arrays.md)
##### [Многомерные массивы (C)](multidimensional-arrays-c.md)
##### [Вызов функций (C)](function-call-c.md)
##### [Члены структур и объединений](structure-and-union-members.md)
##### [Постфиксные операторы увеличения и уменьшения в C](c-postfix-increment-and-decrement-operators.md)
#### [Унарные операторы C](c-unary-operators.md)
##### [Префиксные операторы увеличения и уменьшения](prefix-increment-and-decrement-operators.md)
##### [Операторы косвенного обращения и адреса операнда](indirection-and-address-of-operators.md)
##### [Унарные арифметические операторы](unary-arithmetic-operators.md)
##### [Оператор sizeof (C)](sizeof-operator-c.md)
#### [Операторы приведения](cast-operators.md)
#### [Операторы умножения в C](c-multiplicative-operators.md)
#### [Аддитивные операторы в C](c-additive-operators.md)
##### [Сложение (+)](addition-plus.md)
##### [Вычитание (-)](subtraction-minus.md)
##### [Использование операторов сложения](using-the-additive-operators.md)
##### [Расчеты с указателями](pointer-arithmetic.md)
#### [Операторы побитового сдвига](bitwise-shift-operators.md)
#### [Операторы отношения и равенства C](c-relational-and-equality-operators.md)
#### [Побитовые операторы в C](c-bitwise-operators.md)
#### [Логические операторы в C](c-logical-operators.md)
#### [Оператор Conditional-Expression](conditional-expression-operator.md)
#### [Операторы присваивания C](c-assignment-operators.md)
##### [Простое назначение (C)](simple-assignment-c.md)
##### [Составное назначение C](c-compound-assignment.md)
#### [Оператор последовательного вычисления](sequential-evaluation-operator.md)
### [Преобразования типов (C)](type-conversions-c.md)
#### [Преобразования назначений](assignment-conversions.md)
##### [Преобразования из целочисленных типов со знаком](conversions-from-signed-integral-types.md)
##### [Преобразования из целочисленных типов без знака](conversions-from-unsigned-integral-types.md)
##### [Преобразования типов с плавающей запятой](conversions-from-floating-point-types.md)
##### [Преобразования в типы указателей и из типов указателей](conversions-to-and-from-pointer-types.md)
##### [Преобразования из других типов](conversions-from-other-types.md)
#### [Преобразования приведений типов](type-cast-conversions.md)
#### [Преобразования вызова функции](function-call-conversions.md)
## [Операторы (C)](statements-c.md)
### [Общие сведения об операторах в C](overview-of-c-statements.md)
### [Оператор break (C)](break-statement-c.md)
### [Составной оператор (C)](compound-statement-c.md)
### [Оператор continue (C)](continue-statement-c.md)
### [Выражение do-while (C)](do-while-statement-c.md)
### [Оператор выражений (C)](expression-statement-c.md)
### [Оператор for (C)](for-statement-c.md)
### [Оператор goto и помеченные операторы (C)](goto-and-labeled-statements-c.md)
### [Оператор if (C)](if-statement-c.md)
### [Оператор NULL (C)](null-statement-c.md)
### [Оператор return (C)](return-statement-c.md)
### [Оператор switch (C)](switch-statement-c.md)
### [Оператор try-except (C)](try-except-statement-c.md)
### [Оператор try-finally (C)](try-finally-statement-c.md)
### [Оператор while (C)](while-statement-c.md)
## [Функции (C)](functions-c.md)
### [Общие сведения о функциях](overview-of-functions.md)
#### [Устаревшие формы объявлений и определений функций](obsolete-forms-of-function-declarations-and-definitions.md)
### [Определения функций в C](c-function-definitions.md)
#### [Атрибуты функций](function-attributes.md)
##### [Указание соглашений о вызовах](specifying-calling-conventions.md)
##### [Встраиваемые функции](inline-functions.md)
##### [Встроенный ассемблер (C)](inline-assembler-c.md)
#### [Функции импорта и экспорта DLL](dll-import-and-export-functions.md)
##### [Определения и объявления (C)](definitions-and-declarations-c.md)
##### [Определение встроенных функций C с помощью dllexport и dllimport](defining-inline-c-functions-with-dllexport-and-dllimport.md)
##### [Правила и ограничения dllimport-dllexport](rules-and-limitations-for-dllimport-dllexport.md)
#### [Функции naked](naked-functions.md)
##### [Правила и ограничения при использовании функций Naked](rules-and-limitations-for-using-naked-functions.md)
##### [Вопросы, связанные с написанием кода пролога и эпилога](considerations-when-writing-prolog-epilog-code.md)
#### [Класс хранения](storage-class.md)
#### [Тип возвращаемого значения](return-type.md)
#### [Параметры](parameters.md)
#### [Тело функции](function-body.md)
### [Прототипы функции](function-prototypes.md)
### [Вызовы функций](function-calls.md)
#### [Аргументы](arguments.md)
#### [Вызовы с переменным количеством аргументов](calls-with-a-variable-number-of-arguments.md)
#### [Рекурсивные функции](recursive-functions.md)
## [Краткие сведения о синтаксисе языка C](c-language-syntax-summary.md)
### [Определения и соглашения](definitions-and-conventions.md)
### [Лексическая грамматика](lexical-grammar.md)
#### [Общие сведения о токенах](summary-of-tokens.md)
#### [Общие сведения о ключевых словах](summary-of-keywords.md)
#### [Общие сведения об идентификаторах](summary-of-identifiers.md)
#### [Общие сведения о константах](summary-of-constants.md)
#### [Общие сведения о строковых литералах](summary-of-string-literals.md)
#### [Операторы (C)](operators-c.md)
#### [Символы пунктуации](punctuators.md)
### [Грамматика структуры фразы](phrase-structure-grammar.md)
#### [Общие сведения о выражениях](summary-of-expressions.md)
#### [Общие сведения об объявлениях](summary-of-declarations.md)
#### [Общие сведения об операторах](summary-of-statements.md)
#### [Внешние определения](external-definitions.md)
## [Поведение, определяемое реализацией](implementation-defined-behavior.md)
### [Трансляция. Диагностика](translation-diagnostics.md)
### [Среда](environment.md)
#### [Аргументы функции main](arguments-to-main.md)
#### [Интерактивные устройства](interactive-devices.md)
### [Поведение идентификаторов](behavior-of-identifiers.md)
#### [Значимые символы без внешней компоновки](significant-characters-without-external-linkage.md)
#### [Значимые символы с внешней компоновкой](significant-characters-with-external-linkage.md)
#### [Верхний и нижний регистр](uppercase-and-lowercase.md)
### [Символы](characters.md)
#### [Набор символов ASCII](ascii-character-set.md)
#### [Многобайтовая кодировка](multibyte-characters.md)
#### [Число битов на символ](bits-per-character.md)
#### [Символ Sets1](character-sets1.md)
#### [Непредставимые символьные константы](unrepresented-character-constants.md)
#### [Расширенные символы](wide-characters.md)
#### [Преобразование многобайтовых символов](converting-multibyte-characters.md)
#### [Диапазон значений char](range-of-char-values.md)
### [Целые числа](integers.md)
#### [Диапазон целочисленных значений](range-of-integer-values.md)
#### [Понижение уровня целых чисел](demotion-of-integers.md)
#### [Поразрядные операции со знаком](signed-bitwise-operations.md)
#### [Остатки от деления](remainders.md)
#### [Сдвиги вправо](right-shifts.md)
### [Вычисления с плавающей запятой](floating-point-math.md)
#### [Значения](values.md)
#### [Приведение целочисленных значений к значениям с плавающей запятой](casting-integers-to-floating-point-values.md)
#### [Усечение значений с плавающей запятой](truncation-of-floating-point-values.md)
### [Массивы и указатели](arrays-and-pointers.md)
#### [Максимальный размер массива](largest-array-size.md)
#### [Вычитание указателей](pointer-subtraction.md)
### [Регистры. Доступность регистров](registers-availability-of-registers.md)
### [Структуры, объединения, перечисления и битовые поля](structures-unions-enumerations-and-bit-fields.md)
#### [Неправильный доступ к объединению](improper-access-to-a-union.md)
#### [Заполнение и выравнивание членов структуры](padding-and-alignment-of-structure-members.md)
#### [Знак битовых полей](sign-of-bit-fields.md)
#### [Хранение битовых полей](storage-of-bit-fields.md)
#### [Тип enum](enum-type.md)
### [Квалификаторы. Доступ к временным объектам](qualifiers-access-to-volatile-objects.md)
### [Деклараторы. Максимальное количество](declarators-maximum-number.md)
### [Операторы. Пределы операторов выбора](statements-limits-on-switch-statements.md)
### [Директивы предварительной обработки](preprocessing-directives.md)
#### [Символьные константы и условное включение](character-constants-and-conditional-inclusion.md)
#### [Включение имен файлов в скобках](including-bracketed-filenames.md)
#### [Включение имен файлов в кавычках](including-quoted-filenames.md)
#### [Последовательности символов](character-sequences.md)
#### [Директивы pragma](pragmas.md)
#### [Дата и время по умолчанию](default-date-and-time.md)
### [Функции библиотеки](library-functions.md)
#### [Макрос NULL](null-macro.md)
#### [Диагностика, напечатанная функцией assert](diagnostic-printed-by-the-assert-function.md)
#### [Тестирование символов](character-testing.md)
#### [Ошибки домена](domain-errors.md)
#### [Потеря точности значений с плавающей запятой](underflow-of-floating-point-values.md)
#### [Функция fmod](fmod-function.md)
#### [Функция signal (C)](signal-function-c.md)
#### [Сигналы по умолчанию](default-signals.md)
#### [Завершающие символы новой строки](terminating-newline-characters.md)
#### [Пустые строки](blank-lines.md)
#### [Символы NULL](null-characters.md)
#### [Позиция файла в режиме добавления](file-position-in-append-mode.md)
#### [Усечение текстовых файлов](truncation-of-text-files.md)
#### [Буферизация файла](file-buffering.md)
#### [Файлы нулевой длины](zero-length-files.md)
#### [Имена файлов](filenames.md)
#### [Ограничения доступа к файлам](file-access-limits.md)
#### [Удаление открытых файлов](deleting-open-files.md)
#### [Переименование с использованием существующего имени](renaming-with-a-name-that-exists.md)
#### [Чтение значений указателя](reading-pointer-values.md)
#### [Диапазоны чтения](reading-ranges.md)
#### [Ошибки положения файла](file-position-errors.md)
#### [Сообщения, созданные функцией perror](messages-generated-by-the-perror-function.md)
#### [Выделение обнуленной памяти](allocating-zero-memory.md)
#### [Функция abort (C)](abort-function-c.md)
#### [Функция atexit (C)](atexit-function-c.md)
#### [Имена сред](environment-names.md)
#### [Функция system](system-function.md)
#### [Функция strerror](strerror-function.md)
#### [Часовой пояс](time-zone.md)
#### [Функция clock (C)](clock-function-c.md)