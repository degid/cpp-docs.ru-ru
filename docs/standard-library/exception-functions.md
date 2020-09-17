---
title: Функции &lt;exception&gt;
ms.date: 11/04/2016
f1_keywords:
- exception/std::current_exception
- exception/std::get_terminate
- exception/std::get_unexpected
- exception/std::make_exception_ptr
- exception/std::rethrow_exception
- exception/std::set_terminate
- exception/std::set_unexpected
- exception/std::terminate
- exception/std::uncaught_exception
- exception/std::unexpected
ms.assetid: c09ac569-5e35-4fe8-872d-ca5810274dd7
helpviewer_keywords:
- std::current_exception [C++]
- std::get_terminate [C++]
- std::get_unexpected [C++]
- std::make_exception_ptr [C++]
- std::rethrow_exception [C++]
- std::set_terminate [C++]
- std::set_unexpected [C++]
- std::terminate [C++]
- std::uncaught_exception [C++]
- std::unexpected [C++]
ms.openlocfilehash: 849f3c8406c43b0efc2d34837e00fee6ff64e52a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193787"
---
# <a name="ltexceptiongt-functions"></a>Функции &lt;exception&gt;

## <a name="current_exception"></a><a name="current_exception"></a>current_exception

Получает интеллектуальный указатель на текущее исключение.

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), указывающий на текущее исключение.

### <a name="remarks"></a>Примечания

Вызовите функцию `current_exception` в блоке catch. Если исключение находится в полете и блок перехвата может перехватить это исключение, функция `current_exception` возвращает объект `exception_ptr`, который ссылается на это исключение. В противном случае функция возвращает объект `exception_ptr` со значением null.

`current_exception`Функция захватывает исключение, которое находится в полете, независимо от того, **`catch`** указывает ли инструкция [объявление исключения](../cpp/try-throw-and-catch-statements-cpp.md) .

Деструктор текущего исключения вызывается в конце **`catch`** блока, если исключение не будет создано заново. Но даже при вызове функции `current_exception` в деструкторе эта функция возвращает объект `exception_ptr`, который ссылается на текущее исключение.

Последующие вызовы функции `current_exception` возвращают объекты `exception_ptr`, которые ссылаются на различные копии текущего исключения. Соответственно, при сравнении объекты не признаются равными, поскольку они ссылаются на различные копии, даже если эти копии имеют одинаковые бинарные значения.

## <a name="make_exception_ptr"></a><a name="make_exception_ptr"></a>make_exception_ptr

Создает объект [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), содержащий копию исключения.

```cpp
template <class E>
    exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>Параметры

*Варианта*\
Класс с исключением, подлежащим копированию. Обычно объект [класс исключений](../standard-library/exception-class.md) указывается в качестве аргумента функции `make_exception_ptr`, однако аргументом может быть любой объект класса.

### <a name="return-value"></a>Возвращаемое значение

Объект [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) , указывающий на копию текущего исключения, *за исключением*.

### <a name="remarks"></a>Примечания

Вызов функции `make_exception_ptr` аналогичен созданию исключения C++, его перехвату в блоке catch и последующему вызову функции [current_exception](../standard-library/exception-functions.md#current_exception) для возвращения объекта `exception_ptr`, ссылающегося на это исключение. Реализация Майкрософт для функции `make_exception_ptr` является более эффективной, чем создание и последующий перехват исключения.

Приложение обычно не требует функции `make_exception_ptr`, и мы не рекомендуем использовать ее.

## <a name="rethrow_exception"></a><a name="rethrow_exception"></a>rethrow_exception

Создает исключение, переданное в качестве параметра.

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>Параметры

*Ш*\
Перехваченное исключение, подлежащее повторному вызову. Если параметр *P* имеет [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)null, функция создает исключение [std:: bad_exception](../standard-library/bad-exception-class.md).

### <a name="remarks"></a>Примечания

После сохранения перехваченного исключения в объект `exception_ptr` основной поток может обработать этот объект. В основном потоке вызовите функцию `rethrow_exception`, указав объект `exception_ptr` в качестве аргумента. Функция `rethrow_exception` извлекает исключение из объекта `exception_ptr` и затем вызывает это исключение в контексте основного потока.

## <a name="get_terminate"></a><a name="get_terminate"></a>get_terminate

Получает текущую функцию `terminate_handler`.

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a><a name="set_terminate"></a>set_terminate

Создает новый `terminate_handler`, подлежащий вызову при завершении программы.

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>Параметры

*фнев*\
Функция, которая должна вызываться при завершении.

### <a name="return-value"></a>Возвращаемое значение

Адрес предыдущей функция, используемой для вызова при завершении.

### <a name="remarks"></a>Примечания

Функция устанавливает новый [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler) в качестве функции * *фнев*. Таким словами, *фнев* не должен быть пустым указателем. Функция возвращает адрес предыдущего обработчика завершения.

### <a name="example"></a>Пример

```cpp
// exception_set_terminate.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void termfunction()
{
    cout << "My terminate function called." << endl;
    abort();
}

int main()
{
    terminate_handler oldHandler = set_terminate(termfunction);

    // Throwing an unhandled exception would also terminate the program
    // or we could explicitly call terminate();

    //throw bad_alloc();
    terminate();
}
```

## <a name="get_unexpected"></a><a name="get_unexpected"></a>get_unexpected

Получает текущую функцию `unexpected_handler`.

```cpp
unexpected_handler get_unexpected();
```

## <a name="rethrow_if_nested"></a><a name="rethrow_if_nested"></a>rethrow_if_nested

```cpp
template <class E>
    void rethrow_if_nested(const E& e);
