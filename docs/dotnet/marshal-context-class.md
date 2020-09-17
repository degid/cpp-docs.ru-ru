---
title: Класс marshal_context
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 110fe4abf7eb90b05e7feef563efa4882bed0fc6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332013"
---
# <a name="marshal_context-class"></a>Класс marshal_context

Этот класс преобразует данные между родной и управляемой средой.

## <a name="syntax"></a>Синтаксис

```cpp
class marshal_context
```

## <a name="remarks"></a>Примечания

Используйте `marshal_context` класс для конверсий данных, требующих контекста. Для получения дополнительной информации о том, какие преобразования требуют контекста и какой файл маршалинга должен быть включен, [см.](../dotnet/overview-of-marshaling-in-cpp.md) Результат маршалинга при использовании контекста действителен `marshal_context` только до тех пор, пока объект не будет уничтожен. Чтобы сохранить результат, необходимо скопировать данные.

То `marshal_context` же самое можно использовать для многочисленных преобразований данных. Повторное использование контекста таким образом не повлияет на результаты предыдущих вызовов маршалов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|Строит объект `marshal_context` для использования для преобразования данных между управляемыми и родными типами данных.|
|[marshal_context::-marshal_context](#tilde-marshal-context)|Уничтожает объект `marshal_context` .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|Выполняет маршалинг на определенном объекте данных для преобразования его между управляемым и родным типом данных.|

## <a name="requirements"></a>Требования

**Файл заголовка:** \<msclr-marshal.h \<>, msclr-marshal_windows.h>, \<msclr-marshal_cppstd.h>, или \<msclr-marshal_atl.h>

**Название:** msclr::interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context::marshal_context

Строит объект `marshal_context` для использования для преобразования данных между управляемыми и родными типами данных.

```cpp
marshal_context();
```

### <a name="remarks"></a>Примечания

Некоторые преобразования данных требуют контекста маршала. Для получения дополнительной информации о том, какие переводы требуют контекста и какой файл маршалинга вы должны включить в ваше приложение, [см.](../dotnet/overview-of-marshaling-in-cpp.md)

### <a name="example"></a>Пример

Смотрите пример [для marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context::-marshal_context

Уничтожает объект `marshal_context` .

```cpp
~marshal_context();
```

### <a name="remarks"></a>Примечания

Некоторые преобразования данных требуют контекста маршала. Дополнительную информацию о том, какие переводы требуют контекста и какой файл маршалинга должен быть включен в ваше приложение, читайте [в обзоре маршалинга в СЗ.](../dotnet/overview-of-marshaling-in-cpp.md)

Удаляемый `marshal_context` объект аннулирует данные, преобразованные в этом контексте. Если требуется сохранить данные `marshal_context` после уничтожения объекта, необходимо вручную скопировать данные на переменную, которая сохранится.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context:::marshal_as

Выполняет маршалинг на определенном объекте данных для преобразования его между управляемым и родным типом данных.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Параметры

*input*<br/>
(в) Значение, которое вы хотите `To_Type` привести к переменной.

### <a name="return-value"></a>Возвращаемое значение

Переменная типа, `To_Type` которая является преобразованным значением. `input`

### <a name="remarks"></a>Примечания

Эта функция выполняет маршалинг на определенном объекте данных. Используйте эту функцию только с конверсиями, указанными в таблице в [Обзоре маршалинга в СЗ](../dotnet/overview-of-marshaling-in-cpp.md).

Если вы попытаетесь привести пару типов данных, которые не поддерживаются, `marshal_as` будет генерировать ошибку [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Для получения дополнительной информации ознакомьтесь с сообщением с этой ошибкой. Ошибка `C4996` может быть сгенерирована не только для обесточенных функций. Два условия, генерирующие эту ошибку, пытаются привести к тому, что пара типов данных не поддерживается и используется `marshal_as` для преобразования, требующего контекста.

Библиотека маршалинга состоит из нескольких файлов заголовка. Любое преобразование требует только одного файла, но вы можете включить дополнительные файлы, если вам нужно для других конверсий. В `Marshaling Overview in C++` таблице указывается, какой файл маршалинга должен быть включен для каждого преобразования.

### <a name="example"></a>Пример

Этот пример создает контекст для `System::String` маршалинга `const char *` от переменного типа. Преобразованные данные не будут действительны после строки, которая удаляет контекст.

```cpp
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```
