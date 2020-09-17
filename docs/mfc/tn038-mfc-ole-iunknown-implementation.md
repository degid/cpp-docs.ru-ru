---
title: 'TN038: реализация MFC-OLE IUnknown'
ms.date: 06/28/2018
helpviewer_keywords:
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
ms.openlocfilehash: 83166b32a20b8d24f748f85946caa01dbc76d4d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230445"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038. Реализация MFC/OLE IUnknown

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

В основе OLE 2 лежит модель COM OLE. Модель COM определяет стандарт взаимодействия совместно действующих объектов. Сюда входят сведения о самом «объекте», включая то, какие методы подготавливаются для отправки в объект. Модель COM также определяет базовый класс, от которого наследуются все COM-совместимые классы. Этот базовый класс является [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown). Несмотря на то, что интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) называется классом C++, com не относится ни к одному языку — он может быть реализован на языке C, Pascal или любом другом языке, поддерживающем двоичную структуру COM-объекта.

OLE относится ко всем классам, производным от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , как "интерфейсы". Это важное отличие, так как «интерфейс», такой как [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , переносится в него без реализации. Он просто определяет протокол, по которому взаимодействуют объекты, а не особенности этих реализаций. Это оправдано для системы, которая нацелена на максимальную гибкость. За реализацию поведения по умолчанию для программ MFC/C++ отвечает MFC.

Чтобы понять реализацию интерфейса [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) в MFC, необходимо сначала понять, что такое интерфейс. Упрощенная версия [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) определена ниже:

```cpp
class IUnknown
{
public:
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;
    virtual ULONG AddRef() = 0;
    virtual ULONG Release() = 0;
};
```

> [!NOTE]
> Некоторые необходимые сведения о соглашении о вызовах, например, **`__stdcall`** не указаны для этой иллюстрации.

Функции [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) контролируют управление памятью объекта. Модель COM использует схему подсчета ссылок для отслеживания объектов. Ссылка на объект никогда не указывается напрямую, как это происходит в C++. Вместо этого ссылка на COM-объекты всегда осуществляется через указатель. Чтобы освободить объект, когда владелец уже использует его, вызывается член [выпуска](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) объекта (в отличие от использования оператора DELETE, как это было сделано для традиционного объекта C++). Механизм подсчета ссылок позволяет управлять несколькими ссылками на один объект. Реализация [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) поддерживает счетчик ссылок на объект — объект не удаляется до тех пор, пока его число ссылок не достигнет нуля.

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) довольно просты на основе точки зрения реализации. Вот пример простой реализации:

```cpp
ULONG CMyObj::AddRef()
{
    return ++m_dwRef;
}

ULONG CMyObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}
```

Функция-член [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) немного интересна. Не очень интересно иметь объект, для которого только функции-члены имеют [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) — было бы неплохо дать объекту возможность делать больше возможностей, чем обеспечивает [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) . В этом случае [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) полезен. Он позволяет получать разный «интерфейс» на базе одного и того же объекта. Эти интерфейсы обычно являются производными от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) и добавляют дополнительные функции, добавляя новые функции элементов. COM-интерфейсы никогда не имеют объявляемых в интерфейсе переменных-членов, а все функции-члены объявлены как чисто виртуальные. например следующие.

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

Чтобы получить Ипринтинтерфаце, если у вас только [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), вызовите [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) с помощью метода `IID` `IPrintInterface` . `IID` представляет собой 128-разрядное число, которое однозначно определяет интерфейс. `IID` присутствует для каждого интерфейса, определенного вами или OLE. Если *Punk* является указателем на объект [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , код для получения ипринтинтерфаце из него может выглядеть так:

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

Это выглядит довольно просто, но как реализовать объект, поддерживающий интерфейс Ипринтинтерфаце и [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) в этом случае, так как ипринтинтерфаце является производным от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , реализуя ипринтинтерфаце, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) автоматически поддерживается. Пример:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

Реализации [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) будут точно такими же, как и ранее реализованные выше. `CPrintObj::QueryInterface`будет выглядеть примерно так:

```cpp
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = this;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}
```

