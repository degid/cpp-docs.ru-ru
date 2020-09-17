---
title: Класс CPathT
ms.date: 03/27/2019
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: 76273e7fbfa50e610b437e11859821374413d008
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032138"
---
# <a name="cpatht-class"></a>Класс CPathT

Этот класс представляет собой путь.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Параметры

*StringType*<br/>
Класс строк ATL/MFC для использования для пути [(см. CStringT).](../../atl-mfc-shared/reference/cstringt-class.md)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CPathT::PXSTR](#pcxstr)|Постоянный тип строки.|
|[CPathT::PXSTR](#pxstr)|Тип string.|
|[CPathT::XCHAR](#xchar)|Тип символа.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPathT:CPathT](#cpatht)|Конструктор для пути.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPatht:AddBackslash](#addbackslash)|Вызовите этот метод, чтобы добавить обратный срез в конце строки, чтобы создать правильный синтаксис для пути.|
|[CPathT::AddExtension](#addextension)|Вызовите этот метод, чтобы добавить расширение файла в путь.|
|[CPathT::Приложение](#append)|Вызовите этот метод, чтобы придать строку текущему пути.|
|[CPathT:BuildRoot](#buildroot)|Вызовите этот метод, чтобы создать корневой путь из заданного номера диска.|
|[CPathT::Каноникализация](#canonicalize)|Вызовите этот метод, чтобы преобразовать путь в каноническую форму.|
|[CPathT::Комбинат](#combine)|Вызовите этот метод, чтобы совпь строки, представляющие имя каталога и строку, представляющую имя пути файла в один путь.|
|[CPathT::CommonPrefix](#commonprefix)|Вызовите этот метод, чтобы определить, разделяет ли указанный путь общую префикс с текущим путем.|
|[CPathT::CompactPath](#compactpath)|Вызовите этот метод, чтобы усеченный путь файла, чтобы поместиться в пределах заданной ширины пикселя, заменив компоненты пути эллипсисом.|
|[CPathT::CompactPathEx](#compactpathex)|Вызовите этот метод, чтобы усеченный путь файла, чтобы поместиться в определенное количество символов, заменив компоненты пути эллипсисом.|
|[CPathT::FileExists](#fileexists)|Вызовите этот метод, чтобы проверить, существует ли файл на этом имени пути.|
|[CPathT::FindExtension](#findextension)|Вызовите этот метод, чтобы найти положение расширения файла в пути.|
|[CPathT:FindFileName](#findfilename)|Вызовите этот метод, чтобы найти положение имени файла в пути.|
|[CPatht:GetDriveNumber](#getdrivenumber)|Вызовите этот метод для поиска пути для дисковой буквы в диапазоне 'A' до 'Я' и верните соответствующий номер диска.|
|[CPathT::GetExtension](#getextension)|Вызовите этот метод, чтобы получить расширение файла от пути.|
|[CPathT::IsDirectory](#isdirectory)|Вызовите этот метод, чтобы проверить, является ли путь действительным каталогом.|
|[Cpatht::IsFileSpec](#isfilespec)|Вызовите этот метод для поиска пути для любых символов, разгранижаемых по путям (например, ':' или ').\\ Если нет символов, разгранижая путь, путь считается путем спецификации файла.|
|[Cpatht::IsPrefix](#isprefix)|Вызовите этот метод, чтобы определить, содержит ли путь действительную префикс типа, пройденое *pszPrefix.*|
|[Cpatht::Относительно](#isrelative)|Вызовите этот метод, чтобы определить, является ли путь относительным.|
|[Cpatht::Isroot](#isroot)|Вызовите этот метод, чтобы определить, является ли путь корнем каталога.|
|[Cpatht::Issameroot](#issameroot)|Вызовите этот метод, чтобы определить, есть ли у другого пути общий корневой компонент с текущим путем.|
|[CPatht::ISUNC](#isunc)|Вызовите этот метод, чтобы определить, является ли путь действительной КООН (универсальная конвенция именования) для сервера и обмена.|
|[CPatht::ISUNCServer](#isuncserver)|Вызовите этот метод, чтобы определить, является ли путь действительным коонт (универсальное наименование конвенции) путь только для сервера.|
|[CPatht::ISUNCServerShare](#isuncservershare)|Вызовите этот метод, чтобы определить, является ли путь действительным коонт (универсальная конвенция именования) \\ \ путь общего обмена,*доля* *сервера.*\ |
|[CPatht:MakePretty](#makepretty)|Вызов исчерпайте этот метод, чтобы преобразовать путь ко всем символам нижнего регистра, чтобы придать пути последовательный внешний вид.|
|[Cpatht:MatchSpec](#matchspec)|Вызовите этот метод для поиска пути для строки, содержащей тип соответствия подстановочных знаков.|
|[CPathT::КвотаПространства](#quotespaces)|Вызовите этот метод, чтобы приложить путь в кавычки, если он содержит какие-либо пробелы.|
|[Cpatht:RelativepathTo](#relativepathto)|Вызовите этот метод, чтобы создать относительный путь из одного файла или папки в другой.|
|[CPathT::RemoveArgs](#removeargs)|Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.|
|[CPatht::RemoveBackslash](#removebackslash)|Вызовите этот метод, чтобы удалить задний срез с пути.|
|[CPathT::RemoveBlanks](#removeblanks)|Вызовите этот метод, чтобы удалить все ведущие и задние пространства с пути.|
|[CPathT::RemoveExtension](#removeextension)|Вызовите этот метод, чтобы удалить расширение файла из пути, если он есть.|
|[Cpatht::RemoveFileSpec](#removefilespec)|Вызовите этот метод, чтобы удалить имя задней файла и backslash из пути, если он имеет их.|
|[CPatht::Переименование](#renameextension)|Вызовите этот метод, чтобы заменить расширение имени файла в пути новым расширением. Если имя файла не содержит расширения, расширение будет прикреплено к концу строки.|
|[CPathT::SkipRoot](#skiproot)|Вызовите этот метод, чтобы разобрать путь, игнорируя письмо диска или части пути сервера/доли КООН.|
|[CPathT::StripPath](#strippath)|Вызовите этот метод, чтобы удалить часть пути полностью квалифицированного пути и имя файла.|
|[Cpatht::Striptoroot](#striptoroot)|Вызовите этот метод, чтобы удалить все части пути, за исключением корневой информации.|
|[CPathT::UnquoteSpaces](#unquotespaces)|Вызовите этот метод, чтобы удалить кавычки из начала и конца пути.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPathT:оператор const StringType &](#operator_const_stringtype_amp)|Этот оператор позволяет рассматривать объект как строку.|
|[CPatht:оператор Cpatht::PXSTR](#operator_cpatht__pcxstr)|Этот оператор позволяет рассматривать объект как строку.|
|[CPathT:оператор StringType &](#operator_stringtype_amp)|Этот оператор позволяет рассматривать объект как строку.|
|[CPathT::оператор](#operator_add_eq)|Этот оператор привязывает строку к пути.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|Путь.|

## <a name="remarks"></a>Примечания

`CPath`, `CPathA`, `CPathW` и мгновений `CPathT` определяется следующим образом:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

## <a name="cpathtaddbackslash"></a><a name="addbackslash"></a>CPatht:AddBackslash

Вызовите этот метод, чтобы добавить обратный срез в конце строки, чтобы создать правильный синтаксис для пути. Если путь уже имеет задний backslash, не backslash не будет добавлено.

```cpp
void AddBackslash();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)

## <a name="cpathtaddextension"></a><a name="addextension"></a>CPathT::AddExtension

Вызовите этот метод, чтобы добавить расширение файла в путь.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Параметры

*pszExtension*<br/>
Расширение файла для добавления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)

## <a name="cpathtappend"></a><a name="append"></a>CPathT::Приложение

Вызовите этот метод, чтобы придать строку текущему пути.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Параметры

*pszMore*<br/>
Добавляемая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)информации см.

## <a name="cpathtbuildroot"></a><a name="buildroot"></a>CPathT:BuildRoot

Вызовите этот метод, чтобы создать корневой путь из заданного номера диска.

```cpp
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Параметры

*Idrive*<br/>
Номер диска (0: A:, 1 - B:и так далее).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)

## <a name="cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::Каноникализация

Вызовите этот метод, чтобы преобразовать путь в каноническую форму.

```cpp
void Canonicalize();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).

## <a name="cpathtcombine"></a><a name="combine"></a>CPathT::Комбинат

Вызовите этот метод, чтобы совпь строки, представляющие имя каталога и строку, представляющую имя пути файла в один путь.

```cpp
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Параметры

*pszDir*<br/>
Путь к каталогу.

*pszFile*<br/>
Путь к файлу.

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)см.

## <a name="cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::CommonPrefix

Вызовите этот метод, чтобы определить, разделяет ли указанный путь общую префикс с текущим путем.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Параметры

*pszДругие*<br/>
Путь для сравнения с текущим.

### <a name="return-value"></a>Возвращаемое значение

Возвращает общую префикс.

### <a name="remarks"></a>Примечания

Приставка является одним из этих типов: "C:\\\\",,", "..,". \\\\". Для получения дополнительной [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)информации см.

## <a name="cpathtcompactpath"></a><a name="compactpath"></a>CPathT::CompactPath

Вызовите этот метод, чтобы усеченный путь файла, чтобы поместиться в пределах заданной ширины пикселя, заменив компоненты пути эллипсисом.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Параметры

*Hdc*<br/>
Контекст устройства используется для метрик шрифта.

*nWidth*<br/>
Ширина, в пикселях, что строка будет вынужден вписаться в.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)см.

## <a name="cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::CompactPathEx

Вызовите этот метод, чтобы усеченный путь файла, чтобы поместиться в определенное количество символов, заменив компоненты пути эллипсисом.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*nMaxChars*<br/>
Максимальное количество символов, содержащихся в новой строке, включая термин NULL.

*dwFlags*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)см.

## <a name="cpathtcpatht"></a><a name="cpatht"></a>CPathT:CPathT

Конструктор.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
Указатель на строку пути.

*путь*<br/>
Строка пути.

## <a name="cpathtfileexists"></a><a name="fileexists"></a>CPathT::FileExists

Вызовите этот метод, чтобы проверить, существует ли файл на этом имени пути.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если файл существует, FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)

## <a name="cpathtfindextension"></a><a name="findextension"></a>CPathT::FindExtension

Вызовите этот метод, чтобы найти положение расширения файла в пути.

```
int FindExtension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию "., предшествующую расширению. Если расширение не найдено, возвращается -1.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)

## <a name="cpathtfindfilename"></a><a name="findfilename"></a>CPathT:FindFileName

Вызовите этот метод, чтобы найти положение имени файла в пути.

```
int FindFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение имени файла. Если имя файла не найдено, возвращается -1.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)

## <a name="cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPatht:GetDriveNumber

Вызовите этот метод для поиска пути для дисковой буквы в диапазоне 'A' до 'Я' и верните соответствующий номер диска.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает номер диска в виде целых с 0 по 25 (соответствующий букве "А" через "Я"), если на пути есть буква привода, или -1 в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)информации см.

## <a name="cpathtgetextension"></a><a name="getextension"></a>CPathT::GetExtension

Вызовите этот метод, чтобы получить расширение файла от пути.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает расширение файла.

## <a name="cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::IsDirectory

Вызовите этот метод, чтобы проверить, является ли путь действительным каталогом.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение (16), если путь является каталогом, FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)см.

## <a name="cpathtisfilespec"></a><a name="isfilespec"></a>Cpatht::IsFileSpec

Вызовите этот метод для поиска пути для любых символов, разгранижаемых по путям (например, ':' или ').\\ Если нет символов, разгранижая путь, путь считается путем спецификации файла.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если в пути нет символов, разгранижая путь, или FALSE, если есть символы, разгранижая путь.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)

## <a name="cpathtisprefix"></a><a name="isprefix"></a>Cpatht::IsPrefix

Вызовите этот метод, чтобы определить, содержит ли путь действительную префикс типа, пройденое *pszPrefix.*

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Параметры

*pszPrefix*<br/>
Приставка для поиска. Приставка является одним из этих типов: "C:\\\\",,", "..,". \\\\".

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь содержит префикс, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)информации см.

## <a name="cpathtisrelative"></a><a name="isrelative"></a>Cpatht::Относительно

Вызовите этот метод, чтобы определить, является ли путь относительным.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь является относительным, или FALSE, если он является абсолютным.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)информации см.

## <a name="cpathtisroot"></a><a name="isroot"></a>Cpatht::Isroot

Вызовите этот метод, чтобы определить, является ли путь корнем каталога.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь корень, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)

## <a name="cpathtissameroot"></a><a name="issameroot"></a>Cpatht::Issameroot

Вызовите этот метод, чтобы определить, есть ли у другого пути общий корневой компонент с текущим путем.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Параметры

*pszДругие*<br/>
Другой путь.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если обе строки имеют один и тот же корневой компонент, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [PathIssameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).

## <a name="cpathtisunc"></a><a name="isunc"></a>CPatht::ISUNC

Вызовите этот метод, чтобы определить, является ли путь действительной КООН (универсальная конвенция именования) для сервера и обмена.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь является действительным пути КООН, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)информации см.

## <a name="cpathtisuncserver"></a><a name="isuncserver"></a>CPatht::ISUNCServer

Вызовите этот метод, чтобы определить, является ли путь действительным коонт (универсальное наименование конвенции) путь только для сервера.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если строка является действительным пути КООН только для сервера (без имени общего доля), или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)информации см.

## <a name="cpathtisuncservershare"></a><a name="isuncservershare"></a>CPatht::ISUNCServerShare

Вызовите этот метод, чтобы определить, является ли путь действительным коонт (универсальная конвенция именования) \\ \ путь общего обмена,*доля* *сервера.*\ 

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь \\ \ находится в форме*доли* *сервера,*\ или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)информации см.

## <a name="cpathtm_strpath"></a><a name="m_strpath"></a>CPathT::m_strPath

Путь.

```
StringType m_strPath;
```

### <a name="remarks"></a>Примечания

`StringType`является параметром `CPathT`шаблона для .

## <a name="cpathtmakepretty"></a><a name="makepretty"></a>CPatht:MakePretty

Вызов исчерпайте этот метод, чтобы преобразовать путь ко всем символам нижнего регистра, чтобы придать пути последовательный внешний вид.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если путь был преобразован, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).

## <a name="cpathtmatchspec"></a><a name="matchspec"></a>Cpatht:MatchSpec

Вызовите этот метод для поиска пути для строки, содержащей тип соответствия подстановочных знаков.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Параметры

*pszSpec*<br/>
Указатель на нулевую строку с типом файла для поиска. Например, чтобы проверить, является ли файл на текущем пути файлом DOC, *pszSpec* должен быть установлен на "к.doc".

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если строка совпадает, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)

## <a name="cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::оператор

Этот оператор привязывает строку к пути.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Параметры

*pszMore*<br/>
Добавляемая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный путь.

## <a name="cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT:оператор const StringType&amp;

Этот оператор позволяет рассматривать объект как строку.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку, представляющую текущий путь, управляемый этим объектом.

## <a name="cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPatht:оператор Cpatht::PXSTR

Этот оператор позволяет рассматривать объект как строку.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку, представляющую текущий путь, управляемый этим объектом.

## <a name="cpathtoperator-stringtype-amp"></a><a name="operator_stringtype_amp"></a>CPathT:оператор StringType&amp;

Этот оператор позволяет рассматривать объект как строку.

```
operator StringType&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку, представляющую текущий путь, управляемый этим объектом.

## <a name="cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PXSTR

Постоянный тип строки.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Примечания

`StringType`является параметром `CPathT`шаблона для .

## <a name="cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR

Тип string.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Примечания

`StringType`является параметром `CPathT`шаблона для .

## <a name="cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::КвотаПространства

Вызовите этот метод, чтобы приложить путь в кавычки, если он содержит какие-либо пробелы.

```cpp
void QuoteSpaces();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)

## <a name="cpathtrelativepathto"></a><a name="relativepathto"></a>Cpatht:RelativepathTo

Вызовите этот метод, чтобы создать относительный путь из одного файла или папки в другой.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Параметры

*pszFrom*<br/>
Начало относительного пути.

*dwAttrFrom*<br/>
Атрибуты файла *pszFrom*. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, *pszFrom* считается каталогом; в противном случае, *pszFrom* считается файлом.

*pszTo*<br/>
Конечная точка относительного пути.

*dwAttrTo*<br/>
Атрибуты файла *pszTo*. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, *pszTo* считается каталогом; в противном случае, *pszTo* считается файлом.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)

## <a name="cpathtremoveargs"></a><a name="removeargs"></a>CPathT::RemoveArgs

Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.

```cpp
void RemoveArgs();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)

## <a name="cpathtremovebackslash"></a><a name="removebackslash"></a>CPatht::RemoveBackslash

Вызовите этот метод, чтобы удалить задний срез с пути.

```cpp
void RemoveBackslash();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)информации см.

## <a name="cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::RemoveBlanks

Вызовите этот метод, чтобы удалить все ведущие и задние пространства с пути.

```cpp
void RemoveBlanks();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)информации см.

## <a name="cpathtremoveextension"></a><a name="removeextension"></a>CPathT::RemoveExtension

Вызовите этот метод, чтобы удалить расширение файла из пути, если он есть.

```cpp
void RemoveExtension();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)см.

## <a name="cpathtremovefilespec"></a><a name="removefilespec"></a>Cpatht::RemoveFileSpec

Вызовите этот метод, чтобы удалить имя задней файла и backslash из пути, если он имеет их.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).

## <a name="cpathtrenameextension"></a><a name="renameextension"></a>CPatht::Переименование

Вызовите этот метод, чтобы заменить расширение имени файла в пути новым расширением. Если имя файла не содержит расширения, расширение будет прикреплено к концу пути.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Параметры

*pszExtension*<br/>
Новое расширение имени файла, предшествуемому символу "."

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)см.

## <a name="cpathtskiproot"></a><a name="skiproot"></a>CPathT::SkipRoot

Вызовите этот метод, чтобы разобрать путь, игнорируя письмо диска или КООН (универсальная конвенция именования) сервера/доли частей пути.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение начала подпата, следующего за корнем (письмо диска или сервер/доля КООН).

### <a name="remarks"></a>Примечания

Для получения дополнительной [информации](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)см.

## <a name="cpathtstrippath"></a><a name="strippath"></a>CPathT::StripPath

Вызовите этот метод, чтобы удалить часть пути полностью квалифицированного пути и имя файла.

```cpp
void StripPath();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)

## <a name="cpathtstriptoroot"></a><a name="striptoroot"></a>Cpatht::Striptoroot

Вызовите этот метод, чтобы удалить все части пути, за исключением корневой информации.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если действительное письмо диска было найдено в пути, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)

## <a name="cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::UnquoteSpaces

Вызовите этот метод, чтобы удалить кавычки из начала и конца пути.

```cpp
void UnquoteSpaces();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)

## <a name="cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR

Тип символа.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Примечания

`StringType`является параметром `CPathT`шаблона для .

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)
