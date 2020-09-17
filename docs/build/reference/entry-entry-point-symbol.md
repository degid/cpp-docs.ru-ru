---
title: /ENTRY (символ точки входа)
ms.date: 11/04/2016
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
ms.openlocfilehash: 80833980b64e8fdd2a2f57b2dc40eb21c784b6f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232707"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (символ точки входа)

```
/ENTRY:function
```

## <a name="arguments"></a>Аргументы

*function*<br/>
Функция, указывающая определяемый пользователем начальный адрес для EXE-файла или библиотеки DLL.

## <a name="remarks"></a>Примечания

Параметр/ENTRY задает функцию точки входа в качестве начального адреса для EXE-файла или библиотеки DLL.

Для использования **`__stdcall`** соглашения о вызовах функция должна быть определена. Параметры и возвращаемое значение зависят от того, является ли программа консольным приложением, приложением Windows или библиотекой DLL. Рекомендуется позволить компоновщику установить точку входа таким образом, чтобы библиотека времени выполнения языка C была инициализирована правильно, а также выполнялись конструкторы C++ для статических объектов.

По умолчанию начальный адрес — это имя функции из библиотеки времени выполнения языка C. Компоновщик выбирает его в соответствии с атрибутами программы, как показано в следующей таблице.

|Имя функции|По умолчанию для|
|-------------------|-----------------|
|**mainCRTStartup** (или **вмаинкртстартуп**)|Приложение, использующее/SUBSYSTEM: CONSOLE; вызовы `main` (или `wmain` )|
|**Винмаинкртстартуп** (или **ввинмаинкртстартуп**)|Приложение, использующее/SUBSYSTEM:**Windows**; вызовы `WinMain` (или `wWinMain` ), которые должны быть определены для использования**`__stdcall`**|
|**_DllMainCRTStartup**|DLL; вызывает `DllMain` , если он существует, который должен быть определен для использования**`__stdcall`**|

Если параметр [/DLL](dll-build-a-dll.md) или [/SUBSYSTEM](subsystem-specify-subsystem.md) не указан, компоновщик выбирает подсистему и точку входа в зависимости от того, `main` `WinMain` определено ли значение.

Функции `main` , `WinMain` и `DllMain` являются тремя формами пользовательской точки входа.

При создании управляемого образа функция, указанная в/ENTRY, должна иметь сигнатуру (ЛПВОИД *var1*, DWORD *var2*, лпвоид *var3*).

Сведения о том, как определить собственную `DllMain` точку входа, см. в разделе [dll и Visual C++ поведение библиотеки времени выполнения](../run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Перейдите на страницу свойств **Дополнительно** .

1. Измените свойство **точки входа** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>См. также статью

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
