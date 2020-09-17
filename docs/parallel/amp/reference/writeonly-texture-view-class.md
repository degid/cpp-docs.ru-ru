---
title: Класс writeonly_texture_view
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 8978a548ed246c59d7e7f007f1180685c7343a14
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126244"
---
# <a name="writeonly_texture_view-class"></a>Класс writeonly_texture_view

Предоставляет WriteOnly доступ к текстуре.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов текстуры.

*_Rank*<br/>
Ранг текстуры.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Тип элементов текстуры.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор writeonly_texture_view](#ctor)|Инициализирует новый экземпляр класса `writeonly_texture_view`.|
|[Деструктор ~ writeonly_texture_view](#ctor)|Уничтожает объект `writeonly_texture_view`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[set](#set)|Задает значение элемента по указанному индексу.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Копирует указанный объект `writeonly_texture_view` в этот элемент.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа Rank](#rank)|Возвращает ранг объекта `writeonly_texture_view`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics

## <a name="dtor"></a>~ writeonly_texture_view

Уничтожает объект `writeonly_texture_view`.

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator_eq"></a>Оператор =

Копирует указанный объект `writeonly_texture_view` в этот элемент.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `writeonly_texture_view`, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `writeonly_texture_view`.

## <a name="rank"></a>Рейтинг

Возвращает ранг объекта `writeonly_texture_view`.

```cpp
static const int rank = _Rank;
```

## <a name="set"></a>параметр

Задает значение элемента по указанному индексу.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента.

*value*<br/>
Новое значение элемента.

## <a name="ctor"></a>writeonly_texture_view

Инициализирует новый экземпляр класса `writeonly_texture_view`.

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг текстуры.

*value_type*<br/>
Тип элементов текстуры.

*_Src*<br/>
Текстура, используемая для создания `writeonly_texture_view`.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
