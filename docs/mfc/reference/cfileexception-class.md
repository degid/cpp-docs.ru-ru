---
title: Класс Кфиликсцептион
ms.date: 06/09/2020
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: 6d3102cfd41d68458332025cbf3410e3f169523b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212453"
---
# <a name="cfileexception-class"></a>Класс Кфиликсцептион

Представляет состояние, связанное с файлом исключения.

## <a name="syntax"></a>Синтаксис

```
class CFileException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кфиликсцептион:: Кфиликсцептион](#cfileexception)|Формирует объект `CFileException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кфиликсцептион:: Еррнотоексцептион](#errnotoexception)|Возвращает код, соответствующий номеру ошибки времени выполнения.|
|[Кфиликсцептион:: Жетеррормессаже](#geterrormessage)|Получает сообщение, описывающее исключение.|
|[Кфиликсцептион:: Осеррортоексцептион](#oserrortoexception)|Возвращает код причины, соответствующий коду ошибки операционной системы.|
|[Кфиликсцептион:: Сроверрно](#throwerrno)|Создает исключение файла на основе номера ошибки времени выполнения.|
|[Кфиликсцептион:: Сровосеррор](#throwoserror)|Создает исключение файла на основе номера ошибки операционной системы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кфиликсцептион:: m_cause](#m_cause)|Содержит переносимый код, соответствующий причине исключения.|
|[Кфиликсцептион:: m_lOsError](#m_loserror)|Содержит номер связанной ошибки операционной системы.|
|[Кфиликсцептион:: m_strFileName](#m_strfilename)|Содержит имя файла для этого исключения.|

## <a name="remarks"></a>Примечания

`CFileException`Класс содержит открытые члены данных, которые содержат переносимый код причины и номер ошибки, зависящий от операционной системы. Класс также предоставляет статические функции-члены для генерации исключений файлов и для возврата кодов причин ошибок операционной системы и ошибок времени выполнения C.

`CFileException`объекты создаются и создаются в `CFile` функциях элементов и в функциях членов производных классов. Доступ к этим объектам можно получить в области выражения **catch** . Для обеспечения переносимости используйте только код причины, чтобы получить причину исключения. Дополнительные сведения об исключениях см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a>Кфиликсцептион:: Кфиликсцептион

Конструирует `CFileException` объект, хранящий код причины и код операционной системы в объекте.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Переменная перечислимого типа, указывающая причину исключения. Список возможных значений см. в разделе [кфиликсцептион:: m_cause](#m_cause) .

*лосеррор*<br/>
Причина исключения, зависящая от операционной системы, если она доступна. Параметр *лосеррор* предоставляет больше информации, чем *Причина* .

*лпсзарчивенаме*<br/>
Указывает на строку, содержащую имя `CFile` объекта, вызвавшего исключение.

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, а вызовите глобальную функцию [афкссровфиликсцептион](exception-processing.md#afxthrowfileexception).

> [!NOTE]
> Переменная *лосеррор* применяется только к `CFile` объектам и `CStdioFile` . `CMemFile`Класс не обрабатывает этот код ошибки.

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>Кфиликсцептион:: Еррнотоексцептион

Преобразует заданное значение ошибки библиотеки времени выполнения в `CFileException` перечислимое значение ошибки.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Параметры

*неррно*<br/>
Целочисленный код ошибки, как определено в файле времени выполнения. Высоты.

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, соответствующее указанному значению ошибки библиотеки времени выполнения.

### <a name="remarks"></a>Примечания

Список возможных перечислимых значений см. в разделе [кфиликсцептион:: m_cause](#m_cause) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>Кфиликсцептион:: Жетеррормессаже

Извлекает текст, описывающий исключение.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Параметры

*лпсзеррор*<br/>
[вход, выход] Указатель на буфер, который получает сообщение об ошибке.

*нмаксеррор*<br/>
окне Максимальное число символов, которое может хранить указанный буфер. Сюда входит завершающий нуль символ.

*пнхелпконтекст*<br/>
[вход, выход] Указатель на целое число без знака, которое получает идентификатор контекста справки. Если `NULL` значение равно, идентификатор не возвращается.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Если указанный буфер слишком мал, сообщение об ошибке усекается.

### <a name="example"></a>Пример

В следующем примере используется функция `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a>Кфиликсцептион:: m_cause

Содержит значения, заданные перечисляемым типом `CFileException`.

```
int m_cause;
```

### <a name="remarks"></a>Примечания

Этот элемент данных является открытой переменной типа **`int`** . Перечислители и их значение представлено далее.

| Error | Значение и значение |
|--|--|
| `CFileException::none` | 	0: ошибка отсутствует. |
| `CFileException::genericException` | 	1: возникла неизвестная ошибка. |
| `CFileException::fileNotFound` | 	2: не удалось найти файл. |
| `CFileException::badPath` | 	3: путь целиком или частично является недопустимым. |
| `CFileException::tooManyOpenFiles` | 	4: превышено разрешенное число открытых файлов. |
| `CFileException::accessDenied` | 	5: не удалось получить доступ к файлу. |
| `CFileException::invalidFile` | 	6: попытка использовать недопустимый дескриптор файла. |
| `CFileException::removeCurrentDir` | 	7: не удается удалить текущий рабочий каталог. |
| `CFileException::directoryFull` | 	8: других записей каталога нет. |
| `CFileException::badSeek` | 	9: при попытке задать указатель на файл возникла ошибка. |
| `CFileException::hardIO` | 	10: аппаратная ошибка. |
| `CFileException::sharingViolation` | 	11: файл SHARE.EXE не был загружен или общий регион заблокирован. |
| `CFileException::lockViolation` | 	12: попытка заблокировать регион, который уже заблокирован. |
| `CFileException::diskFull` | 13: диск заполнен. |
| `CFileException::endOfFile` | 14: достигнут конец файла. |

> [!NOTE]
> Перечислители причины `CFileException` отличаются от перечислителей причины `CArchiveException`.

> [!NOTE]
> `CArchiveException::generic` не рекомендуется к использованию. Используйте вместо этого `genericException`. Если **универсальное** приложение используется в приложении и строится с помощью параметра/CLR, то в результате синтаксических ошибок не будет легко расшифроваться.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a>Кфиликсцептион:: m_lOsError

Содержит код ошибки операционной системы для этого исключения.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Примечания

Список кодов ошибок см. в техническом руководстве по операционной системе. Этот элемент данных является открытой переменной типа LONG.

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a>Кфиликсцептион:: m_strFileName

Содержит имя файла для этого условия исключения.

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>Кфиликсцептион:: Осеррортоексцептион

Возвращает перечислитель, соответствующий заданному значению *лосеррор* . Если код ошибки неизвестен, функция возвращает `CFileException::generic` .

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Параметры

*лосеррор*<br/>
Код ошибки, относящийся к операционной системе.

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, соответствующее заданному значению ошибки операционной системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a>Кфиликсцептион:: Сроверрно

Создает `CFileException` объект, соответствующий заданному значению *неррно* , а затем создает исключение.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*неррно*<br/>
Целочисленный код ошибки, как определено в файле времени выполнения. Высоты.

*лпсзфиленаме*<br/>
Указатель на строку, содержащую имя файла, вызвавшего исключение, если он есть.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a>Кфиликсцептион:: Сровосеррор

Создает объект, `CFileException` соответствующий заданному значению *лосеррор* . Если код ошибки неизвестен, функция создает исключение, закодированное как `CFileException::generic` .

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*лосеррор*<br/>
Код ошибки, относящийся к операционной системе.

*лпсзфиленаме*<br/>
Указатель на строку, содержащую имя файла, вызвавшего исключение, если он есть.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)
