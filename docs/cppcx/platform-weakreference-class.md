---
title: Класс Platform::WeakReference
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
ms.openlocfilehash: befefba7cc76f24f6dddd58d0c5f040bfd205508
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216600"
---
# <a name="platformweakreference-class"></a>Класс Platform::WeakReference

Представляет слабую ссылку на экземпляр класса ссылок.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakReference
```

#### <a name="parameters"></a>Параметры

### <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Член|Описание|
|------------|-----------------|
|[WeakReference:: WeakReference](#ctor)|Инициализирует новый экземпляр класса WeakReference.|

### <a name="methods"></a>Методы

|Член|Описание|
|------------|-----------------|
|[WeakReference:: Resolve](#resolve)|Возвращает дескриптор базовому классу ссылок или значение nullptr, если объект больше не существует.|

### <a name="operators"></a>Операторы

|Член|Описание|
|------------|-----------------|
|[WeakReference::operator=](#operator-assign)|Присваивает новое значение объекту WeakReference.|
|[WeakReference::operator BoolType](#booltype)|Реализует шаблон безопасного логического типа.|

### <a name="remarks"></a>Примечания

Класс WeakReference сам не является классом ссылок и поэтому не наследуется от Platform::Object^ и не может использоваться в сигнатуре открытого метода.

## <a name="weakreferenceoperator"></a><a name="operator-assign"></a>WeakReference::operator=

Присваивает значение WeakReference.

### <a name="syntax"></a>Синтаксис

```cpp
WeakReference& operator=(decltype(__nullptr));
WeakReference& operator=(const WeakReference& otherArg);
WeakReference& operator=(WeakReference&& otherArg);
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg);
```

### <a name="remarks"></a>Примечания

Последняя перегрузка в списке выше позволяет назначить класс ссылок переменной WeakReference. В этом случае класс ссылки является производным от класса [Platform:: Object](../cppcx/platform-object-class.md)^. Исходный тип восстанавливается позднее путем указания его в качестве аргумента для параметра типа в функции члена [WeakReference:: Resolve \<T> ](#resolve) .

## <a name="weakreferenceoperator-booltype"></a><a name="booltype"></a>WeakReference::operator BoolType

Реализует безопасный шаблон bool для класса WeakReference. Не предназначен для явного вызова в коде.

### <a name="syntax"></a>Синтаксис

```cpp
BoolType BoolType();
```

## <a name="weakreferenceresolve-method-platform-namespace"></a><a name="resolve"></a>Метод WeakReference:: Resolve (пространство имен платформы)

Возвращает маркер исходного класса ссылки или **`nullptr`** значение, если объект больше не существует.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
T^ Resolve() const;
```

### <a name="parameters"></a>Параметры

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Дескриптор класс ссылок, с которым ранее был связан объект WeakReference, или значение nullptr.

### <a name="example"></a>Пример

```cpp
Bar^ bar = ref new Bar();
//use bar...

if (bar != nullptr)
{
    WeakReference wr(bar);
    Bar^ newReference = wr.Resolve<Bar>();
}
```

Обратите внимание, что параметр типа — T, а не T^.

## <a name="weakreferenceweakreference-constructor"></a><a name="ctor"></a>Конструктор WeakReference:: WeakReference

Предоставляет различные способы построения WeakReference.

### <a name="syntax"></a>Синтаксис

```cpp
WeakReference();
WeakReference(decltype(__nullptr));
WeakReference(const WeakReference& otherArg);
WeakReference(WeakReference&& otherArg);
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);
```

### <a name="example"></a>Пример

```cpp
MyClass^ mc = ref new MyClass();
WeakReference wr(mc);
MyClass^ copy2 = wr.Resolve<MyClass>();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
