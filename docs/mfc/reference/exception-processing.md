---
title: Обработка исключений
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
ms.openlocfilehash: 9d6a1c30ca0811085124a5fb5994c5f35d412ae7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837193"
---
# <a name="exception-processing"></a>Обработка исключений

При выполнении программы может возникнуть ряд ненормальных условий и ошибок, называемых исключениями. К ним могут относиться нехватки памяти, ошибки выделения ресурсов и невозможность поиска файлов.

Библиотека Microsoft Foundation Class использует схему обработки исключений, которая моделируется в тесном соответствии с предложенным Комитетом по стандартам ANSI для C++. Перед вызовом функции, которая может столкнуться с аномальной ситуацией, необходимо настроить обработчик исключений. Если функция обнаруживает аномальное состояние, она вызывает исключение, и управление передается обработчику исключений.

Несколько макросов, входящих в библиотека Microsoft Foundation Class, настроили обработчики исключений. Ряд других глобальных функций помогает создавать специализированные исключения и завершать программы при необходимости. Эти макросы и глобальные функции делятся на следующие категории:

- Макросы исключений, которые представляют собой структуру обработчика исключений.

- Функции, создающие исключения), которые создают исключения конкретных типов.

- Функции завершения, которые вызывают завершение программы.

Примеры и дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="exception-macros"></a>Макросы исключений

