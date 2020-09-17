---
title: Класс SafeInt
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt
- SafeInt::SafeInt
- SafeInt.SafeInt
helpviewer_keywords:
- SafeInt class
- SafeInt class, constructor
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
ms.openlocfilehash: d61ce20a8644ca64d37c0eca605d52fb308c0863
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560967"
---
# <a name="safeint-class"></a>Класс SafeInt

Расширяет примитивы целых чисел, чтобы предотвратить переполнение целого числа, и позволяет сравнивать разные типы целых чисел.

> [!NOTE]
> Последняя версия библиотеки SafeInt находится по адресу [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) . Чтобы использовать библиотеку SafeInt, клонировать репозиторий и `#include "SafeInt.hpp"`

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Параметры

*`T`*\
Тип целого числа или логического параметра, который заменяет `SafeInt`.

*`E`*\
Перечисляемый тип данных, который определяет политику обработки ошибок.

*`U`*\
Тип целого числа или логического параметра для дополнительного операнда.

*RHS*\
[in] Входной параметр, представляющий значение справа от оператора в нескольких отдельных функциях.

*сохранении*\
[in] Входной параметр, представляющий значение справа от оператора в нескольких отдельных функциях.

*числа*\
[in] Входной параметр, представляющий значение справа от оператора в нескольких отдельных функциях.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

| name                          |  Описание |
|---------------------------|--------------------|
| [SafeInt:: SafeInt](#safeint)  |  Конструктор по умолчанию. |

### <a name="assignment-operators"></a>Операторы присваивания

| Имя  |  Синтаксис |
|----|---------|
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const U& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const T& rhs) throw()` |
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()` |

### <a name="casting-operators"></a>Операторы приведения

| Имя              |  Синтаксис |
|------|---------------------------------|
| bool              |  `operator bool() throw()` |
| char              |  `operator char() const` |
| signed char       |  `operator signed char() const` |
| unsigned char     |  `operator unsigned char() const` |
| __int16           |  `operator __int16() const` |
| unsigned __int16  |  `operator unsigned __int16() const` |
| __int32           |  `operator __int32() const` |
| unsigned __int32  |  `operator unsigned __int32() const` |
| long              |  `operator long() const` |
| unsigned long     |  `operator unsigned long() const` |
| __int64           |  `operator __int64() const` |
| unsigned __int64  |  `operator unsigned __int64() const` |
| wchar_t           |  `operator wchar_t() const` |

### <a name="comparison-operators"></a>Операторы сравнения

| Имя  |  Синтаксис |
|----|----------------|
| \<     |  `template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()` |
| \<     |  `bool operator< (SafeInt<T,E> rhs) const throw()` |
| \>=    |  `template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()` |
| \>=    |  `Bool operator>= (SafeInt<T,E> rhs) const throw()` |
| \>     |  `template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()` |
| \>     |  `Bool operator> (SafeInt<T,E> rhs) const throw()` |
| \<=    |  `template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()` |
| \<=    |  `bool operator<= (SafeInt<T,E> rhs) const throw()` |
| ==    |  `template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()` |
| ==    |  `bool operator== (bool rhs) const throw()` |
| ==    |  `bool operator== (SafeInt<T,E> rhs) const throw()` |
| !=    |  `template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()` |
| !=    |  `bool operator!= (bool b) const throw()` |
| !=    |  `bool operator!= (SafeInt<T,E> rhs) const throw()` |

### <a name="arithmetic-operators"></a>Арифметические операторы

| Имя  |  Синтаксис |
|----|--------------|
| +     |  `const SafeInt<T,E>& operator+ () const throw()` |
| -     |  `SafeInt<T,E> operator- () const` |
| ++    |  `SafeInt<T,E>& operator++ ()` |
| --    |  `SafeInt<T,E>& operator-- ()` |
| %     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const` |
| %     |  `SafeInt<T,E> operator% (SafeInt<T,E> rhs) const` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)` |
| \*     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const` |
| \*     |  `SafeInt<T,E> operator* (SafeInt<T,E> rhs) const` |
| \*=    |  `SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)` |
| /     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const` |
| /     |  `SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const` |
| /=    |  `SafeInt<T,E>& operator/= (SafeInt<T,E> i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)` |
| +     |  `SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const` |
| +     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const` |
| +=    |  `SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)` |
| -     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const` |
| -     |  `SafeInt<T,E> operator- (SafeInt<T,E> rhs) const` |
| -=    |  `SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)` |

