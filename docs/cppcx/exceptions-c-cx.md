---
title: Исключения (C++/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: 7b4475cfa92aa952dd5a2996508d9343255b7ed2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231017"
---
# <a name="exceptions-ccx"></a>Исключения (C++/CX)

Обработка ошибок в C++/CX основана на исключениях. На самом базовом уровне среда выполнения Windows компоненты сообщают об ошибках как значения HRESULT. В C++/CX эти значения преобразуются в строго типизированные исключения, которые содержат значение HRESULT и строковое описание, доступ к которым можно получить программным способом.  Исключения реализуются в виде **`ref class`** , производном от `Platform::Exception` .  В пространстве имен `Platform` определены отдельные классы исключений для наиболее часто встречающихся значений HRESULT. Все остальные значения передаются через класс `Platform::COMException` . Все классы исключений имеют [Exception::HResult](platform-exception-class.md#hresult) , которое можно использовать для получения исходного значения HRESULT. Также можно изучить сведения стека вызовов для пользовательского кода в отладчике, который может помочь выявить исходный источник исключения, даже если он был создан в коде, написанном на языке, отличном от C++.

## <a name="exceptions"></a>Исключения

В программе на C++ можно создавать и перехватывать исключения, поступающие из среда выполнения Windowsной операции, исключения, производного от `std::exception` , или определяемого пользователем типа. Исключение среда выполнения Windows необходимо вызывать только в том случае, если оно будет пересекать границу интерфейса ABI, например, когда код, перехватывающий исключение, написан на JavaScript. Когда исключение C++, не относящееся к среда выполнения Windows, достигает границы ABI, исключение преобразуется в `Platform::FailureException` исключение, представляющее E_FAIL HRESULT. Дополнительные сведения об интерфейсе ABI см. в разделе [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Можно объявить [Platform:: Exception](platform-exception-class.md) , используя один из двух конструкторов, принимающих параметр HRESULT, или параметр HRESULT и параметр [Platform:: String](platform-string-class.md)^, который может передаваться по интерфейсу ABI в любое среда выполнения Windowsое приложение, которое его обрабатывает. Либо можно объявить исключение, воспользовавшись одним из двух перегрузок [метода Exception::CreateException](platform-exception-class.md#createexception) , которые могут принимать параметр HRESULT или параметры HRESULT и `Platform::String^` .

## <a name="standard-exceptions"></a>Стандартные исключения

C++/CX поддерживает набор стандартных исключений, которые представляют типичные ошибки HRESULT. Каждое стандартное исключение наследуется от класса [Platform::COMException](platform-comexception-class.md), который, в свою очередь, наследуется от `Platform::Exception`. Если вы вызываете исключение через границы интерфейса ABI, оно должно быть одним из стандартных исключений.

Делать собственные типы исключений производными от класса `Platform::Exception`не допускается. Чтобы создать пользовательское исключение, используйте определяемое пользователем значение HRESULT для создания объекта `COMException` .

В следующей таблице перечислены стандартные исключения.

|Имя|Значение HRESULT|Описание:|
|----------|------------------------|-----------------|
|COMException|*Определяемое пользователем значение hresult*|Возникает при возвращении неизвестного значения HRESULT после вызова метода COM.|
|AccessDeniedException|E \_ ACCESSDENIED|Возникает при запрете доступа к ресурсу или функции.|
|ChangedStateException|\_измененное \_ состояние|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|
|ClassNotRegisteredException|РЕГДБ \_ E \_ класснотрег|Возникает, если COM-класс не зарегистрирован.|
|DisconnectedException|RPC \_ E \_ отключен|Возникает, если объект отключен от своих клиентов.|
|FailureException|\_Ошибка E|Возникает, если операция завершается неудачно.|
|InvalidArgumentException|E \_ INVALIDARG|Вызывается, если один из передаваемых методу аргументов является недопустимым.|
|InvalidCastException|\_интерфейс E|Возникает, если тип не удается привести к другому типу.|
|NotImplementedException|E \_ нотимпл|Возникает, если метод интерфейса не реализован в классе.|
|NullReferenceException|\_указатель E|Возникает при попытке разыменовать ссылку на объект NULL.|
|ObjectDisposedException|RO \_ е \_ закрыто|Вызывается при выполнении операции над ликвидированным объектом.|
|OperationCanceledException|\_прервать|Возникает при отмене операции.|
|OutOfBoundsException|\_границы E|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|
|OutOfMemoryException|E \_ OUTOFMEMORY|Возникает, если недостаточно памяти для выполнения операции.|
|WrongThreadException|RPC \_ E \_ неправильный \_ поток|Вызывается, если поток выполняет вызов посредством указателя на интерфейс для прокси-объекта, который не принадлежит к подразделению потока.|

## <a name="hresult-and-message-properties"></a>Свойства HResult и Message

Все исключения имеют свойство [HResult](platform-comexception-class.md#hresult) и свойство [Message](platform-comexception-class.md#message) . Свойство [Exception::HResult](platform-exception-class.md#hresult) получает базовое числовое значение HRESULT соответствующего исключения. Свойство [Exception::Message](platform-exception-class.md#message) получает предоставленную системой строку с описанием исключения. В Windows 8 сообщение доступно только в отладчике и доступно только для чтения. Это означает, что его невозможно изменить после повторного создания исключения. В Windows 8.1 к строке сообщения можно получить доступ программным образом и предоставить новое сообщение, если необходимо заново создать исключение. В отладчике доступны более подробные данные стеков вызовов, включая данные об асинхронных вызовах методов.

### <a name="examples"></a>Примеры

В этом примере показано, как вызвать исключение среда выполнения Windows для синхронных операций:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

В следующем пример показано, как перехватить исключение.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Чтобы перехватить исключения, возникающие во время асинхронной операции, используйте класс Task и добавьте продолжение обработки ошибок. Продолжение обработки ошибок маршалирует исключения, вызванные в других потоках, обратно вызывающему потоку, что позволяет обрабатывать все возможные исключения в одной структурной единице кода. Дополнительные сведения см. [в разделе Асинхронное программирование на C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>Событие UnhandledErrorDetected

В Windows 8.1 можно подписываться на статическое событие [Windows:: ApplicationModel:: Core:: CoreApplication:: UnhandledErrorDetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected) , которое предоставляет доступ к необработанным ошибкам, которые будут выдавать процесс. Независимо от того, где возникла ошибка, она достигнет этого обработчика в виде объекта [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) , который передается с аргументами события. При вызове метода `Propagate` для объекта он создает исключение `Platform::*Exception` типа, соответствующего коду ошибки. В блоках catch можно сохранить пользовательское состояние при необходимости, а затем либо разрешить завершение процесса путем вызова **`throw`** , либо выполнить какие-либо действия для возвращения программы в известное состояние. В следующем примере демонстрируется использование основного подхода:

В App. XAML.h:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

В App. XAML. cpp:

```cpp
// Subscribe to the event, for example in the app class constructor:
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);

// Event handler implementation:
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)
{
    auto err = e->UnhandledError;

    if (!err->Handled) //Propagate has not been called on it yet.
{
    try
    {
        err->Propagate();
    }
    // Catch any specific exception types if you know how to handle them
    catch (AccessDeniedException^ ex)
    {
        // TODO: Log error and either take action to recover
        // or else re-throw exception to continue fail-fast
    }
}
```

### <a name="remarks"></a>Примечания

C++/CX не использует **`finally`** предложение.

## <a name="see-also"></a>См. также статью

[Справочник по языку C++/CX](visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](namespaces-reference-c-cx.md)
