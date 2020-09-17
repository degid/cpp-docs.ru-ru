---
title: Класс CStdioFile
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 80ee65aa339a38b3d8434bc4c7cb977e263f037b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366012"
---
# <a name="cstdiofile-class"></a>Класс CStdioFile

Представляет файл потока c run-time, открытый функцией run-time [fopen.](../../c-runtime-library/reference/fopen-wfopen.md)

## <a name="syntax"></a>Синтаксис

```
class CStdioFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Строит `CStdioFile` объект из указателя пути или файла.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::Открыто](#open)|Перегружен. Open предназначен для использования `CStdioFile` с конструктором по умолчанию (Overrides [CFile::Open).](../../mfc/reference/cfile-class.md#open)|
|[CStdioFile::ReadString](#readstring)|Читает одну строку текста.|
|[CStdioFile::Ищите](#seek)|Позиции текущего указателя файла.|
|[CStdioFile::WriteString](#writestring)|Пишет одну строку текста.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Содержит указатель на открытый файл.|

## <a name="remarks"></a>Примечания

Файлы потоков буферизированы и могут быть открыты в текстовом режиме (по умолчанию) или двоичном режиме.

Текстовый режим обеспечивает специальную обработку для кареты обратных линий кормовых пар. Когда вы пишете символ ленты (newline) на объект текстового режима, `CStdioFile` пара байт (0x0D, 0x0A) отправляется в файл. Когда вы читаете, пара байт (0x0D, 0x0A) переводится на один байт 0x0A.

Функции [CFile](../../mfc/reference/cfile-class.md) [Duplicate,](../../mfc/reference/cfile-class.md#duplicate) [LockRange](../../mfc/reference/cfile-class.md#lockrange)и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не поддерживаются. `CStdioFile`

Если вы называете `CStdioFile`эти функции на, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Для получения дополнительной `CStdioFile`информации об использовании , см. [статьи Файлы в MFC](../../mfc/files-in-mfc.md) и [обработки файлов](../../c-runtime-library/file-handling.md) в *Run-Time Библиотека Справка*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdioFile::CStdioFile

Создает и инициализирует объект `CStdioFile`.

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Параметры

*pOpenStream*<br/>
Обращет указатель файла, возвращенный вызовом в функцию C run-time [fopen.](../../c-runtime-library/reference/fopen-wfopen.md)

*lpszFileName*<br/>
Определяет строку, которая является путь к желаемому файлу. Путь может быть как относительным, так и абсолютным.

*nОткрытыефлаги*<br/>
Определяет варианты создания файлов, обмена файлами и режимов доступа к файлам. Вы можете указать несколько вариантов **|** с помощью bitwise ИЛИ ( ) оператора.

Требуется один вариант режима доступа к файлам; другие режимы не являются обязательными. Смотрите [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) для списка вариантов режима и других флагов. В версии MFC 3.0 и позже разрешены флаги общего обмена.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию не прикрепляет файл к объекту. `CStdioFile` При использовании этого конструктора `CStdioFile::Open` необходимо использовать метод, чтобы открыть `CStdioFile` файл и прикрепить его к объекту.

Конструктор с одним параметром прикрепляет открытый поток файлов к объекту. `CStdioFile` Допустимые значения указателя включают предопределенные входные/выходные файлы указатели *stdin,* *stdout*, или *stderr.*

Двухпараметр конструктор создает `CStdioFile` объект и открывает соответствующий файл с заданный путь.

Если вы проходите NULL для *pOpenStream* или *lpszFileName*, конструктор бросает `CInvalidArgException*`.

Если файл не может быть открыт или создан, конструктор бросает `CFileException*`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

## <a name="cstdiofilem_pstream"></a><a name="m_pstream"></a>CStdioFile::m_pStream

Элемент `m_pStream` данных является указателем на открытый файл, как `fopen`возвращается функцией c run-time.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Примечания

Это NULL, если файл никогда не был открыт или был закрыт.

## <a name="cstdiofileopen"></a><a name="open"></a>CStdioFile::Открыто

Перегружен. Open предназначен для использования `CStdioFile` с конструктором по умолчанию.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, которая является путь к желаемому файлу. Путь может быть как относительным, так и абсолютным.

*nОткрытыефлаги*<br/>
Режим обмена и доступа. Упоняет действие, необходимое при открытии файла. Вы можете комбинировать опции с помощью оператора bitwise-OR (&#124;). Требуется одно разрешение на доступ и один опцион на участие; режимы modeCreate и modeNoInherit не являются обязательными.

*pОшибка*<br/>
Указатель на существующий объект исключения файлов, который получит статус сбойной операции.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

## <a name="cstdiofilereadstring"></a><a name="readstring"></a>CStdioFile::ReadString

Читает текстовые данные в буфер, до предела *символов nMax*-1, из файла, связанного с объектом. `CStdioFile`

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Укажите указатель на буфер, поставляемый пользователем, который получит строку текста с нулевым завершением.

*nMax*<br/>
Определяет максимальное количество символов для чтения, не считая термина null.

*rString*<br/>
Ссылка на `CString` объект, который будет содержать строку при возврате функции.

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер, содержащий текстовые данные. NULL, если конец файла был достигнут без считывания каких-либо данных; или если boolean, FALSE, если конец файла был достигнут без чтения каких-либо данных.

### <a name="remarks"></a>Примечания

Чтение останавливается первым новым персонажем. Если в этом случае было прочитано меньше символов *nMax*-1, в буфере хранится новый символ строки. В любом случае приложен нулевой символ (''0'.

[CFile::Read](../../mfc/reference/cfile-class.md#read) также доступен для ввода текстового режима, но он не прекращается на паре кормов для возврата каретки.

> [!NOTE]
> Версия `CString` этой функции удаляет, `'\n'` если присутствует; версия LPTSTR не делает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

## <a name="cstdiofileseek"></a><a name="seek"></a>CStdioFile::Ищите

Перепозиционирует указатель в ранее открытом файле.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Параметры

*lOff*<br/>
Количество байтов для перемещения указателя.

*nОт*<br/>
Режим движения указателя. Необходимо установить одно из следующих значений.

- `CFile::begin`: Переместите указатель файла *lOff* байты вперед с начала файла.

- `CFile::current`: Переместите указатель файла *lOff* байтов из текущего положения в файле.

- `CFile::end`: Переместите файл указатель *lOff* байтов из конца файла. Обратите внимание, что *lOff* должен быть отрицательным, чтобы искать в существующий файл; положительные значения будут искать мимо конца файла.

### <a name="return-value"></a>Возвращаемое значение

Если запрашиваемый вопрос `Seek` является законным, возвращает новый байт смещения от начала файла. В противном случае значение возврата `CFileException` не определено и объект брошен.

### <a name="remarks"></a>Примечания

Функция `Seek` позволяет случайный доступ к содержимому файла, перемещая указатель указанную сумму, абсолютно или относительно. Никакие данные фактически не читаются во время поиска. Если запрашиваемый удлиненный размер файла больше, длина файла будет увеличена до этой позиции, и никаких исключений не будет.

При открытии файла указатель файла размещается в смещении 0, в начале файла.

Эта реализация `Seek` основана на функции `fseek`Run-Time Library (CRT). Существует несколько ограничений на `Seek` использование потоков, открытых в текстовом режиме. Для получения дополнительной информации, [см. fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Пример

Ниже приводится следующий `Seek` пример, как использовать для перемещения указателя 1000 байтов от начала файла. `cfile` Обратите `Seek` внимание, что не читает данные, поэтому вы должны впоследствии позвонить [CStdioFile::ReadString](#readstring) для чтения данных.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

## <a name="cstdiofilewritestring"></a><a name="writestring"></a>CStdioFile::WriteString

Записывает данные из буфера `CStdioFile` в файл, связанный с объектом.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Украсил указатель буфера, содержащего строку с нулевым завершением.

### <a name="remarks"></a>Примечания

Прекращение нулевого символа `\0`() не записано в файл. Этот метод записывает новые символы в *lpsz* в файл в качестве пары кормов для возврата каретки.

Если вы хотите написать данные, которые не являются `CStdioFile::Write` недействительными в файле, используйте или [CFile::Write](../../mfc/reference/cfile-class.md#write).

Этот метод бросает, `CInvalidArgException*` если вы указываете NULL для параметра *lpsz.*

Этот метод бросает `CFileException*` в ответ на ошибки файловой системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)
