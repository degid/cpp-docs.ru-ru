---
title: Пошаговое руководство. Создание и использование статической библиотеки (C++)
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.author: corob
ms.openlocfilehash: 506db5ea8e94887d9971b48c06ce8c0d6156dccb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785089"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>Пошаговое руководство. Создание и использование статической библиотеки (C++)

В этом пошаговом руководстве описывается создание статической библиотеки (LIB-файла) для использования с приложениями C++. Статические библиотеки являются хорошим способом повторного использования кода. Вместо того чтобы воссоздание те же подпрограммы в каждом приложении, требуются функциональные возможности, вы пишете одно время в статической библиотеке и затем ссылаться на него из приложений. Код, подключенный из статической библиотеки, становится частью вашего приложения — для использования кода не нужно устанавливать еще какой-либо файл.

В этом пошаговом руководстве рассматриваются следующие задачи:

- [Создание проекта статической библиотеки](#CreateLibProject)

- [Добавление класса в статическую библиотеку](#AddClassToLib)

- [Создание консольного приложения C++, ссылающегося на статическую библиотеку](#CreateAppToRefTheLib)

- [Использование функциональности из статической библиотеки в приложении](#UseLibInApp)

- [Запуск приложения](#RunApp)

## <a name="prerequisites"></a>Предварительные требования

Для работы необходимо владеть основами языка C++.

##  <a name="CreateLibProject"></a> Создание проекта статической библиотеки

### <a name="to-create-a-static-library-project"></a>Создание проекта статической библиотеки

1. В строке меню выберите **Файл** > **Создать** > **Проект**.

1. В левой части **новый проект** диалоговое окно последовательно раскройте элементы **установленные** > **Visual C++**, а затем выберите **Windows Desktop**. В центральной области выберите **мастер создания классических приложений Windows**.

   > [!NOTE]
   > Для версий старше 2017, Visual Studio в **новый проект** диалогового окна разверните узел **установленные** > **шаблоны**  >  **Visual C++**, а затем выберите **Win32**. В центральной области выберите **Консольное приложение Win32**.

1. Укажите имя для проекта, например *MathFuncsLib*, в поле **Имя** . Укажите имя для решения, например *StaticLibrary*, в поле **Имя решения** . Нажмите кнопку **ОК** .

    - Для Visual Studio 2017

        1. В разделе **тип приложения**выберите **статическая библиотека (.lib)**.

        1. В разделе **Дополнительные параметры**, снимите флажок **предкомпилированный заголовок** "флажок".

        1. Выберите **ОК** для создания проекта.

    - Для версий старше 2017, Visual Studio

        1. Нажмите кнопку **Далее**.

        1. В разделе **тип приложения**выберите **статическую библиотеку**. Затем снимите флажок **предкомпилированный заголовок** можно выбрать **Готово**.

##  <a name="AddClassToLib"></a> Добавление класса в статическую библиотеку

### <a name="to-add-a-class-to-the-static-library"></a>Добавление класса в статическую библиотеку

1. Чтобы создать файл заголовка для нового класса, откройте контекстное меню для **MathFuncsLib** проекта в среде **обозревателе решений**, а затем выберите **добавить**  >   **Новый элемент**. В диалоговом окне **Добавление нового элемента** в левой области в разделе **Visual C++** выберите **Код**. В центральной области выберите **Заголовочный файл (.h)**. Укажите имя для файла заголовка, например *MathFuncsLib.h*, и нажмите кнопку **Добавить** . Отобразится пустой файл заголовка.

1. Добавьте класс с именем `MyMathFuncs` общие арифметические операции, такие как сложение, вычитание, умножение и деление. Код должен выглядеть как:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]

1. Для создания исходного файла для нового класса, откройте контекстное меню для **MathFuncsLib** в проекте **обозревателе решений**, а затем выберите **добавить**  >   **Новый элемент**. В диалоговом окне **Добавление нового элемента** в левой области в разделе **Visual C++** выберите **Код**. В центральной области выберите **Файл C++ (.cpp)**. Укажите имя исходного файла, например *MathFuncsLib.cpp*, и нажмите кнопку **Добавить** . Отобразится пустой исходный файл.

1. Используйте этот исходный файл для реализации функций **MyMathFuncs**. Код должен выглядеть как:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]

1. Скомпилируйте статическую библиотеку, выбрав **построения** > **построить решение** в строке меню. Компиляция создает статическую библиотеку, который может использоваться другими программами.

   > [!NOTE]
   > При выполнении сборки из командной строки Visual Studio программа собирается в два этапа. Сначала запустите `cl /c /EHsc MathFuncsLib.cpp` скомпилировать код и создать файл объекта с именем `MathFuncsLib.obj`. (Команда `cl` вызывает компилятор Cl.exe, а параметр `/c` дает указание компилировать без компоновки. Дополнительные сведения см. в разделе [/c (компиляция без связывания)](../build/reference/c-compile-without-linking.md).) Во-вторых, запустите `lib MathFuncsLib.obj` чтобы связать код и создать статическую библиотеку `MathFuncsLib.lib`. (Команда `lib` вызывает диспетчер библиотек, Lib.exe. Дополнительные сведения см. в разделе [LIB Reference](../build/reference/lib-reference.md).)

##  <a name="CreateAppToRefTheLib"></a> Создание консольного приложения C++, ссылающегося на статическую библиотеку

### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>Создание консольного приложения C++, ссылающегося на статическую библиотеку

1. В строке меню выберите **Файл** > **Создать** > **Проект**.

1. В левой части **новый проект** диалоговое окно последовательно раскройте элементы **установленные** > **Visual C++**, а затем выберите **Windows Desktop**. В центральной области выберите **мастер создания классических приложений Windows**.

   > [!NOTE]
   > Для версий старше 2017, Visual Studio в **новый проект** диалогового окна разверните узел **установленные** > **шаблоны**  >  **Visual C++**, а затем выберите **Win32**. В центральной области выберите **Консольное приложение Win32**.

1. Укажите имя проекта, например *MyExecRefsLib*, в поле **Имя** . В раскрывающемся списке рядом с полем **Решение**выберите **Добавить в решение**. Команда добавляет новый проект в решение, содержащее статическую библиотеку. Нажмите кнопку **ОК** .

    - Для Visual Studio 2017

        1. В разделе **тип приложения**выберите **консольное приложение (.exe)**.

        1. В разделе **Дополнительные параметры**, снимите флажок **предкомпилированный заголовок** "флажок".

        1. Выберите **ОК** для создания проекта.

    - Для версий старше 2017, Visual Studio

        1. Нажмите кнопку **Далее**.

        1. Убедитесь, что **консольное приложение** выбран. Затем проверьте **пустой проект** можно выбрать **Готово**.

##  <a name="UseLibInApp"></a> Использование функциональности из статической библиотеки в приложении

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Использование функциональности из статической библиотеки в приложении

1. После создания консольного приложения будет создана пустая программа. Имя исходного файла будет совпадать с ранее выбранным именем. В этом примере он называется `MyExecRefsLib.cpp`.

1. Для использования математических процедур из статической библиотеки необходимо сослаться на эту библиотеку. Откройте контекстное меню для **MyExecRefsLib** в проекте **обозревателе решений**и нажмите кнопку **добавить** > **ссылку**.

1. В диалоговом окне **Добавление ссылки** перечислены библиотеки, на которые можно создать ссылку. **Проекты** вкладке перечислены все проекты текущего решения и все библиотеки, они ссылаются. На вкладке **Проекты** установите флажок **MathFuncsLib** , а затем нажмите кнопку **ОК** .

1. Ссылка `MathFuncsLib.h` файла заголовка, необходимо изменить путь к каталогам включения. Для этого в диалоговом окне **Окна свойств** библиотеки **MyExecRefsLib**последовательно разверните узлы **Свойства конфигурации** , **C/C++** , а затем выберите **Общие**. Рядом с полем **Дополнительные каталоги включаемых файлов**, укажите путь к **MathFuncsLib** или найдите его каталог.

   Чтобы найти путь к каталогу, откройте раскрывающийся список значений свойства и выберите **Изменить**. В **Дополнительные каталоги включаемых файлов** диалоговое окно, в текстовом поле выберите пустую строку и нажмите кнопку с многоточием (**...** ) в конце строки. В диалоговом окне **Выбор каталога** выберите каталог **MathFuncsLib** и нажмите кнопку **Выбор папки** , чтобы сохранить выбранное значение и закрыть диалоговое окно. В диалоговом окне **Дополнительные каталоги включаемых файлов** , нажмите кнопку **ОК** , затем в диалоговом окне **Окна свойств** нажмите кнопку **ОК** для сохранения изменений в проект.

1. Теперь вы можете использовать `MyMathFuncs` класс в этом приложении, включая `#include "MathFuncsLib.h"` заголовка в коде. Замените содержимое файла `MyExecRefsLib.cpp` следующим кодом:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]

1. Соберите исполняемый файл, выбрав **построения** > **построить решение** в строке меню.

##  <a name="RunApp"></a> Запуск приложения

### <a name="to-run-the-app"></a>Запуск приложения

1. Убедитесь, что проект **MyExecRefsLib** выбран в качестве проекта по умолчанию, открыв контекстное меню для **MyExecRefsLib** в **обозревателе решений**и выбрав пункт **Назначить запускаемым проектом**.

1. Чтобы запустить проект, в строке меню выберите **Отладка** > **Запуск без отладки**. Выходные данные должны иметь:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>См. также

[Пошаговое руководство: Создание и использование библиотеки DLL (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Классические приложения (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>