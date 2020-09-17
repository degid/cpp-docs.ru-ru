---
title: Класс CObList
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: f24965357e0b71f28ba39b82d045600e7e1a44e2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749683"
---
# <a name="coblist-class"></a>Класс CObList

FSupports приказал списки `CObject` неуникальных указателей доступны последовательно или по указателю значение.

## <a name="syntax"></a>Синтаксис

```
class CObList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CObList::CObList](#coblist)|Строит пустой список указателей. `CObject`|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CObList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) к главе списка (делает новую голову).|
|[CObList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) к хвосту списка (делает новый хвост).|
|[CObList::Найти](#find)|Получает положение элемента, указанное значением указателя.|
|[CObList::FindIndex](#findindex)|Получает положение элемента, указанного индексом с нулевым уровнем.|
|[Коблист:GetAt](#getat)|Получает элемент в заданной позиции.|
|[CObList::GetCount](#getcount)|Возвращает количество элементов в этом списке.|
|[CObList::GetHead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CObList::GetHeadPosition](#getheadposition)|Возвращает положение головного элемента списка.|
|[CObList::GetNext](#getnext)|Получает следующий элемент для итерации.|
|[CObList::GetPrev](#getprev)|Получает предыдущий элемент для итерации.|
|[CObList::GetSize](#getsize)|Возвращает количество элементов в этом списке.|
|[CObList::GetTail](#gettail)|Возвращает хвостовой элемент списка (не может быть пустым).|
|[CObList::GetTailPosition](#gettailposition)|Возвращает положение хвостового элемента списка.|
|[CObList::InsertAfter](#insertafter)|Вставляет новый элемент после заданного положения.|
|[CObList::Вставитьперед](#insertbefore)|Вставляет новый элемент перед заданной позицией.|
|[COblist::Isempty](#isempty)|Тесты для состояния пустого списка (без элементов).|
|[CObList::RemoveAll](#removeall)|Удаляет все элементы из этого списка.|
|[Коблист:Удаление](#removeat)|Удаляет элемент из этого списка, указанный позицией.|
|[CObList::RemoveHead](#removehead)|Удаляет элемент из главы списка.|
|[CObList::RemoveTail](#removetail)|Удаляет элемент из хвоста списка.|
|[Коблист:SetAt](#setat)|Устанавливает элемент в заданной позиции.|

## <a name="remarks"></a>Примечания

`CObList`списки ведут себя как вдвойне связанные списки.

Переменная типа POSITION является ключом к списку. Вы можете использовать переменную POSITION как в качестве итератора, чтобы последовательно пересекать список, так и как закладку для удержания места. Однако позиция не является такой же, как индекс.

Элемент вставки очень быстро в списке голову, на хвосте, и на известном POSITION. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может быть медленным, если список длинный.

`CObList`включает IMPLEMENT_SERIAL макрос для поддержки сериализации и сброса его элементов. Если список `CObject` указателей хранится в архиве, либо с перегруженным оператором вставки, либо с функцией `Serialize` члена, каждый `CObject` элемент сериализуется по очереди.

Если вам нужна свалка отдельных `CObject` элементов в списке, необходимо установить глубину контекста дампа до 1 или больше.

Когда `CObList` объект удаляется или когда его элементы `CObject` удаляются, удаляются только указатели, а не объекты, на которые они ссылаются.

Вы можете получить свои `CObList`собственные классы из . Ваш новый класс списка, предназначенный для `CObject`хранения указателей на объекты, полученные из, добавляет новые члены данных и новые функции членов. Обратите внимание, что полученный список не является строго тип `CObject` безопасным, потому что он позволяет вставки любого указателя.

> [!NOTE]
> Если вы собираетесь выполнить [список,](run-time-object-model-services.md#implement_serial) необходимо использовать IMPLEMENT_SERIAL макрос в реализации производного класса.

Для получения дополнительной `CObList`информации [Collections](../../mfc/collections.md)об использовании , см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="coblistaddhead"></a><a name="addhead"></a>CObList::AddHead

Добавляет новый элемент или список элементов к главе этого списка.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
Указатель, `CObject` который будет добавлен в этот список.

*pNewList*<br/>
Указатель на `CObList` другой список. Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::AddHead`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddHead (пустота);** <strong>\*</strong> `newElement` **);**<br /><br /> **пустота AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead (конст CString** `newElement` **&);**<br /><br /> **POSITION AddHead (LPCTSTR);** `newElement` **);**<br /><br /> **пустота AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Примечания

Список может быть пустым до операции.

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Результаты этой программы следующие:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a>CObList::AddTail

Добавляет новый элемент или список элементов в хвост этого списка.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
Указатель, `CObject` который будет добавлен в этот список.

*pNewList*<br/>
Указатель на `CObList` другой список. Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

### <a name="remarks"></a>Примечания