### <a name="logical-operators"></a>Логические операторы

| Имя     |  Синтаксис |
|------|--------------|
| !        |  `bool operator !() const throw()` |
| ~        |  `SafeInt<T,E> operator~ () const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()` |
| &        |  `SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()` |
| &        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()` |
| &=       |  `SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()` |
| ^        |  `SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()` |
| ^        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()` |
| ^=       |  `SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()` |
| &#124;   |  `SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()` |
| &#124;   |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()` |
| &#124;=  |  `SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()` |

## <a name="remarks"></a>Примечания

Класс `SafeInt` защищает от переполнения целого числа в математических операциях. Например, добавьте два 8-битовых целых числа: одно из них со значением 200, а второе со значением 100. Правильной математической операцией будет 200 + 100 = 300. Тем не менее из-за ограничения 8-битового целого числа верхний бит будет утерян и компилятор вернет 44 (300-2<sup>8</sup>) в качестве результата. Любая операция, которая зависит от этого математического уравнения, создаст непредвиденное поведение.

Класс `SafeInt` проверяет, происходит ли арифметическое переполнение или предпринимается ли в коде попытка деления на ноль. В обоих случаях класс вызывает обработчик ошибок, чтобы предупредить программу о потенциальных проблемах.

Этот класс также позволяет сравнить два различных типа целых чисел, пока они являются объектами `SafeInt`. Как правило, при сравнении необходимо сначала преобразовать числа в один и тот же тип. При приведении одного числа в другой тип часто требуется выполнить проверку, чтобы убедиться в отсутствии потери данных.

В таблице "Операторы" в этом разделе перечислены математические операторы и операторы сравнения, поддерживаемые классом `SafeInt`. Большинство математических операторов возвращают объект `SafeInt` типа `T`.

Операции сравнения между `SafeInt` и целочисленным типом данных могут выполняться в любом направлении. Например, `SafeInt<int>(x) < y` и `y> SafeInt<int>(x)` являются допустимыми и вернут один и тот же результат.

Многие бинарные операторы не поддерживают использование двух разных `SafeInt` типов. Примером этого является оператор `&`. `SafeInt<T, E> & int` поддерживается, но `SafeInt<T, E> & SafeInt<U, E>` не является. В последнем примере компилятору не удалось определить тип возвращаемого параметра. Одно из решений этой проблемы состоит в приведении второго параметра в базовый тип. Используя те же параметры, это можно сделать с помощью `SafeInt<T, E> & (U)SafeInt<U, E>`.

