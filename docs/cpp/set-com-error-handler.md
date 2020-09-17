---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: debad733f351c710ada342e29fa95a4d1ff03b7d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749806"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

Заменяет функцию по умолчанию, используемую для обработки ошибок COM. **_set_com_error_handler** специфичен для корпорации Майкрософт.

## <a name="syntax"></a>Синтаксис

```cpp
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>Параметры

*pHandler*<br/>
Указатель на функцию замены.

*Hr*<br/>
Информация HRESULT.

*perrinfo*<br/>
Объект `IErrorInfo`.

## <a name="remarks"></a>Примечания

По умолчанию [_com_raise_error](../cpp/com-raise-error.md) обрабатывает все ошибки COM. Вы можете изменить это поведение, используя **_set_com_error_handler** для вызова собственной функции обработки ошибок.

Функция замены должна иметь сигнатуру, эквивалентную сигнатуре `_com_raise_error`.

## <a name="example"></a>Пример

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef.h>

**Lib:** Если указан абии компилятора **/sc:wchar_t** (по умолчанию), используйте comsuppw.lib или comsuppwd.lib. Если указан аномалку **/c:wchar_t-** компилятор, используйте comsupp.lib. Для получения дополнительной информации, в том числе о том, как установить эту опцию в IDE, [см.: wchar_t (wchar_t является родным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также раздел

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)
