---
title: /J (тип знака по умолчанию не подписан)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: d95fed3d9af81d89ac03a52a1e6433786118430e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223841"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (тип знака по умолчанию не подписан)

Изменяет тип по умолчанию **`char`** с **`signed char`** на **`unsigned char`** , а **`char`** тип — без расширения, если он расширяется до **`int`** типа.

## <a name="syntax"></a>Синтаксис

```
/J
```

## <a name="remarks"></a>Примечания

Если **`char`** значение явно объявлено как **`signed`** , параметр **/j** не влияет на него, а значение будет расширено знаком, когда оно расширяется до **`int`** типа.

Параметр **/j** определяет `_CHAR_UNSIGNED` , который используется с `#ifndef` в файле limits.h для определения диапазона типа по умолчанию **`char`** .

В ANSI C и C++ не требуется определенная реализация **`char`** типа. Этот параметр полезен при работе с символьными данными, которые со временем будут переведены на язык, отличный от английского.

> [!NOTE]
> При использовании этого параметра компилятора с ATL/MFC может возникать ошибка. Хотя эту ошибку можно отключить, определив `_ATL_ALLOW_CHAR_UNSIGNED` , это решение не поддерживается и может не всегда работать.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.

1. В диалоговом окне **страницы свойств** проекта в области слева в разделе **Свойства конфигурации**разверните узел **C/C++** и выберите пункт **Командная строка**.

1. В области **Дополнительные параметры** укажите параметр компилятора **/j** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>См. также статью

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md)