Как видите, если распознается идентификатор интерфейса (IID), в объект возвращается указатель, в противном случае возникает ошибка. Также обратите внимание, что результатом успешного выполнения [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) является подразумеваемый [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref). Конечно же, необходимо также реализовать CEditObj::Print. Это просто, так как Ипринтинтерфаце был непосредственно унаследован от интерфейса [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) . Однако, если требуется поддержка двух разных интерфейсов, как производных от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), учитывайте следующее.

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

Хотя существует несколько разных способов реализации класса, поддерживающего как IEditInterface, так и IPrintInterface, включая использование множественного наследования C++, эта заметка будет посвящена использованию вложенных классов для реализации данной функциональности.

```cpp
class CEditPrintObj
{
public:
    CEditPrintObj();

    HRESULT QueryInterface(REFIID iid, void**);
    ULONG AddRef();
    ULONG Release();
    DWORD m_dwRef;

    class CPrintObj : public IPrintInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_printObj;

    class CEditObj : public IEditInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_editObj;
};
```

Полная реализация приведена ниже.

```cpp
CEditPrintObj::CEditPrintObj()
{
    m_editObj.m_pParent = this;
    m_printObj.m_pParent = this;
}

ULONG CEditPrintObj::AddRef()
{
    return ++m_dwRef;
}

CEditPrintObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}

HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = &m_printObj;
        AddRef();
        return NOERROR;
    }
    else if (iid == IID_IEditInterface)
    {
        *ppvObj = &m_editObj;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}

ULONG CEditPrintObj::CEditObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CEditObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CEditObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}

ULONG CEditPrintObj::CPrintObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CPrintObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}
```

Обратите внимание, что большая часть реализации [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) помещается в класс цедитпринтобж вместо дублирования кода в цедитпринтобж:: Цедитобж и цедитпринтобж:: кпринтобж. Это уменьшает объем кода и помогает избежать ошибок. Ключевым моментом здесь является то, что из интерфейса IUnknown можно вызвать [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) для получения любого интерфейса, который может поддерживаться объектом, и из каждого из этих интерфейсов можно сделать то же самое. Это означает, что все функции [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) , доступные в каждом интерфейсе, должны вести себя точно так же. Чтобы эти внедренные объекты вызвали реализацию во «внешнем объекте», используется обратный указатель (m_pParent). Указатель m_pParent инициализируется во время выполнения конструктора CEditPrintObj. Затем следует реализовать CEditPrintObj::CPrintObj::PrintObject, а также CEditPrintObj::CEditObj::EditObject. Потребовалось написать довольно большой объем кода для реализации одной функции — возможности изменения объекта. К счастью, интерфейсы крайне редко имеют только одну функцию-член (хотя такое и случается), и в этом случае EditObject и PrintObject обычно объединяются в единый интерфейс.

Такой простой сценарий требует слишком долгих пояснений и слишком большого объема кода. Классы MFC/OLE предоставляют более простую альтернативу. Реализация MFC использует методику, аналогичную использованию программы-оболочки для сообщений Windows с помощью схем сообщений. Этот механизм называется *сопоставлением интерфейсов* и рассматривается в следующем разделе.

## <a name="mfc-interface-maps"></a>Схемы интерфейсов MFC

MFC/OLE включает в себя реализацию «Схемы интерфейсов», аналогичную компонентам «Схемы сообщений» и «Схемы подготовки к отправке» MFC в рамках концепции и выполнения. Схемы интерфейсов MFC имеют следующие основные возможности.

- Стандартная реализация [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), встроенная в `CCmdTarget` класс.

- Обслуживание счетчика ссылок, измененных [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) и [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)

- Управляемая данными реализация [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))

Кроме того, схемы интерфейсов поддерживают следующие дополнительные возможности.

- Поддержка создания COM-объектов, допускающих статистическую обработку

- Поддержка использования агрегатных объектов в реализации COM-объекта

- Реализация является обрабатываемой и расширяемой

Дополнительные сведения о статистической обработке см. в разделе [Статистическая обработка](/windows/win32/com/aggregation) .

