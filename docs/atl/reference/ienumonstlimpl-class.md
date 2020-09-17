---
title: Класс IenumOnSTLimpl
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 2fbe6ccfbea2836c42a054da7ea9ebeac4e1555d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329714"
---
# <a name="ienumonstlimpl-class"></a>Класс IenumOnSTLimpl

Этот класс определяет интерфейс регистратора на основе коллекции Стандартной библиотеки СЗ.

## <a name="syntax"></a>Синтаксис

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Перечисление COM. См примера можно осмотреть [IEnumString.](/windows/win32/api/objidl/nn-objidl-ienumstring)

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса.

*T*<br/>
Тип элемента, выставленного интерфейсом перечисления.

*Копирование*<br/>
[Класс политики копирования](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
Класс контейнеров Стандартной библиотеки СЗ.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IEnumOnSTLImpl::Клон](#clone)|Реализация **клонов**.|
|[IEnumOnSTLImpl::Init](#init)|Инициализирует перечислитель.|
|[IenumOnSTLImpl::Следующий](#next)|Реализация **Next**.|
|[IEnumOnSTLImpl::Перезагрузка](#reset)|Реализация **перезагрузки**.|
|[IenumOnSTLImpl::Skip](#skip)|Реализация **Skip**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IenumOnSTLImpl::m_iter](#m_iter)|Итератор, представляющий текущее положение регистратора в коллекции.|
|[IenumOnSTLImpl::m_pcollection](#m_pcollection)|Указатель на контейнер Стандартной библиотеки СЗ, вмещающих перечисленные элементы.|
|[IenumOnSTLImpl::m_spUnk](#m_spunk)|Указатель `IUnknown` объекта, поставляющего коллекцию.|

## <a name="remarks"></a>Примечания

`IEnumOnSTLImpl`обеспечивает реализацию интерфейса com enumerator, в котором перечисленные элементы хранятся в контейнере, совместимом со стандартной библиотекой. Этот класс аналогис [cComEnumImpl,](../../atl/reference/ccomenumimpl-class.md) который обеспечивает реализацию интерфейса enumerator на основе массива.

> [!NOTE]
> Смотрите [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) для получения подробной информации о дальнейших различиях между `CComEnumImpl` и `IEnumOnSTLImpl`.

Как правило, вам *не* нужно создавать свой собственный класс enumerator, исходя из этой реализации интерфейса. Если вы хотите использовать регистратор ATL,поставленный на основе контейнера стандартной библиотеки СЗ, чаще создается экземпляр [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)или создается класс коллекции, который возвращает регистратор, вытекая из [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).

Однако, если вам нужно предоставить пользовательский регистратор (например, тот, который предоставляет интерфейсы в дополнение к интерфейсу перечисления), вы можете извлечь из этого класса. В этой ситуации вполне вероятно, что вам придется переопределить метод [клона,](#clone) чтобы обеспечить собственную реализацию.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ienumonstlimplinit"></a><a name="init"></a>IEnumOnSTLImpl::Init

Инициализирует перечислитель.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Параметры

*pUnkForRelease*<br/>
(в) Указатель `IUnknown` объекта, который должен быть сохранен в живых в течение всего срока службы регистратора. Передайте NULL, если такого объекта не существует.

*Коллекции*<br/>
Ссылка на контейнер Стандартной библиотеки СЗ, в мещах элементов, которые будут перечислены.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если вы `Init` передаете ссылку на коллекцию, хранящуюся в другом объекте, можно использовать параметр *pUnkForRelease,* чтобы гарантировать, что объект и его коллекция доступны до тех пор, пока он нужен регистратору.

Вы должны вызвать этот метод перед передачей указателя на интерфейс перечисления обратно к любым клиентам.

## <a name="ienumonstlimplclone"></a><a name="clone"></a>IEnumOnSTLImpl::Клон

Этот метод обеспечивает реализацию метода **клона** путем `CComEnumOnSTL`создания объекта типа, инициализации его с той же коллекцией и итератором, используемого текущим объектом, и возвращения интерфейса на вновь созданный объект.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Параметры

*ppEnum*<br/>
(ваут) Интерфейс перечисления на недавно созданном объекте, клонированном из текущего регистратора.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a>IenumOnSTLImpl::m_spUnk

Указатель `IUnknown` объекта, поставляющего коллекцию.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Примечания

Этот умный указатель поддерживает ссылку на объект, передаваемый [IEnumOnSTLImpl::Init](#init), гарантируя, что он остается живым в течение всего срока службы регистратора.

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a>IenumOnSTLImpl::m_pcollection

Этот участник указывает на коллекцию, которая предоставляет данные, движущие реализацию интерфейса enumerator.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Примечания

Этот участник инициализирован вызовом в [IEnumOnSTLImpl::Init](#init).

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a>IenumOnSTLImpl::m_iter

Этот участник удерживает итератор, используемый для обозначения текущего положения в коллекции и навигации по последующим элементам.

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a>IenumOnSTLImpl::Следующий

Этот метод обеспечивает реализацию **следующего** метода.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Параметры

*celt*<br/>
(в) Количество запрошенных элементов.

*Rgelt*<br/>
(ваут) Массив, который должен быть заполнен элементами.

*pceltFetched*<br/>
(ваут) Количество элементов фактически возвращается в *rgelt*. Это может быть меньше, чем *кельт,* если меньше, чем *элементы кельта* остаются в списке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ienumonstlimplreset"></a><a name="reset"></a>IEnumOnSTLImpl::Перезагрузка

Этот метод обеспечивает реализацию метода **сбросить.**

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ienumonstlimplskip"></a><a name="skip"></a>IenumOnSTLImpl::Skip

Этот метод обеспечивает реализацию метода **Skip.**

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Параметры

*celt*<br/>
(в) Количество элементов, чтобы пропустить.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
