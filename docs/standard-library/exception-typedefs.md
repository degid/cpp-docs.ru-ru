---
title: Определения типов &lt;exception&gt;
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: f71c03e0c0a2e7ea4f37a85e85628ccf630ea317
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368728"
---
# <a name="ltexceptiongt-typedefs"></a>Определения типов &lt;exception&gt;

## <a name="exception_ptr"></a><a name="exception_ptr"></a>Exception_ptr

Тип, который описывает указатель на исключение.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Примечания

Неуказанный внутренний класс, используемый для реализации типа `exception_ptr`.

Используйте объект `exception_ptr` для ссылки на текущее исключение или экземпляр указанного пользователем исключения. В реализации Майкрософт исключение представлено структурой [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record). Каждый объект `exception_ptr` содержит поле ссылки на исключение, указывающее на копию структуры `EXCEPTION_RECORD`, представляющую исключение.

При объявлении переменной `exception_ptr` эта переменная не связана ни с одним исключением. То есть в поле ссылки на исключение находится значение NULL. Такой объект `exception_ptr` называется *exception_ptr null*.

Используйте функцию `current_exception` или `make_exception_ptr` для назначения исключения объекту `exception_ptr`. При назначении исключения переменной `exception_ptr` поле ссылки на исключение переменной указывает на копию исключения. При нехватке памяти для копирования исключения поле ссылки на исключение указывает на копию исключения [std::bad_alloc](../standard-library/bad-alloc-class.md). Если `current_exception` функция `make_exception_ptr` не может скопировать исключение по какой-либо другой причине, функция вызывает функцию `terminate` CRT для выхода из текущего процесса.

Несмотря на свое имя, объект `exception_ptr` не является указателем. Он не повинуется семантике указателя и не может использоваться с операторами доступа к членам указателей (`->`) или косвенного обращения (*). Объект `exception_ptr` не имеет открытых данных-членов и функций-членов.

**Сравнения:**

Можно использовать операторы равенства (`==`) и неравенства (`!=`) для сравнения двух объектов `exception_ptr`. Эти операторы не сравнивают бинарное значение (битовый шаблон) структур `EXCEPTION_RECORD`, которые представляют исключения. Вместо этого операторы сравнивают адреса в поле ссылки на исключение объектов `exception_ptr`. Поэтому `exception_ptr` со значением null и значение NULL при сравнении считаются равными.

## <a name="terminate_handler"></a><a name="terminate_handler"></a>terminate_handler

Тип, который описывает указатель на функцию, подходящую для использования в качестве `terminate_handler`.

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Примечания

Тип, который описывает указатель на функцию, подходящую для использования в качестве обработчика завершения.

### <a name="example"></a>Пример

См. [set_terminate](../standard-library/exception-functions.md#set_terminate), чтобы ознакомиться с примером использования `terminate_handler`.

## <a name="unexpected_handler"></a><a name="unexpected_handler"></a>unexpected_handler

Тип, который описывает указатель на функцию, подходящую для использования в качестве `unexpected_handler`.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Пример

См. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) в качестве примера использования `unexpected_handler`.