Поддержка схем интерфейсов MFC заключена в класс `CCmdTarget`. `CCmdTarget`"*содержит*" счетчик ссылок, а также все функции-члены, связанные с реализацией [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) (число ссылок для примера — in `CCmdTarget` ). Чтобы создать класс, поддерживающий модель COM OLE, создайте класс, производный от `CCmdTarget`, и используйте различные макросы и функции-члены `CCmdTarget` для реализации требуемых интерфейсов. Реализация MFC использует вложенные классы для определения каждой реализации интерфейса, что во многом похоже на приведенный выше пример. Эта задача упрощается благодаря стандартной реализации IUnknown, а также набору макросов, позволяющих исключить некоторые из повторяющихся частей кода.

## <a name="interface-map-basics"></a>Основы использования схем интерфейсов

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>Реализация класса с помощью схем интерфейсов MFC

1. Создайте класс, который явно или косвенно является от `CCmdTarget`.

2. Используйте функцию `DECLARE_INTERFACE_MAP` в определении производного класса.

3. Для каждого интерфейса, который вы хотите поддерживать, используйте макросы BEGIN_INTERFACE_PART и END_INTERFACE_PART в определении класса.

4. В файле реализации Используйте макросы BEGIN_INTERFACE_MAP и END_INTERFACE_MAP, чтобы определить карту интерфейса класса.

5. Для каждого поддерживаемого идентификатора IID используйте макрос INTERFACE_PART между макросами BEGIN_INTERFACE_MAP и END_INTERFACE_MAP, чтобы сопоставлять идентификатор IID с определенной «частью» класса.

6. Реализуйте каждый из вложенных классов, представляющих интерфейсы, которые вы поддерживаете.

7. Используйте макрос METHOD_PROLOGUE для доступа к родительскому `CCmdTarget` объекту, производному от.

8. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) могут делегировать `CCmdTarget` реализацию этих функций ( `ExternalAddRef` , `ExternalRelease` и `ExternalQueryInterface` ).

Приведенный выше пример CPrintEditObj можно реализовать следующим образом:

```cpp
class CPrintEditObj : public CCmdTarget
{
public:
    // member data and member functions for CPrintEditObj go here

// Interface Maps
protected:
    DECLARE_INTERFACE_MAP()

    BEGIN_INTERFACE_PART(EditObj, IEditInterface)
        STDMETHOD_(void, EditObject)();
    END_INTERFACE_PART(EditObj)

    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)
        STDMETHOD_(void, PrintObject)();
    END_INTERFACE_PART(PrintObj)
};
```

Указанное выше объявление создает класс, производный от `CCmdTarget`. Макрос DECLARE_INTERFACE_MAP сообщает платформе, что этот класс будет иметь настраиваемую карту интерфейса. Кроме того, макросы BEGIN_INTERFACE_PART и END_INTERFACE_PART определяют вложенные классы, в данном случае с именами Цедитобж и Кпринтобж (X используется только для различения вложенных классов от глобальных классов, начинающихся с "C" и классов интерфейсов, начинающихся с "I"). Создаются два вложенных элемента этих классов — m_CEditObj и m_CPrintObj соответственно. Макросы автоматически объявляют функции [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) . Поэтому объявляются только функции, относящиеся к этому интерфейсу: Едитобжект и Принтобжект (СТДМЕСОД-макрос OLE используется, чтобы **_stdcall** и виртуальные ключевые слова были предоставлены в соответствии с целевой платформой).

Чтобы реализовать схему интерфейсов для этого класса, используйте следующий код:

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

Он соединяет IID_IPrintInterface IID с m_CPrintObj, а IID_IEditInterface — с m_CEditObj. `CCmdTarget`Реализация [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) ( `CCmdTarget::ExternalQueryInterface` ) использует эту карту для возвращения указателей на m_CPrintObj и m_CEditObj по запросу. Включать запись для `IID_IUnknown` не нужно, при запросе `IID_IUnknown` платформа будет использовать первый интерфейс в схеме (в данном случае это m_CPrintObj).

Несмотря на то, что BEGIN_INTERFACE_PARTный макрос автоматически объявил функции [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) , все равно необходимо реализовать их:

