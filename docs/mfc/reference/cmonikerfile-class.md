---
title: Класс CMonikerFile
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: fc74ad2499fcde63faa2c5859a87fd9ffd2846eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319774"
---
# <a name="cmonikerfile-class"></a>Класс CMonikerFile

Представляет поток данных [(IStream](/windows/win32/api/objidl/nn-objidl-istream)), названный [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker).

## <a name="syntax"></a>Синтаксис

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Формирует объект `CMonikerFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::Закрыть](#close)|Отсоединяет и выпускает поток и выпускает кличка.|
|[CMonikerFile::Detach](#detach)|Отделяет `IMoniker` от этого `CMonikerFile` объекта.|
|[CMonikerFile::GetMoniker](#getmoniker)|Возвращает текущее прозвище.|
|[CMonikerFile::Открыто](#open)|Открывает указанный файл для получения потока.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|Получает контекст связывания или создает инициализированный контекст связывания по умолчанию.|

## <a name="remarks"></a>Примечания

Кличка содержит информацию, похожую на имя пути к файлу. Если у вас есть указатель на интерфейс `IMoniker` объекта моникера, вы можете получить доступ к идентифицированному файлу без какой-либо другой конкретной информации о том, где файл на самом деле находится.

Полученные `COleStreamFile`из `CMonikerFile` , берет прозвище или строки представление он может сделать в прозвище и связывается с потоком, для которого прозвище имя. Затем вы можете читать и писать в этот поток. `CMonikerFile` Реальная цель заключается в `IStream`том, `IMoniker`чтобы обеспечить простой доступ к s имени `CFile` s так, что вам не придется связываться с потоком самостоятельно, но есть функциональность для потока.

`CMonikerFile`не может быть использован для привязки к чему-либо, кроме потока. Если вы хотите привязаться к хранению `IMoniker` или объекту, вы должны использовать интерфейс напрямую.

Для получения дополнительной информации о потоках и кличках, [см. COleStreamFile](../../mfc/reference/colestreamfile-class.md) в *MFC Reference* и [IStream](/windows/win32/api/objidl/nn-objidl-istream) и [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="cmonikerfileclose"></a><a name="close"></a>CMonikerFile::Закрыть

Вызовите эту функцию, чтобы отсоединить и освободить поток и выпустить кличка.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Можно вызвать неоткрытые или уже закрытые потоки.

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>CMonikerFile::CMonikerFile

Формирует объект `CMonikerFile`.

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>CMonikerFile::CreateBindContext

Вызовите эту функцию, чтобы создать инициализированный контекст связывания по умолчанию.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Параметры

*pОшибка*<br/>
Указатель на исключение файла. В случае ошибки, она будет установлена на причину.

### <a name="return-value"></a>Возвращаемое значение

Указатель на контекст связывать [IBindCtx,](/windows/win32/api/objidl/nn-objidl-ibindctx) чтобы связать с в случае успеха; в противном случае NULL. Если экземпляр был открыт `IBindHost` с интерфейсом, контекст связывания извлекается из `IBindHost`. Если интерфейс `IBindHost` отсутствует или интерфейс не возвращает контекст связывания, создается контекст связывания. Для описания интерфейса [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\)) см.

### <a name="remarks"></a>Примечания

Контекст связывания — это объект, который хранит информацию о конкретной операции связывания моникера. Эту функцию можно переопределить, чтобы обеспечить пользовательский контекст связывания.

## <a name="cmonikerfiledetach"></a><a name="detach"></a>CMonikerFile::Detach

Вызовите эту функцию, чтобы закрыть поток.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*pОшибка*<br/>
Указатель на исключение файла. В случае ошибки, она будет установлена на причину.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a>CMonikerFile::GetMoniker

Вызов исправьте эту функцию, чтобы получить указатель к текущему прозвищу.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий интерфейс моникера [(IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)).

### <a name="remarks"></a>Примечания

Поскольку `CMonikerFile` это не интерфейс, возврат указателя не приращает количество ссылок (через [AddRef),](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)и прозвище освобождается при освобождении `CMonikerFile` объекта. Если вы хотите, чтобы держаться за прозвище или `AddRef` освободить его самостоятельно, вы должны его.

## <a name="cmonikerfileopen"></a><a name="open"></a>CMonikerFile::Открыто

Вызовите эту функцию участника, чтобы открыть файл или объект моникера.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
URL или имя файла, которое будет открыто.

*pОшибка*<br/>
Указатель на исключение файла. В случае ошибки, она будет установлена на причину.

*pMoniker*<br/>
Указатель на интерфейс `IMoniker` моникера, который будет использоваться для получения потока.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Параметр *lpszURL* не может быть использован на Macintosh. Только *pMoniker* форма `Open` может быть использована на Macintosh.

Для параметра *lpszURL* можно использовать URL или имя файла. Пример:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- или -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс ColeStreamFile](../../mfc/reference/colestreamfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
