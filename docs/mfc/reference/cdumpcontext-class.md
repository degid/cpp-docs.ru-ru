---
title: Класс CDumpContext
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: 3a81e06586e6de14d57ce4c4de36dc30c73383f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212518"
---
# <a name="cdumpcontext-class"></a>Класс CDumpContext

Поддерживает ориентированных на поток диагностические данные в форме человекочитаемого текста.

## <a name="syntax"></a>Синтаксис

```
class CDumpContext
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDumpContext:: CDumpContext](#cdumpcontext)|Формирует объект `CDumpContext`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDumpContext::D Умпашекс](#dumpashex)|Выводит указанный элемент в шестнадцатеричном формате.|
|[CDumpContext:: Flush](#flush)|Очищает все данные в буфере контекста дампа.|
|[CDumpContext:: Depth](#getdepth)|Возвращает целое число, соответствующее глубине дампа.|
|[CDumpContext:: Хексдумп](#hexdump)|Выводит байты, содержащиеся в массиве, в шестнадцатеричном формате.|
|[CDumpContext:: Сетдепс](#setdepth)|Задает глубину дампа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|Вставляет переменные и объекты в контекст дампа.|

## <a name="remarks"></a>Примечания

`CDumpContext`не имеет базового класса.

Для большей части дампа можно использовать [афксдумп](diagnostic-services.md#afxdump), предварительно объявленный `CDumpContext` объект. `afxDump`Объект доступен только в отладочной версии Библиотека Microsoft Foundation Class.

Некоторые [службы диагностики](../../mfc/reference/diagnostic-services.md) памяти используют `afxDump` для их вывода.

В среде Windows выходные данные предопределенного `afxDump` объекта, сходно схожие с `cerr` потоком, направляются отладчику через функцию Windows `OutputDebugString` .

`CDumpContext`Класс содержит перегруженный оператор вставки ( **<<** ) для `CObject` указателей, которые выгружают данные объекта. Если для производного объекта требуется пользовательский формат дампа, переопределите [CObject::D УМП](../../mfc/reference/cobject-class.md#dump). Большинство классов Microsoft Foundation реализует переопределенную `Dump` функцию члена.

Классы, которые не являются производными от `CObject` , такие как `CString` , `CTime` и `CTimeSpan` , имеют собственные перегруженные `CDumpContext` Операторы вставки, как и часто используемые структуры, такие как `CFileStatus` , `CPoint` и `CRect` .

Если в реализации класса используется макрос [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) или [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) , `CObject::Dump` выводится имя `CObject` класса, производного от. В противном случае он выполнит печать `CObject` .

`CDumpContext`Класс доступен как в отладочной, так и в окончательной версиях библиотеки, но `Dump` функция-член определена только в отладочной версии. Используйте инструкции **#ifdef _DEBUG**  /  `#endif` , чтобы включить в код диагностики скобки, включая пользовательские `Dump` функции элементов.

Перед созданием собственного `CDumpContext` объекта необходимо создать `CFile` объект, который выступает в качестве назначения дампа.

