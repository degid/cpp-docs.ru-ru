---
title: Функция CreateActivationFactory
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: ab03b15a968c6aba3fa6df8c975fb98e873f8e23
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214075"
---
# <a name="createactivationfactory-function"></a>Функция CreateActivationFactory

Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Сочетание одного или нескольких значений перечисления [RuntimeClassType](runtimeclasstype-enumeration.md) .

*entry*<br/>
Указатель на [CreatorMap](creatormap-structure.md) , содержащий сведения об инициализации и регистрации параметра *riid*.

*riid*<br/>
Ссылка на идентификатор интерфейса.

*ппфактори*<br/>
Если эта операция завершается успешно, указатель на фабрику активации.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Если *фабрика* параметров шаблона не является производной от интерфейса `IActivationFactory`, генерируется ошибка Assert.

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Wrappers::Details](microsoft-wrl-wrappers-details-namespace.md)
