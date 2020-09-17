---
title: Класс CTypedPtrList
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 9f4899d4470903a4145cc171579e4b251b984f95
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747184"
---
# <a name="ctypedptrlist-class"></a>Класс CTypedPtrList

Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrList`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс класса списка набранных указателей; должен быть класс списка `CObList` указателей (или). `CPtrList`

*ТИП*<br/>
Тип элементов, хранящихся в списке базового класса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) к главе списка (делает новую голову).|
|[CTypedPtrList:AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) к хвосту списка (делает новый хвост).|
|[CTypedPtrList::GetAt](#getat)|Получает элемент в заданной позиции.|
|[CTypedPtrList::GetHead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CTypedPtrList::GetNext](#getnext)|Получает следующий элемент для итерации.|
|[CTypedPtrList::GetPrev](#getprev)|Получает предыдущий элемент для итерации.|
|[CTypedPtrList::GetTail](#gettail)|Возвращает хвостовой элемент списка (не может быть пустым).|
|[CTypedPtrlist::RemoveHead](#removehead)|Удаляет элемент из главы списка.|
|[CTypedPtrlist::RemoveTail](#removetail)|Удаляет элемент из хвоста списка.|
|[CTypedPtrList::SetAt](#setat)|Устанавливает элемент в заданной позиции.|

## <a name="remarks"></a>Примечания

При `CTypedPtrList` использовании, `CObList` `CPtrList`а не в том, что объект проверки типа СЗ помогает устранить ошибки, вызванные несовместимыми типами указателей.

Кроме того, `CTypedPtrList` обертка выполняет большую часть литья, `CObList` `CPtrList`которые будут необходимы, если вы использовали или .

Поскольку `CTypedPtrList` все функции являются внеочередными, использование этого шаблона не оказывает существенного влияния на размер или скорость кода.

Списки, `CObList` полученные из могут быть сериализованы, но те, полученные из `CPtrList` не может.

Когда `CTypedPtrList` объект удаляется или когда его элементы удаляются, удаляются только указатели, а не объекты, на которые они ссылаются.

Для получения дополнительной `CTypedPtrList`информации об [Template-Based Classes](../../mfc/template-based-classes.md)использовании , [см.](../../mfc/collections.md)

## <a name="example"></a>Пример

Этот пример создает `CTypedPtrList`экземпляр: добавляет один объект, сериализирует список на диск, а затем удаляет объект:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a>CTypedPtrList::AddHead

Эта функция `BASE_CLASS`участника **вызывает::AddHead**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип элементов, хранящихся в списке базового класса.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот список. Допускается значение NULL.

*BASE_CLASS*<br/>
Базовый класс класса списка набранных указателей; должен быть класс списка указателей [(CObList](../../mfc/reference/coblist-class.md) или [CPtrList).](../../mfc/reference/cptrlist-class.md)

*pNewList*<br/>
Указатель на другой объект [CTypedPtrList.](../../mfc/reference/ctypedptrlist-class.md) Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

### <a name="remarks"></a>Примечания

Первая версия добавляет новый элемент перед главой списка. Вторая версия добавляет еще один список элементов перед головой.

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a>CTypedPtrList:AddTail

Эта функция `BASE_CLASS`участника **вызывает::AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип элементов, хранящихся в списке базового класса.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот список. Допускается значение NULL.

*BASE_CLASS*<br/>
Базовый класс класса списка набранных указателей; должен быть класс списка указателей [(CObList](../../mfc/reference/coblist-class.md) или [CPtrList).](../../mfc/reference/cptrlist-class.md)

*pNewList*<br/>
Указатель на другой объект [CTypedPtrList.](../../mfc/reference/ctypedptrlist-class.md) Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

### <a name="remarks"></a>Примечания

Первая версия добавляет новый элемент после хвоста списка. Вторая версия добавляет еще один список элементов после хвоста списка.

## <a name="ctypedptrlistgetat"></a><a name="getat"></a>CTypedPtrList::GetAt

Переменная типа POSITION является ключом к списку.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в списке.

*Позиции*<br/>
Значение POSITION, возвращаемые предыдущим `GetHeadPosition` вызовом функции или `Find` функции участника.

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CTypedPtrList`на, затем `GetAt` возвращает указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CTypedPtrList`указатель `GetAt` на, затем возвращает ссылку на указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. `GetAt`получает указатель, `CObject` связанный с заданной позицией.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Эта влиневая функция вызывает `BASE_CLASS` **::GetAt**.

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a>CTypedPtrList::GetHead

Получает указатель, представляющий головной элемент этого списка.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CTypedPtrList`на, затем `GetHead` возвращает указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CTypedPtrList`указатель `GetHead` на, затем возвращает ссылку на указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `GetHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a>CTypedPtrList::GetNext

