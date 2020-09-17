---
title: /CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: ccf13971bf77fb8e960b781e4a1aa2a0e06a5d61
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686107"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)

**Параметр/CLRSUPPORTLASTERROR**, который включен по умолчанию, сохраняет последний код ошибки функций, вызываемых через механизм P/Invoke, который позволяет вызывать собственные функции в библиотеках DLL из кода, скомпилированного с **параметром/CLR**.

## <a name="syntax"></a>Синтаксис

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Примечания

Сохранение последнего кода ошибки подразумевает снижение производительности.  Если вы не хотите повлиять на производительность с сохранением последнего кода ошибки, выполните компоновку с помощью  **параметр/CLRSUPPORTLASTERROR: No**.

Можно уменьшить влияние на производительность, связавсь с **параметр/CLRSUPPORTLASTERROR: системдлл**, который сохраняет только последний код ошибки для функций в системных библиотеках DLL.

> [!NOTE]
> Сохранение последней ошибки не поддерживается для неуправляемых функций, используемых кодом CLR в одном модуле.

- Дополнительные сведения см. в разделе [/CLR (компиляция среды CLR)](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в поле **Дополнительные параметры** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Примеры

В следующем примере определяется собственная библиотека DLL с одной экспортированной функцией, которая изменяет последнюю ошибку.

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

В следующем примере используется библиотека DLL, в которой демонстрируется использование **параметр/CLRSUPPORTLASTERROR**.

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
