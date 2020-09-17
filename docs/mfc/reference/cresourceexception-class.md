---
title: Класс CResourceException
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: 557bfe1cc41c3dda65bd95d7d687820c0b9862b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368331"
---
# <a name="cresourceexception-class"></a>Класс CResourceException

Генерируется, когда Windows не может найти или выбрать запрошенный ресурс.

## <a name="syntax"></a>Синтаксис

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Формирует объект `CResourceException`.|

## <a name="remarks"></a>Примечания

Никакая дальнейшая квалификация не требуется или невозможна.

Для получения дополнительной `CResourceException`информации [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)об использовании см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>CResourceException::CResourceException

Формирует объект `CResourceException`.

```
CResourceException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, а скорее позвоните в глобальную функцию [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). для получения дополнительной информации об [Exception Handling in MFC](../exception-handling-in-mfc.md)исключениях см.

## <a name="see-also"></a>См. также раздел

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)
