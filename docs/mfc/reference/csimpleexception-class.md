---
title: Класс Ксимпликсцептион
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: afd83c1ddd6f68b10c5cc8c47c0e939bbd01b6c2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840717"
---
# <a name="csimpleexception-class"></a>Класс Ксимпликсцептион

Этот класс является базовым классом для исключений MFC, связанных с критическими ресурсами.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ксимпликсцептион:: Ксимпликсцептион](#csimpleexception)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ксимпликсцептион:: Жетеррормессаже](#geterrormessage)|Содержит текст о произошедшей ошибке.|

## <a name="remarks"></a>Примечания

`CSimpleException` является базовым классом для критически важных для ресурса исключений MFC и обрабатывает владение и инициализацию сообщения об ошибке. Следующие классы используют `CSimpleException` в качестве базового класса:

|Имя|Описание|
|-|-|
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|
|[Класс Кнотсуппортедексцептион](../../mfc/reference/cnotsupportedexception-class.md)|Запросы на неподдерживаемую операцию|
|[Класс Кресаурцеексцептион](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows не найден или не является создаваемым|
|[Класс Кусерексцептион](../../mfc/reference/cuserexception-class.md)|Исключение, указывающее, что ресурс не найден|
|[Класс Цинвалидаржексцептион](../../mfc/reference/cinvalidargexception-class.md)|Исключение, указывающее на недопустимый аргумент|

Поскольку `CSimpleException` является абстрактным базовым классом, объект нельзя объявить `CSimpleException` напрямую. Вместо этого необходимо объявить производные объекты, такие как, в предыдущей таблице. При объявлении собственного производного класса используйте приведенные выше классы в качестве модели.

Дополнительные сведения см. в разделе [Класс CException](../../mfc/reference/cexception-class.md) и [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a> Ксимпликсцептион:: Ксимпликсцептион

Конструктор.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*баутоделете*<br/>
Укажите значение TRUE, если память для `CSimpleException` объекта была выделена в куче. Это приведет к `CSimpleException` удалению объекта при `Delete` вызове функции-члена для удаления исключения. Укажите значение FALSE, если `CSimpleException` объект находится в стеке или является глобальным объектом. В этом случае `CSimpleException` объект не будет удален при `Delete` вызове функции-члена.

### <a name="remarks"></a>Примечания

Обычно вызывать этот конструктор напрямую не требуется. Функция, вызывающая исключение, должна создать экземпляр `CException` производного класса и вызвать его конструктор или использовать одну из функций Throw MFC, например [афкссровфиликсцептион](exception-processing.md#afxthrowfileexception), для создания предопределенного типа.

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a> Ксимпликсцептион:: Жетеррормессаже

Вызовите эту функцию члена, чтобы указать текст о произошедшей ошибке.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзеррор*<br/>
Указатель на буфер, который получит сообщение об ошибке.

*нмаксеррор*<br/>
Максимальное число символов, которое может хранить буфер, включая символ завершения NULL.

*пнхелпконтекст*<br/>
Адрес типа UINT, который получит идентификатор контекста справки. Если значение равно NULL, идентификатор не будет возвращен.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0, если текст сообщения об ошибке недоступен.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [CException:: жетеррормессаже](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Обработка исключений](../../mfc/exception-handling-in-mfc.md)