Дополнительные сведения о см `CDumpContext` . в разделе [Отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDumpContext`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpContext:: CDumpContext

Конструирует объект класса `CDumpContext` .

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на `CFile` объект, который является назначением дампа.

### <a name="remarks"></a>Примечания

`afxDump`Объект создается автоматически.

Не записывайте запись в базовый объект `CFile` , пока активен контекст дампа. в противном случае вы будете конфликтовать с дампом. В среде Windows выходные данные направляются в отладчик через функцию Windows `OutputDebugString` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::D Умпашекс

Выводит указанный тип в формате шестнадцатеричных чисел.

```
CDumpContext& DumpAsHex(BYTE b);
CDumpContext& DumpAsHex(DWORD dw);
CDumpContext& DumpAsHex(int n);
CDumpContext& DumpAsHex(LONG l);
CDumpContext& DumpAsHex(LONGLONG n);
CDumpContext& DumpAsHex(UINT u);
CDumpContext& DumpAsHex(ULONGLONG n);
CDumpContext& DumpAsHex(WORD w);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CDumpContext`.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член для вывода элемента указанного типа в виде шестнадцатеричного числа. Чтобы создать дамп массива, вызовите метод [CDumpContext:: хексдумп](#hexdump).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>CDumpContext:: Flush

Принудительная запись всех данных, остающихся в буферах, в файл, присоединенный к контексту дампа.

```cpp
void Flush();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpContext:: Depth

Определяет, находится ли в процессе глубокий или поверхностный дамп.

```
int GetDepth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Глубина дампа, заданная параметром `SetDepth` .

### <a name="example"></a>Пример

  См. пример для [сетдепс](#setdepth).

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>CDumpContext:: Хексдумп

Выводит массив байтов в формате шестнадцатеричных чисел.

```cpp
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Параметры

*лпсзлине*<br/>
Строка для вывода в начале новой строки.

*пби*<br/>
Указатель на буфер, содержащий байты для дампа.

*nBytes*<br/>
Число байтов для дампа.

*нвидс*<br/>
Максимальное число байтов, записываемых в строку (не является шириной строки вывода).

### <a name="remarks"></a>Примечания

Чтобы создать дамп одного определенного типа элемента в виде шестнадцатеричного числа, вызовите [CDumpContext::D умпашекс](#dumpashex).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext::operator&lt;&lt;

Выводит указанные данные в контекст дампа.

```
CDumpContext& operator<<(const CObject* pOb);
CDumpContext& operator<<(const CObject& ob);
CDumpContext& operator<<(LPCTSTR lpsz);
CDumpContext& operator<<(const void* lp);
CDumpContext& operator<<(BYTE by);
CDumpContext& operator<<(WORD w);
CDumpContext& operator<<(DWORD dw);
CDumpContext& operator<<(int n);
CDumpContext& operator<<(double d);
CDumpContext& operator<<(float f);
CDumpContext& operator<<(LONG l);
CDumpContext& operator<<(UINT u);
CDumpContext& operator<<(LPCWSTR lpsz);
CDumpContext& operator<<(LPCSTR lpsz);
CDumpContext& operator<<(LONGLONG n);
CDumpContext& operator<<(ULONGLONG n);
CDumpContext& operator<<(HWND h);
CDumpContext& operator<<(HDC h);
CDumpContext& operator<<(HMENU h);
CDumpContext& operator<<(HACCEL h);
CDumpContext& operator<<(HFONT h);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка `CDumpContext`. С помощью возвращаемого значения можно записывать несколько вставок в одну строку исходного кода.

### <a name="remarks"></a>Примечания

Оператор вставки перегружается для `CObject` указателей, а также для большинства типов-примитивов. Указатель на символ приводит к дампу содержимого строки. Указатель на **`void`** результат в шестнадцатеричном дампе адреса. ЛОНГЛОНГ приводит к дампу 64-разрядного целого числа со знаком; УЛОНГЛОНГ приводит к дампу 64-разрядного целого числа без знака.

Если в реализации класса используется макрос IMPLEMENT_DYNAMIC или IMPLEMENT_SERIAL, то в операторе вставки с помощью `CObject::Dump` будет распечатано имя `CObject` класса, производного от. В противном случае он выполнит печать `CObject` . При переопределении `Dump` функции класса можно предоставить более информативный вывод содержимого объекта вместо шестнадцатеричного дампа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpContext:: Сетдепс

Задает глубину дампа.

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Параметры

*нневдепс*<br/>
Новое значение глубины.

### <a name="remarks"></a>Примечания

Если вы создаете дамп простого типа или простой `CObject` , который не содержит указателей на другие объекты, достаточно иметь значение 0. Значение больше 0 указывает глубокий дамп, в котором рекурсивно выводятся дампы всех объектов. Например, при глубоком дампе коллекции будут выгружаться все элементы коллекции. В производных классах можно использовать и другие конкретные значения глубины.

> [!NOTE]
> Циклические ссылки не обнаруживаются в глубоких дампах и могут привести к бесконечному циклу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кфиле](../../mfc/reference/cfile-class.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)
