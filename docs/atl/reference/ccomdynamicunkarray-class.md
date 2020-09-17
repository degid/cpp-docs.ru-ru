---
title: Класс CComDynamicUnkArray
ms.date: 11/04/2016
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: 51b1d7e81c98bd5dbcf957b1705e7a717bfb9ab0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747989"
---
# <a name="ccomdynamicunkarray-class"></a>Класс CComDynamicUnkArray

Этот класс хранит `IUnknown` множество указателей.

## <a name="syntax"></a>Синтаксис

```
class CComDynamicUnkArray
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Конструктор. Инициализирует значения коллекции до NULL, а размер коллекции - к нулю.|
|[CComDynamicUnkArray:: »CComDynamicUnkArray](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComDynamicUnkArray::Добавить](#add)|Вызовите этот `IUnknown` метод, чтобы добавить указатель в массив.|
|[CComDynamicUnkArray::начало](#begin)|Возвращает указатель на `IUnknown` первый указатель в коллекции.|
|[CComDynamicUnkArray::ясно](#clear)|Опустошает массив.|
|[CComDynamicUnkArray::end](#end)|Возвращает указатель на один `IUnknown` последний указатель в коллекции.|
|[CComDynamicUnkArray::GetAt](#getat)|Извлекает элемент по указанному индексу.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|Вызовите этот метод, чтобы `IUnknown` получить файлcookieо-файлы, связанные с заданным указателем.|
|[CComDynamicUnkArray::GetSize](#getsize)|Возвращает длину массива.|
|[CComDynamicUnkArray::](#getunknown)|Вызовите этот `IUnknown` метод, чтобы получить указатель, связанный с данным файлом cookie.|
|[CComDynamicUnkArray::Удалить](#remove)|Вызов иметод, `IUnknown` чтобы удалить указатель из массива.|

## <a name="remarks"></a>Примечания

`CComDynamicUnkArray`содержит динамически распределенный `IUnknown` массив указателей, каждый из которых имеет интерфейс на точке соединения. `CComDynamicUnkArray`может быть использован в качестве параметра для класса шаблонов [IConnectionPointImpl.](../../atl/reference/iconnectionpointimpl-class.md)

Методы `CComDynamicUnkArray` [начинаются](#begin) и [заканчиваются,](#end) можно использовать для прослеживании всех точек соединения (например, при выстреле события).

[См. Добавление точек соединения к объекту](../../atl/adding-connection-points-to-an-object.md) для получения подробной информации об автоматизации создания прокси-сервисов точки соединения.

> [!NOTE]
> **Заметка** Класс `CComDynamicUnkArray` используется мастером **add Class** при создании элемента управления, который имеет точки соединения. Если вы хотите указать количество точек соединения вручную, измените ссылку `CComDynamicUnkArray` с `CComUnkArray<` *n,* `>`где *n* — это необходимое количество точек соединения.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a>CComDynamicUnkArray::Добавить

Вызовите этот `IUnknown` метод, чтобы добавить указатель в массив.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
Указатель `IUnknown` для добавления в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файлы cookie, связанные с недавно добавленным указателем.

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a>CComDynamicUnkArray::начало

Возвращает указатель к началу сбора `IUnknown` указателей интерфейса.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель интерфейса.

### <a name="remarks"></a>Примечания

Коллекция содержит указатели на интерфейсы, `IUnknown`хранящиеся локально как. Вы отбрасываете каждый `IUnknown` интерфейс в реальный тип интерфейса, а затем вызвать через него. Сначала не нужно запросить интерфейс.

Перед использованием интерфейса `IUnknown` следует проверить, что он не является NULL.

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a>CComDynamicUnkArray::ясно

Опустошает массив.

```cpp
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray

Конструктор.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Устанавливает размер коллекции до нуля и инициализирует значения до NULL. Деструктор освобождает коллекцию, если это необходимо.

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a>CComDynamicUnkArray:: »CComDynamicUnkArray

Деструктор

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Освобождает ресурсы, выделенные конструктором класса.

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a>CComDynamicUnkArray::end

Возвращает указатель на один `IUnknown` последний указатель в коллекции.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель интерфейса.

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a>CComDynamicUnkArray::GetAt

Извлекает элемент по указанному индексу.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс извлекаемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [IUnknown.](/windows/win32/api/unknwn/nn-unknwn-iunknown)

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a>CComDynamicUnkArray::GetCookie

Вызовите этот метод, чтобы `IUnknown` получить файлcookieо-файлы, связанные с заданным указателем.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Параметры

*ppFind*<br/>
Указатель, `IUnknown` для которого требуется связанное cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файлcookieо-файлы, связанные с указателем, `IUnknown` или ноль, если не найдено соответствующего `IUnknown` указателя.

### <a name="remarks"></a>Примечания

Если существует несколько экземпляров `IUnknown` одного и того же указателя, эта функция возвращает файл cookie для первого.

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a>CComDynamicUnkArray::GetSize

Возвращает длину массива.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина массива.

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a>CComDynamicUnkArray::

Вызовите этот `IUnknown` метод, чтобы получить указатель, связанный с данным файлом cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*<br/>
Файлы cookie, `IUnknown` для которых требуется связанный указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `IUnknown` указатель или NULL, если не найдено соответствующее файловое печенье.

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a>CComDynamicUnkArray::Удалить

Вызов иметод, `IUnknown` чтобы удалить указатель из массива.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*<br/>
Файлы cookie, ссылающиеся на указатель, `IUnknown` который должен быть удален из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если указатель удален; в противном случае FALSE.

## <a name="see-also"></a>См. также раздел

[Класс CComUnkArray](../../atl/reference/ccomunkarray-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
