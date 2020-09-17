---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 26dda2dff83ff0adbb7ef05c5e75f64b44138bd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170675"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Блок, относящийся только к системам Microsoft**

Вызывает функцию члена **QueryInterface** `IUnknown` с указателем на инкапсулированный интерфейс.

## <a name="syntax"></a>Синтаксис

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>Параметры

*IID*<br/>
`IID` указателя интерфейса.

*p*<br/>
Необработанный указатель на интерфейс.

## <a name="remarks"></a>Примечания

Вызывает `IUnknown::QueryInterface` в инкапсулированном указателе интерфейса с указанным `IID` и возвращает результирующий необработанный указатель интерфейса в *p*. Эта подпрограммы возвращает значение HRESULT для обозначения успеха или неудачи.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
