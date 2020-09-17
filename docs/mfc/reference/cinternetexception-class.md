---
title: Класс CInternetException
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: b0239afa2b984ccf93d661ec11f11013c89fd912
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372409"
---
# <a name="cinternetexception-class"></a>Класс CInternetException

Представляет условие исключения, касающееся интернет-операции.

## <a name="syntax"></a>Синтаксис

```
class CInternetException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetИсключение::CInternetИсключение](#cinternetexception)|Формирует объект `CInternetException`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CInternetИсключение::m_dwContext](#m_dwcontext)|Значение контекста, связанное с операцией, вызвавшей исключение.|
|[CInternetИсключение::m_dwError](#m_dwerror)|Ошибка, ставшая причиной исключения.|

## <a name="remarks"></a>Примечания

Класс `CInternetException` включает в себя два открытых члена данных: один содержит код ошибки, связанный с исключением, а другой содержит идентификатор контекста интернет-приложения, связанного с ошибкой.

Для получения дополнительной информации об идентификаторах контекста для интернет-приложений, [см.](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a>CInternetИсключение::CInternetИсключение

Эта функция члена вызывается при создании `CInternetException` объекта.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Параметры

*dwОшибка*<br/>
Ошибка, ставшая причиной исключения.

### <a name="remarks"></a>Примечания

Чтобы бросить CInternetException, позвоните в Глобальную функцию MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a>CInternetИсключение::m_dwContext

Значение контекста, связанное с связанной с интернет-операцией.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Примечания

Идентификатор контекста первоначально указан в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и передается MFC [классам CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- и [CInternetFile](../../mfc/reference/cinternetfile-class.md)- производным. Вы можете переопределить этот по умолчанию и назначить любой параметр *dwContext* значение по вашему выбору. *dwContext* связан с любой операцией данного объекта. *dwContext* определяет информацию о состоянии операции, возвращенную [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a>CInternetИсключение::m_dwError

Ошибка, ставшая причиной исключения.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Примечания

Значение ошибки может быть кодом системной ошибки, найденным в WINERROR. H или значение ошибки от WININET. H.

Для списка кодов ошибок Win32 [см.](/windows/win32/Debug/system-error-codes) Список сообщений об ошибках, связанных с Интернетом, см. Обе темы находятся в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
