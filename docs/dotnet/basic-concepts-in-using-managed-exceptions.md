---
title: Основные принципы использования управляемых исключений
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: 4eeec5db00ceca5429f4a3a270e1b249a8955249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230926"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Основные принципы использования управляемых исключений

В этом разделе обсуждается обработка исключений в управляемых приложениях. Это значит, что приложение компилируется с параметром компилятора **/CLR** .

## <a name="in-this-topic"></a>В этом разделе

- [Создание исключений в/CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [Блоки try/catch для расширений среды CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Примечания

При компиляции с параметром **/CLR** можно ОБРАБАТЫВАТЬ исключения CLR, а также стандартный <xref:System.Exception> класс предоставляет множество полезных методов для обработки исключений CLR и рекомендуется в качестве базового класса для определяемых пользователем классов исключений.

Перехват типов исключений, производных от интерфейса, не поддерживается в **параметре/CLR**. Кроме того, среда CLR не позволяет перехватывать исключения переполнения стека; исключение переполнения стека приведет к прерыванию процесса.

Дополнительные сведения о различиях в обработке исключений в управляемых и неуправляемых приложениях см. в [разделе различия в поведении обработки исключений в управляемые расширения для C++](../dotnet/differences-in-exception-handling-behavior-under-clr.md).

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>Создание исключений в/CLR

Выражение выдачи C++ расширяется для создания обработчика типа CLR. В следующем примере создается пользовательский тип исключения, а затем создается экземпляр этого типа:

```cpp
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

Тип значения должен быть упакован перед вызываемым:

```cpp
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Блоки try/catch для расширений среды CLR

Одну и ту же **`try`** / **`catch`** структуру блока можно использовать для перехвата исключений CLR и машинного кода:

```cpp
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>Выходные данные

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>Порядок очистки для объектов C++

Очистка происходит для всех объектов C++ с деструкторами, которые могут находиться в стеке времени выполнения между функцией выдачи и функцией обработки. Поскольку типы CLR выделяются в куче, для них не применяется очистка.

Порядок событий для выданного исключения выглядит следующим образом:

1. Среда выполнения проходит по стеку для поиска соответствующего предложения catch или в случае SEH, исключение Filter для SEH, для перехвата исключения. Предложения catch сначала ищутся в лексической последовательности, а затем динамически вниз по стеку вызовов.

1. После обнаружения правильного обработчика стек будет развернут до этой точки. Для каждого вызова функции в стеке его локальные объекты деструктурны, и выполняются блоки __finally, от наиболее вложенных внешних.

1. После того как стек будет развернут, выполняется предложение catch.

### <a name="catching-unmanaged-types"></a>Перехват неуправляемых типов

При вызове типа неуправляемого объекта он упаковывается с исключением типа <xref:System.Runtime.InteropServices.SEHException> . При поиске соответствующего **`catch`** предложения есть две возможности.

- При обнаружении собственного типа C++ исключение разносится в оболочку и сравнивается с обнаруженным типом. Это сравнение позволяет перехватывать собственный тип C++ обычным способом.

- Однако если **`catch`** сначала проверяется предложение типа **SEHException** или какого-либо из его базовых классов, это исключение будет перехвачено предложением. Поэтому перед любыми предложениями catch типов CLR следует размещать все предложения catch, которые перехватывают собственные типы C++.

Обратите внимание на следующее:

```
catch(Object^)
```

и

```
catch(...)
```

будет перехватывать любой вызванный тип, включая исключения SEH.

Если неуправляемый тип перехвачен блоком catch (Object ^), то создаваемый объект не будет уничтожен.

При вызове или перехвате неуправляемых исключений рекомендуется использовать параметр компилятора [/EHsc](../build/reference/eh-exception-handling-model.md) вместо параметра **/EHs** или **/EHa**.

## <a name="see-also"></a>См. также статью

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)
