---
title: Класс CComUnkArray
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: c1d2f0296394d3979ef4f152e3f902c89adf5b45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327305"
---
# <a name="ccomunkarray-class"></a>Класс CComUnkArray

Этот класс `IUnknown` хранит указатели и предназначен для использования в качестве параметра для шаблона [IConnectionPointImpl.](../../atl/reference/iconnectionpointimpl-class.md)

## <a name="syntax"></a>Синтаксис

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Параметры

*nMaxSize*<br/>
Максимальное количество `IUnknown` указателей, которые могут быть проведены в статическом массиве.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComUnkArray::Добавить](#add)|Вызовите этот `IUnknown` метод, чтобы добавить указатель в массив.|
|[CComUnkArray::начало](#begin)|Возвращает указатель на `IUnknown` первый указатель в коллекции.|
|[CComUnkArray::end](#end)|Возвращает указатель на один `IUnknown` последний указатель в коллекции.|
|[CComUnkArray::GetCookie](#getcookie)|Вызовите этот метод, чтобы `IUnknown` получить файлcookieо-файлы, связанные с заданным указателем.|
|[CComUnkArray::Газета.Ru](#getunknown)|Вызовите этот `IUnknown` метод, чтобы получить указатель, связанный с данным файлом cookie.|
|[CComUnkArray::Удалить](#remove)|Вызов иметод, `IUnknown` чтобы удалить указатель из массива.|

## <a name="remarks"></a>Примечания

`CComUnkArray`содержит фиксированное `IUnknown` количество указателей, каждый интерфейс на точке соединения. `CComUnkArray`может быть использован в качестве параметра для класса шаблонов [IConnectionPointImpl.](../../atl/reference/iconnectionpointimpl-class.md) `CComUnkArray<1>`является шаблоном, `CComUnkArray` специализацией которого была оптимизирована для одной точки соединения.

Методы `CComUnkArray` [начинаются](#begin) и [заканчиваются,](#end) можно использовать для прослеживании всех точек соединения (например, при выстреле события).

[См. Добавление точек соединения к объекту](../../atl/adding-connection-points-to-an-object.md) для получения подробной информации об автоматизации создания прокси-сервисов точки соединения.

> [!NOTE]
> **Заметка** Класс [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) используется мастером **Add Class** при создании элемента управления, который имеет точки соединения. Если вы хотите указать количество точек соединения вручную, измените ссылку `CComDynamicUnkArray` с `CComUnkArray<` *n,* `>`где *n* — это необходимое количество точек соединения.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomunkarrayadd"></a><a name="add"></a>CComUnkArray::Добавить

Вызовите этот `IUnknown` метод, чтобы добавить указатель в массив.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
Вызовите этот `IUnknown` метод, чтобы добавить указатель в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файлcookieо-файлы, связанные с недавно добавленным указателем, или 0, если массив недостаточно велик, чтобы содержать новый указатель.

## <a name="ccomunkarraybegin"></a><a name="begin"></a>CComUnkArray::начало

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

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a>CComUnkArray::CComUnkArray

Конструктор.

```
CComUnkArray();
```

### <a name="remarks"></a>Примечания

Устанавливает коллекцию `nMaxSize` `IUnknown` для удержания указателей и инициализирует указатели на NULL.

## <a name="ccomunkarrayend"></a><a name="end"></a>CComUnkArray::end

Возвращает указатель на один `IUnknown` последний указатель в коллекции.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель интерфейса.

### <a name="remarks"></a>Примечания

Методы `CComUnkArray` `begin` и `end` могут быть использованы для цикла через все точки соединения, например, при выстреле события.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a>CComUnkArray::GetCookie

Вызовите этот метод, чтобы `IUnknown` получить файлcookieо-файлы, связанные с заданным указателем.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Параметры

*ppFind*<br/>
Указатель, `IUnknown` для которого требуется связанное cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файлcookieо-файлы, связанные с указателем, `IUnknown` или 0, если не найдено подходящего `IUnknown` указателя.

### <a name="remarks"></a>Примечания

Если существует несколько экземпляров `IUnknown` одного и того же указателя, эта функция возвращает файл cookie для первого.

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a>CComUnkArray::Газета.Ru

Вызовите этот `IUnknown` метод, чтобы получить указатель, связанный с данным файлом cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*<br/>
Файлы cookie, `IUnknown` для которых требуется связанный указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `IUnknown` указатель или NULL, если не найдено соответствующее файловое печенье.

## <a name="ccomunkarrayremove"></a><a name="remove"></a>CComUnkArray::Удалить

Вызов иметод, `IUnknown` чтобы удалить указатель из массива.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*<br/>
Файлы cookie, ссылающиеся на указатель, `IUnknown` который должен быть удален из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если указатель удален, FALSE в противном случае.

## <a name="see-also"></a>См. также раздел

[Класс CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
