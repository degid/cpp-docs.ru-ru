---
title: Класс COleDispatchException
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 4572b639b757569d8e3cfa731f99c123762f3900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375065"
---
# <a name="coledispatchexception-class"></a>Класс COleDispatchException

Обрабатывает исключения, относящиеся к интерфейсу OLE `IDispatch` и являющиеся ключевой частью OLE-автоматизации.

## <a name="syntax"></a>Синтаксис

```
class COleDispatchException : public CException
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeDispatchИсключение::m_dwHelpContext](#m_dwhelpcontext)|Справка контекст для ошибки.|
|[ColeDispatchИсключение::m_strDescription](#m_strdescription)|Описание вербальной ошибки.|
|[ColeDispatchИсключение::m_strHelpFile](#m_strhelpfile)|Справка файл `m_dwHelpContext`для использования с .|
|[ColeDispatchИсключение::m_strSource](#m_strsource)|Приложение, генерируемое исключением.|
|[ColeDispatchИсключение::m_wCode](#m_wcode)|`IDispatch`-специфический код ошибки.|

## <a name="remarks"></a>Примечания

Как и другие классы `CException` исключений, полученные из базового класса, `COleDispatchException` могут использоваться с macros THROW, THROW_LAST, TRY, CATCH, AND_CATCH и END_CATCH.

В общем, вы должны вызвать [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) для создания и броска `COleDispatchException` объекта.

Для получения дополнительной информации об [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md) исключениях см. [Exceptions: OLE Exceptions](../../mfc/exceptions-ole-exceptions.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>ColeDispatchИсключение::m_dwHelpContext

Определяет контекст справки в справке приложения (. HLP) файл.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Примечания

Этот элемент устанавливается функцией [AfxThrowOleDispatchException,](exception-processing.md#afxthrowoledispatchexception) когда выбрасывается исключение.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a>ColeDispatchИсключение::m_strDescription

Содержит устное описание ошибки, например "Диск полный".

```
CString m_strDescription;
```

### <a name="remarks"></a>Примечания

Этот элемент устанавливается функцией [AfxThrowOleDispatchException,](exception-processing.md#afxthrowoledispatchexception) когда выбрасывается исключение.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a>ColeDispatchИсключение::m_strHelpFile

Платформа заполняет эту строку с именем файла справки приложения.

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a>ColeDispatchИсключение::m_strSource

Платформа заполняет эту строку с именем приложения, которое создало исключение.

```
CString m_strSource;
```

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a>ColeDispatchИсключение::m_wCode

Содержит код ошибки, характерный для приложения.

```
WORD m_wCode;
```

### <a name="remarks"></a>Примечания

Этот элемент устанавливается функцией [AfxThrowOleDispatchException,](exception-processing.md#afxthrowoledispatchexception) когда выбрасывается исключение.

## <a name="see-also"></a>См. также раздел

[MFC Пример CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)<br/>
[Класс COleException](../../mfc/reference/coleexception-class.md)