> [!NOTE]
> Для любых битовых операций два различных параметра должны быть одного размера. Если размеры отличаются, компилятор выдаст исключение [ASSERT](../mfc/reference/diagnostic-services.md#assert). Результаты этой операции не гарантировано должны быть точными. Чтобы устранить эту проблему, приведите меньший параметр до того, как он будет иметь тот же размер, что и параметр большего размера.

Для операторов сдвига выполнение сдвига на большее количество бит, чем это возможно для типа шаблона, приведет к исключению ASSERT. Это не будет действовать в режиме выпуска. Для операторов сдвига возможно сочетание двух типов параметров SafeInt, так как тип возвращаемого значения совпадает с исходным. Число справа от оператора лишь указывает количество битов для сдвига.

При логическом сравнении с объектом SafeInt сравнение является строго арифметическим. Например, рассмотрим эти выражения:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

Первая инструкция разрешается в **`true`** , но вторая инструкция разрешается в **`false`** . Результат битового отрицания 0 — 0xFFFFFFFF. Во второй инструкции оператор сравнения по умолчанию сравнивает 0xFFFFFFFF с 0xFFFFFFFF и рассматривает их как равные. Оператор сравнения для класса `SafeInt` определяет, что второй параметр является отрицательным, тогда как первый параметр — без знака. Таким образом, несмотря на то, что битовое представление идентично, логический оператор `SafeInt` определяет, что целое число без знака больше, чем значение -1.

Будьте внимательны при использовании класса `SafeInt` вместе с тернарным оператором `?:`. Рассмотрим приведенную ниже строку кода.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Компилятор преобразует ее в следующий код:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

Если `flag` имеет **`false`** значение, компилятор создает исключение вместо присвоения значения-1 в `x` . Таким образом, чтобы избежать этого, воспользуйтесь правильным кодом, приведенным в следующей строке.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` и `U` можно назначить логический тип, тип символа или целочисленный тип. Целочисленные типы могут быть со знаком или без него, а также любого размера — от 8 до 64 бит.

> [!NOTE]
> Несмотря на то, что класс `SafeInt` принимает любой целочисленный тип, он выполняется эффективнее с типами без знака.

`E` — это механизм обработки ошибок, используемый `SafeInt`. С библиотекой SafeInt предоставляются два механизма обработки ошибок. Политика по умолчанию — `SafeIntErrorPolicy_SafeIntException`, которая вызывает исключение [Класс SafeIntException](safeintexception-class.md) при возникновении ошибки. Другой политикой является `SafeIntErrorPolicy_InvalidParameter`, которая останавливает программу, если произошла ошибка.

Есть два варианта настройки политики ошибок. Первый вариант — задать параметр `E` при создании `SafeInt`. Используйте этот вариант, если необходимо изменить политику обработки ошибок только для одного `SafeInt`. Другой вариант — определить _SAFEINT_DEFAULT_ERROR_POLICY настраиваемым классом обработки ошибок до добавления библиотеки `SafeInt`. Используйте этот вариант, когда необходимо изменить политику обработки ошибок по умолчанию для всех экземпляров класса `SafeInt` в вашем коде.

> [!NOTE]
> Настраиваемый класс, который обрабатывает ошибки из библиотеки SafeInt, не должен возвращать элемент управления в код, который вызвал обработчик ошибок. После вызова обработчика ошибок результат `SafeInt` операции не может быть доверенным.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SafeInt`

## <a name="requirements"></a>Требования

**Заголовок:** SafeInt.hpp
> [!NOTE]
> Последняя версия этой библиотеки находится по адресу [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) . Выполните клонирование библиотеки и включите SafeInt.hpp, чтобы использовать библиотеку SafeInt.
> Предпочитать этот репозиторий GitHub <SafeInt.h>. Это современная версия <SafeInt.h>, которая включает небольшое количество исправлений ошибок, использует современные функции C++, что приводит к более эффективному коду и является переносимой на любую платформу с использованием компиляторов GCC, Clang или Intel.

### <a name="example"></a>Пример

```c
#include "SafeInt.hpp" // set path to your clone of the SafeInt GitHub repo (https://github.com/dcleblanc/SafeInt)

int main()
{
    int divisor = 3;
    int dividend = 6;
    int result;

    bool success = SafeDivide(dividend, divisor, result); // result = 2
    success = SafeDivide(dividend, 0, result); // expect fail. result isn't modified.
}
```

**Пространство имен:** нет

## <a name="safeintsafeint"></a><a name="safeint"></a> SafeInt:: SafeInt

Формирует объект `SafeInt`.

```cpp
SafeInt() throw

SafeInt (const T& i) throw ()

SafeInt (bool b) throw ()

template <typename U>
SafeInt (const SafeInt <U, E>& u)

I template <typename U>
SafeInt (const U& i)
```

### <a name="parameters"></a>Параметры

`i`<br/>
[in] Значение для нового объекта `SafeInt`. Это должен быть параметр типа T или U в зависимости от конструктора.

`b`<br/>
[in] Логическое значение для нового объекта `SafeInt`.

`u`<br/>
[in] Объект `SafeInt` типа U. Новый объект `SafeInt` будет иметь то же значение, что и *u*, но будет иметь тип T.

`U` Тип данных, хранящихся в `SafeInt` . Это может быть логический тип, тип символа или целочисленный тип. Если это целочисленный тип, его можно подписать или без знака и иметь длину от 8 до 64 бит.

### <a name="remarks"></a>Примечания

Входной параметр для конструктора, *i* или *u*, должен быть логическим типом, типом символа или целочисленным типом. Если это другой тип параметра, `SafeInt` класс вызывает [static_assert](../cpp/static-assert.md) , чтобы указать недопустимый входной параметр.

Конструкторы, использующие тип шаблона `U`, автоматически преобразовывают входной параметр в тип, заданный параметром `T`. Класс `SafeInt` преобразовывает данные без потери. Он сообщает обработчику ошибок, `E` если не удается преобразовать данные в тип `T` без потери данных.

Если вы создаете `SafeInt` из логического параметра, необходимо немедленно инициализировать значение. Создать `SafeInt` с помощью кода нельзя `SafeInt<bool> sb;` . Это приведет к ошибке компиляции.
