---
title: Класс CInvalidargException
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: b28b6e84043b85a8117694a67ff5fff13e7c786b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372365"
---
# <a name="cinvalidargexception-class"></a>Класс CInvalidargException

Этот класс представляет условие исключения, связанного с недопустимым аргументом.

## <a name="syntax"></a>Синтаксис

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInvalidargException::CInvalidargException](#cinvalidargexception)|Конструктор.|

## <a name="remarks"></a>Примечания

Объект `CInvalidArgException` представляет собой недействительное условие исключения аргумента.

Для получения дополнительной информации об обработке исключений можно ознакомиться на теме [класса CException](../../mfc/reference/cexception-class.md) и [обращении с исключениями (MFC).](../../mfc/exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a>CInvalidargException::CInvalidargException

Конструктор.

```
CInvalidArgException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую; вызов глобальной функции **AfxThrowInvalidargException**.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSimpleException](../../mfc/reference/csimpleexception-class.md)