```cpp
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalAddRef();
}

ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalRelease();
}

HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);
}

void FAR EXPORT CEditPrintObj::XEditObj::EditObject()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    // code to "Edit" the object, whatever that means...
}
```

Реализация CEditPrintObj::CPrintObj будет похожа на приведенные выше определения CEditPrintObj::CEditObj. Несмотря на то что возможно создать макрос, который может использоваться для автоматического создания таких функций (а так было ранее при разработке MFC/OLE), становится трудно задавать точки останова, когда макрос создает более одной строки кода. По этой причине этот код будет расширен вручную.

При использовании реализации платформы для схем сообщений существует несколько вещей, которые не нужно было выполнять.

- Реализация QueryInterface

- Реализация AddRef и Release

- Объявление любого из этих встроенных методов для обоих интерфейсов

Кроме того, платформа использует схемы сообщений для внутренних целей. Это позволяет создавать производные объекты от класса платформы, например `COleServerDoc`, который уже поддерживает определенные интерфейсы и предоставляет замены или дополнения для интерфейсов, предоставляемых платформой. Это можно сделать, так как платформа полностью поддерживает наследование схемы интерфейсов от базового класса. Это причина, по которой BEGIN_INTERFACE_MAP принимает в качестве второго параметра имя базового класса.

> [!NOTE]
> В общем случае нельзя повторно использовать реализацию встроенных реализаций интерфейсов OLE MFC путем простого наследования внедренных специализаций этого интерфейса от версии MFC. Это невозможно, поскольку использование макроса METHOD_PROLOGUE для получения доступа к содержащему его `CCmdTarget` производному объекту подразумевает *фиксированное смещение* внедренного объекта от `CCmdTarget` производного объекта. Это означает, например, что нельзя наследовать внедренный XMyAdviseSink от реализации MFC в `COleClientItem::XAdviseSink`, так как XAdviseSink ожидает наличия определенного смещения относительно верхнего края объект `COleClientItem`.

> [!NOTE]
> Однако можно делегировать реализацию MFC для всех функций, для которых требуется поведение по умолчанию MFC. Это делается в реализации MFC `IOleInPlaceFrame` (XOleInPlaceFrame) в классе `COleFrameHook` (он делегирует в m_xOleInPlaceUIWindow для многих функций). Такой подход был выбран для уменьшения размера среды выполнения объектов, реализующих несколько интерфейсов. Он устраняет необходимость в обратном указателе (например, в m_pParent из примера в предыдущем разделе).

### <a name="aggregation-and-interface-maps"></a>Статистическая обработка и схемы интерфейсов

В дополнение к поддержке изолированных COM-объектов MFC также поддерживает статистическую обработку. Сама Статистическая обработка слишком сложна для обсуждения. Дополнительные сведения о статистической обработке см. в разделе [Статистическая обработка](/windows/win32/com/aggregation) . Эта заметка просто описывает поддержку статистической обработки, встроенную в платформу и схемы интерфейсов.

Существует два способа использования статистической обработки: (1) использование COM-объекта, поддерживающего статистическую обработку, и (2) реализация объекта, который может быть статистически вычислен другим объектом. Эти возможности можно называть «использование агрегатного объекта» и «превращение объекта в допускающий статистическую обработку». MFC поддерживает оба этих варианта.

### <a name="using-an-aggregate-object"></a>Использование агрегатного объекта

Для использования агрегатного объекта требуется какой-либо способ связать статистическое выражение с механизмом QueryInterface. Другими словами, агрегатный объект должен работать так, как будто это собственная часть объекта. Итак, как эта привязка применяется к механизму сопоставления интерфейсов MFC в дополнение к макросу INTERFACE_PART, где вложенный объект сопоставляется с IID, можно также объявить агрегатный объект как часть `CCmdTarget` производного класса. Для этого используется макрос INTERFACE_AGGREGATE. Это позволяет указать переменную-член (которая должна быть указателем на [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) или производный класс), которая должна быть интегрирована в механизм карты интерфейсов. Если при вызове метода указатель не имеет значение NULL `CCmdTarget::ExternalQueryInterface` , то платформа автоматически вызовет функцию-член [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) агрегатного объекта, если `IID` запрошенный объект не является одним из `IID` собственных объектов s, поддерживаемых `CCmdTarget` самим объектом.

