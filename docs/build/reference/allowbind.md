---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 4f5b662223914cbb4970188595afb52cc2500cd4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440391"
---
# <a name="allowbind"></a>/ALLOWBIND

Указывает, может ли быть привязана библиотека DLL.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Примечания

Параметр **/ALLOWBIND** задает бит в заголовке библиотеки DLL, который указывает BIND. exe на то, что образ может быть привязан. Привязка позволяет быстрее загружать изображение, когда загрузчику не нужно перегружаться и выполнять исправление адресов для каждой библиотеки DLL, на которую указывает ссылка. Вы не хотите, чтобы библиотека DLL была привязана, если она подписана цифровой подписью, а привязывание сделает сигнатуру недействительной. Привязка не действует, если для образа включен случайный выбор структуры адресного пространства (ASLR) с помощью **/DynamicBase** для версий Windows, поддерживающих ASLR.

Используйте **/ALLOWBIND: No** , чтобы запретить BIND. exe ПРИВЯЗКУ библиотеки DLL.

Дополнительные сведения см. в описании параметра компоновщика [/ALLOWBIND](allowbind-prevent-dll-binding.md) .

## <a name="see-also"></a>См. также раздел

[Параметры EDITBIN](editbin-options.md)
