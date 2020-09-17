---
title: TN016. Использование множественного наследования C++ с MFC
ms.date: 06/28/2018
f1_keywords:
- vc.inheritance
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
ms.openlocfilehash: c44639e713f6d0b26d5b74e9f645f60c8627e0c8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231771"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016. Использование множественного наследования C++ с MFC

В этом заметке описывается использование множественного наследования (MI) с Microsoft Foundation Classes. Использование MI в MFC не требуется. MI не используется ни в каких классах MFC и не требуется для записи библиотеки классов.

Следующие подразделы описывают, как MI влияет на использование общих идиом MFC, а также охватывает некоторые ограничения MI. Некоторые из этих ограничений являются общими ограничениями C++. Другие объекты накладываются архитектурой MFC.

В конце этой технической заметки вы найдете законченное приложение MFC, использующее MI.

## <a name="cruntimeclass"></a>крунтимекласс

Механизмы сохранения и динамического создания объектов MFC используют структуру данных [крунтимекласс](../mfc/reference/cruntimeclass-structure.md) для уникальной идентификации классов. MFC связывает одну из этих структур с каждым динамическим и/или сериализуемым классом в приложении. Эти структуры инициализируются при запуске приложения с помощью специального статического объекта типа `AFX_CLASSINIT` .

Текущая реализация не `CRuntimeClass` поддерживает сведения о типе среды выполнения MI. Это не означает, что в приложении MFC нельзя использовать MI. Однако при работе с объектами, имеющими более одного базового класса, у вас будут определенные обязанности.

Метод [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) не будет правильно определять тип объекта, если он имеет несколько базовых классов. Таким образом, нельзя использовать [CObject](../mfc/reference/cobject-class.md) в качестве виртуального базового класса, и все вызовы `CObject` функций-членов, таких как [CObject:: Serialize](../mfc/reference/cobject-class.md#serialize) и [CObject::operator new](../mfc/reference/cobject-class.md#operator_new) , должны иметь квалификаторы области, чтобы C++ мог устранить неоднозначность соответствующего вызова функции. Когда программа использует MI в MFC, класс, содержащий `CObject` базовый класс, должен быть самым левым классом в списке базовых классов.

Альтернативой является использование **`dynamic_cast`** оператора. Приведение объекта с MI к одному из его базовых классов приведет к принудительному использованию компилятором функций в предоставляемом базовом классе. Дополнительные сведения см. в разделе [оператор dynamic_cast](../cpp/dynamic-cast-operator.md).

## <a name="cobject---the-root-of-all-classes"></a>CObject — корень всех классов;

Все значимые классы прямо или косвенно наследуются от класса `CObject` . `CObject`не содержит данных элементов, но имеет некоторые функциональные возможности по умолчанию. При использовании MI вы обычно наследуете от двух или более `CObject` производных классов. В следующем примере показано, как класс может наследовать от [CFrameWnd](../mfc/reference/cframewnd-class.md) и [коблист](../mfc/reference/coblist-class.md):

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

В этом случае `CObject` включается два раза. Это означает, что необходим способ устранения неоднозначности ссылок на `CObject` методы или операторы. **Оператор New** и [оператор DELETE](../mfc/reference/cobject-class.md#operator_delete) являются двумя операторами, которые необходимо устранить неоднозначность. В качестве другого примера следующий код вызывает ошибку во время компиляции:

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>Повторное внедрение методов CObject

При создании нового класса с двумя или более `CObject` производными базовыми классами необходимо повторно реализовать `CObject` методы, которые будут использоваться другими пользователями. Операторы **`new`** и **`delete`** являются обязательными, поэтому рекомендуется использовать [дамп](../mfc/reference/cobject-class.md#dump) . В следующем примере повторно реализуются **`new`** **`delete`** операторы и и `Dump` метод:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd::operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd::operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>Виртуальное наследование CObject

Может показаться, что практически наследуемое `CObject` решение решает проблему неоднозначности функции, но это не так. Поскольку в отсутствуют данные о членах `CObject` , виртуальное наследование не требуется для предотвращения нескольких копий данных члена базового класса. В первом примере, показанном ранее, `Dump` виртуальный метод по-прежнему является неоднозначным, так как он реализован иначе в `CFrameWnd` и `CObList` . Лучший способ удаления неоднозначности — следовать рекомендациям, приведенным в предыдущем разделе.

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject:: IsKindOf и ввод во время выполнения

Механизм ввода во время выполнения, поддерживаемый MFC в, `CObject` использует макросы DECLARE_DYNAMIC, IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, DECLARE_SERIAL и IMPLEMENT_SERIAL. Эти макросы могут выполнять проверку типов во время выполнения для обеспечения безопасного образования производных типов.

Эти макросы поддерживают только один базовый класс и будут работать в ограниченном виде для умножения наследуемых классов. Базовый класс, указанный в IMPLEMENT_DYNAMIC или IMPLEMENT_SERIAL, должен быть первым (или самым левым) базовым классом. Это размещение позволяет выполнять проверку типов только для самого левого базового класса. Система типов времени выполнения ничего не знает о дополнительных базовых классах. В следующем примере системы времени выполнения выполняют проверку типов `CFrameWnd` , но ничего не знает о `CObList` .

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd и схемы сообщений

Для правильной работы системы схемы сообщений MFC существуют два дополнительных требования.

- Должен быть только один `CWnd` производный базовый класс.

- `CWnd`Базовый класс, производный от, должен быть первым (или левым) базовым классом.

Ниже приведены некоторые примеры, которые не будут работать.

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>Пример программы, использующей MI

Следующий пример представляет собой изолированное приложение, состоящее из одного класса, производного от `CFrameWnd` и [CWinApp](../mfc/reference/cwinapp-class.md). Не рекомендуется структурировать приложение таким образом, но это пример наименьшего приложения MFC с одним классом.

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

    // Necessary because of MI disambiguity
    void* operator new(size_t nSize)
        { return CFrameWnd::operator new(nSize); }
    void operator delete(void* p)
        { CFrameWnd::operator delete(p); }

    // Implementation
    // CWinApp overrides
    virtual BOOL InitInstance();
    // CFrameWnd overrides
    virtual void PostNcDestroy();
    afx_msg void OnPaint();

    DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)
    ON_WM_PAINT()
END_MESSAGE_MAP()

// because the frame window is not allocated on the heap, we must
// override PostNCDestroy not to delete the frame object
void CHelloAppAndFrame::PostNcDestroy()
{
    // do nothing (do not call base class)
}

void CHelloAppAndFrame::OnPaint()
{
    CPaintDC dc(this);
    CRect rect;
    GetClientRect(rect);

    CString s = "Hello, Windows!";
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));
    dc.SetBkMode(TRANSPARENT);
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);
}

// Application initialization
BOOL CHelloAppAndFrame::InitInstance()
{
    // first create the main frame
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",
        WS_OVERLAPPEDWINDOW, rectDefault))
        return FALSE;

    // the application object is also a frame window
    m_pMainWnd = this;
    ShowWindow(m_nCmdShow);
    return TRUE;
}

CHelloAppAndFrame theHelloAppAndFrame;
```

## <a name="see-also"></a>См. также раздел

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категориям](../mfc/technical-notes-by-category.md)