#### <a name="to-use-the-interface_aggregate-macro"></a>Использование макроса INTERFACE_AGGREGATE

1. Объявите переменную-член (`IUnknown*`) которая будет содержать указатель на агрегатный объект.

2. Включите в карту интерфейса INTERFACE_AGGREGATE макрос, который ссылается на переменную члена по имени.

3. В определенный момент (обычно во время `CCmdTarget::OnCreateAggregates`) инициализируйте переменную-член со значением, отличным от NULL.

Пример:

```cpp
class CAggrExample : public CCmdTarget
{
public:
    CAggrExample();

protected:
    LPUNKNOWN m_lpAggrInner;
    virtual BOOL OnCreateAggregates();

    DECLARE_INTERFACE_MAP()
    // "native" interface part macros may be used here
};

CAggrExample::CAggrExample()
{
    m_lpAggrInner = NULL;
}

BOOL CAggrExample::OnCreateAggregates()
{
    // wire up aggregate with correct controlling unknown
    m_lpAggrInner = CoCreateInstance(CLSID_Example,
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)
        return FALSE;
    // optionally, create other aggregate objects here
    return TRUE;
}

BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)
    // native "INTERFACE_PART" entries go here
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)
END_INTERFACE_MAP()
```

Переменная m_lpAggrInner инициализируется в конструкторе со значением NULL. Платформа не учитывает ПУСТую переменную-член в реализации [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))по умолчанию. `OnCreateAggregates` удобно использовать для создания агрегатных объектов. Его потребуется вызвать явным образом при создании объекта за пределами реализации `COleObjectFactory` MFC. Причина создания статистических выражений в `CCmdTarget::OnCreateAggregates` и использование `CCmdTarget::GetControllingUnknown` станут очевидными при рассмотрении создания агрегатных объектов.

Эта методика дает объекту все интерфейсы, поддерживаемые агрегатным объектом, а также все его собственные интерфейсы. Если требуется только подмножество интерфейсов, поддерживаемых статистическим выражением, можно переопределить `CCmdTarget::GetInterfaceHook`. Это обеспечивает очень низкую возможность привязки, аналогичную [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)). В общем случае требуются все интерфейсы, которые поддерживает статистическое выражение.

### <a name="making-an-object-implementation-aggregatable"></a>Превращение реализации объекта в допускающую статистическую обработку

Чтобы обеспечить возможность статистической обработки объекта, реализация [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) должна делегироваться в «Управление неизвестными». Другими словами, чтобы он был частью объекта, он должен делегировать [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) другому объекту, который также является производным от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown). Этот «управляющий unknown» предоставляется для объекта при его создании, то есть предоставляется реализации `COleObjectFactory`. Такая реализация имеет небольшое количество издержек и в некоторых случаях является нежелательной, поэтому MFC делает ее необязательной. Чтобы сделать объект допускающим статистическую обработку, вызовите `CCmdTarget::EnableAggregation` из конструктора объекта.

Если этот объект также использует статистические выражения, необходимо обязательно передать в агрегатные объекты правильный «управляющий unknown». Обычно этот указатель [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) передается объекту при создании статистического выражения. Например, параметр pUnkOuter является «управляющим unknown» для объектов, созданных с использованием `CoCreateInstance`. Можно получить правильный указатель «управляющий unknown» путем вызова `CCmdTarget::GetControllingUnknown`. Однако значение, возвращаемое из этой функции, является недопустимым во время конструктора. Поэтому рекомендуется создавать ваши статистические выражения только в переопределении `CCmdTarget::OnCreateAggregates`, где возвращаемое значение из `GetControllingUnknown` является надежным, даже если оно создано на базе реализации `COleObjectFactory`.

Не менее важно, чтобы объект изменял правильный счетчик ссылок во время добавления или освобождения искусственных счетчиков ссылок. Чтобы обеспечить это, следует всегда вызывать `ExternalAddRef` и `ExternalRelease` вместо `InternalRelease` и `InternalAddRef`. `InternalRelease` или `InternalAddRef` редко вызываются для класса, поддерживающего статистическую обработку.

