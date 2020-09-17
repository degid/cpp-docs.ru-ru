---
title: Класс Кптрлист
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: d7da4fe52d25d9ffdf6371aa40f41d7082f1165c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226845"
---
# <a name="cptrlist-class"></a>Класс Кптрлист

Поддерживает списки пустых указателей.

## <a name="syntax"></a>Синтаксис

```
class CPtrList : public CObject
```

## <a name="members"></a>Участники

Функции элементов `CPtrList` похожи на функции членов класса [коблист](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Когда `CObject` указатель отображается как параметр функции или возвращаемое значение, замените указатель на **`void`** .

`CObject*& CObList::GetHead() const;`

, например, преобразуется в

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Примечания

`CPtrList`включает в себя макрос IMPLEMENT_DYNAMIC для поддержки доступа к типу во время выполнения и дампа в `CDumpContext` объекте. Если требуется дамп отдельных элементов списка указателей, необходимо установить глубину контекста дампа в 1 или более.

Списки указателей не могут быть сериализованы.

При `CPtrList` удалении объекта или удалении его элементов удаляются только указатели, а не сущности, на которые они ссылаются.

Дополнительные сведения об использовании `CPtrList` см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл.h

## <a name="see-also"></a>См. также статью

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Коблист](../../mfc/reference/coblist-class.md)
