---
title: '&lt;iterator&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 08e2051db70ee1891c7b60860c7ea0b423855be5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841926"
---
# <a name="ltiteratorgt"></a>&lt;iterator&gt;

Определяет примитивы итератора, предопределенные итераторы и итераторы потока, а также несколько поддерживаемых шаблонов. Предопределенные итераторы включают адаптеры вставки и обратные адаптеры. Существует три класса адаптеров итераторов вставки: передний, задний и общий. Они предоставляют семантику вставки вместо семантики переписи, которую предоставляют итераторы функции-члена контейнера.

## <a name="requirements"></a>Требования

**Заголовок:**\<iterator>

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Итераторы представляют собой обобщение указателей, которое абстрагируется от их требований способом, предоставляющим программе C++ возможность применять однородные принципы обработки к разным структурам данных. Итераторы используются в качестве посредников между контейнерами и универсальными алгоритмами. Алгоритмы применяются не к определенным типам данных, а к диапазону, указанному типом итератора. К любой структуре данных, удовлетворяющей требованиям итератора, может применяться алгоритм. Существует пять типов, или категорий итераторов, каждая из которых обладает отдельным набором требований и соответствующими функциями:

- Вывод: перемещение вперед, возможно сохранение, но не извлечение значений, обеспеченное структурами данных ostream и inserter.

- Ввод: перемещение вперед, возможно извлечение, но не сохранение значений, обеспеченное элементом istream.

- Прямой: перемещение вперед, возможно сохранение и извлечение значений.

- Двунаправленный: перемещение вперед и назад, возможно сохранение и извлечение значений, предоставленных структурами данных list, set, multiset, map и multimap.

- Произвольный доступ: доступ к элементам предоставляется в любом порядке, возможно сохранение и извлечение значений, предоставленных структурами данных vector, deque, string и array.

Итераторы с более значительными требованиями и, как следствие, с более широкими возможностями доступа к элементам, можно использовать вместо итераторов с менее значительными требованиями. Например, при вызове прямого итератора вместо него можно использовать итератор произвольного доступа.

Visual Studio добавляет расширения к итераторам стандартной библиотеки C++, чтобы обеспечить поддержку различных ситуаций режима отладки для проверенных и непроверенных итераторов. Дополнительные сведения см. в разделе [Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md).

