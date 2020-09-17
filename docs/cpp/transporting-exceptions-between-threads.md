---
title: Перенос исключений между потоками
ms.date: 05/07/2019
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
ms.openlocfilehash: c3ba61062421462dea8f4280575be9f00ac3931a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561366"
---
# <a name="transporting-exceptions-between-threads"></a>Перенос исключений между потоками

Компилятор Microsoft C++ (КОМПИЛЯТОРОМ MSVC) поддерживает *транспортное исключение* из одного потока в другой. Передача исключений позволяет перехватывать исключение в одном потоке и затем обеспечить видимость того, что исключение возникло в другом потоке. Например, эту возможность можно использовать для создания многопоточного приложения, где первостепенный поток обрабатывает все исключения, создаваемые его второстепенными потоками. Передача исключений в основном полезна для разработчиков, создающих системы или библиотеки параллельного программирования. Чтобы реализовать перенос исключений, КОМПИЛЯТОРОМ MSVC предоставляет тип [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) и функции [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)и [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) .

## <a name="syntax"></a>Синтаксис

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>Параметры

*Unspecified*\
Неуказанный внутренний класс, используемый для реализации типа `exception_ptr`.

*ш*\
Объект `exception_ptr`, который ссылается на исключение.

*&*\
Класс, представляющий исключение.

*&*\
Экземпляр класса `E` параметров.

## <a name="return-value"></a>Возвращаемое значение

Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение, выполняемое в данный момент. Если никакое исключение не выполняется, функция возвращает объект `exception_ptr`, не связанный ни с одним исключением.

`make_exception_ptr`Функция возвращает `exception_ptr` объект, который ссылается на исключение, заданное параметром *e* .

## <a name="remarks"></a>Примечания

### <a name="scenario"></a>Сценарий

Предположим, что требуется создать приложение, которое может масштабироваться для выполнения переменного объема работы. Для достижения этой цели создается многопоточное приложение, где исходный основной поток создает столько второстепенных потоков, сколько необходимо для выполнения задачи. Второстепенные потоки помогают первичному потоку распоряжаться ресурсами, распределять нагрузку и повышать пропускную способность. Благодаря распределению работы многопоточное приложение работает быстрее, чем однопоточное.

Однако если второстепенный поток вызывает исключение, необходимо обеспечить его обработку основным потоком. Это обусловлено тем, что требуется обеспечить обработку исключений приложением единообразным, унифицированным способом независимо от количества второстепенных потоков.

### <a name="solution"></a>Решение

Для выполнения указанного выше сценария стандарт C++ поддерживает передачу исключений между потоками. Если дополнительный поток создает исключение, это исключение станет *текущим исключением*. По аналогии с реальным миром, текущее исключение говорится *в полете*. Текущее исключение находится в полете со времени создания до возвращения результата обработчиком исключений, перехватывающим его.

Вторичный поток может перехватить текущее исключение в **`catch`** блоке, а затем вызвать `current_exception` функцию для хранения исключения в `exception_ptr` объекте. Объект `exception_ptr` должен быть доступным для второстепенного и первичного потоков. Например, объект `exception_ptr` может быть глобальной переменной, доступ к который регулируется мьютексом. Термин *транспорт — исключение* означает, что исключение в одном потоке можно преобразовать в форму, к которой может получить доступ другой поток.

Далее основной поток вызывает функцию `rethrow_exception`, которая извлекает исключение из объекта `exception_ptr` и затем вызывает его. При вызове исключения оно становится текущим исключением в основном потоке. Это означает, что создается видимость того, что исключение возникает в основном потоке.

Наконец, основной поток может перехватить текущее исключение в **`catch`** блоке, а затем обработать его или создать обработчик исключений более высокого уровня. Также основной поток может проигнорировать исключение и позволить процессу завершиться.

Большинству приложений не требуется передавать исключения между потоками. Однако эта возможность полезна в системе параллельных вычислений, поскольку система может распределить работу между второстепенными потоками, процессорами или ядрами. В среде параллельных вычислений один выделенный поток может обрабатывать все исключения из второстепенных потоков и может предоставлять единообразную модель обработки исключений любому приложению.

Дополнительные сведения о предложении Комитета по стандартам C++ можно получить, найдя в Интернете документ с номером N2179 «Поддержка передачи исключений между потоками в языке».

### <a name="exception-handling-models-and-compiler-options"></a>Модели обработки исключений и параметры компилятора