```

### <a name="remarks"></a>Примечания

Если не является типом класса полиморфизма или `nested_exception` недоступен или является неоднозначным, то никакого влияния не происходит. В противном случае выполняет динамическое приведение.

## <a name="set_unexpected"></a><a name="set_unexpected"></a>set_unexpected

Создает новый `unexpected_handler`, подлежащий вызову при обнаружении неожиданного исключения.

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>Параметры

*фнев*\
Функция, предназначенная для вызова при обнаружении непредвиденного исключения.

### <a name="return-value"></a>Возвращаемое значение

Адрес предыдущего обработчика `unexpected_handler`.

### <a name="remarks"></a>Примечания

*фнев* не должен быть пустым указателем.

Стандарт C++ требует вызова `unexpected` в том случае, когда функция создает исключение, которого нет в ее списке throw. Текущая реализация это не поддерживает. В следующем примере `unexpected` вызывается напрямую, который затем вызывает `unexpected_handler`.

### <a name="example"></a>Пример

```cpp
// exception_set_unexpected.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void uefunction()
{
    cout << "My unhandled exception function called." << endl;
    terminate(); // this is what unexpected() calls by default
}

int main()
{
    unexpected_handler oldHandler = set_unexpected(uefunction);

    unexpected(); // library function to force calling the
                  // current unexpected handler
}
```

## <a name="terminate"></a><a name="terminate"></a>заканчива

Вызывает обработчик завершения.

```cpp
void terminate();
```

### <a name="remarks"></a>Примечания

Функция вызывает обработчик завершения, функцию типа **`void`** . Если `terminate` программа вызывается непосредственно программой, обработчик завершения является последним установленным путем вызова [set_terminate](../standard-library/exception-functions.md#set_terminate). Если `terminate` вызывается по какой-либо из нескольких других причин во время вычисления выражения Throw, обработчик завершения является, что он действует сразу после вычисления выражения Throw.

Обработчик завершения не может вернуть значение в вызывающий его объект. При запуске программы обработчик завершения — это функция, которая вызывает `abort` .

### <a name="example"></a>Пример

См. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) в качестве примера использования `terminate`.

## <a name="throw_with_nested"></a><a name="throw_with_nested"></a>throw_with_nested

```cpp
template <class T> [[noreturn]]
    void throw_with_nested(T&& t);
```

### <a name="remarks"></a>Примечания

Создает исключение с вложенными исключениями.

## <a name="uncaught_exception"></a><a name="uncaught_exception"></a>uncaught_exception

Возвращает, **`true`** только если в настоящее время обрабатывается исключение.

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** после завершения вычисления выражения Throw и до завершения инициализации объявления исключения в обработчике сопоставления или [непредвиденного](../standard-library/exception-functions.md#unexpected) вызова в результате выражения Throw. В частности, `uncaught_exception` будет возвращать **`true`** при вызове из деструктора, который вызывается во время очистки исключения. На устройствах `uncaught_exception` поддерживается только на платформе Windows CE 5.00 и более поздних версий, включая Windows Mobile 2005.

### <a name="example"></a>Пример

```cpp
// exception_uncaught_exception.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>
#include <string>

class Test
{
public:
   Test( std::string msg ) : m_msg( msg )
   {
      std::cout << "In Test::Test(\"" << m_msg << "\")" << std::endl;
   }
   ~Test( )
   {
      std::cout << "In Test::~Test(\"" << m_msg << "\")" << std::endl
         << "        std::uncaught_exception( ) = "
         << std::uncaught_exception( )
         << std::endl;
   }
private:
    std::string m_msg;
};

// uncaught_exception will be true in the destructor
// for the object created inside the try block because
// the destructor is being called as part of the unwind.

int main( void )
   {
      Test t1( "outside try block" );
      try
      {
         Test t2( "inside try block" );
         throw 1;
      }
      catch (...) {
   }
}
```

```Output
In Test::Test("outside try block")
In Test::Test("inside try block")
In Test::~Test("inside try block")
        std::uncaught_exception( ) = 1
In Test::~Test("outside try block")
        std::uncaught_exception( ) = 0
```

## <a name="unexpected"></a><a name="unexpected"></a>известно

Вызывает обработчик неожиданных исключений.

```cpp
void unexpected();
```

### <a name="remarks"></a>Примечания

Стандарт C++ требует вызова `unexpected` в том случае, когда функция создает исключение, которого нет в ее списке throw. Текущая реализация это не поддерживает. В данном примере `unexpected` вызывается напрямую, что вызывает обработчик неожиданных исключений.

Функция вызывает непредвиденный обработчик, функцию типа **`void`** . Если `unexpected` вызывается непосредственно программой, в качестве обработчика неожиданных исключений используется последний обработчик, установленный вызовом метода [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

Обработчик неожиданных исключений не может вернуть значение в вызывающий его объект. Он может завершить выполнение следующим образом:

- Создание объекта типа, представленного в спецификации исключений, или объекта любого типа, если обработчик неожиданных исключений вызывается непосредственно программой.

- Создание объекта типа [bad_exception](../standard-library/bad-exception-class.md).

- Вызов [terminate](../standard-library/exception-functions.md#terminate)метода Terminate `abort` или `exit` .

При запуске программы обработчик неожиданных исключений — это функция, которая вызывает функцию [terminate](../standard-library/exception-functions.md#terminate).

### <a name="example"></a>Пример

См. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) в качестве примера использования `unexpected`.
