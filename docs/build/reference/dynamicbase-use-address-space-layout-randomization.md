---
title: /DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))
ms.date: 06/12/2018
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
ms.openlocfilehash: 9af502d65dd81efdedc6b80951f11d68f766cb31
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842628"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))

Указывает, создавать ли исполняемый образ, который может быть случайным образом изменен во время загрузки, с помощью функции имитации макета адресного пространства (ASLR) Windows, которая была впервые доступна в Windows Vista.

## <a name="syntax"></a>Синтаксис

> **/DynamicBase**[**: нет**]

## <a name="remarks"></a>Примечания

Параметр **/DynamicBase** изменяет заголовок *исполняемого образа*, DLL или EXE-файла, чтобы указать, должно ли приложение случайным образом перераспределяться во время загрузки, и разрешает случайное выделение виртуальных адресов, что влияет на расположение кучи, стеки и другие выделения операционных систем. Параметр **/DynamicBase** применяется как для 32-разрядных, так и для 64-разрядных изображений. ASLR поддерживается в операционных системах Windows Vista и более поздних версий. Этот параметр не учитывается в более ранних операционных системах.

По умолчанию **/DynamicBase** включен. Чтобы отключить этот параметр, используйте **/DynamicBase: No**. Параметр **/DynamicBase** требуется для того, чтобы параметр [/highentropyva](highentropyva-support-64-bit-aslr.md) действовал.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите вкладку **Свойства конфигурации**  >  **компоновщика**  >  **Дополнительные** свойства.

1. Измените свойство " **случайный базовый адрес** ".

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>См. также раздел

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Средства защиты программного обеспечения Windows ISV](/previous-versions/bb430720(v=msdn.10))
