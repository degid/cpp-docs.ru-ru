---
title: Класс Platform::Collections::VectorView
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
ms.openlocfilehash: 207f5d517eaae475af1c65a284a3d1ebe50621af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218394"
---
# <a name="platformcollectionsvectorview-class"></a>Класс Platform::Collections::VectorView

Представляет доступное только для чтения представление упорядоченной коллекции объектов, в которой возможен доступ к каждому отдельному объекту по его индексу. Тип каждого объекта в коллекции задается параметром шаблона.

## <a name="syntax"></a>Синтаксис

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип элементов, содержащихся в объекте `VectorView` .

*&*<br/>
Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.

### <a name="remarks"></a>Примечания

`VectorView`Класс реализует интерфейс [Windows:: Foundation:: Collections:: IVectorView \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1) и поддерживает итераторы стандартной библиотеки шаблонов.

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[VectorView:: VectorView](#ctor)|Инициализирует новый экземпляр класса VectorView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[VectorView:: First](#first)|Возвращает итератор, указывающий первый элемент объекта VectorView.|
|[VectorView:: GetAt](#getat)|Извлекает элемент текущего VectorView, указанный заданным индексом.|
|[VectorView:: many](#getmany)|Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.|
|[VectorView:: IndexOf](#indexof)|Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.|
|[VectorView::Size](#size)|Возвращает количество элементов в текущем объекте VectorView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a>Метод VectorView:: First

Возвращает итератор, указывающий первый элемент объекта VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта VectorView.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myVectorView->First();`.

## <a name="vectorviewgetat-method"></a><a name="getat"></a>Метод VectorView:: GetAt

Извлекает элемент текущего VectorView, указанный заданным индексом.

### <a name="syntax"></a>Синтаксис

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте VectorView.

### <a name="return-value"></a>Возвращаемое значение

Элемент, заданный параметром `index`. Тип элемента задается параметром шаблона VectorView, *т*. е.

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a>Метод VectorView:: many

Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.

### <a name="syntax"></a>Синтаксис

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>Параметры

*startIndex*<br/>
Отсчитываемый от нуля индекс начала элементов для извлечения.

*dest*<br/>
Когда эта операция завершается, массив элементов начинается с элемента, заданного `startIndex`, и заканчивается последним элементом объекта VectorView.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

## <a name="vectorviewindexof-method"></a><a name="indexof"></a>Метод VectorView:: IndexOf

Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Элемент, который нужно найти.

*номер*<br/>
Отсчитываемый от нуля индекс элемента, если параметр `value` найден; в противном случае — 0.

Параметр *индекса* равен 0, если элемент является первым элементом элемента `VectorView` или элемент не найден. Если возвращаемое значение равно **`true`** , элемент был найден и является первым элементом; в противном случае элемент не был найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если указанный элемент найден; в противном случае — **`false`** .

## <a name="vectorviewsize-method"></a><a name="size"></a>Метод VectorView:: size

Возвращает количество элементов в текущем объекте VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте VectorView.

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a>Конструктор VectorView:: VectorView

Инициализирует новый экземпляр класса VectorView.

### <a name="syntax"></a>Синтаксис

```
VectorView();
explicit VectorView(
   UInt32 size
);
VectorView(
   UInt32 size,
   T value
);
explicit VectorView(
   const ::std::vector<T>& v
);
explicit VectorView(
   ::std::vector<T>&& v
);
VectorView(
   const T * ptr,
   UInt32 size
);

template <
   size_t N
>
explicit VectorView(
   const T (&arr)[N]
);

template <
   size_t N
>
explicit VectorView(
   const ::std::array<T,
   N>& a
);

explicit VectorView(
   const ::Platform::Array<T>^ arr
);

template <
   typename InIt
>
VectorView(
   InItfirst,
   InItlast
);

VectorView(
   std::initializer_list<T> il
);
```

### <a name="parameters"></a>Параметры

*Ini*<br/>
Тип коллекции объектов, используемой для инициализации текущего объекта VectorView.

*компонента*<br/>
Объект [std:: initializer_list](../standard-library/initializer-list-class.md) , элементы которого будут использоваться для инициализации VectorView.

*N*<br/>
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта VectorView.

*size*<br/>
Количество элементов в объекте VectorView.

*value*<br/>
Значение, используемое для инициализации каждого элемента в текущем объекте VectorView.

*3,3*<br/>
[Значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std:: Vector](../standard-library/vector-class.md) , который используется для инициализации текущего VectorView.

*ptr*<br/>
Указатель на объект `std::vector`, используемый для инициализации текущего объекта VectorView.

*маленькая*<br/>
Объект [Platform:: Array](../cppcx/platform-array-class.md) , который используется для инициализации текущего VectorView.

*конкретного*<br/>
Объект [std:: Array](../standard-library/array-class-stl.md) , который используется для инициализации текущего VectorView.

*first*<br/>
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `first` передается средствами *идеальной пересылки*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*last*<br/>
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `last` передается средствами *идеальной пересылки*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
