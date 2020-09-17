---
title: Класс WeakRef
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 715a823784aaa75f9abe349ef0a7ddc9e5d607d1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218355"
---
# <a name="weakref-class"></a>Класс WeakRef

Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор WeakRef::WeakRef](#weakref)|Инициализирует новый экземпляр класса `WeakRef`.|
|[Деструктор WeakRef::~WeakRef](#tilde-weakref)|Выполняет деинициализацию текущего экземпляра `WeakRef` класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод WeakRef::As](#as)|Задает указанный `ComPtr` параметр указателя для представления указанного интерфейса.|
|[Метод WeakRef::AsIID](#asiid)|Задает указанный `ComPtr` параметр указателя для представления УКАЗАННОГО идентификатора интерфейса.|
|[Метод WeakRef::CopyTo](#copyto)|Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор WeakRef::operator&](#operator-ampersand-operator)|Возвращает `ComPtrRef` объект, представляющий текущий `WeakRef` объект.|

## <a name="remarks"></a>Примечания

`WeakRef`Объект поддерживает *строгую ссылку*, которая связана с объектом и может быть допустимой или недопустимой. `As()` `AsIID()` Чтобы получить строгую ссылку, вызовите метод или. Когда строгая ссылка допустима, возможно обращение к связанному объекту. Если строгая ссылка является недопустимой ( **`nullptr`** ), связанный объект недоступен.

`WeakRef`Объект обычно используется для представления объекта, существование которого управляется внешним потоком или приложением. Например, создайте `WeakRef` объект из ссылки на файловый объект. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.

Обратите внимание на изменение в поведении методов [As](#as), [AsIID](#asiid) и [CopyTo](#copyto) в пакете SDK для Windows 10. Ранее после вызова любого из этих методов можно было проверить, `WeakRef` **`nullptr`** чтобы определить, успешно ли получена строгая ссылка, как в следующем коде:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)
{
    wprintf(L"Couldn’t get strong ref!");
}
```

Приведенный выше код не работает при использовании пакета SDK для Windows 10 (или более поздней версии). Вместо этого проверьте указатель, переданный в параметре **`nullptr`** .

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

`WeakRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>Деструктор WeakRef:: ~ WeakRef

Выполняет деинициализацию текущего экземпляра `WeakRef` класса.

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>Метод WeakRef:: AS

Задает указанный `ComPtr` параметр указателя для представления указанного интерфейса.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>Параметры

*U*<br/>
Идентификатор интерфейса.

*ptr*<br/>
По завершении этой операции объект, представляющий параметр *U*.

### <a name="return-value"></a>Возвращаемое значение

- S_OK, если эта операция завершилась с ошибкой; в противном случае возвращается значение HRESULT, указывающее причину сбоя операции, а для свойства *ptr* — значение **`nullptr`** .

- S_OK, если эта операция завершилась успешно, но текущий `WeakRef` объект уже был освобожден. Параметр *ptr* имеет значение **`nullptr`** .

- S_OK, если эта операция завершилась с ошибкой, но текущий `WeakRef` объект не является производным от параметра *U*. Параметр *ptr* имеет значение **`nullptr`** .

### <a name="remarks"></a>Примечания

Если параметр *U* имеет значение `IWeakReference` или не является производным от, генерируется ошибка `IInspectable` .

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

Начиная с пакета SDK для Windows 10, этот метод не задает `WeakRef` для экземпляра значение **`nullptr`** , если не удалось получить слабую ссылку, поэтому следует избегать проверки ошибок, которые проверяют значение `WeakRef` для **`nullptr`** . Вместо этого проверьте *ptr* для **`nullptr`** .

## <a name="weakrefasiid-method"></a><a name="asiid"></a>Метод WeakRef:: AsIID

Задает указанный `ComPtr` параметр указателя для представления УКАЗАННОГО идентификатора интерфейса.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ptr*<br/>
По завершении этой операции объект, представляющий параметр *riid*.

### <a name="return-value"></a>Возвращаемое значение

- S_OK, если эта операция завершилась с ошибкой; в противном случае возвращается значение HRESULT, указывающее причину сбоя операции, а для свойства *ptr* — значение **`nullptr`** .

- S_OK, если эта операция завершилась успешно, но текущий `WeakRef` объект уже был освобожден. Параметр *ptr* имеет значение **`nullptr`** .

- S_OK, если эта операция выполнена, но текущий `WeakRef` объект не является производным от параметра *riid*. Параметр *ptr* имеет значение **`nullptr`** . (Дополнительные сведения см. в разделе "Примечания".)

### <a name="remarks"></a>Примечания

Если параметр *riid* не является производным от, генерируется ошибка `IInspectable` . Эта ошибка заменяет возвращаемое значение.

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон (не показанный здесь, но объявленный в файле заголовка) является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

Начиная с пакета SDK для Windows 10, этот метод не задает `WeakRef` для экземпляра значение **`nullptr`** , если не удалось получить слабую ссылку, поэтому следует избегать проверки ошибок, которые проверяют значение `WeakRef` для **`nullptr`** . Вместо этого проверьте *ptr* для **`nullptr`** .

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>Метод WeakRef:: CopyTo

Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Параметры

*U*<br/>
Указатель `IInspectable` интерфейса. Если *U* не является производным от, генерируется ошибка `IInspectable` .

*riid*<br/>
Идентификатор интерфейса. Если *riid* не является производным от, генерируется ошибка `IWeakReference` .

*ptr*<br/>
Двойной непрямой указатель на `IInspectable` или `IWeakReference` .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Дополнительные сведения см. в разделе **Примечания**.

### <a name="remarks"></a>Примечания

Возвращаемое значение S_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если возвращается S_OK, проверьте, является ли параметр *p* строгой ссылкой; то есть параметр *p* не равен **`nullptr`** .

Начиная с пакета SDK для Windows 10, этот метод не задает `WeakRef` для экземпляра значение **`nullptr`** , если слабая ссылка не может быть получена, поэтому следует избегать проверки ошибок, которые проверяют значение `WeakRef` для **`nullptr`** . Вместо этого проверьте *ptr* для **`nullptr`** .

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>Оператор WeakRef::operator &amp;

Возвращает `ComPtrRef` объект, представляющий текущий `WeakRef` объект.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Возвращаемое значение

`ComPtrRef`Объект, представляющий текущий `WeakRef` объект.

### <a name="remarks"></a>Примечания

Это внутренний вспомогательный оператор, который не предназначен для использования в коде.

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>Конструктор WeakRef:: WeakRef

Инициализирует новый экземпляр класса `WeakRef`.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Указатель, ссылка или rvalue-ссылка на существующий объект, который инициализирует текущий `WeakRef` объект.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует пустой `WeakRef` объект. Второй конструктор инициализирует `WeakRef` объект из указателя на `IWeakReference` интерфейс. Третий конструктор инициализирует `WeakRef` объект из ссылки на `ComPtr<IWeakReference>` объект. Четвертый и пятый конструкторы инициализируют `WeakRef` объект из другого `WeakRef` объекта.
