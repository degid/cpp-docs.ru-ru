---
title: Приведение типов объектов классов MFC
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: e3702ced83021e42ac6bf71a78efc51fa07b8be9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840496"
---
# <a name="type-casting-of-mfc-class-objects"></a>Приведение типов объектов классов MFC

Макросы приведения типов предоставляют способ приведения заданного указателя на указатель, указывающий на объект определенного класса, с проверкой или без проверки того, что приведение является допустимым.

В следующей таблице перечислены макросы приведения типов MFC.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Макросы, которые приводят указатели к объектам классов MFC

|Имя|Описание|
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Приводит указатель к указателю на объект класса при проверке допустимости приведения.|
|[STATIC_DOWNCAST](#static_downcast)|Приводит указатель к объекту из одного класса в указатель связанного типа. В отладочной сборке вызывает ASSERT, если объект не является типом целевого типа.|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a> DYNAMIC_DOWNCAST

Предоставляет удобный способ приведения указателя на указатель на объект класса при проверке допустимости приведения.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Параметры

*class*<br/>
Имя класса.

*вид*<br/>
Указатель, приведенный к указателю на объект типа *Class*.

### <a name="remarks"></a>Примечания

Макрос преобразует параметр *указателя* в указатель на объект типа параметра *класса* .

Если объект, на который ссылается указатель, является «разновидностью» идентифицированного класса, макрос возвращает соответствующий указатель. Если он не является допустимым приведением, макрос возвращает значение NULL.

## <a name="static_downcast"></a><a name="static_downcast"></a> STATIC_DOWNCAST

Приводит *объект* к указателю на объект *class_name* .

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса, к которому выполняется приведение.

*объект*<br/>
Указатель, который должен быть приведен к указателю на объект *class_name* .

### <a name="remarks"></a>Примечания

*объект* должен иметь значение null или указывать на объект класса, который прямо или косвенно является производным от *class_name*. В сборках приложения с определенным символом препроцессора _DEBUG макрос будет утверждать, если *объект* не равен null, или если он указывает на объект, который не является "типом" класса, указанного в параметре *class_name* (см. [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). В сборках, не связанных с **_DEBUG** , макрос выполняет приведение без проверки типа.

Класс, указанный в параметре *class_name* , должен быть производным от класса `CObject` и должен использовать DECLARE_DYNAMIC и IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE, а также макросы DECLARE_SERIAL и IMPLEMENT_SERIAL, как описано в статье [класс CObject: создание производного класса от CObject](../../mfc/deriving-a-class-from-cobject.md).

Например, вы можете привести указатель к `CMyDoc` , вызываемому `pMyDoc` , к указателю на `CDocument` использование этого выражения:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Если не `pMyDoc` указывает на объект, производный напрямую или косвенно от `CDocument` , макрос будет утверждать.

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
