---
title: Класс Иатлстрингмгр
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: a617ba829999e9e5778bd7f0091cfb0d624dce71
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832013"
---
# <a name="iatlstringmgr-class"></a>Класс Иатлстрингмгр

Этот класс представляет интерфейс для `CStringT` диспетчера памяти.

## <a name="syntax"></a>Синтаксис

```
__interface IAtlStringMgr
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[Памяти](#allocate)|Вызовите этот метод, чтобы выделить новую структуру строковых данных.|
|[Клонировать](#clone)|Вызовите этот метод, чтобы вернуть указатель на новый диспетчер строк для использования с другим экземпляром `CSimpleStringT` .|
|[Бесплатный](#free)|Вызовите этот метод, чтобы освободить структуру строковых данных.|
|[жетнилстринг](#getnilstring)|Возвращает указатель на `CStringData` объект, используемый пустыми строковыми объектами.|
|[Перераспределения](#reallocate)|Вызовите этот метод, чтобы перераспределить структуру строковых данных.|

## <a name="remarks"></a>Примечания

Этот интерфейс управляет памятью, используемой независимыми от MFC строковыми классами; например [ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)и [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).

Кроме того, этот класс можно использовать для реализации пользовательского диспетчера памяти для класса настраиваемых строк. Дополнительные сведения см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлсимпстр.h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a> Иатлстрингмгр:: allocate

Выделяет новую структуру строковых данных.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*наллокленгс*<br/>
Число символов в новом блоке памяти.

*нчарсизе*<br/>
Размер (в байтах) символьного типа, используемого диспетчером строк.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

> [!NOTE]
> Не сообщайте о сбое выделения, вызывая исключение. Вместо этого необходимо получить сигнал о неудачном выделении, возвращая значение NULL.

### <a name="remarks"></a>Примечания

Вызовите метод [иатлстрингмгр:: Free](#free) или [иатлстрингмгр:: reallocate](#reallocate) , чтобы освободить память, выделенную этим методом.

> [!NOTE]
> Примеры использования см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrclone"></a><a name="clone"></a> Иатлстрингмгр:: Clone

Возвращает указатель на новый диспетчер строк для использования с другим экземпляром `CSimpleStringT` .

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию объекта `IAtlStringMgr`.

### <a name="remarks"></a>Примечания

Обычно вызывается платформой, когда для новой строки требуется диспетчер строк. В большинстве случаев **`this`** возвращается указатель.

Однако если диспетчер памяти не поддерживает использование несколькими экземплярами `CSimpleStringT` , должен возвращаться указатель на совместно используемый диспетчер строк.

> [!NOTE]
> Примеры использования см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrfree"></a><a name="free"></a> Иатлстрингмгр:: Free

Освобождает строковую структуру данных.

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на блок памяти, который должен быть освобожден.

### <a name="remarks"></a>Примечания

Освобождает указанный блок памяти, выделенный ранее путем [выделения](#allocate) или [перераспределения](../../atl/reference/iatlmemmgr-class.md#reallocate).

> [!NOTE]
> Примеры использования см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a> Иатлстрингмгр:: Жетнилстринг

Возвращает указатель на структуру строковых данных для пустой строки.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, `CStringData` используемый для представления пустой строки.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы вернуть представление пустой строки.

> [!NOTE]
> При реализации диспетчера пользовательских строк эта функция никогда не должна завершаться ошибкой. Это можно обеспечить, внедрив экземпляр `CNilStringData` в класс диспетчера строк и возвращая указатель на этот экземпляр.

> [!NOTE]
> Примеры использования см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a> Иатлстрингмгр:: перераспределение

Перераспределяет структуру строковых данных.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на память, выделенную ранее этим диспетчером памяти.

*наллокленгс*<br/>
Число символов в новом блоке памяти.

*нчарсизе*<br/>
Размер (в байтах) символьного типа, используемого диспетчером строк.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы изменить размер существующего блока памяти, заданного в *pData*.

Вызовите метод [иатлстрингмгр:: Free](#free) , чтобы освободить память, выделенную этим методом.

> [!NOTE]
> Примеры использования см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