Получает элемент списка, идентифицированный *rPosition,* затем устанавливает *rPosition* к значению POSITION следующей записи в списке.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, содержащихся в этом списке.

*rPosition*<br/>
Ссылка на значение POSITION, `GetNext`возвращенное предыдущим вызовом `GetHeadPosition`функции участника.

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CTypedPtrList`на, затем `GetNext` возвращает указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CTypedPtrList`указатель `GetNext` на, затем возвращает ссылку на указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Вы можете `GetNext` использовать в цикле передних итерации, если `GetHeadPosition` вы установите исходное положение с вызовом в или [CPtrList::Find](../../mfc/reference/coblist-class.md#find).

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является последним в списке, то новое значение *rPosition* устанавливается на NULL.

Можно удалить элемент во время итерации. Смотрите пример [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a>CTypedPtrList::GetPrev

Получает элемент списка, идентифицированный *rPosition,* затем устанавливает *rPosition* к значению POSITION предыдущей записи в списке.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, содержащихся в этом списке.

*rPosition*<br/>
Ссылка на значение POSITION, `GetPrev` возвращенное предыдущим или другим вызовом функции участника.

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CTypedPtrList`на, затем `GetPrev` возвращает указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CTypedPtrList`указатель `GetPrev` на, затем возвращает ссылку на указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Вы можете `GetPrev` использовать в обратном цикле итерации, если `GetTailPosition` `Find`вы установите исходное положение с вызовом или .

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является первым в списке, то новое значение *rPosition* устанавливается на NULL.

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a>CTypedPtrList::GetTail

Получает указатель, представляющий головной элемент этого списка.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список доступен через указатель `const CTypedPtrList`на, затем `GetTail` возвращает указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию только на правой стороне оператора назначения и таким образом защищает список от модификации.

Если список доступен непосредственно или через `CTypedPtrList`указатель `GetTail` на, затем возвращает ссылку на указатель типа, указанного параметром шаблона *TYPE.* Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `GetTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a>CTypedPtrlist::RemoveHead

Удаляет элемент из головы списка и возвращает его.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Указатель ранее возглавлял список. Этот указатель имеет тип, указанный параметром шаблона *TYPE.*

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a>CTypedPtrlist::RemoveTail

Удаляет элемент из хвоста списка и возвращает его.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Указатель ранее в хвосте списка. Этот указатель имеет тип, указанный параметром шаблона *TYPE.*

### <a name="remarks"></a>Примечания

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

## <a name="ctypedptrlistsetat"></a><a name="setat"></a>CTypedPtrList::SetAt

Эта функция `BASE_CLASS`участника **вызывает ::SetAt**.

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
POSITION элемента, который будет установлен.

*ТИП*<br/>
Тип элементов, хранящихся в списке базового класса.

*newElement*<br/>
Указатель объекта, который должен быть записан в список.

### <a name="remarks"></a>Примечания

Переменная типа POSITION является ключом к списку. Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. `SetAt`записывает указатель объекта на указанное положение в списке.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Для более подробных замечаний, [см. Coblist::Setat](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPtrList](../../mfc/reference/cptrlist-class.md)<br/>
[Класс CObList](../../mfc/reference/coblist-class.md)
