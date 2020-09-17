---
title: Класс messages
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
ms.openlocfilehash: deb9eaedba3c99bb2fcb8399ac412ccedb11545f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375925"
---
# <a name="messages-class"></a>Класс messages

Шаблон класса описывает объект, который может служить в качестве аспекта локализации для получения локализованных сообщений из каталога интернационализированных сообщений для данного языка.

В настоящее время при использовании данного класса сообщений сообщения не создаются.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

По сути, этот аспект открывает каталог сообщений, заданных в базовом классе messages_base, извлекает необходимую информацию и закрывает каталог.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[Сообщения](#messages)|Функция конструктора аспекта сообщения.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип символа, используемого для отображения сообщений.|
|[string_type](#string_type)|Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Закрыть](#close)|Закрывает каталог сообщений.|
|[do_close](#do_close)|Виртуальная функция, вызываемая для закрытия каталога сообщений.|
|[do_get](#do_get)|Виртуальная функция, вызываемая для извлечения каталога сообщений.|
|[do_open](#do_open)|Виртуальная функция, вызываемая для открытия каталога сообщений.|
|[get](#get)|Извлекает каталог сообщений.|
|[open](#open)|Открывает каталог сообщений.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="messageschar_type"></a><a name="char_type"></a>сообщения::char_type

Тип символа, используемого для отображения сообщений.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона **Chartype**.

## <a name="messagesclose"></a><a name="close"></a>сообщения::закрыть

Закрывает каталог сообщений.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Параметры

*_Catval*\
Каталог для закрытия.

### <a name="remarks"></a>Примечания

Функция-член вызывает [do_close](#do_close)(_ *Catval*).

## <a name="messagesdo_close"></a><a name="do_close"></a>сообщения::do-close

Виртуальная функция, вызываемая для закрытия каталога сообщений.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Параметры

*_Catval*\
Каталог для закрытия.

### <a name="remarks"></a>Примечания

Защищенная функция участника закрывает каталог сообщений *_Catval,* который должен быть открыт более ранним вызовом [do_open.](#do_open)

Значение *_Catval* должно быть получено из ранее открытого каталога, который не закрыт.

### <a name="example"></a>Пример

См. пример для [close](#close), в котором вызывается `do_close`.

## <a name="messagesdo_get"></a><a name="do_get"></a>сообщения::do-get

Виртуальная функция, вызываемая для извлечения каталога сообщений.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Параметры

*_Catval*\
Значение идентификации, указывающее каталог сообщений для поиска.

*_Set*\
Первый идентификатор, использованный для поиска сообщения в каталоге сообщений.

*_Message*\
Второй идентификатор, использованный для поиска сообщения в каталоге сообщений.

*_Dfault*\
Строка, которая будет возвращаться при сбое.

### <a name="return-value"></a>Возвращаемое значение

Он возвращает копию *_Dfault* на сбой. В противном случае он возвращает копию указанной последовательности сообщений.

### <a name="remarks"></a>Примечания

Защищенная функция члена пытается получить последовательность сообщений из каталога сообщений *_Catval*. Он может использовать *_Set,* *_Message,* и *_Dfault* при этом.

### <a name="example"></a>Пример

См. пример для [get](#get), в котором вызывается `do_get`.

## <a name="messagesdo_open"></a><a name="do_open"></a>сообщения::do-open

Виртуальная функция, вызываемая для открытия каталога сообщений.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Параметры

*_Catname*\
Имя каталога для поиска.

*_Loc*\
Языковой стандарт, который ищется в каталоге.

### <a name="return-value"></a>Возвращаемое значение

Он возвращает значение, которое при сбое получает значение меньше нуля. В противном случае возвращаемое значение может использоваться в качестве первого аргумента в последующем вызове [get](#get).

### <a name="remarks"></a>Примечания

Защищенная функция участника пытается открыть каталог сообщений, имя которого *_Catname.* Он может использовать *_Loc* в этом

Возвращаемое значение следует использовать как аргумент для последующего вызова [close](#close).

### <a name="example"></a>Пример

См. пример для [open](#open), в котором вызывается `do_open`.

## <a name="messagesget"></a><a name="get"></a>сообщения::получить

Извлекает каталог сообщений.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Параметры

*_Catval*\
Значение идентификации, указывающее каталог сообщений для поиска.

*_Set*\
Первый идентификатор, использованный для поиска сообщения в каталоге сообщений.

*_Message*\
Второй идентификатор, использованный для поиска сообщения в каталоге сообщений.

*_Dfault*\
Строка, которая будет возвращаться при сбое.

### <a name="return-value"></a>Возвращаемое значение

Он возвращает копию *_Dfault* на сбой. В противном случае он возвращает копию указанной последовательности сообщений.

### <a name="remarks"></a>Примечания

Функция участника [do_get](#do_get)возвращает `_Catval`do_get `_Set` `_Message`(, , , `_Dfault`).

## <a name="messagesmessages"></a><a name="messages"></a>сообщения::сообщения

Функция конструктора аспекта сообщения.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

*_Locname*\
Имя языкового стандарта.

### <a name="remarks"></a>Примечания

Возможные значения для *параметра _Refs* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с `_Refs` **помощью локализации::**[грань](../standard-library/locale-class.md#facet_class)( ).

## <a name="messagesopen"></a><a name="open"></a>сообщения::открыто

Открывает каталог сообщений.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Параметры

*_Catname*\
Имя каталога для поиска.

*_Loc*\
Языковой стандарт, который ищется в каталоге.

### <a name="return-value"></a>Возвращаемое значение

Он возвращает значение, которое при сбое получает значение меньше нуля. В противном случае возвращаемое значение может использоваться в качестве первого аргумента в последующем вызове [get](#get).

### <a name="remarks"></a>Примечания

Функция участника [do_open](#do_open)возвращает `_Catname`do_open `_Loc`(, ).

## <a name="messagesstring_type"></a><a name="string_type"></a>сообщения::string_type

Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [basic_string](../standard-library/basic-string-class.md) объекты которого могут хранить копии последовательностей сообщений.

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[класс messages_base](../standard-library/messages-base-class.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
