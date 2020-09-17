---
title: Макрос ActivatableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 7bc3d789d6c0d304aa170d59dff23a97a67061d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214289"
---
# <a name="activatableclass-macros"></a>Макрос ActivatableClass

Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса.

## <a name="syntax"></a>Синтаксис

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя создаваемого класса.

*установлен*<br/>
Фабрика, которая создаст экземпляр указанного класса.

*serverName*<br/>
Имя, указывающее подмножество фабрик в модуле.

## <a name="remarks"></a>Примечания

Не используйте эти макросы с классической моделью COM, если не используется директива `#undef`, чтобы гарантировать удаление определения макроса `__WRL_WINRT_STRICT__`.

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Класс Module](module-class.md)
