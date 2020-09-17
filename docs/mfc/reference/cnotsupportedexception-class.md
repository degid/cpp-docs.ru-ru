---
title: Класс CNotSupportedException
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: b859b939baef018e69b245e597eea90e608253ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363197"
---
# <a name="cnotsupportedexception-class"></a>Класс CNotSupportedException

Представляет исключение, являющееся результатом запроса неподдерживаемой возможности.

## <a name="syntax"></a>Синтаксис

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CNotSupportedИсключение::CNotSupportedИсключение](#cnotsupportedexception)|Формирует объект `CNotSupportedException`.|

## <a name="remarks"></a>Примечания

Никакая дальнейшая квалификация не требуется или невозможна.

Для получения дополнительной `CNotSupportedException`информации [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)об использовании см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a>CNotSupportedИсключение::CNotSupportedИсключение

Формирует объект `CNotSupportedException`.

```
CNotSupportedException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, а скорее позвоните в глобальную функцию [AfxThrowNotSupported.](exception-processing.md#afxthrownotsupportedexception) для получения дополнительной информации об [Exception Handling in MFC](../exception-handling-in-mfc.md)обработке исключений см.

## <a name="see-also"></a>См. также раздел

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)
