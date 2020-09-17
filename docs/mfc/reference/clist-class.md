---
title: Класс CList
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: 7ba85445e3aba1df853d7d3666c92fdabdfa3970
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182880"
---
# <a name="clist-class"></a>Класс CList

Поддерживает упорядоченные списки неуникальных объектов, доступные последовательно или по значению.

## <a name="syntax"></a>Синтаксис

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CList:: CList](#clist)|Конструирует пустой упорядоченный список.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CList:: Аддхеад](#addhead)|Добавляет элемент (или все элементы из другого списка) в заголовок списка (создает новый заголовок).|
|[CList:: AddTail](#addtail)|Добавляет элемент (или все элементы из другого списка) в конец списка (создает новый хвост).|
|[CList:: Find](#find)|Возвращает расположение элемента, заданного значением указателя.|
|[CList:: FindIndex](#findindex)|Возвращает расположение элемента, указанного с помощью индекса, начинающегося с нуля.|
|[CList:: GetAt](#getat)|Возвращает элемент в заданной позиции.|
|[CList:: NOCOUNT](#getcount)|Возвращает число элементов в этом списке.|
|[CList:: onhead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CList:: Жесеадпоситион](#getheadposition)|Возвращает расположение головного элемента списка.|
|[CList:: GetNext](#getnext)|Возвращает следующий элемент для итерации.|
|[CList:: prev](#getprev)|Возвращает предыдущий элемент для итерации.|
|[CList:: DataSize](#getsize)|Возвращает число элементов в этом списке.|
|[CList:: tail](#gettail)|Возвращает заключительный элемент списка (не может быть пустым).|
|[CList:: Жеттаилпоситион](#gettailposition)|Возвращает расположение элемента хвоста в списке.|
|[CList:: InsertAfter](#insertafter)|Вставляет новый элемент после заданной позицией.|
|[CList::InsertBefore](#insertbefore)|Вставляет новый элемент перед заданной позицией.|
|[CList:: IsEmpty](#isempty)|Проверяет условие пустого списка (нет элементов).|
|[CList:: RemoveAll](#removeall)|Удаляет все элементы из этого списка.|
|[CList:: RemoveAt](#removeat)|Удаляет элемент из этого списка, заданный по положению.|
|[CList:: Ремовехеад](#removehead)|Удаляет элемент из заголовка списка.|
|[CList:: Ремоветаил](#removetail)|Удаляет элемент из хвоста списка.|
|[CList:: SetAt](#setat)|Задает элемент в заданной позиции.|

#### <a name="parameters"></a>Параметры

*TYPE*<br/>
Тип объекта, хранящегося в списке.

*ARG_TYPE*<br/>
Тип, используемый для ссылки на объекты, хранящиеся в списке. Может быть ссылкой.

## <a name="remarks"></a>Примечания

`CList`списки ведут себя как двунаправленные списки.

Переменная типа "расположение" является ключом для списка. Можно использовать переменную позиции в качестве итератора для последовательного прохода по списку и в виде закладки для размещения места. Однако позиция не совпадает с индексом.

Вставка элемента происходит очень быстро в заголовке списка, в хвосте и в известной позиции. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может выполняться медленно, если список длинный.

Если вам нужен дамп отдельных элементов в списке, необходимо задать для контекста дампа значение 1 или больше.

Некоторые функции элементов этого класса вызывают глобальные вспомогательные функции, которые необходимо настроить для большинства случаев использования `CList` класса. См. раздел [вспомогательные методы класса Collection](../../mfc/reference/collection-class-helpers.md) в разделе "макросы и глобальные".

Дополнительные сведения об использовании `CList` см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a>CList:: Аддхеад

Добавляет новый элемент или список элементов в заголовок этого списка.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*невелемент*<br/>
Новый элемент.

*пневлист*<br/>
Указатель на другой `CList` список. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

### <a name="remarks"></a>Примечания

Перед операцией список может быть пустым.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>CList:: AddTail

Добавляет новый элемент или список элементов в конец этого списка.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*невелемент*<br/>
Элемент, добавляемый в список.

*пневлист*<br/>
Указатель на другой `CList` список. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

### <a name="remarks"></a>Примечания

Перед операцией список может быть пустым.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>CList:: CList

Конструирует пустой упорядоченный список.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*нблокксизе*<br/>
Гранулярность выделения памяти для расширения списка.

### <a name="remarks"></a>Примечания

По мере роста списка память выделяется в единицах *нблокксизе* записей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>CList:: Find

Выполняет поиск в списке последовательно, чтобы найти первый элемент, соответствующий указанному *сеарчвалуе*.

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*сеарчвалуе*<br/>
Значение, которое должно быть найдено в списке.

*стартафтер*<br/>
Начальное расположение для поиска. Если значение не указано, поиск начинается с головного элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если объект не найден.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>CList:: FindIndex

Использует значение *ниндекс* в качестве индекса в списке.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс элемента списка, который необходимо найти.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; NULL, если *ниндекс* является отрицательным или слишком большим.

### <a name="remarks"></a>Примечания

Он запускает последовательное сканирование из заголовка списка, останавливаясь на *n*-ом элементе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>CList:: GetAt

Возвращает элемент списка в заданной позиции.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип объекта в списке.

*разместить*<br/>
Местоположение элемента, который необходимо получить.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для `GetHead` .

### <a name="remarks"></a>Примечания

`GetAt`Возвращает элемент (или ссылку на элемент), связанный с заданной позицией. Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. Переменная типа "расположение" является ключом для списка.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

### <a name="example"></a>Пример

  См. пример для [CList:: жесеадпоситион](#getheadposition).

## <a name="clistgetcount"></a><a name="getcount"></a>CList:: NOCOUNT

Возвращает число элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение, содержащее число элементов.

### <a name="remarks"></a>Примечания

Вызов этого метода приведет к формированию того же результата, что и метод [CList:: resize](#getsize) .

### <a name="example"></a>Пример

  См. пример для [CList:: ремовехеад](#removehead).

## <a name="clistgethead"></a><a name="gethead"></a>CList:: onhead

Возвращает элемент head (или ссылку на головной элемент) этого списка.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип объекта в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список имеет значение **`const`** , `GetHead` возвращает копию элемента в заголовке списка. Это позволяет использовать функцию только с правой стороны оператора присваивания и защищать список от изменения.

Если список не имеет значение **`const`** , `GetHead` возвращает ссылку на элемент в заголовке списка. Это позволяет использовать функцию с любой стороны оператора присваивания и тем самым допустить изменение записей в списке.

### <a name="remarks"></a>Примечания

Перед вызовом необходимо убедиться, что список не пуст `GetHead` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>CList:: Жесеадпоситион

Возвращает расположение головного элемента этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>CList:: GetNext

Возвращает элемент List, определенный параметром *rPosition*, а затем устанавливает *rPosition* в значение value следующей записи в списке.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в списке.

*rPosition*<br/>
Ссылка на значение расположения, возвращенное предыдущим `GetNext` , [жесеадпоситион](#getheadposition)или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

Если список имеет значение **`const`** , `GetNext` возвращает копию элемента списка. Это позволяет использовать функцию только с правой стороны оператора присваивания и защищать список от изменения.

Если список не имеет значение **`const`** , `GetNext` возвращает ссылку на элемент списка. Это позволяет использовать функцию с любой стороны оператора присваивания и тем самым допустить изменение записей в списке.

### <a name="remarks"></a>Примечания

Можно использовать `GetNext` в цикле прямой итерации, если исходное расположение устанавливается с вызовом `GetHeadPosition` или `Find` .

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является последним в списке, новое значение устанавливается `rPosition` в значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>CList:: prev

Возвращает элемент списка, заданный параметром `rPosition` , а затем устанавливает `rPosition` для значение расположения предыдущей записи в списке.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в списке.

*rPosition*<br/>
Ссылка на значение расположения, возвращаемое предыдущим `GetPrev` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

Если список имеет значение **`const`** , `GetPrev` возвращает копию элемента в заголовке списка. Это позволяет использовать функцию только с правой стороны оператора присваивания и защищать список от изменения.

Если список не имеет значение **`const`** , `GetPrev` возвращает ссылку на элемент списка. Это позволяет использовать функцию с любой стороны оператора присваивания и тем самым допустить изменение записей в списке.

### <a name="remarks"></a>Примечания

Можно использовать `GetPrev` в цикле обратных итераций, если исходное расположение устанавливается с вызовом `GetTailPosition` или `Find` .

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является первым в списке, новое значение *rPosition* устанавливается в NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>CList:: DataSize

Возвращает число элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов в списке.  Вызов этого метода приведет к формированию того же результата, что и метод [CList:: NOCOUNT](#getcount) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>CList:: tail

Возвращает `CObject` указатель, представляющий элемент хвоста данного списка.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](../../mfc/reference/coblist-class.md#gethead).

### <a name="remarks"></a>Примечания

Перед вызовом необходимо убедиться, что список не пуст `GetTail` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](../../mfc/reference/coblist-class.md#isempty) , чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>CList:: Жеттаилпоситион

Возвращает расположение элемента хвоста в этом списке; Значение NULL, если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>CList:: InsertAfter

Добавляет элемент в этот список после элемента в указанной позиции.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*разместить*<br/>
Значение расположения, возвращенное предыдущим `GetNext` `GetPrev` `Find` вызовом функции-члена, или.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка.

*невелемент*<br/>
Элемент, добавляемый в список.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое можно использовать для итерации или извлечения элемента списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>CList:: методов insertBefore

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*разместить*<br/>
Значение расположения, возвращенное предыдущим `GetNext` `GetPrev` `Find` вызовом функции-члена, или.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*невелемент*<br/>
Элемент, добавляемый в список.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое можно использовать для итерации или извлечения элемента списка.

### <a name="remarks"></a>Примечания

Если параметр *позиции* имеет значение null, элемент вставляется в заголовок списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>CList:: IsEmpty

Указывает, содержит ли этот список элементы.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот список пуст; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>CList:: RemoveAll

Удаляет все элементы из этого списка и освобождает связанную память.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Если список уже пуст, то ошибка не создается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>CList:: RemoveAt

Удаляет указанный элемент из этого списка.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*разместить*<br/>
Расположение элемента, удаляемого из списка.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>CList:: Ремовехеад

Удаляет элемент из заголовка списка и возвращает указатель на него.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

Элемент, расположенный ранее в заголовке списка.

### <a name="remarks"></a>Примечания

Перед вызовом необходимо убедиться, что список не пуст `RemoveHead` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>CList:: Ремоветаил

Удаляет элемент из заключительного фрагмента списка и возвращает указатель на него.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

Элемент, который находится в заключительном фрагменте списка.

### <a name="remarks"></a>Примечания

Перед вызовом необходимо убедиться, что список не пуст `RemoveTail` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>CList:: SetAt

Переменная типа "расположение" является ключом для списка.

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
РАСПОЛОЖЕНИЕ элемента, который необходимо задать.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*невелемент*<br/>
Элемент, добавляемый в список.

### <a name="remarks"></a>Примечания

Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. `SetAt`Записывает элемент в указанную точку в списке.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример СОБРАНий MFC](../../overview/visual-cpp-samples.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кмап](../../mfc/reference/cmap-class.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)