## <a name="reference-material"></a>Справочные материалы

Расширенное использование OLE, например при определении собственных интерфейсов или переопределении реализации интерфейсов OLE платформы, требует использования базового механизма схем интерфейсов.

В этом разделе рассматриваются все макросы и интерфейсы API, которые используются для реализации этих дополнительных функций.

### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — описание функции

```cpp
void EnableAggregation();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в конструкторе производного класса, если хотите обеспечить поддержку статистической обработки OLE для объектов этого типа. При этом подготавливается специальная реализация IUnknown, которая необходима для агрегатных объектов.

### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — описание функции

```cpp
DWORD ExternalQueryInterface(
    const void FAR* lpIID,
    LPVOIDFAR* ppvObj
);
```

#### <a name="parameters"></a>Параметры

*лпиид*<br/>
Дальний указатель на IID (первый аргумент QueryInterface)

*ппвобж*<br/>
Указатель на IUnknown * (второй аргумент QueryInterface)

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown для каждого интерфейса, который реализуется вашим классом. Эта функция предоставляет стандартную управляемую данными реализацию QueryInterface, основанную на схеме интерфейсов объекта. Это необходимо, чтобы привести возвращаемое значение к HRESULT. Если объект является статистическим выражением, вместо использования локальной схемы интерфейсов эта функция вызывает «управляющий IUnknown».

### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — описание функции

```cpp
DWORD ExternalAddRef();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown::AddRef для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение является новым счетчиком ссылок для объекта CCmdTarget. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».

### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — описание функции

```cpp
DWORD ExternalRelease();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown::Release для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение указывает новый счетчик для объекта. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».

### <a name="declare_interface_map--macro-description"></a>DECLARE_INTERFACE_MAP — описание макроса

```cpp
DECLARE_INTERFACE_MAP
```

#### <a name="remarks"></a>Примечания

Используйте этот макрос в любом классе, производном от `CCmdTarget`, который будет иметь схему интерфейсов. Используется во многом так же, как DECLARE_MESSAGE_MAP. Вызов этого макроса следует поместить в определение класса, обычно для этого используется файл заголовка (. (H). Класс с DECLARE_INTERFACE_MAP должен определять карту интерфейса в файле реализации (. CPP) с BEGIN_INTERFACE_MAP и END_INTERFACE_MAP макросами.

### <a name="begin_interface_part-and-end_interface_part--macro-descriptions"></a>BEGIN_INTERFACE_PART и END_INTERFACE_PART — описания макросов

```cpp
BEGIN_INTERFACE_PART(localClass, iface);
END_INTERFACE_PART(localClass)
```

#### <a name="parameters"></a>Параметры

*локалкласс*<br/>
Имя класса, реализующего интерфейс.

*iface*<br/>
Имя интерфейса, реализуемого с помощью данного класса.

#### <a name="remarks"></a>Примечания

Для каждого интерфейса, который будет реализован классом, необходимо иметь пару BEGIN_INTERFACE_PART и END_INTERFACE_PART. Эти макросы определяют локальный класс, производный от определенного вами интерфейса OLE, а также внедренную переменную-член этого класса. Члены [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)и [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) объявляются автоматически. Необходимо включить объявления для других функций-членов, которые являются частью реализуемого интерфейса (эти объявления помещаются между BEGIN_INTERFACE_PART и END_INTERFACE_PART макросами).

Аргумент *iface* — это интерфейс OLE, который вы хотите реализовать, например `IAdviseSink` , или `IPersistStorage` (или собственный пользовательский интерфейс).

Аргумент *локалкласс* — это имя локального класса, который будет определен. К имени будет автоматически добавляться буква X. Это соглашение об именовании используется для предотвращения конфликтов с глобальными классами, имеющими такое же имя. Кроме того, имя внедренного элемента совпадает с именем *локалкласс* , за исключением префикса "m_x".

Пример:

```cpp
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)
    STDMETHOD_(void, OnDataChange)(LPFORMATETC, LPSTGMEDIUM);
    STDMETHOD_(void, OnViewChange)(DWORD, LONG);
    STDMETHOD_(void, OnRename)(LPMONIKER);
    STDMETHOD_(void, OnSave)();
    STDMETHOD_(void, OnClose)();