Модель обработки исключений приложения определяет, возможен ли в нем перехват и передача исключения. Visual C++ поддерживает 3 модели, которые могут обрабатывать исключения C++, исключения структурированной обработки (SEH) и исключения среды CLR. Используйте параметры компилятора [/EH](../build/reference/eh-exception-handling-model.md) и [/CLR](../build/reference/clr-common-language-runtime-compilation.md) , чтобы указать модель обработки исключений приложения.

Только следующее сочетание параметров компилятора и операторов программирования может передавать исключение. Другие сочетания либо не могут перехватывать исключения, либо могут перехватывать, но не могут передавать исключения.

- Параметр компилятора **/EHa** и **`catch`** оператор может передавать исключения SEH и C++.

- Параметры компилятора **/EHa**, **/EHs**и **/EHsc** , а также **`catch`** инструкции могут передавать исключения C++.

- Параметр компилятора **/CLR** и **`catch`** инструкция могут передавать исключения C++. Параметр компилятора **/CLR** подразумевает спецификацию параметра **/EHa** . Обратите внимание, что компилятор не поддерживает передачу управляемых исключений. Это обусловлено тем, что управляемые исключения, которые являются производными от [класса System. Exception](../standard-library/exception-class.md), уже являются объектами, которые можно перемещать между потоками с помощью средств общей среды выполнения лангуанже.

   > [!IMPORTANT]
   > Рекомендуется указывать параметр компилятора **/EHsc** и перехватывать только исключения C++. Вы предоставляете себе угрозу безопасности, если используете параметр компилятора **/EHa** или **/CLR** и **`catch`** оператор с многоточием *Exception* ( `catch(...)` ). Возможно, вы планируете использовать **`catch`** инструкцию для записи нескольких конкретных исключений. Однако оператор `catch(...)` перехватывает все исключения C++ и SEH, включая непредвиденные, которые должны приводить к сбою. Если непредвиденное исключение игнорируется или обрабатывается неверно, вредоносный код может использовать эту возможность, чтобы подорвать безопасность программы.

## <a name="usage"></a>Использование

В следующих разделах описывается передача исключений с помощью `exception_ptr` типа, а также `current_exception` `rethrow_exception` функций, и `make_exception_ptr` .

## <a name="exception_ptr-type"></a>Тип exception_ptr

Используйте объект `exception_ptr` для ссылки на текущее исключение или экземпляр указанного пользователем исключения. В реализации Майкрософт исключение представлено структурой [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record). Каждый объект `exception_ptr` содержит поле ссылки на исключение, указывающее на копию структуры `EXCEPTION_RECORD`, представляющую исключение.

При объявлении переменной `exception_ptr` эта переменная не связана ни с одним исключением. То есть в поле ссылки на исключение находится значение NULL. Такой объект `exception_ptr` называется *exception_ptr null*.

Используйте функцию `current_exception` или `make_exception_ptr` для назначения исключения объекту `exception_ptr`. При назначении исключения переменной `exception_ptr` поле ссылки на исключение переменной указывает на копию исключения. При нехватке памяти для копирования исключения поле ссылки на исключение указывает на копию исключения [std::bad_alloc](../standard-library/bad-alloc-class.md). Если `current_exception` функция или `make_exception_ptr` не может скопировать исключение по какой бы то ни было другим причинам, функция вызывает функцию [Terminate](../c-runtime-library/reference/terminate-crt.md) для выхода из текущего процесса.

Несмотря на свое имя, объект `exception_ptr` не является указателем. Он не подчиняется семантике указателя и не может использоваться с операторами доступа к членам указателя ( `->` ) или косвенного обращения ( `*` ). Объект `exception_ptr` не имеет открытых данных-членов и функций-членов.

### <a name="comparisons"></a>Сравнение

Можно использовать операторы равенства (`==`) и неравенства (`!=`) для сравнения двух объектов `exception_ptr`. Эти операторы не сравнивают бинарное значение (битовый шаблон) структур `EXCEPTION_RECORD`, которые представляют исключения. Вместо этого операторы сравнивают адреса в поле ссылки на исключение объектов `exception_ptr`. Поэтому `exception_ptr` со значением null и значение NULL при сравнении считаются равными.

## <a name="current_exception-function"></a>Функция current_exception

Вызовите `current_exception` функцию в **`catch`** блоке. Если исключение находится в полете и **`catch`** блок может перехватить исключение, `current_exception` функция возвращает `exception_ptr` объект, который ссылается на исключение. В противном случае функция возвращает объект `exception_ptr` со значением null.

### <a name="details"></a>Сведения