Список может быть пустым до операции.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::AddTail`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddTail (пустота);** <strong>\*</strong> `newElement` **);**<br /><br /> **пустота AddTail (CPtrList);** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddTail (конст CString** `newElement` **&);**<br /><br /> **POSITION AddTail (LPCTSTR);** `newElement` **);**<br /><br /> **пустота AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Результаты этой программы следующие:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a>CObList::CObList

Строит пустой `CObject` список указателей.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Детализация распределения памяти для расширения списка.

### <a name="remarks"></a>Примечания

По мере роста списка память распределяется в единицах записей *nBlockSize.* Если выделение памяти завершается неудачей, он `CMemoryException` бросается.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::CObList`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **no 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **No 10);**|

### <a name="example"></a>Пример

  Ниже приведен список `CObject`класса, `CAge` используемого во всех примерах коллекции:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Ниже приведен пример `CObList` использования конструктора:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a>CObList::Найти

Поиск по списку последовательно, чтобы найти `CObject` первый указатель, соответствующий указанному `CObject` указателю.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Параметры

*searchValue*<br/>
Указатель объекта можно найти в этом списке.

*startAfter*<br/>
Стартовая позиция для поиска.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если объект не найден.

### <a name="remarks"></a>Примечания

Обратите внимание, что сравниваются значения указателя, а не содержимое объектов.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::Find`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION Найти (недействительным** <strong>\*</strong> `searchValue` **, POSITION** `startAfter` **- NULL ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION Найти (LPCTSTR** `searchValue` **, POSITION** `startAfter` **- NULL ) const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a>CObList::FindIndex

Использует значение *nIndex* в качестве индекса в списке.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс элемента списка, который можно найти.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если *nIndex* слишком велик. (Основа генерирует утверждение, если *nIndex* отрицательный.)

### <a name="remarks"></a>Примечания

Он начинает последовательное сканирование от главы списка, останавливаясь на *n*th элемент.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::FindIndex`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION FindIndex (INT_PTR)** `nIndex` **const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION FindIndex (INT_PTR)** `nIndex` **const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a>Коблист:GetAt

Переменная типа POSITION является ключом к списку.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Значение POSITION, возвращаемые предыдущим `GetHeadPosition` вызовом функции или `Find` функции участника.

### <a name="return-value"></a>Возвращаемое значение

