---
title: Класс CBookmark
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: 4013e40c364593676ebb099804304ffb2adb42c1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838481"
---
# <a name="cbookmark-class"></a>Класс CBookmark

Содержит значение закладки в своем буфере.

## <a name="syntax"></a>Синтаксис

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Параметры

*нсизе*<br/>
Размер буфера закладки в байтах. Если *нсизе* равен нулю, буфер закладки будет динамически создаваться во время выполнения.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[CBookmark](#cbookmark)|Конструктор|
|[GetBuffer](#getbuffer)|Получает указатель на буфер.|
|[GetSize](#getsize)|Возвращает размер буфера в байтах.|
|[сетбукмарк](#setbookmark)|Задает значение закладки.|

### <a name="operators"></a>Операторы

| Имя | Описание |
|-|-|
|[operator=](#operator)|Назначает один `CBookmark` класс другому.|

## <a name="remarks"></a>Примечания

`CBookmark<0>` является специализацией шаблона `CBookmark` ; ее буфер динамически создается во время выполнения.

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a> CBookmark:: CBookmark

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Параметры

*нсизе*<br/>
окне Размер буфера закладки в байтах.

### <a name="remarks"></a>Примечания

Первая функция устанавливает буфер в значение NULL, а размер буфера — в 0. Вторая функция задает размер буфера равным *нсизе*, а буфер — массиву байтов *нсизе* байт.

> [!NOTE]
> Эта функция доступна только в `CBookmark<0>` .

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a> CBookmark:: buffer

Получает указатель на буфер закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер закладки.

## <a name="cbookmarkgetsize"></a><a name="getsize"></a> CBookmark:: DataSize

Возвращает размер буфера закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Размер буфера в байтах.

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a> CBookmark:: Сетбукмарк

Копирует значение закладки, на которое ссылается *pBuffer* , в `CBookmark` буфер и устанавливает размер буфера равным *нсизе*.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Параметры

*нсизе*<br/>
окне Размер буфера закладок.

*pBuffer*<br/>
окне Указатель на массив байтов, содержащий значение закладки.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция доступна только в `CBookmark<0>` .

## <a name="cbookmarkoperator-"></a><a name="operator"></a> CBookmark::operator=

Присваивает `CBookmark` объект другому объекту.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Примечания

Этот оператор необходим только в `CBookmark<0>` .

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