`current_exception`Функция захватывает исключение, которое находится в полете, независимо от того, **`catch`** указывает ли инструкция [объявление исключения](../cpp/try-throw-and-catch-statements-cpp.md) .

Деструктор текущего исключения вызывается в конце **`catch`** блока, если исключение не будет создано заново. Но даже при вызове функции `current_exception` в деструкторе эта функция возвращает объект `exception_ptr`, который ссылается на текущее исключение.

Последующие вызовы функции `current_exception` возвращают объекты `exception_ptr`, которые ссылаются на различные копии текущего исключения. Соответственно, при сравнении объекты не признаются равными, поскольку они ссылаются на различные копии, даже если эти копии имеют одинаковые бинарные значения.

### <a name="seh-exceptions"></a>Исключения SEH

При использовании параметра компилятора **/EHa** можно перехватывать исключение SEH в **`catch`** блоке C++. Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение SEH. И `rethrow_exception` функция создает исключение SEH, если вы вызываете его с помощью `exception_ptr` объекта сетранспортед в качестве аргумента.

`current_exception`Функция возвращает значение NULL `exception_ptr` при вызове в **`__finally`** обработчике завершения SEH, **`__except`** обработчике исключений или **`__except`** критерии фильтра.

Переданное исключение не поддерживает вложенные исключения. Вложенное исключение возникает, если во время обработки одного исключения возникает другое исключение. Если производится перехват вложенного исключения, данные-член `EXCEPTION_RECORD.ExceptionRecord` указывает на цепочку структур `EXCEPTION_RECORD`, описывающих соответствующие исключения. Функция `current_exception` не поддерживает вложенные исключения, поскольку она возвращает объект `exception_ptr`, данные-член `ExceptionRecord` которого обнулен.

Если производится перехват исключения SEH, необходимо обеспечить распределение памяти, на которую ссылается любой указатель в массиве данных-членов `EXCEPTION_RECORD.ExceptionInformation`. Необходимо гарантировать, что эта память действительна в течение времени существования соответствующего объекта `exception_ptr` и что эта память освобождается, когда объект `exception_ptr` удаляется.

Можно использовать возможности преобразователя структурированного исключения (SE) вместе с возможностью передачи исключений. Если исключение SEH преобразуется в исключение C++, функция `current_exception` возвращает `exception_ptr`, который ссылается на преобразованное исключение вместо исходного исключения SEH. Затем функция `rethrow_exception` вызывает преобразованное , а не исходное исключение. Дополнительные сведения о функциях переводчика SE см. в разделе [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>Функция rethrow_exception

После сохранения перехваченного исключения в объект `exception_ptr` основной поток может обработать этот объект. В основном потоке вызовите функцию `rethrow_exception`, указав объект `exception_ptr` в качестве аргумента. Функция `rethrow_exception` извлекает исключение из объекта `exception_ptr` и затем вызывает это исключение в контексте основного потока. Если параметр *p* `rethrow_exception` функции имеет значение NULL `exception_ptr` , функция создает исключение [std::bad_exception](../standard-library/bad-exception-class.md).

Извлеченное исключение теперь является текущим исключением в основном потоке, и его можно обработать как любое другое исключение. Если вы перехватите исключение, его можно немедленно обработать или использовать **`throw`** оператор, чтобы отправить его в обработчик исключений более высокого уровня. В противном случае можно ничего не делать и позволить системному обработчику исключений по умолчанию завершить процесс.

## <a name="make_exception_ptr-function"></a>Функция make_exception_ptr

Функция `make_exception_ptr` принимает экземпляр класса в качестве аргумента и затем возвращает `exception_ptr`, который ссылается на этот экземпляр. Обычно объект [класс исключений](../standard-library/exception-class.md) указывается в качестве аргумента функции `make_exception_ptr`, однако аргументом может быть любой объект класса.

Вызов `make_exception_ptr` функции эквивалентен созданию исключения C++, его перехвату в **`catch`** блоке и последующему вызову `current_exception` функции для возврата `exception_ptr` объекта, который ссылается на исключение. Реализация Майкрософт для функции `make_exception_ptr` является более эффективной, чем создание и последующий перехват исключения.

Приложение обычно не требует функции `make_exception_ptr`, и мы не рекомендуем использовать ее.

## <a name="example"></a>Пример

В следующем примере стандартное исключение C++ и пользовательское исключение C++ передаются из одного потока в другой.

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>Требования

**Заголовок:**\<exception>

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (компиляция среды выполнения)](../build/reference/clr-common-language-runtime-compilation.md)
