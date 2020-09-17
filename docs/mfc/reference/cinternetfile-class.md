---
title: Класс Цинтернетфиле
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: 460130d98fc9bce761ee293e1a46c86c770b24c9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223074"
---
# <a name="cinternetfile-class"></a>Класс Цинтернетфиле

Разрешает доступ к файлам в удаленных системах, использующих протоколы Интернета.

## <a name="syntax"></a>Синтаксис

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[Цинтернетфиле:: Цинтернетфиле](#cinternetfile)|Формирует объект `CInternetFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Цинтернетфиле:: Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|
|[Цинтернетфиле:: Close](#close)|Закрывает `CInternetFile` и освобождает свои ресурсы.|
|[Цинтернетфиле:: Flush](#flush)|Очищает содержимое буфера записи и гарантирует, что данные в памяти записываются на целевой компьютер.|
|[Цинтернетфиле:: DATALENGTH](#getlength)|Возвращает размер файла.|
|[Цинтернетфиле:: Read](#read)|Считывает количество указанных байтов.|
|[Цинтернетфиле:: ReadString](#readstring)|Считывает поток символов.|
|[Цинтернетфиле:: Seek](#seek)|Перемещает указатель в открытый файл.|
|[Цинтернетфиле:: Сетреадбуфферсизе](#setreadbuffersize)|Задает размер буфера, в который будут считываться данные.|
|[Цинтернетфиле:: Сетвритебуфферсизе](#setwritebuffersize)|Задает размер буфера, в который будут записываться данные.|
|[Цинтернетфиле:: Write](#write)|Записывает количество указанных байтов.|
|[Цинтернетфиле:: WriteString](#writestring)|Записывает строку, завершающуюся нулем, в файл.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Цинтернетфиле::operator ХИНТЕРНЕТ](#operator_hinternet)|Оператор приведения для обработчика Интернета.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[Цинтернетфиле:: m_hFile](#m_hfile)|Маркер файла.|

## <a name="remarks"></a>Примечания

Предоставляет базовый класс для классов файлов [чттпфиле](../../mfc/reference/chttpfile-class.md) и [CGopherFile](../../mfc/reference/cgopherfile-class.md) . Вы никогда не создаете `CInternetFile` объект напрямую. Вместо этого создайте объект одного из производных от него классов, вызвав [кгоферконнектион:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [Чттпконнектион:: опенрекуест](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете создать `CInternetFile` объект, вызвав [кфтпконнектион:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

`CInternetFile`Функции элементов `Open` ,, `LockRange` `UnlockRange` и `Duplicate` не реализованы для `CInternetFile` . При вызове этих функций для `CInternetFile` объекта вы получите [кнотсуппортедексцептион](../../mfc/reference/cnotsupportedexception-class.md).

Дополнительные сведения о `CInternetFile` работе с другими классами Интернета MFC см. в статье Интернет – [программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет.h

## <a name="cinternetfileabort"></a><a name="abort"></a>Цинтернетфиле:: Abort

Закрывает файл, связанный с этим объектом, и делает его недоступным для чтения или записи.

```
virtual void Abort();
```

### <a name="remarks"></a>Примечания

Если вы не закрыли файл перед уничтожением объекта, деструктор закроет его.

При обработке исключений `Abort` отличается от [закрытия](#close) двумя важными способами. Во-первых, `Abort` функция не создает исключение в случае сбоев, поскольку оно игнорирует сбои. Во вторых, не `Abort` выполняет **утверждение** , если файл не был открыт или был закрыт ранее.

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a>Цинтернетфиле:: Цинтернетфиле

Эта функция-член вызывается при `CInternetFile` создании объекта.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Маркер для файла Интернета.

*пстрфиленаме*<br/>
Указатель на строку, содержащую имя файла.

*пконнектион*<br/>
Указатель на объект [Цинтернетконнектион](../../mfc/reference/cinternetconnection-class.md) .

*бреадмоде*<br/>
Указывает, доступен ли файл только для чтения.

*хсессион*<br/>
Маркер сеанса Интернета.

*пстрсервер*<br/>
Указатель на строку, содержащую имя сервера.

*двконтекст*<br/>
Идентификатор контекста для `CInternetFile` объекта. Дополнительные сведения об идентификаторе контекста см. в статье [основы WinInet](../../mfc/wininet-basics.md) .

### <a name="remarks"></a>Примечания

Вы никогда не создаете `CInternetFile` объект напрямую. Вместо этого создайте объект одного из производных от него классов, вызвав [кгоферконнектион:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [Чттпконнектион:: опенрекуест](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете создать `CInternetFile` объект, вызвав [кфтпконнектион:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

## <a name="cinternetfileclose"></a><a name="close"></a>Цинтернетфиле:: Close

Закрывает `CInternetFile` и освобождает все свои ресурсы.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Если файл был открыт для записи, вызывается неявный вызов функции [flush](#flush) , чтобы гарантировать запись всех буферизованных данных на узел. По `Close` завершении использования файла следует вызвать метод.

## <a name="cinternetfileflush"></a><a name="flush"></a>Цинтернетфиле:: Flush

Вызовите эту функцию члена, чтобы очистить содержимое буфера записи.

```
virtual void Flush();
```

### <a name="remarks"></a>Примечания

Используйте `Flush` , чтобы убедиться, что все данные в памяти на самом деле были записаны на целевой компьютер, а также чтобы убедиться, что транзакция с ведущим компьютером завершена. `Flush`действует только для `CInternetFile` объектов, открытых для записи.

## <a name="cinternetfilegetlength"></a><a name="getlength"></a>Цинтернетфиле:: DATALENGTH

Возвращает размер файла.

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a>Цинтернетфиле:: m_hFile

Маркер файла, связанного с этим объектом.

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>Цинтернетфиле::operator ХИНТЕРНЕТ

Этот оператор используется для получения маркера Windows для текущего сеанса Интернета.

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a>Цинтернетфиле:: Read

Вызывайте эту функцию члена для чтения в заданную память, начиная с *лпвбуф*, заданное число байтов, *нкаунт*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*лпбуф*<br/>
Указатель на адрес в памяти, по которому считываются данные из файла.

*нкаунт*<br/>
Число записываемых байтов.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, переданных в буфер. Возвращаемое значение может быть меньше *нкаунт* , если достигнут конец файла.

### <a name="remarks"></a>Примечания

Функция возвращает число фактически считанных байтов — число, которое может быть меньше *нкаунт* , если файл завершается. Если при чтении файла возникает ошибка, функция создает объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) , описывающий ошибку. Обратите внимание, что чтение после завершения файла не является ошибкой и не может быть причиной выдачи исключения.

Чтобы гарантировать получение всех данных, приложение должно продолжать вызывать `CInternetFile::Read` метод до тех пор, пока метод не возвратит нуль.

## <a name="cinternetfilereadstring"></a><a name="readstring"></a>Цинтернетфиле:: ReadString

Вызывайте эту функцию-член для чтения потока символов до тех пор, пока не обнаружит символ новой строки.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Параметры

*пстр*<br/>
Указатель на строку, которая будет принимать считанную строку.

*Nмакс.*<br/>
Максимальное число считываемых символов.

*rStr*<br/>
Ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , получающий строку Read.

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер, содержащий обычные данные, полученные из объекта [Цинтернетфиле](../../mfc/reference/cinternetfile-class.md) . Независимо от типа данных буфера, переданного этому методу, он не выполняет никаких манипуляций с данными (например, преобразование в Юникод), поэтому необходимо сопоставлять возвращенные данные с предполагаемой структурой, как если **`void`** <strong>\*</strong> бы был возвращен тип.

Значение NULL, если конец файла был достигнут без считывания данных; или, если логическое значение, значение FALSE, если конец файла был достигнут без считывания каких-либо данных.

### <a name="remarks"></a>Примечания

Функция помещает полученную строку в память, на которую ссылается параметр *ПСТР* . Он прекращает чтение символов при достижении максимального количества символов, заданного параметром *nмакс.*. Буфер всегда получает завершающий нуль-символ.

При вызове `ReadString` без предварительного вызова [сетреадбуфферсизе](#setreadbuffersize)вы получите буфер 4096 байт.

## <a name="cinternetfileseek"></a><a name="seek"></a>Цинтернетфиле:: Seek

Вызовите эту функцию-член, чтобы изменить расположение указателя в ранее открытом файле.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Параметры

*лоффсет*<br/>
Смещение в байтах для перемещения указателя чтения/записи в файле.

*Nиз*<br/>
Относительная ссылка для смещения. Необходимо установить одно из следующих значений.

- `CFile::begin`Переместите указатель файла *ЛОФФ* байт вперед от начала файла.

- `CFile::current`Переместите указатель файла *ЛОФФ* байт из текущей позиции в файле.

- `CFile::end`Переместите указатель файла *ЛОФФ* байт из конца файла. для поиска в существующем файле *ЛОФФ* должно быть отрицательным. положительные значения будут искать после конца файла.

### <a name="return-value"></a>Возвращаемое значение

Новое смещение в байтах с начала файла, если запрошенная позиция является допустимой. в противном случае значение не определено и создается объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) .

### <a name="remarks"></a>Примечания

`Seek`Функция позволяет получить произвольный доступ к содержимому файла, перемещая указатель на указанную величину, абсолютно или относительно. Во время поиска данные в действительности не считываются.

В настоящее время вызов этой функции-члена поддерживается только для данных, связанных с `CHttpFile` объектами. Он не поддерживается для запросов FTP или gopher. При вызове `Seek` одной из этих неподдерживаемых служб она перейдет к коду ошибки Win32 ERROR_INTERNET_INVALID_OPERATION.

При открытии файла указатель файла находится в смещении 0, в начале файла.

> [!NOTE]
> Использование `Seek` может привести к неявному вызову функции [flush](#flush).

### <a name="example"></a>Пример

  См. пример для реализации базового класса ( [кфиле:: Seek](../../mfc/reference/cfile-class.md#seek)).

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>Цинтернетфиле:: Сетреадбуфферсизе

Вызовите эту функцию-член, чтобы задать размер временного буфера чтения, используемого `CInternetFile` производным объектом.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Параметры

*нреадсизе*<br/>
Требуемый размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

Базовые API-интерфейсы WinInet не выполняют буферизацию, поэтому выбирайте размер буфера, позволяющий приложению эффективно считывать данные независимо от объема считываемых данных. Если при каждом вызове метода [Read](#read) обычно используется большой ааунт данных (например, четыре или более килобайта), то буфер не нужен. Однако при вызове `Read` для получения небольших фрагментов данных или при использовании метода [ReadString](#readstring) для считывания отдельных строк за раз буфер чтения повышает производительность приложения.

По умолчанию `CInternetFile` объект не предоставляет буферизацию для чтения. При вызове этой функции члена необходимо убедиться, что файл открыт для доступа на чтение.

Размер буфера можно увеличить в любое время, но сжатие буфера не будет действовать. Если вызвать метод [ReadString](#readstring) без первого вызова `SetReadBufferSize` , вы получите буфер 4096 байт.

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>Цинтернетфиле:: Сетвритебуфферсизе

Вызовите эту функцию-член, чтобы задать размер временного буфера записи, используемого `CInternetFile` производным объектом.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Параметры

*нвритесизе*<br/>
Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

Базовые API-интерфейсы WinInet не выполняют буферизацию, поэтому выбирайте размер буфера, позволяющий приложению эффективно записывать данные независимо от объема записываемых данных. Если каждый вызов для [записи](#write) обычно включает большой объем данных (например, четыре или более килобайта за один раз), то буфер не нужен. Однако при вызове [Write](#write) для записи небольших фрагментов данных буфер записи повышает производительность приложения.

По умолчанию `CInternetFile` объект не предоставляет буферизацию для записи. При вызове этой функции члена необходимо убедиться, что файл открыт для доступа на запись. Размер буфера записи можно изменить в любое время, но это приведет к неявному вызову функции [flush](#flush).

## <a name="cinternetfilewrite"></a><a name="write"></a>Цинтернетфиле:: Write

Вызовите эту функцию члена для записи в заданную память, *лпвбуф*, указанное число байтов, *нкаунт*.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*лпбуф*<br/>
Указатель на первый байт, который необходимо записать.

*нкаунт*<br/>
Указывает число записываемых байтов.

### <a name="remarks"></a>Примечания

Если при записи данных возникает ошибка, функция создает объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) , описывающий ошибку.

## <a name="cinternetfilewritestring"></a><a name="writestring"></a>Цинтернетфиле:: WriteString

Эта функция записывает строку, завершающуюся нулем, в связанный файл.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Параметры

*пстр*<br/>
Указатель на строку, содержащую содержимое, которое необходимо записать.

### <a name="remarks"></a>Примечания

Если при записи данных возникает ошибка, функция создает объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) , описывающий ошибку.

## <a name="see-also"></a>См. также статью

[Класс Кстдиофиле](../../mfc/reference/cstdiofile-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Цинтернетконнектион](../../mfc/reference/cinternetconnection-class.md)
