---
title: Implements - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
ms.openlocfilehash: 223f37d7cabbd0b8cd238582773c05d7b9eaabf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371409"
---
# <a name="implements-structure"></a>Implements - структура

Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

template <
    int flags,
    typename I0,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8
>
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Идентификатор интерфейса нулевой. (обязательный параметр)

*I1*<br/>
Первый идентификатор интерфейса. (необязательно)

*I2*<br/>
Второй идентификатор интерфейса. (необязательно)

*I3*<br/>
Третий идентификатор интерфейса. (необязательно)

*I4*<br/>
Четвертый идентификатор интерфейса. (необязательно)

*I5*<br/>
Пятый идентификатор интерфейса. (необязательно)

*I6*<br/>
Шестой идентификатор интерфейса. (необязательно)

*I7*<br/>
Седьмой идентификатор интерфейса. (необязательно)

*I8*<br/>
Восьмой идентификатор интерфейса. (необязательно)

*I9*<br/>
Девятый идентификатор интерфейса. (необязательно)

*Флаги*<br/>
Конфигурация флагов для класса. Один или несколько [перечислений RuntimeClassType,](runtimeclasstype-enumeration.md) указанные в структуре [RuntimeClassFlags.](runtimeclassflags-structure.md)

## <a name="remarks"></a>Примечания

Выводится из списка указанных интерфейсов и реализует `QueryInterface` `GetIid`шаблоны помощников для и .

Каждый параметр интерфейса *I0* `IUnknown`через `IInspectable` *I9* должен вытекать из шаблона [ChainInterfaces.](chaininterfaces-structure.md) Параметр *флагов* определяет, генерируется ли поддержка для `IUnknown` или `IInspectable`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

| Имя        | Описание                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| Синоним для `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Защищенные методы

| Имя                                              | Описание                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Реализует::CanCastTo](#cancastto)               | Получает указатель на указанный интерфейс.                                                                    |
| [Реализует::CastToUnknown](#casttounknown)       | Получает указатель на базовый `IUnknown` интерфейс.                                                        |
| [Реализации::FillArrayWithIid](#fillarraywithiid) | Вставляет идентификатор интерфейса, указанный текущим параметром шаблона нулевой, в указанный элемент массива. |

### <a name="protected-constants"></a>Защищенные константы

| Имя                              | Описание                                    |
| --------------------------------- | ---------------------------------------------- |
| [Реализации::IidCount](#iidcount) | Сохраняет количество итогов интерфейса. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="implementscancastto"></a><a name="cancastto"></a>Реализует::CanCastTo

Получает указатель на указанный интерфейс.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса.

*Ppv*<br/>
В случае успеха указатель на интерфейс, указанный *riid*.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, HRESULT, который указывает на ошибку, такие как E_NOINTERFACE.

### <a name="remarks"></a>Примечания

Это внутренняя функция помощника, выполняющего операцию QueryInterface.

## <a name="implementscasttounknown"></a><a name="casttounknown"></a>Реализует::CastToUnknown

Получает указатель на базовый `IUnknown` интерфейс.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Эта операция всегда удается `IUnknown` и возвращает указатель.

### <a name="remarks"></a>Примечания

Внутренняя вспомогательная функция.

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a>Реализации::FillArrayWithIid

Вставляет идентификатор интерфейса, указанный текущим параметром шаблона нулевой, в указанный элемент массива.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Индекс с нулевым уровнем, указывающий элемент стартового массива для этой операции. Когда эта операция завершается, *индекс* приравнизирован на 1.

*iids*<br/>
Массив типа IID.

### <a name="remarks"></a>Примечания

Внутренняя вспомогательная функция.

## <a name="implementsiidcount"></a><a name="iidcount"></a>Реализации::IidCount

Сохраняет количество итогов интерфейса.

```cpp
static const unsigned long IidCount;
```
