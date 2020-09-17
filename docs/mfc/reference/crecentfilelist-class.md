---
title: Класс CRecentFileList
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: a2102c6a39c14c548828e57ad1c49de6a5bc03dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370896"
---
# <a name="crecentfilelist-class"></a>Класс CRecentFileList

Поддерживает элемент управления последнего использовавшегося списка файлов (MRU).

## <a name="syntax"></a>Синтаксис

```
class CRecentFileList
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Формирует объект `CRecentFileList`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRecentFileList:Добавить](#add)|Добавляет файл в список файлов MRU.|
|[CRecentFileList:GetDisplayName](#getdisplayname)|Предоставляет имя отображения меню отимением файла MRU.|
|[CRecentFileList:GetSize](#getsize)|Извлекает количество файлов в списке файлов MRU.|
|[CRecentFileList:ReadList](#readlist)|Читает список файлов MRU из реестра или . Файл INI.|
|[CRecentFileList::Удалить](#remove)|Удаляет файл из списка файлов MRU.|
|[CRecentFileList::UpdateMenu](#updatemenu)|Обновление отображения меню в списке файлов MRU.|
|[CRecentFileList::WriteList](#writelist)|Записывает список файлов MRU из реестра или . Файл INI.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CRecentFileList::оператор \[\]](#operator_at)|Возвращает `CString` объект в заданной позиции.|

## <a name="remarks"></a>Примечания

Файлы могут быть добавлены или удалены из списка файлов MRU, список файлов может быть прочитан или записан в реестр или . Файл INI и меню, отображающее список файлов MRU, могут быть обновлены.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CRecentFileList`

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

## <a name="crecentfilelistadd"></a><a name="add"></a>CRecentFileList:Добавить

Добавляет файл в список самых недавно используемых файлов (MRU).

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Осведляет имя пути, которое будет добавлено в список.

*lpszAppID*<br/>
Определяет идентификатор модели пользователя приложения для приложения.

*pItem*<br/>
Укажите указатель на элемент Shell, который будет добавлен в список.

*pLink*<br/>
Укажите указатель на Shell Link, который будет добавлен в список.

*pidl*<br/>
Осваивает IDLIST для элемента оболочки, который должен быть добавлен в папку последних документов.

### <a name="remarks"></a>Примечания

Имя файла будет добавлено в верхней части списка MRU. Если имя файла уже существует в списке MRU, оно будет перемещено в верхнюю часть.

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a>CRecentFileList::CRecentFileList

Формирует объект `CRecentFileList`.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Параметры

*nСтарт*<br/>
Смещение для нумеринга в меню отображения MRU (самый недавно используемый) список файлов.

*lpszSection*<br/>
Указывает на название раздела реестра или приложения. Файл INI, в котором читается и/или пишется список файлов MRU.

*lpszEntryФормат*<br/>
Указывает на строку формата, которая будет использоваться для имен записей, хранящихся в реестре или в приложении. Файл INI.

*Nsize*<br/>
Максимальное количество файлов в списке файлов MRU.

*nMaxDispLen*<br/>
Максимальная длина, в символах, доступна для отображения в меню имени файла в списке файлов MRU.

### <a name="remarks"></a>Примечания

Строка формата, на которую указывает *lpszEntryFormat,* должна содержать "%d", которая будет использоваться для замены индекса каждого элемента MRU. Например, если строка `"file%d"` формата, то `file0`записи будут названы , `file1`и так далее.

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a>CRecentFileList:GetDisplayName

Получение имени отображения файла в списке файлов MRU для использования в меню в списке MRU.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>Параметры

*strName*<br/>
Полный путь файла, имя которого должно отображаться в списке меню файлов MRU.

*Nindex*<br/>
Нулевой индекс файла в списке файлов MRU.

*lpszCurDir*<br/>
Строка, держащая текущий каталог.

*nCurDir*<br/>
Длина текущей строки каталога.

*bAtLeastName*<br/>
Если ненулевой, указывает, что базовое имя файла должны быть возвращены, даже если она превышает максимальную `CRecentFileList` длину дисплея (прошел как *nMaxDispLen* параметр к конструктору).

### <a name="return-value"></a>Возвращаемое значение

**FALSE,** если в указанном индексе нет имени файла в списке самых последних используемых файлов (MRU).

### <a name="remarks"></a>Примечания

Если файл находится в текущем каталоге, функция оставляет каталог от дисплея. Если имя файла слишком длинное, каталог и расширение удаляются. Если имя файла еще слишком длинное, имя дисплея устанавливается на пустую строку, если *bAtLeastName* не является нулевым.

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a>CRecentFileList:GetSize

Извлекает количество файлов в списке файлов MRU.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество файлов в текущем списке самых последних файлов (MRU).

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a>CRecentFileList::оператор

Перегруженный подскрипт`[]`() Оператор `CString` возвращает одно указанное нулевым индексом в *nIndex.*

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс в `CString` наборе `CString`s.

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a>CRecentFileList:ReadList

Читает самый последний использованный (MRU) список файлов из реестра или приложения . Файл INI.

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a>CRecentFileList::Удалить

Удаляет файл из списка файлов MRU.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс файла, который будет удален из списка самых последних используемых файлов (MRU).

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a>CRecentFileList::UpdateMenu

Обновление отображения меню в списке файлов MRU.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на объект [CCmdUI](../../mfc/reference/ccmdui-class.md) для самого недавно используемого меню списка файлов (MRU).

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a>CRecentFileList::WriteList

Записывает самый недавно используемый (MRU) список файлов в реестр или в приложение . Файл INI.

```
virtual void WriteList();
```

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
