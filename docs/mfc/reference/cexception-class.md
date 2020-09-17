---
title: Класс CException
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: e27802e05c832d28d848d9eb1235d6ef5980b306
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841562"
---
# <a name="cexception-class"></a>Класс CException

Базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CException:: CException](#cexception)|Формирует объект `CException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CException::D удалить](#delete)|Удаляет `CException` объект.|
|[CException:: ReportError](#reporterror)|Сообщает пользователю сообщение об ошибке в окне сообщения.|

## <a name="remarks"></a>Примечания

Поскольку `CException` является абстрактным базовым классом, нельзя создавать `CException` объекты напрямую; необходимо создавать объекты производных классов. Если необходимо создать собственный `CException` класс, используйте один из производных классов, перечисленных выше, в качестве модели. Убедитесь, что производный класс также использует `IMPLEMENT_DYNAMIC` .

Ниже перечислены производные классы и их описания.

|Имя|Описание|
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для исключений MFC, критических для ресурсов|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Недопустимое условие исключения аргумента|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос неподдерживаемой операции|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключение, относящееся к архиву|
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение для конкретного файла|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows не найден или не является создаваемым|
|[COleException](../../mfc/reference/coleexception-class.md)|Исключение OLE|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключение базы данных (то есть условия исключения, возникающие для классов баз данных MFC на основе открытого подключения к базе данных)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Исключение OLE-диспетчеризации (автоматизация)|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, указывающее, что не удалось найти ресурс|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Исключение объектов доступа к данным (то есть условия исключений, возникающие для классов DAO)|
|[CInternetConnection](../../mfc/reference/cinternetexception-class.md)|Интернет-исключение (то есть условия исключения, возникающие для Интернет-классов).|

Эти исключения предназначены для использования с макросами [throw](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [try](exception-processing.md#try), [catch](exception-processing.md#catch), [AND_CATCH](exception-processing.md#and_catch)и [END_CATCH](exception-processing.md#end_catch) . Дополнительные сведения об исключениях см. в разделе [обработка исключений](exception-processing.md)или в статье [обработка исключений (MFC)](../exception-handling-in-mfc.md).

Чтобы перехватить конкретное исключение, используйте соответствующий производный класс. Чтобы перехватить все типы исключений, используйте `CException` , а затем используйте [CObject:: IsKindOf](cobject-class.md#iskindof) для различения между `CException` производными классами. Обратите внимание, что `CObject::IsKindOf` работает только для классов, объявленных с помощью макроса [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) , чтобы воспользоваться преимуществами динамической проверки типов. `CException`При создании любого производного класса необходимо использовать `IMPLEMENT_DYNAMIC` макрос.

Вы можете сообщить сведения об исключениях пользователю, вызвав [жетеррормессаже](cfileexception-class.md#geterrormessage) или [ReportError](#reporterror), две функции члена, которые работают с любыми `CException` производными классами.

Если исключение перехвачено одним из макросов, `CException` объект удаляется автоматически; не удаляйте его самостоятельно. Если исключение перехвачено с помощью **`catch`** ключевого слова, оно не удаляется автоматически. Дополнительные сведения о том, когда следует удалять объект ексептион, см. в статье [обработка исключений (MFC)](../exception-handling-in-mfc.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cexceptioncexception"></a><a name="cexception"></a> CException:: CException

Эта функция-член конструирует `CException` объект.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*b_AutoDelete*<br/>
Укажите значение TRUE, если память для `CException` объекта была выделена в куче. Это приведет к `CException` удалению объекта при `Delete` вызове функции-члена для удаления исключения. Укажите значение FALSE, если `CException` объект находится в стеке или является глобальным объектом. В этом случае `CException` объект не будет удален при `Delete` вызове функции-члена.

### <a name="remarks"></a>Примечания

Обычно вызывать этот конструктор напрямую не требуется. Функция, вызывающая исключение, должна создать экземпляр `CException` производного класса и вызвать его конструктор или использовать одну из функций Throw MFC, например [афкссровфиликсцептион](exception-processing.md#afxthrowfileexception), для создания предопределенного типа. Эта документация предоставляется только для полноты.

## <a name="cexceptiondelete"></a><a name="delete"></a> CException::D удалить

Эта функция проверяет, `CException` был ли объект создан в куче, и если да, то он вызывает **`delete`** оператор для объекта.

```cpp
void Delete();
```

### <a name="remarks"></a>Примечания

При удалении `CException` объекта используйте `Delete` функцию-член для удаления исключения. Не используйте **`delete`** оператор напрямую, так как `CException` объект может быть глобальным объектом или создан в стеке.

Можно указать, следует ли удалять объект при создании объекта. Дополнительные сведения см. в разделе [CException:: CException](#cexception).

Вызов требуется только `Delete` при использовании **`try`** -  **`catch`** механизма C++. Если вы используете макросы MFC **try** и **catch**, эти макросы будут автоматически вызывать эту функцию.

### <a name="example"></a>Пример

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

## <a name="cexceptionreporterror"></a><a name="reporterror"></a> CException:: ReportError

Вызовите эту функцию-член, чтобы сообщить пользователю о тексте ошибки в окне сообщения.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает стиль окна сообщения. Примените к полю любое сочетание [стилей окна сообщения](styles-used-by-mfc.md#message-box-styles) . Если этот параметр не указан, по умолчанию используется значение MB_OK.

*нмессажеид*<br/>
Указывает идентификатор ресурса (запись строковой таблицы) отображаемого сообщения, если объект исключения не имеет сообщения об ошибке. Если значение равно 0, отображается сообщение "сообщение об ошибке недоступно".

### <a name="return-value"></a>Возвращаемое значение

`AfxMessageBox`Значение; в противном случае — 0, если недостаточно памяти для вывода окна сообщения. Возможные возвращаемые значения см. в разделе [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) .

### <a name="example"></a>Пример

Ниже приведен пример использования `CException::ReportError` . Другой пример см. в примере для [catch](exception-processing.md#catch).

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>См. также раздел

[CObject, класс](cobject-class.md)<br/>
[Иерархическая диаграмма](../hierarchy-chart.md)<br/>
[Обработка исключений](exception-processing.md)<br/>
[Инструкции. Создание собственных классов пользовательских исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
