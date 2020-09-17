---
title: /Wp64 (выявление проблем переносимости на 64-разрядные платформы)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: e5c30ac9096094948a83195f5b3990794c421685
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335890"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (выявление проблем переносимости на 64-разрядные платформы)

Этот параметр компилятора не рекомендуется. В версиях до Visual Studio 2013 это позволяет выявить проблемы с 64-разрядной переносимостью для типов, помеченных также ключевым словом [__w64](../../cpp/w64.md) .

## <a name="syntax"></a>Синтаксис

```
/Wp64
```

## <a name="remarks"></a>Примечания

По умолчанию, в версиях Visual Studio перед Visual Studio 2013, опция компилятора **/Wp64** выключена в компиляторе MSVC, который создает 32-битный код x86, и в компиляторе MSVC, который создает 64-битный код x64.

> [!IMPORTANT]
> Параметр компилятора [/Wp64](wp64-detect-64-bit-portability-issues.md) и ключевое слово [__w64](../../cpp/w64.md) являются устаревшими в Visual Studio 2010 и Visual Studio 2012. Они не поддерживаются в версиях начиная с Visual Studio 2013. Если вы преобразуете проект, использующий этот параметр, то во время преобразования он не будет перенесен. Для использования этого параметра в Visual Studio 2010 или Visual Studio 2012 следует ввести параметр компилятора в области **Дополнительные параметры** раздела **Командная строка** в свойствах проекта. Если в командной строке используется параметр компилятора **/Wp64** , компилятор выводит предупреждение командной строки D9002. Вместо того, чтобы использовать эту опцию и ключевое слово для обнаружения 64-битных проблем переносимости, используйте компилятор MSVC, который нацелен на 64-битную платформу и укажите опцию [/W4.](compiler-option-warning-level.md) Для получения дополнительной [Configure C++ projects for 64-bit, x64 targets](../configuring-programs-for-64-bit-visual-cpp.md)информации см.

Следующие типы переменных проверяются в 32-разрядной операционной системе, как если бы они использовались в 64-разрядной операционной системе:

- INT

- long

- указатель

Если вы регулярно компилируете свое приложение с помощью компилятора, который создает 64-разрядный код x64, вы можете просто отключить **/Wp64** в 32-битных компиляциях, потому что 64-разрядный компилятор обнаружит все проблемы. Для получения более подробной информации о том, [Configure C++ projects for 64-bit, x64 targets](../configuring-programs-for-64-bit-visual-cpp.md)как настроить таргетинг на операционную систему Windows 64,8, см.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта.

   Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Измените поле **Дополнительные параметры** , включив в него параметр **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)<br/>
[Настройка проектов C++ для 64-разрядных целевых объектов с архитектурой x64](../configuring-programs-for-64-bit-visual-cpp.md)