Смотрите описание значения возврата для [GetHead.](#gethead)

### <a name="remarks"></a>Примечания

Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. `GetAt`получает указатель, `CObject` связанный с заданной позицией.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* пустота& GetAt (POSITION** *позиции* **) const;**<br /><br /> **\* пустота& GetAt (позиция ПОЗИЦИОНЕ);** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetAt (POSITION** *позиция)* **const;**<br /><br /> **Cstring& GetAt (позиция** *position* **ПОЗИЦИОН);**|

### <a name="example"></a>Пример

  Смотрите пример [FindIndex](#findindex).

## <a name="coblistgetcount"></a><a name="getcount"></a>CObList::GetCount

Получает количество элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее количество элементов.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetCount`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a>CObList::GetHead

Получает `CObject` указатель, представляющий головной элемент этого списка.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CObList`на, `GetHead` `CObject` затем возвращает указатель. Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CObList`указатель `GetHead` на, затем `CObject` возвращает ссылку на указатель. Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `GetHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetHead`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* пустой& GetHead () Const; пустота\*& GetHead();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead() Const; CString& GetHead();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

Следующий пример иллюстрирует использование `GetHead` на левой стороне оператора назначения.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a>CObList::GetHeadPosition

Получает положение головного элемента этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetHeadPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION GetHeadPosition( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetHeadPosition( ) const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a>CObList::GetNext

Получает элемент списка, идентифицированный *rPosition,* затем `POSITION` устанавливает *rPosition* к значению следующей записи в списке.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение POSITION, `GetNext`возвращенное предыдущим вызовом `GetHeadPosition`функции участника.

### <a name="return-value"></a>Возвращаемое значение

Смотрите описание значения возврата для [GetHead.](#gethead)

### <a name="remarks"></a>Примечания

Вы можете `GetNext` использовать в цикле передних итерации, если `GetHeadPosition` `Find`вы установите исходное положение с вызовом или .

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является последним в списке, то новое значение *rPosition* устанавливается на NULL.

Можно удалить элемент во время итерации. Смотрите пример [для RemoveAt](#removeat).

> [!NOTE]
> По состоянию на MFC 8.0 конст `const CObject*` версия `const CObject*&`этого метода изменилась, чтобы вернуться вместо .  Это изменение было сделано, чтобы привести компилятор в соответствие со стандартом C'.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetNext`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Результаты этой программы следующие:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a>CObList::GetPrev

Получает элемент списка, идентифицированный *rPosition,* затем устанавливает *rPosition* к значению POSITION предыдущей записи в списке.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение POSITION, `GetPrev` возвращенное предыдущим или другим вызовом функции участника.

### <a name="return-value"></a>Возвращаемое значение

Смотрите описание значения возврата для [GetHead.](#gethead)

### <a name="remarks"></a>Примечания

Вы можете `GetPrev` использовать в обратном цикле итерации, если `GetTailPosition` `Find`вы установите исходное положение с вызовом или .

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является первым в списке, то новое значение *rPosition* устанавливается на NULL.

> [!NOTE]
> По состоянию на MFC 8.0 конст `const CObject*` версия `const CObject*&`этого метода изменилась, чтобы вернуться вместо .  Это изменение было сделано, чтобы привести компилятор в соответствие со стандартом C'.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetPrev`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Результаты этой программы следующие:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a>CObList::GetSize

Возвращает количество элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов в списке.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize() Const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize() Const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a>CObList::GetTail

Получает `CObject` указатель, представляющий элемент хвоста этого списка.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Возвращаемое значение

Смотрите описание значения возврата для [GetHead.](#gethead)

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `GetTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetTail`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* пустой& GetTail () const; пустота\*& GetTail();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail() Const; CString& GetTail();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a>CObList::GetTailPosition

Получает положение хвостового элемента этого списка; **NULL,** если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::GetTailPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION GetTailPosition( ) конст;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetTailPosition( ) конст;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a>CObList::InsertAfter

Добавляет элемент в этот список после элемента в указанном положении.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Значение POSITION возвращается `GetNext`предыдущим `GetPrev`вызовом функции `Find` участника.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот список.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::InsertAfter`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION InsertAfter (ПОЗИЦИЯ** *положение* , **пустота);** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION InsertAfter (ПОЗИЦИЯ** *позиции* , **Const CString&);** `newElement` **);**<br /><br /> **POSITION InsertAfter** *(ПОЗИЦИЯ позиция* , **LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое такое же, как параметр *позиции.*

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Результаты этой программы следующие:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a>CObList::Вставитьперед

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Значение POSITION возвращается `GetNext`предыдущим `GetPrev`вызовом функции `Find` участника.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот список.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::InsertBefore`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION InsertBefore (POSITION** *положение* **, пустота);** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION InsertBefore (POSITION** *положение* **, Const CString** `newElement` **&);**<br /><br /> **POSITION InsertBefore** *(ПОЗИЦИЯ позиция* , **LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Результаты этой программы следующие:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a>COblist::Isempty

Указывает, не содержит ли этот список элементов.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если этот список пуст; в противном случае 0.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::IsEmpty`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty() Const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty() Const;**|

### <a name="example"></a>Пример

  Смотрите пример [для RemoveAll](#removeall).

## <a name="coblistremoveall"></a><a name="removeall"></a>CObList::RemoveAll

Удаляет все элементы из этого списка `CObList` и освобождает связанную память.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Ошибка не генерируется, если список уже пуст.

При удалении `CObList`элементов из списка вы удалите указатели объекта из списка. Вы несете ответственность за удаление самих объектов.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::RemoveAll`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**пустота RemoveAll();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**пустота RemoveAll();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a>Коблист:Удаление

Удаляет указанный элемент из этого списка.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Положение элемента, который будет удален из списка.

### <a name="remarks"></a>Примечания

При удалении элемента из `CObList`списка вы удалите указатель объекта из списка. Вы несете ответственность за удаление самих объектов.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::RemoveAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (позиция** *position* **POSITION);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (позиция** *position* **POSITION);**|

### <a name="example"></a>Пример

  Будьте осторожны при удалении элемента во время итерации списка. В следующем примере показана техника удаления, которая гарантирует действительное значение **POSITION** для [GetNext.](#getnext)

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Результаты этой программы следующие:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a>CObList::RemoveHead

Удаляет элемент из головы списка и возвращает указатель к нему.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель `CObject` ранее возглавлял список.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::RemoveHead`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**пустота\* RemoveHead();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a>CObList::RemoveTail

Удаляет элемент из хвоста списка и возвращает указатель к нему.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, который находился в хвосте списка.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::RemoveTail`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**пустота\* RemoveTail();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a>Коблист:SetAt

Устанавливает элемент в заданной позиции.

```cpp
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
POSITION элемента, который будет установлен.

*newElement*<br/>
Указатель, `CObject` который будет записан в список.

### <a name="remarks"></a>Примечания

Переменная типа POSITION является ключом к списку. Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. `SetAt`записывает `CObject` указатель на указанную позицию в списке.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

В следующей таблице показаны другие функции участника, которые аналогичны `CObList::SetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**пустота SetAt (POSITION** `pos` **, Const CString** `newElement` **&);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**недействительный SetAt (ПОЗИЦИЯ** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](#coblist) для перечисления `CAge` класса.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Результаты этой программы следующие:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStringList](../../mfc/reference/cstringlist-class.md)<br/>
[Класс CPtrList](../../mfc/reference/cptrlist-class.md)