|Имя|Описание|
|-|-|
|[Повторите](#try)|Обозначает блок кода для обработки исключений.|
|[CATCH](#catch)|Обозначает блок кода для перехвата исключения из предыдущего блока **try** .|
|[CATCH_ALL](#catch_all)|Обозначает блок кода для перехвата всех исключений из предыдущего блока **try** .|
|[AND_CATCH](#and_catch)|Обозначает блок кода для перехвата дополнительных типов исключений из предыдущего блока **try** .|
|[AND_CATCH_ALL](#and_catch_all)|Обозначает блок кода для перехвата всех других дополнительных типов исключений, созданных в предыдущем блоке **try** .|
|[END_CATCH](#end_catch)|Завершает последний блок кода **catch** или **AND_CATCH** .|
|[END_CATCH_ALL](#end_catch_all)|Завершает последний блок кода **CATCH_ALL** .|
|[THROW](#throw)|Создает указанное исключение.|
|[THROW_LAST](#throw_last)|Создает текущее обработанное исключение для следующего внешнего обработчика.|

### <a name="exception-throwing-functions"></a>Функции генерации исключений

|Имя|Описание|
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Создает исключение архива.|
|[AfxThrowFileException](#afxthrowfileexception)|Вызывает исключение файла.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Вызывает исключение недопустимого аргумента.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Вызывает исключение памяти.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Вызывает исключение "не поддерживается".|
|[AfxThrowResourceException](#afxthrowresourceexception)|Вызывает исключение Windows ресурс — не найдено.|
|[AfxThrowUserException](#afxthrowuserexception)|Создает исключение в действии, инициированном пользователем.|

MFC предоставляет две функции генерации исключений, специально предназначенные для исключений OLE:

### <a name="ole-exception-functions"></a>Функции исключений OLE

|Имя|Описание|
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Создает исключение в функции OLE Automation.|
|[AfxThrowOleException](#afxthrowoleexception)|Вызывает исключение OLE.|

Для поддержки исключений баз данных классы баз данных предоставляют два класса исключений, `CDBException` и и `CDaoException` глобальные функции для поддержки типов исключений:

### <a name="dao-exception-functions"></a>Функции исключений DAO

|Имя|Описание|
|-|-|
|[афкссровдаоексцептион](#afxthrowdaoexception)|Создает исключение [кдаоексцептион](../../mfc/reference/cdaoexception-class.md) из собственного кода.|
|[AfxThrowDBException](#afxthrowdbexception)|Создает исключение [кдбексцептион](../../mfc/reference/cdbexception-class.md) из собственного кода.|

MFC предоставляет следующую функцию завершения:

### <a name="termination-functions"></a>Функции завершения

|Имя|Описание|
|-|-|
|[AfxAbort](#afxabort)|Вызывается для завершения работы приложения при возникновении неустранимой ошибки.|

## <a name="try"></a><a name="try"></a> Повторите

Настраивает блок **try** .

```
TRY
```

### <a name="remarks"></a>Примечания

Блок **try** определяет блок кода, который может вызывать исключения. Эти исключения обрабатываются в следующих блоках **catch** и **AND_CATCH** . Рекурсия разрешена: исключения могут передаваться во внешний блок **try** либо путем их пропуска, либо с помощью макроса THROW_LAST. Завершите блок **try** с помощью макроса END_CATCH или END_CATCH_ALL.

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. пример для [catch](#catch).

### <a name="requirements"></a>Требования

Заголовок: afx.h

## <a name="catch"></a><a name="catch"></a> CATCH

Определяет блок кода, который перехватывает первый тип исключения, вызванный в предыдущем блоке **try** .

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Указывает тип исключения для проверки. Список стандартных классов исключений см. в разделе Class [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Задает имя для указателя на объект Exception, который будет создан с помощью макроса. Для доступа к объекту исключения в блоке **catch** можно использовать имя указателя. Эта переменная объявлена для вас.

### <a name="remarks"></a>Примечания

Код обработки исключений может опрашивать объект исключения, если это уместно, чтобы получить дополнительные сведения о конкретной причине исключения. Вызов макроса THROW_LAST для сдвига обработки на следующий внешний кадр исключения. Завершите блок **try** с помощью макроса END_CATCH.

Если *exception_class* является классом `CException` , будут перехвачены все типы исключений. Чтобы определить, какое конкретное исключение было создано, можно использовать функцию члена [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) . Более эффективным способом перехвата нескольких видов исключений является использование последовательных **AND_CATCH** инструкций, каждый из которых имеет свой тип исключения.

Указатель объекта исключения создается с помощью макроса. Вам не нужно объявлять его самостоятельно.

> [!NOTE]
> Блок **catch** определяется как область C++, разделенная фигурными скобками. Если объявить переменные в этой области, они будут доступны только в пределах этой области. Это также относится к *exception_object_pointer_name*.

Дополнительные сведения об исключениях и макросе CATCH см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a> CATCH_ALL

Определяет блок кода, который перехватывает все типы исключений, созданные в предыдущем блоке **try** .

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Задает имя для указателя на объект Exception, который будет создан с помощью макроса. Для доступа к объекту исключения в блоке можно использовать имя указателя `CATCH_ALL` . Эта переменная объявлена для вас.

### <a name="remarks"></a>Примечания

Код обработки исключений может опрашивать объект исключения, если это уместно, чтобы получить дополнительные сведения о конкретной причине исключения. Вызов `THROW_LAST` макроса для сдвига обработки на следующий внешний кадр исключения. Если вы используете **CATCH_ALL**, завершите блок **try** с помощью макроса END_CATCH_ALL.

> [!NOTE]
> Блок **CATCH_ALL** определяется как область C++, разделенная фигурными скобками. Если объявить переменные в этой области, они будут доступны только в пределах этой области.

Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. пример для [кфиле:: Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="and_catch"></a><a name="and_catch"></a> AND_CATCH

Определяет блок кода для перехвата дополнительных типов исключений, создаваемых в предыдущем блоке **try** .

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Указывает тип исключения для проверки. Список стандартных классов исключений см. в разделе Class [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Имя для указателя на объект Exception, который будет создан с помощью макроса. Для доступа к объекту исключения в блоке **AND_CATCH** можно использовать имя указателя. Эта переменная объявлена для вас.

### <a name="remarks"></a>Примечания

Используйте макрос CATCH для перехвата одного типа исключения, а затем макрос AND_CATCH для перехвата каждого последующего типа. Завершите блок **try** с помощью макроса END_CATCH.

Код обработки исключений может опрашивать объект исключения, если это уместно, чтобы получить дополнительные сведения о конкретной причине исключения. Вызовите макрос THROW_LAST в блоке **AND_CATCH** , чтобы сдвинуть обработку на следующий внешний кадр исключения. **AND_CATCH** помечает конец предыдущего блока **catch** или **AND_CATCH** .

> [!NOTE]
> Блок **AND_CATCH** определяется как область C++ (разделенная фигурными скобками). При объявлении переменных в этой области Помните, что они доступны только в пределах этой области. Это также относится к переменной *exception_object_pointer_name* .

### <a name="example"></a>Пример

См. пример для [catch](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="and_catch_all"></a><a name="and_catch_all"></a> AND_CATCH_ALL

Определяет блок кода для перехвата дополнительных типов исключений, создаваемых в предыдущем блоке **try** .

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Имя для указателя на объект Exception, который будет создан с помощью макроса. Для доступа к объекту исключения в блоке **AND_CATCH_ALL** можно использовать имя указателя. Эта переменная объявлена для вас.

### <a name="remarks"></a>Примечания

Используйте макрос **catch** для перехвата одного типа исключения, а затем макрос AND_CATCH_ALL для перехвата всех остальных последующих типов. Если вы используете AND_CATCH_ALL, завершите блок **try** с помощью макроса END_CATCH_ALL.

Код обработки исключений может опрашивать объект исключения, если это уместно, чтобы получить дополнительные сведения о конкретной причине исключения. Вызовите макрос THROW_LAST в блоке **AND_CATCH_ALL** , чтобы сдвинуть обработку на следующий внешний кадр исключения. **AND_CATCH_ALL** помечает конец предыдущего блока **catch** или **AND_CATCH_ALL** .

> [!NOTE]
> Блок **AND_CATCH_ALL** определяется как область C++ (разделенная фигурными скобками). При объявлении переменных в этой области Помните, что они доступны только в пределах этой области.

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="end_catch"></a><a name="end_catch"></a> END_CATCH

Помечает конец последнего блока **catch** или **AND_CATCH** .

```
END_CATCH
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о макросе END_CATCH см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="end_catch_all"></a><a name="end_catch_all"></a> END_CATCH_ALL

Помечает конец последнего **CATCH_ALL88** или **AND_CATCH_ALL** блока.

```
END_CATCH_ALL
```

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="throw-mfc"></a><a name="throw"></a> THROW (MFC)

Создает указанное исключение.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer*<br/>
Указывает на объект исключения, производный от `CException` .

### <a name="remarks"></a>Примечания

**Вызовет** прерывание выполнения программы и передает управление соответствующему блоку **catch** в программе. Если блок **catch** не указан, то управление передается модулю Библиотека Microsoft Foundation Class, который выводит сообщение об ошибке и завершает работу.

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="throw_last"></a><a name="throw_last"></a> THROW_LAST

Вызывает исключение обратно в следующий внешний блок **catch** .

```
THROW_LAST()
```

### <a name="remarks"></a>Примечания

Этот макрос позволяет создавать локально созданное исключение. При попытке вызвать исключение, которое было только что перехвачено, оно обычно выходит из области и удаляется. При использовании **THROW_LAST**исключение передается правильно в следующий обработчик **catch** .

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. пример для [кфиле:: Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a> афкссроварчивиксцептион

Создает исключение архива.

```cpp
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Задает целое число, указывающее причину исключения. Список возможных значений см. в разделе [карчивиксцептион:: m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*лпсзарчивенаме*<br/>
Указывает на строку, содержащую имя `CArchive` объекта, вызвавшего исключение (если доступно).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a> афкссровфиликсцептион

Вызывает исключение файла.

```cpp
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Задает целое число, указывающее причину исключения. Список возможных значений см. в разделе [кфиликсцептион:: m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*лосеррор*<br/>
Содержит номер ошибки операционной системы (при наличии), который указывает причину исключения. Список кодов ошибок см. в руководстве по операционной системе.

*лпсзфиленаме*<br/>
Указывает на строку, содержащую имя файла, вызвавшего исключение (если доступно).

### <a name="remarks"></a>Примечания

Вы несете ответственность за определение причины на основе кода ошибки операционной системы.

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a> афкссровинвалидаржексцептион

Вызывает исключение недопустимого аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Примечания

Эта функция вызывается, когда используются недопустимые аргументы.

### <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a> афкссровмеморексцептион

Вызывает исключение памяти.

```cpp
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, если вызовы к базовым распределителям памяти системы (например, **malloc** и функция Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) ) завершаются ошибкой. Вам не нужно вызывать его для, **`new`** так как **`new`** в случае сбоя выделения памяти будет автоматически вызывать исключение памяти.

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a> афкссровнотсуппортедексцептион

Создает исключение, которое является результатом запроса неподдерживаемой функции.

```cpp
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a> афкссровресаурцеексцептион

Вызывает исключение ресурса.

```cpp
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается, когда не удается загрузить ресурс Windows.

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a> афкссровусерексцептион

Создает исключение для завершения операции пользователя.

```cpp
void AfxThrowUserException();
```

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается сразу после того, как `AfxMessageBox` пользователь сообщил об ошибке.

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a> афкссроволедиспатчексцептион

Эта функция используется для создания исключения в функции OLE Automation.

```cpp
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,
    LPCSTR lpszDescription,
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,
    UINT nDescriptionID,
    UINT nHelpID = -1);
```

### <a name="parameters"></a>Параметры

*wCode*<br/>
Код ошибки, относящийся к вашему приложению.

*лпсздескриптион*<br/>
Описание ошибки текстовом.

*ндескриптионид*<br/>
Идентификатор ресурса для описания ошибки текстовом.

*нхелпид*<br/>
Контекст справки для справки вашего приложения (. Файл HLP).

### <a name="remarks"></a>Примечания

Сведения, предоставленные этой функции, могут отображаться в приложении, управляющем приложением (Microsoft Visual Basic или другом клиентском приложении OLE-автоматизации).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a> афкссроволиксцептион

Создает объект типа `COleException` и создает исключение.

```cpp
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Параметры

*SC*<br/>
Код состояния OLE, указывающий причину исключения.

*ч*<br/>
Обрабатывает код результата, указывающий причину исключения.

### <a name="remarks"></a>Примечания

Версия, принимающая HRESULT в качестве аргумента, преобразует этот код результата в соответствующий SCODE. Дополнительные сведения о HRESULT и SCODE см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a> афкссровдаоексцептион

Вызовите эту функцию, чтобы вызвать исключение типа [кдаоексцептион](../../mfc/reference/cdaoexception-class.md) из собственного кода.

```cpp
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Параметры

*нафксдаоеррор*<br/>
Целочисленное значение, представляющее расширенный код ошибки DAO, который может быть одним из значений, перечисленных в разделе [кдаоексцептион:: m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*SCODE*<br/>
Код ошибки OLE из DAO типа SCODE. Дополнительные сведения см. в разделе [кдаоексцептион:: m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Примечания

Платформа также вызывает `AfxThrowDaoException` . В вызове можно передать один из параметров или оба. Например, если вы хотите вызвать одну из ошибок, определенных в **кдаоексцептион:: нафксдаоеррор** , но не волнует параметр *SCODE* , передайте допустимый код в параметр *нафксдаоеррор* и примите значение по умолчанию для *SCODE*.

Сведения об исключениях, связанных с классами MFC DAO, см `CDaoException` . в разделе класс в этой книге, а в статье [исключения: исключения базы данных](../../mfc/exceptions-database-exceptions.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдб.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a> афкссровдбексцептион

Вызовите эту функцию, чтобы создать исключение типа `CDBException` из собственного кода.

```cpp
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*нреткоде*<br/>
Значение типа РЕТКОДЕ, определяющее тип ошибки, вызвавшей исключение.

*файле*<br/>
Указатель на `CDatabase` объект, представляющий соединение с источником данных, с которым связано исключение.

*hstmt*<br/>
Обработчик ODBC ХСТМТ, указывающий маркер инструкции, с которым связано исключение.

### <a name="remarks"></a>Примечания

Платформа вызывается `AfxThrowDBException` при получении РЕТКОДЕ ODBC из вызова функции API ODBC и ИНТЕРПРЕТИРУЕТ реткоде как исключительную ситуацию, а не как предполагаемую ошибку. Например, операция доступа к данным может завершиться ошибкой из-за ошибки чтения с диска.

Сведения о значениях РЕТКОДЕ, определенных ODBC, см. в главе 8 «получение сведений о состоянии и ошибках» в Windows SDK. Дополнительные сведения о расширениях MFC для этих кодов см. в разделе Class [кдбексцептион](../../mfc/reference/cdbexception-class.md).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="afxabort"></a><a name="afxabort"></a> афксаборт

Функция завершения по умолчанию, предоставляемая MFC.

```cpp
void  AfxAbort();
```

### <a name="remarks"></a>Примечания

`AfxAbort` вызывается внутренне функциями-членами MFC при возникновении неустранимой ошибки, например неперехваченного исключения, которое не может быть обработано. Можно вызвать `AfxAbort` в редких случаях, когда возникает фатальная ошибка, из-за которой невозможно выполнить восстановление.

### <a name="example"></a>Пример

См. пример для [catch](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** AFX.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CException](cexception-class.md)<br/>
[Класс Цинвалидаржексцептион](cinvalidargexception-class.md)
