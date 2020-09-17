---
title: Класс HString
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 549e3fe2a83bb091bcf90e7957b20c219728bdbc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216587"
---
# <a name="hstring-class"></a>Класс HString

Вспомогательный класс для управления временем существования [HString](/windows/win32/WinRT/hstring) с помощью шаблона RAII.

## <a name="syntax"></a>Синтаксис

```cpp
class HString;
```

## <a name="remarks"></a>Примечания

Среда выполнения Windows предоставляет доступ к строкам через дескрипторы [HString](/windows/win32/WinRT/hstring) . `HString`Класс предоставляет удобные функции и операторы для упрощения использования дескрипторов HString. Этот класс может управлять временем существования HSTRING, которому он владеет, с помощью шаблона RAII.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | -----------------------------------------------------
[HString:: HString](#hstring)        | Инициализирует новый экземпляр класса `HString`.
[HString:: ~ HString](#tilde-hstring) | Уничтожает текущий экземпляр `HString` класса.

### <a name="public-methods"></a>Открытые методы

name                                     | Описание
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString:: Attach](#attach)               | Связывает указанный `HString` объект с текущим `HString` объектом.
[HString::CopyTo](#copyto)               | Копирует текущий `HString` объект в объект HString.
[HString::D етач](#detach)               | Отменяет связь указанного `HString` объекта с его базовым значением.
[HString:: Get](#get)                     | Получает значение базового маркера HSTRING.
[HString:: GetAddressOf](#getaddressof)   | Извлекает указатель на базовый маркер HSTRING.
[HString:: Жетравбуффер](#getrawbuffer)   | Извлекает указатель на базовые строковые данные.
[HString:: IsValid](#isvalid)             | Указывает, является ли текущий `HString` объект допустимым.
[HString:: MakeReference](#makereference) | Создает `HStringReference` объект из указанного строкового параметра.
[HString:: Release](#release)             | Удаляет базовое строковое значение и инициализирует текущий `HString` объект в пустое значение.
[HString:: Set](#set)                     | Устанавливает значение текущего `HString` объекта в указанную строку или параметр расширенных символов `HString` .

### <a name="public-operators"></a>Открытые операторы

Имя                                         | Описание
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::operator=](#operator-assign)       | Перемещает значение другого `HString` объекта в текущий `HString` объект.
[HString::operator==](#operator-equality)    | Указывает, равны ли два параметра.
[HString::operator!=](#operator-inequality)  | Указывает, являются ли два параметра неравными.
[HString::operator&lt;](#operator-less-than) | Указывает, меньше ли первый параметр второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HString`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>HString:: ~ HString

Уничтожает текущий экземпляр `HString` класса.

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>HString:: Attach

Связывает указанный `HString` объект с текущим `HString` объектом.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Параметры

*хстр*<br/>
Существующий объект `HString`.

## <a name="hstringcopyto"></a><a name="copyto"></a>HString:: CopyTo

Копирует текущий `HString` объект в объект HString.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
HSTRING, который получает копию.

### <a name="remarks"></a>Примечания

Этот метод вызывает функцию [виндовсдупликатестринг](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring) .

## <a name="hstringdetach"></a><a name="detach"></a>HString::D етач

Отменяет связь указанного `HString` объекта с его базовым значением.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Базовое `HString` значение до начала операции отсоединения.

## <a name="hstringget"></a><a name="get"></a>HString:: Get

Получает значение базового маркера HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>HString:: GetAddressOf

Извлекает указатель на базовый маркер HSTRING.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый дескриптор HSTRING.

### <a name="remarks"></a>Примечания

После этой операции строковое значение базового дескриптора HSTRING будет уничтожено.

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>HString:: Жетравбуффер

Извлекает указатель на базовые строковые данные.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Параметры

*Длина* Указатель на **`int`** переменную, которая получает длину данных.

### <a name="return-value"></a>Возвращаемое значение

**`const`** Указатель на базовые строковые данные.

## <a name="hstringhstring"></a><a name="hstring"></a>HString:: HString

Инициализирует новый экземпляр класса `HString`.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Параметры

*хстр*<br/>
Обработчик HSTRING.

*иной*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый `HString` пустой объект.

Второй конструктор инициализирует новый `HString` объект значением существующего *другого* параметра, а затем уничтожает *другой* параметр.

## <a name="hstringisvalid"></a><a name="isvalid"></a>HString:: IsValid

Указывает, является ли текущий `HString` объект пустым.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Параметры

**`true`**, если текущий `HString` объект не пуст; в противном случае — **`false`** .

## <a name="hstringmakereference"></a><a name="makereference"></a>HString:: MakeReference

Создает `HStringReference` объект из указанного строкового параметра.

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Параметры

*самый заданный размер*<br/>
Параметр шаблона, указывающий размер `HStringReference` буфера назначения.

*str*<br/>
Ссылка на строку расширенных символов.

*len*<br/>
Максимальная длина буфера параметров *str* для использования в этой операции. Если параметр *Len* не указан, используется весь параметр *str* .

### <a name="return-value"></a>Возвращаемое значение

Объект, значение которого совпадает с `HStringReference` заданным параметром *str* .

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>Оператор HString::operator=

Перемещает значение другого `HString` объекта в текущий `HString` объект.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Примечания

Значение *существующего объекта* копируется в текущий `HString` объект, а затем удаляется *другой* объект.

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>Оператор HString::operator==

Указывает, равны ли два параметра.

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть `HString` объектом или `HStringReference` или обработчиком HString.

*rhs*<br/>
Второй сравниваемый параметр. *RHS* может быть `HString` объектом или `HStringReference` или HString.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если параметры *LHS* и *RHS* равны; в противном случае — **`false`** .

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>Оператор HString::operator!=

Указывает, являются ли два параметра неравными.

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть `HString` объектом или `HStringReference` или обработчиком HString.

*rhs*<br/>
Второй сравниваемый параметр. *RHS* может быть `HString` объектом или `HStringReference` или HString.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если параметры *LHS* и *RHS* не равны; в противном случае — **`false`** .

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>Оператор HString::operator &lt;

Указывает, меньше ли первый параметр второго параметра.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть ссылкой на `HString` .

*rhs*<br/>
Второй сравниваемый параметр. *RHS* может быть ссылкой на `HString` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если параметр *LHS* меньше, чем параметр *RHS* ; в противном случае — **`false`** .

## <a name="hstringrelease"></a><a name="release"></a>HString:: Release

Удаляет базовое строковое значение и инициализирует текущий `HString` объект в пустое значение.

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>HString:: Set

Устанавливает значение текущего `HString` объекта в указанную строку или параметр расширенных символов `HString` .

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка расширенных символов.

*len*<br/>
Максимальная длина параметра *str* , назначенного текущему `HString` объекту.

*хстр*<br/>
Существующий объект `HString`.
