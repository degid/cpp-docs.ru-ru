---
title: Атрибутивное программирование. Часто задаваемые вопросы
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: 70fbcc47884214fb998eb63ebfe50e445dbe95b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843148"
---
# <a name="attribute-programming-faq"></a>Атрибутивное программирование. Часто задаваемые вопросы

В этом разделе содержатся ответы на следующие часто задаваемые вопросы.

- [Что такое HRESULT?](#vcconattributeprogrammmingfaqanchor1)

- [Когда нужно указывать имя параметра для атрибута?](#vcconattributeprogrammmingfaqanchor2)

- [Можно ли использовать комментарии в блоке атрибутов?](#vcconattributeprogrammmingfaqanchor3)

- [Как атрибуты взаимодействуют с наследованием?](#vcconattributeprogrammmingfaqanchor4)

- [Как можно использовать атрибуты в проекте ATL без атрибутов?](#vcconattributeprogrammmingfaqanchor5)

- [Как можно использовать idl-файл в проекте с атрибутами?](#vcconattributeprogrammmingfaqanchor6)

- [Можно ли изменить код, который вставляется с помощью атрибута?](#vcconattributeprogrammmingfaqanchor7)

- [Как можно переадресовать объявление интерфейса с атрибутами?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Можно ли использовать атрибуты класса, производного от класса, который также использует атрибуты?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

## <a name="what-is-an-hresult"></a><a name="vcconattributeprogrammmingfaqanchor1"></a> Что такое HRESULT?

HRESULT — это простой тип данных, который часто используется в качестве возвращаемого значения атрибутами и ATL в целом. В следующей таблице описаны различные значения. Дополнительные значения содержатся в файле заголовка Winerror.h.

|Имя|Описание|Значение|
|----------|-----------------|-----------|
|S_OK|Операция выполнена успешно|0x00000000|
|E_UNEXPECTED|Непредвиденный сбой|0x8000FFFF|
|E_NOTIMPL|Не реализовано|0x80004001|
|E_OUTOFMEMORY|Не удалось выделить требуемую память|0x8007000E|
|E_INVALIDARG|Один или несколько аргументов недопустимы|0x80070057|
|E_NOINTERFACE|Такой интерфейс не поддерживается|0x80004002|
|E_POINTER|Недопустимый указатель|0x80004003|
|E_HANDLE|Недопустимый Handle|0x80070006|
|E_ABORT|Операция прервана|0x80004004|
|E_FAIL|Неопределенный сбой|0x80004005|
|E_ACCESSDENIED|Общая ошибка отказа в доступе|0x80070005|

## <a name="when-do-i-have-to-specify-the-parameter-name-for-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor2"></a> Когда нужно указывать имя параметра для атрибута?

В большинстве случаев, если атрибут имеет единственный параметр, этот параметр называется. Это имя не требуется при вставке атрибута в код. Например, следующее использование [статистического](aggregatable.md) атрибута:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

точно такой же, как:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Однако следующие атрибуты имеют одиночные безымянные параметры:

:::row:::
   :::column span="":::
      [`call_as`](call-as.md)\
      [`case`](case-cpp.md)\
      [`cpp_quote`](cpp-quote.md)\
      [`default`](default-cpp.md)\
      [`defaultvalue`](defaultvalue.md)\
      [`defaultvtable`](defaultvtable.md)\
      [`emitidl`](emitidl.md)\
      [`entry`](entry.md)\
      [`first_is`](first-is.md)
   :::column-end:::
   :::column span="":::
      [`helpcontext`](helpcontext.md)\
      [`helpfile`](helpfile.md)\
      [`helpstring`](helpstring.md)\
      [`helpstringcontext`](helpstringcontext.md)\
      [`helpstringdll`](helpstringdll.md)\
      [`id`](id.md)\
      [`iid_is`](iid-is.md)\
      [`import`](import.md)
   :::column-end:::
   :::column span="":::
      [`importlib`](importlib.md)\
      [`include`](include-cpp.md)\
      [`includelib`](includelib-cpp.md)\
      [`last_is`](last-is.md)\
      [`length_is`](length-is.md)\
      [`max_is`](max-is.md)\
      [`no_injected_text`](no-injected-text.md)\
      [`pointer_default`](pointer-default.md)
   :::column-end:::
   :::column span="":::
      [`pragma`](pragma.md)\
      [`restricted`](restricted.md)\
      [`size_is`](size-is.md)\
      [`source`](source-cpp.md)\
      [`switch_is`](switch-is.md)\
      [`switch_type`](switch-type.md)\
      [`transmit_as`](transmit-as.md)\
      [`wire_marshal`](wire-marshal.md)
   :::column-end:::
:::row-end:::

## <a name="can-i-use-comments-in-an-attribute-block"></a><a name="vcconattributeprogrammmingfaqanchor3"></a> Можно ли использовать комментарии в блоке атрибутов?

В блоке атрибутов можно использовать как однострочные, так и многострочные комментарии. Однако нельзя использовать любой из стилей комментариев в круглых скобках, содержащих параметры атрибута.

Допустимы следующие действия:

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

Запрещены следующие действия:

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

## <a name="how-do-attributes-interact-with-inheritance"></a><a name="vcconattributeprogrammmingfaqanchor4"></a> Как атрибуты взаимодействуют с наследованием?

Классы с атрибутами и без атрибутов можно наследовать от других классов, которые сами по себе могут быть атрибутами. Результат наследования от класса с атрибутом является таким же, как производный от этого класса после преобразования его кода поставщиком атрибутов. Атрибуты не передаются в производные классы через наследование C++. Поставщик атрибутов преобразует код только в окружении его атрибутов.

## <a name="how-can-i-use-attributes-in-a-nonattributed-atl-project"></a><a name="vcconattributeprogrammmingfaqanchor5"></a> Как можно использовать атрибуты в проекте ATL без атрибутов?

У вас может быть проект ATL без атрибута, имеющий IDL-файл, и вы можете начать добавлять объекты с атрибутами. В этом случае для предоставления кода используйте **Мастер добавления классов** .

## <a name="how-can-i-use-an-idl-file-in-an-attributed-project"></a><a name="vcconattributeprogrammmingfaqanchor6"></a> Как можно использовать idl-файл в проекте с атрибутами?

Возможно, у вас есть IDL-файл, который вы хотите использовать в проекте с атрибутами ATL. В этом случае следует использовать атрибут [импортидл](importidl.md) , скомпилировать IDL-файл в файл.h (см. [страницы свойств MIDL](../../build/reference/midl-property-pages.md) в диалоговом окне **страницы свойств** проекта), а затем включить h-файл в проект.

## <a name="can-i-modify-code-that-is-injected-by-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor7"></a> Можно ли изменить код, который вставляется с помощью атрибута?

Некоторые атрибуты вставляют код в проект. Введенный код можно просмотреть с помощью параметра компилятора [/FX](../../build/reference/fx-merge-injected-code.md) . Также можно скопировать код из вставленного файла и вставить его в исходный код. Это позволяет изменить поведение атрибута. Однако также может потребоваться изменить другие части кода.

Следующий пример является результатом копирования вставленного кода в файл исходного кода:

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
]

class ATL_NO_VTABLE CTestTest : public ITestTest,
// the following base classes support added injected code
public IConnectionPointContainerImpl<CTestTest>,
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>
{
public:
   CTestTest() {
   }
   // this line would be commented out from original file
   // __event __interface _ITestTestEvents;
   DECLARE_PROTECT_FINAL_CONSTRUCT()
   HRESULT FinalConstruct() {
      return S_OK;
   }

void FinalRelease() {}

public:
   CComBSTR m_value;
   STDMETHOD(DoTest)(BSTR str) {
      VARIANT_BOOL bCancel = FALSE;
      BeforeChange(str,&bCancel);
      if (bCancel) {
          return Error("Error : Someone don't want us to change the value");
      }

   m_value =str;
   return S_OK;
    }
// the following was copied in from the injected code.
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {
   HRESULT hr = S_OK;
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;
   VARIANT rgvars[2];
   Lock();
   IUnknown** pp = p->m_vec.begin();
   Unlock();
   while (pp < p->m_vec.end()) {
      if (*pp != NULL) {
         IDispatch* pDispatch = (IDispatch*) *pp;
         ::VariantInit(&rgvars[1]);
         rgvars[1].vt = VT_BSTR;
         V_BSTR(&rgvars[1])= (BSTR) i1;
         ::VariantInit(&rgvars[0]);
         rgvars[0].vt = (VT_BOOL | VT_BYREF);
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };
         VARIANT ret_val;
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);
         if (FAILED(hr))
            break;
      }
      pp++;
   }
   return hr;
}

BEGIN_CONNECTION_POINT_MAP(CTestTest)
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))
END_CONNECTION_POINT_MAP()
// end added code section

// _ITestCtrlEvents Methods
public:
};

int main() {}
```

## <a name="how-can-i-forward-declare-an-attributed-interface"></a><a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Как можно переадресовать объявление интерфейса с атрибутами?

Если вы собираетесь создать прямую объявление интерфейса с атрибутом, необходимо применить те же атрибуты к объявлению прямого объявления, которое применяется к фактическому объявлению интерфейса. Также необходимо применить атрибут [Export](export.md) к объявлению прямого объявления.

## <a name="can-i-use-attributes-on-a-class-derived-from-a-class-that-also-uses-attributes"></a><a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Можно ли использовать атрибуты класса, производного от класса, который также использует атрибуты?

Нет, использование атрибутов класса, производного от класса, который также использует атрибуты, не поддерживается.

## <a name="see-also"></a>См. также раздел

[Атрибуты C++ для модели COM и .NET](cpp-attributes-com-net.md)