## <a name="members"></a>Элементы

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[предварительного](../standard-library/iterator-functions.md#advance)|Увеличивает итератор на указанное количество позиций.|
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|Создает итератор, может вставлять элементы с обратной стороны указанного контейнера.|
|[начале](../standard-library/iterator-functions.md#begin)|Извлекает итератор для первого элемента в указанном контейнере.|
|[cbegin](../standard-library/iterator-functions.md#cbegin)|Извлекает постоянный итератор для первого элемента в указанном контейнере.|
|[cend](../standard-library/iterator-functions.md#cend)|Извлекает постоянный итератор для элемента, следующего за последним элементом в указанном контейнере.|
|[crbegin](../standard-library/iterator-functions.md#crbegin)||
|[crend](../standard-library/iterator-functions.md#crend)||
|[data](../standard-library/iterator-functions.md#data)||
|[distance](../standard-library/iterator-functions.md#distance)|Указывает количество приращений между позициями, которые адресуют два итератора.|
|[конце](../standard-library/iterator-functions.md#end)|Извлекает итератор для элемента, следующего за последним элементом в указанном контейнере.|
|[empty](../standard-library/iterator-functions.md#empty)||
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|Создает итератор, может вставлять элементы с передней стороны указанного контейнера.|
|[фрагментов](../standard-library/iterator-functions.md#inserter)|Адаптер итератора, добавляющий в контейнер новый элемент в указанной позиции.|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|Создает [checked_array_iterator](../standard-library/checked-array-iterator-class.md), который может использоваться другими алгоритмами. **Примечание.** Эта функция — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|Возвращает итератор перемещения, содержащий предоставленный итератор в качестве сохраненного базового итератора.|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|Создает [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md), который может использоваться другими алгоритмами. **Примечание.** Эта функция — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.|
|[далее](../standard-library/iterator-functions.md#next)|Выполняет итерацию заданное число раз и возвращает новую позицию итератора.|
|[prev](../standard-library/iterator-functions.md#prev)|Выполняет обратную итерацию заданное число раз и возвращает новую позицию итератора.|
|[rbegin](../standard-library/iterator-functions.md#rbegin)||
|[rend](../standard-library/iterator-functions.md#rend)||
|[size](../standard-library/iterator-functions.md#size)||

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/iterator-operators.md#op_neq)|Проверяет объект итератора в левой части оператора на неравенство объекту итератора в правой части.|
|[operator==](../standard-library/iterator-operators.md#op_eq_eq)|Проверяет объект итератора в левой части оператора на равенство объекту итератора в правой части.|
|[operator<](../standard-library/iterator-operators.md#op_lt)|Определяет, верно ли, что объект итератора в левой части оператора меньше объекта итератора в правой части.|
|[operator\<=](../standard-library/iterator-operators.md#op_gt_eq)|Определяет, верно ли, что объект итератора в левой части оператора меньше или равен объекту итератора в правой части.|
|[operator>](../standard-library/iterator-operators.md#op_gt)|Определяет, верно ли, что объект итератора в левой части оператора больше объекта итератора в правой части.|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|Определяет, верно ли, что объект итератора в левой части оператора больше или равен объекту итератора в правой части.|
|[operator+](../standard-library/iterator-operators.md#op_add)|Добавление смещения к итератору и возврат нового итератора `reverse_iterator`, который обращается к вставленному элементу в новой позиции смещения.|
|[operator-](../standard-library/iterator-operators.md#operator-)|Вычитает один итератор из другого и возвращает разницу.|

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|Шаблон класса описывает объект итератора вывода. Он вставляет элементы в контейнер типа `Container` , к которому он обращается через защищенный объект, который `pointer` хранится под названием Container.|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей двунаправленный итератор.|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|Класс, который обращается к массиву при помощи проверенного итератора произвольного доступа. **Примечание.** Этот класс — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей прямой итератор.|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|Шаблон класса описывает объект итератора вывода. Он вставляет элементы в контейнер типа `Container` , к которому он обращается через защищенный объект, который `pointer` хранится под названием Container.|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей итератор ввода.|
|[insert_iterator](../standard-library/insert-iterator-class.md)|Шаблон класса описывает объект итератора вывода. Он вставляет элементы в контейнер типа `Container` , к которому он обращается через защищенный объект, который `pointer` хранится под названием Container. Он также хранит защищенный `iterator` объект класса с `Container::iterator` именем `iter` .|
|[istream_iterator](../standard-library/istream-iterator-class.md)|Шаблон класса описывает объект итератора ввода. Он извлекает объекты класса `Ty` из входного потока, к которому он обращается через сохраненный объект, типа pointer `basic_istream` \<**Elem**, **Tr**> .|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|Шаблон класса описывает объект итератора ввода. Он вставляет элементы класса `Elem` в буфер потока вывода, к которому он обращается через хранящийся в нем объект типа `pointer` `basic_streambuf` \<**Elem**, **Tr**> .|
|[итераци](../standard-library/iterator-struct.md)|Шаблон класса используется в качестве базового типа для всех итераторов.|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|Вспомогательный класс шаблона, предоставляющий критические типы, связанные с разными типами итераторов, на которые они могут ссылаться аналогичным образом.|
|[move_iterator](../standard-library/move-iterator-class.md)|Объект `move_iterator` содержит итератор произвольного доступа типа `RandomIterator`. Его поведение аналогично поведению итератора произвольного доступа, кроме случаев отмены ссылки. Результат `operator*` неявно приводится к `value_type&&:`, чтобы обеспечить `rvalue reference`.|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|Шаблон класса описывает объект итератора вывода. Он вставляет объекты класса `Type` в выходной поток, к которому он обращается через хранящийся в нем объект, с типом `pointer` `basic_ostream` \<**Elem**, **Tr**> .|
|[Класс ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)|Шаблон класса описывает объект итератора вывода. Он вставляет элементы класса `Elem` в буфер потока вывода, к которому он обращается через хранящийся в нем объект типа pointer `basic_streambuf` \<**Elem**, **Tr**> .|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей итератор вывода.|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей итератор произвольного доступа.|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|Шаблон класса описывает объект, который ведет себя как итератор произвольного доступа, только в обратную.|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|Класс, который обращается к массиву при помощи непроверенного итератора произвольного доступа. **Примечание.** Этот класс — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
