---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: f5efbe98a489a380c4e9be5a0e40603be2a409c0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745081"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft Специфический**

Бросает [_com_error](../cpp/com-error-class.md) в ответ на неудачу.

## <a name="syntax"></a>Синтаксис

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Параметры

*Hr*<br/>
Информация HRESULT.

*perrinfo*<br/>
Объект `IErrorInfo`.

## <a name="remarks"></a>Примечания

**_com_raise_error**, который \<определен в> comdef.h, может быть заменен анаконом одноименной версии и прототипа. Это можно сделать, если требуется использовать `#import` без обработки исключений C++. В этом случае пользовательская версия **_com_raise_error** может `longjmp` принять решение сделать или отобразить окно сообщений и остановиться. Однако пользовательская версия не должна возвращаться, поскольку код поддержки COM в компиляторе не ожидает ее возврата.

Вы также можете использовать [_set_com_error_handler](../cpp/set-com-error-handler.md) для замены функции обработки ошибок по умолчанию.

По умолчанию **_com_raise_error** определяется следующим образом:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**END Microsoft Специфический**

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef.h>

**Lib:** Если wchar_t вариант компилятора **Native Type,** используйте comsuppw.lib или comsuppwd.lib. Если **wchar_t Native Type** выключен, используйте comsupp.lib. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также раздел

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