END_INTERFACE_PART(MyAdviseSink)
```

Этот код определяет локальный класс с именем XMyAdviseSink, являющийся производным от IAdviseSink, и член класса, в котором он определен, с именем m_xMyAdviseSink.Note:

> [!NOTE]
> Строки, начинающиеся с `STDMETHOD` _, по сути копируются из OLE2. H и немного изменили. Их копирование из OLE2.H позволяет уменьшить число трудноразрешимых ошибок.

### <a name="begin_interface_map-and-end_interface_map--macro-descriptions"></a>BEGIN_INTERFACE_MAP и END_INTERFACE_MAP — описания макросов

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>Параметры

*секласс*<br/>
Класс, в котором определяется схема интерфейсов.

*baseClass*<br/>
Класс, от которого наследуется *секласс* .

#### <a name="remarks"></a>Примечания

Макросы BEGIN_INTERFACE_MAP и END_INTERFACE_MAP используются в файле реализации для фактического определения карты интерфейса. Для каждого реализуемого интерфейса существует один или несколько INTERFACE_PART вызовов макросов. Для каждого статистического выражения, используемого классом, существует один INTERFACE_AGGREGATE вызов макроса.

### <a name="interface_part--macro-description"></a>INTERFACE_PART — описание макроса

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса, содержащего схему интерфейсов.

*IID*<br/>
`IID`, который будет сопоставляться с внедренным классом.

*локалкласс*<br/>
Имя локального класса (без буквы X).

#### <a name="remarks"></a>Примечания

Этот макрос используется между макросом BEGIN_INTERFACE_MAP и макросом END_INTERFACE_MAP для каждого интерфейса, который будет поддерживаться объектом. Он позволяет сопоставлять IID с членом класса, указанного в *секласс* и *локалкласс*. Элемент "m_x" будет автоматически добавлен в *локалкласс* . Обратите внимание, что с одним членом можно сопоставить больше одного `IID`. Это очень удобно, если вы реализуете только «самый производный» интерфейс и хотите также предоставить все промежуточные интерфейсы. Хорошим примером этого является интерфейс `IOleInPlaceFrameWindow`. Иерархия выглядит следующим образом.

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

Если объект реализует `IOleInPlaceFrameWindow` , клиент может находиться `QueryInterface` в любом из этих интерфейсов: `IOleUIWindow` , `IOleWindow` или [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), помимо самого дальнего интерфейса `IOleInPlaceFrameWindow` (реализуемого на самом деле). Для решения этой задачи можно использовать несколько макросов INTERFACE_PART, чтобы сопоставлять каждый базовый интерфейс с `IOleInPlaceFrameWindow` интерфейсом:

В файле определения класса:

```cpp
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)
```

В файле реализации класса:

```cpp
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)
END_INTERFACE_MAP
```

Платформа самостоятельно обрабатывает IUnknown, так как он всегда является обязательным.

### <a name="interface_part--macro-description"></a>INTERFACE_PART — описание макроса

```cpp
INTERFACE_AGGREGATE(theClass, theAggr)
```

#### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса, содержащего схему интерфейсов.

*сеаггр*<br/>
Имя переменной-члена, подлежащей статистической обработке.

#### <a name="remarks"></a>Примечания

Этот макрос применяется, чтобы сообщить платформе о том, что класс использует агрегатный объект. Он должен находиться между макросами BEGIN_INTERFACE_PART и END_INTERFACE_PART. Агрегатный объект — это отдельный объект, производный от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown). С помощью агрегата и макроса INTERFACE_AGGREGATE можно сделать так, чтобы все интерфейсы, которые поддерживает агрегат, были непосредственно поддерживаются объектом. Аргумент *сеаггр* — это просто имя переменной-члена класса, производной от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) (прямо или косвенно). Все макросы INTERFACE_AGGREGATE должны следовать за INTERFACE_PART макросами при их помещении в карту интерфейса.

## <a name="see-also"></a>См. также раздел

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категориям](../mfc/technical-notes-by-category.md)
