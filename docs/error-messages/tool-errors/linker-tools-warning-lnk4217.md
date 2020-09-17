---
title: Предупреждение средств компоновщика LNK4217
ms.date: 07/23/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 1ce410312493b353bb68ea7264fce9cd6a394e0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183115"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217

> символ "*symbol*", определенный в "*filename_1. obj*", импортируется "*filename_2. obj*" в функции "*Function*"

для символа был указан [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) , хотя символ определен в объектном файле в том же образе. Удалите модификатор `__declspec(dllimport)`, чтобы устранить это предупреждение.

## <a name="remarks"></a>Примечания

*symbol* — это имя символа, определенное в изображении. *функция* — это функция, которая импортирует символ.

Это предупреждение не появляется при компиляции с параметром [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

LNK4217 также может возникнуть при попытке связать два модуля вместе, когда вместо этого следует компилировать второй модуль с помощью библиотеки импорта первого модуля.

```cpp
// main.cpp
__declspec(dllimport) void func();

int main()
{
    func();
    return 0;
}

```

Затем:

```cpp
// tt.cpp
// compile with: /c
void func() {}
```

Попытка скомпилировать эти два модуля, как показано ниже, приведет к LNK4217:

```cmd
cl.exe /c main.cpp tt.cpp
link.exe main.obj tt.obj
```

Чтобы устранить эту ошибку, после компиляции двух файлов передайте TT. obj в lib. exe, чтобы создать LIB-файл, а затем свяжите Main. obj с TT. lib, как показано ниже:

```cmd
cl.exe /c main.cpp tt.cpp
lib.exe tt.obj /export:func /def
link.exe main.obj tt.lib
```

## <a name="see-also"></a>См. также раздел

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение средств компоновщика LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
