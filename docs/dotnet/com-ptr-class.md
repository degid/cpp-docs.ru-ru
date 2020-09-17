---
title: Класс com::ptr
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: 9cb0ad23450d06bb314b0e2d6fa1d01784d633e2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214910"
---
# <a name="comptr-class"></a>Класс com::ptr

Оболочка для COM-объекта, который может использоваться как член класса CLR.  Программа-оболочка также автоматизирует управление жизненным циклом объекта COM, освобождая все принадлежащие ему ссылки на объект при вызове его деструктора. Аналог [класса CComPtr](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Синтаксис

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Параметры

*_interface_type*<br/>
COM-интерфейс.

## <a name="remarks"></a>Примечания

`com::ptr`Также можно использовать в качестве локальной переменной функции для упрощения различных задач COM и автоматизации управления жизненным циклом.

`com::ptr`Нельзя использовать напрямую в качестве параметра функции; вместо этого используйте [оператор отслеживаемой ссылки](../extensions/tracking-reference-operator-cpp-component-extensions.md) или [оператор объекта (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) .

`com::ptr`Невозможно напрямую вернуть из функции; используйте вместо этого маркер.

## <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  Вызов открытых методов класса приводит к вызову вложенного `IXMLDOMDocument` объекта.  Образец создает экземпляр XML-документа, заполняет его простым XML-кодом и упрощает обход узлов в проанализированном дереве документа для вывода XML на консоль.

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|---------|-----------|
|[PTR::p TR](#ptr)|Создает `com::ptr` оболочку для создания оболочки для COM-объекта.|
|[ptr::~ptr](#tilde-ptr)|Разструктура `com::ptr` .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|---------|-----------|
|[ptr::Attach](#attach)|Присоединяет COM-объект к `com::ptr` .|
|[ptr::CreateInstance](#createInstance)|Создает экземпляр COM-объекта в `com::ptr` .|
|[ptr::Detach](#detach)|Предоставляет владение COM-объектом, возвращая указатель на объект.|
|[ptr::GetInterface](#getInterface)|Создает экземпляр COM-объекта в `com::ptr` .|
|[ptr::QueryInterface](#queryInterface)|Запрашивает принадлежащий объекту COM-объект для интерфейса и присоединяет результат к другому `com::ptr` .|
|[ptr::Release](#release)|Освобождает все принадлежащие ссылки на COM-объект.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|---------|-----------|
|[Оператор PTR::operator-&gt;](#operator-arrow)|Оператор доступа к членам, используемый для вызова методов в принадлежащем COM-объекте.|
|[Оператор PTR::operator=](#operator-assign)|Присоединяет COM-объект к `com::ptr` .|
|[Оператор PTR::operator &nbsp; bool](#operator-bool)|Оператор для использования `com::ptr` в условном выражении.|
|[ptr::operator!](#operator-logical-not)|Оператор, чтобы определить, является ли принадлежащий объект COM недопустимым.|

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\com\ptr.h>

**Пространство имен** мсклр:: com

## <a name="ptrptr"></a><a name="ptr"></a>PTR::p TR

Возвращает указатель на принадлежащий объекту COM.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель интерфейса COM.

### <a name="remarks"></a>Примечания

Конструктор без аргументов присваивается **`nullptr`** базовому обработчику объекта. Будущие вызовы метода `com::ptr` проверяют внутренний объект и автоматически завершаются сбоем, пока объект не будет создан или присоединен.

Конструктор с одним аргументом добавляет ссылку на COM-объект, но не освобождает ссылку на вызывающий объект, поэтому вызывающий объект должен вызвать `Release` для COM-объекта, чтобы действительно обеспечить управление. При `com::ptr` вызове деструктор автоматически освобождает свои ссылки на COM-объект.

Передача `NULL` в этот конструктор аналогична вызову версии без аргумента.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . Он демонстрирует использование обеих версий конструктора.

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrptr"></a><a name="tilde-ptr"></a>PTR:: ~ PTR

Разструктура `com::ptr` .

```cpp
~ptr();
```

### <a name="remarks"></a>Примечания

При уничтожении `com::ptr` освобождает все ссылки, которыми владеет объект COM. При условии, что отсутствуют другие ссылки на COM-объект, COM-объект будет удален и освобождена память.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  В `main` функции `XmlDocument` будут вызываться деструкторы двух объектов, когда они выходят за пределы области **`try`** блока, в результате чего `com::ptr` вызывается базовый деструктор, освобождая все принадлежащие ему ссылки на COM-объект.

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrattach"></a><a name="attach"></a>PTR:: Attach

Присоединяет COM-объект к `com::ptr` .

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель интерфейса COM для присоединения.

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылкой на COM-объект, `Attach` вызывает исключение <xref:System.InvalidOperationException> .

### <a name="remarks"></a>Примечания

Вызов ссылается на `Attach` COM-объект, но не освобождает ссылку вызывающего объекта.

Передача `NULL` в `Attach` результаты не выполняется никаких действий.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . `ReplaceDocument`Функция-член сначала вызывает метод для `Release` любого ранее принадлежащего объекта, а затем вызывает метод `Attach` для присоединения нового объекта документа.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>указатель:: CreateInstance

Создает экземпляр COM-объекта в `com::ptr` .

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>Параметры

*ID*<br/>
Строка `ProgID`.

*паутер*<br/>
Указатель на интерфейс IUnknown объекта Aggregate (управляющий IUnknown). Если `pouter` не указан, `NULL` используется.

*cls_context*<br/>
Контекст, в котором будет выполняться код, управляющий только что созданным объектом. Значения берутся из `CLSCTX` перечисления. Если параметр `cls_context` не указан, используется значение CLSCTX_ALL.

*рклсид*<br/>
`CLSID`связан с данными и кодом, который будет использоваться для создания объекта.

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылкой на COM-объект, `CreateInstance` вызывает исключение <xref:System.InvalidOperationException> .

Эта функция вызывает `CoCreateInstance` и использует <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> для преобразования любой ошибки `HRESULT` в соответствующее исключение.

### <a name="remarks"></a>Примечания

`CreateInstance`использует `CoCreateInstance` для создания нового экземпляра указанного объекта, идентифицируемого из ProgID или CLSID. `com::ptr`Ссылается на только что созданный объект и автоматически освобождает все принадлежащие ему ссылки при уничтожении.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . Конструкторы классов используют две различные формы `CreateInstance` для создания объекта документа либо из ProgID, либо из идентификатора CLSID, а также клскткс.

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="ptrdetach"></a><a name="detach"></a>PTR::D етач

Предоставляет владение COM-объектом, возвращая указатель на объект.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на COM-объект.

Если объект не владеет, возвращается значение NULL.

### <a name="exceptions"></a>Исключения

Внутренне `QueryInterface` метод вызывается для принадлежащего объекта COM, и любая ошибка `HRESULT` преобразуется в исключение с помощью <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Примечания

`Detach`сначала добавляет ссылку на COM-объект от имени вызывающего объекта, а затем освобождает все ссылки, принадлежащие объекту `com::ptr` .  Вызывающая сторона должна в конечном итоге освободить возвращенный объект, чтобы уничтожить его.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  `DetachDocument`Функция-член вызывает метод `Detach` , чтобы предоставить право собственности на объект COM и вернуть указатель на вызывающий объект.

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="ptrgetinterface"></a><a name="getInterface"></a>Интерфейс PTR::-interface

Возвращает указатель на принадлежащий объекту COM.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на принадлежащий объекту COM.

### <a name="exceptions"></a>Исключения

Внутренне `QueryInterface` метод вызывается для принадлежащего объекта COM, и любая ошибка `HRESULT` преобразуется в исключение с помощью <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Примечания

`com::ptr`Компонент добавляет ссылку на COM-объект от имени вызывающего объекта, а также сохраняет собственную ссылку на COM-объект. Вызывающая сторона должна в конечном итоге освободить ссылку на возвращенный объект или никогда не будет уничтожена.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . `GetDocument`Функция-член использует `GetInterface` для возвращения указателя на COM-объект.

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>PTR:: QueryInterface

Запрашивает принадлежащий объекту COM-объект для интерфейса и присоединяет результат к другому `com::ptr` .

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Объект `com::ptr` , который получит интерфейс.

### <a name="exceptions"></a>Исключения

Внутренне `QueryInterface` метод вызывается для принадлежащего объекта COM, и любая ошибка `HRESULT` преобразуется в исключение с помощью <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Примечания

Этот метод используется для создания оболочки COM для другого интерфейса COM-объекта, принадлежащего текущей обертке. Этот метод вызывает `QueryInterface` через собственный COM-объект для запроса указателя на конкретный интерфейс COM-объекта и присоединяет возвращенный указатель интерфейса к переданному объекту `com::ptr` .

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . `WriteTopLevelNode`Функция-член использует `QueryInterface` для заполнения локальной `com::ptr` функции, `IXMLDOMNode` а затем передает `com::ptr` (по отслеживаемой ссылке) закрытой член, который записывает свойства имени узла и текста в консоль.

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="ptrrelease"></a><a name="release"></a>PTR:: Release

Освобождает все принадлежащие ссылки на COM-объект.

```cpp
void Release();
```

### <a name="remarks"></a>Примечания

Вызов этой функции освобождает все ссылки, принадлежащие объекту COM, и задает для внутреннего дескриптора COM-объекта значение **`nullptr`** .  Если других ссылок на COM-объект не существует, он будет уничтожен.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  `ReplaceDocument`Функция члена использует `Release` для освобождения любого объекта документа перед присоединением нового документа.

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>Оператор PTR::operator-&gt;

Оператор доступа к членам, используемый для вызова методов в принадлежащем COM-объекте.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `smart_com_ptr` для COM-объекта.

### <a name="exceptions"></a>Исключения

Внутренне `QueryInterface` метод вызывается для принадлежащего объекта COM, и любая ошибка `HRESULT` преобразуется в исключение с помощью <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Примечания

Этот оператор позволяет вызывать методы принадлежащего объекта COM. Он возвращает временный объект `smart_com_ptr` , который автоматически обрабатывает свои собственные `AddRef` и `Release` .

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . `WriteDocument`Функция использует `operator->` для вызова `get_firstChild` члена объекта Document.

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptroperator"></a><a name="operator-assign"></a>Оператор PTR::operator=

Присоединяет COM-объект к `com::ptr` .

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель интерфейса COM для присоединения.

### <a name="return-value"></a>Возвращаемое значение

Отслеживаемая ссылка на `com::ptr` .

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылкой на COM-объект, `operator=` вызывает исключение <xref:System.InvalidOperationException> .

### <a name="remarks"></a>Примечания

Назначение COM-объекта объекту `com::ptr` ссылается на COM-объект, но не освобождает ссылку на него вызывающего объекта.

Этот оператор действует так же, как и `Attach` .

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  `ReplaceDocument`Функция-член сначала вызывает метод для `Release` любого ранее принадлежащего объекта, а затем использует `operator=` для присоединения нового объекта документа.

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>Оператор PTR::operator bool

Оператор для использования `com::ptr` в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект, принадлежащий объекту COM, является допустимым; **`false`** в противном случае — значение.

### <a name="remarks"></a>Примечания

Объект, принадлежащий объекту COM, является допустимым, если нет **`nullptr`** .

Этот оператор преобразует в `_detail_class::_safe_bool` , который является более безопасным, чем, **`bool`** так как он не может быть преобразован в целочисленный тип.

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` . `CreateInstance`Функция-член использует `operator bool` после создания нового объекта Document, чтобы определить его допустимость и запись в консоль, если это так.

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="ptroperator"></a><a name="operator-logical-not"></a>Оператор PTR::operator!

Оператор, чтобы определить, является ли принадлежащий объект COM недопустимым.

```cpp
bool operator!();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если принадлежащего COM-объекта является недопустимым; **`false`** в противном случае — значение.

### <a name="remarks"></a>Примечания

Объект, принадлежащий объекту COM, является допустимым, если нет **`nullptr`** .

### <a name="example"></a>Пример

В этом примере реализуется класс CLR, который использует `com::ptr` для создания оболочки для объекта закрытого члена `IXMLDOMDocument` .  `CreateInstance`Функция-член использует, `operator!` чтобы определить, является ли объект документа уже владельцем, и создает новый экземпляр, только если объект является недопустимым.

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
