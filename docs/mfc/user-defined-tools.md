---
title: Инструменты, определяемые пользователем
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 785e37c63653dde91176bedd0321fc58ac122c7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180840"
---
# <a name="user-defined-tools"></a>Инструменты, определяемые пользователем

MFC поддерживает определенные пользователем инструменты. Определяемый пользователем инструмент — это специальные команда, которая выполняет программу внешних, предоставленных пользователем. Процесс настройки можно использовать для управления определенные пользователем инструменты. Тем не менее, нельзя использовать этот процесс, если объекта приложения не является производным от [класс CWinAppEx](../mfc/reference/cwinappex-class.md). Дополнительные сведения о настройке см. в разделе [Настройка для MFC](../mfc/customization-for-mfc.md).

Если вы включили поддержку определенные пользователем инструменты, диалоговое окно настройки автоматически включает в себя **средства** вкладки. На следующем рисунке показано **средства** страницы.

![Вкладки средства в диалоговом окне настройки](../mfc/media/custdialogboxtoolstab.png "вкладки \"Сервис\" в диалоговом окне настройки") <br/>
Настройка вкладки диалогового окна "Сервис"

## <a name="enabling-user-defined-tools-support"></a>Включение пользовательских средств поддержки

Чтобы включить определенные пользователем инструменты в приложении, вызовите [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Тем не менее необходимо сначала определить несколько констант в файлы ресурсов приложения для использования в качестве параметров для этого вызова.

В редакторе ресурсов создайте фиктивный команда, которая использует идентификатор соответствующую команду. В следующем примере мы используем `ID_TOOLS_ENTRY` как идентификатор команды. Этот идентификатор команды отмечает расположение в одном или нескольких меню, где платформа будет вставлять определенные пользователем инструменты.

Необходимо зарезервировать несколько последовательных идентификаторов в таблице строк для представления, определенные пользователем инструменты. Число строк, которые резервировались равно максимальное число пользователей средств, которые пользователи могут определять. В следующем примере, эти параметры назывались `ID_USER_TOOL1` через `ID_USER_TOOL10`.

Можно предложить пользователям, чтобы помочь им выбрать каталоги и аргументы для внешних программ, которые будут вызываться в качестве средства. Чтобы сделать это, создайте два всплывающее меню в редакторе ресурсов. В следующем примере эти параметры назывались `IDR_MENU_ARGS` и `IDR_MENU_DIRS`. Для каждой команды в этих меню определите строку в таблице строк вашего приложения. Идентификатор ресурса строки должен быть равным идентификатор команды.

Можно также создать класс, производный от [класс CUserTool](../mfc/reference/cusertool-class.md) заменить реализацию по умолчанию. Чтобы сделать это, передать данные среды выполнения для производного класса в качестве четвертого параметра в CWinAppEx::EnableUserTools вместо RUNTIME_CLASS ([класс CUserTool](../mfc/reference/cusertool-class.md)).

После определения соответствующих константы, вызовите [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств.

Следующий вызов метода показано, как использовать эти константы:

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

Вкладка "Сервис" в этом примере будет включено в **настройки** диалоговое окно. Платформа заменит любую команду, соответствующий Идентификатору команды `ID_TOOLS_ENTRY` ни в одном меню с набором средств в настоящее время определены пользователя каждый раз, когда пользователь открывает соответствующее меню. Идентификаторы команд `ID_USER_TOOL1` через `ID_USER_TOOL10` зарезервированы для использования для пользовательских инструментов. Класс [класс CUserTool](../mfc/reference/cusertool-class.md) обрабатывает вызовы пользовательских средств. На вкладке средство **настройки** диалоговое окно предоставляет кнопки для доступа к меню справа от поля ввода аргумента и directory **IDR_MENU_ARGS** и **IDR_MENU_DIRS**. Когда пользователь выбирает команду из следующих меню, платформа добавляет соответствующее текстовое поле строки, которая содержит идентификатор ресурса, равным идентификатор команды.

### <a name="including-predefined-tools"></a>Включая стандартных инструментов

Если вы хотите заранее определить некоторые средства при запуске приложения, необходимо переопределить [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) метод главного окна приложения. В этом методе необходимо выполнить следующие действия.

##### <a name="to-add-new-tools-in-loadframe"></a>Чтобы добавить новые средства в LoadFrame

1. Получить указатель на [класс CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md) путем вызова метода [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).

1. Каждое средство, которое вы хотите создать, вызовите [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Этот метод возвращает указатель на [класс CUserTool](../mfc/reference/cusertool-class.md) и добавляет в коллекцию средств средство только что созданного пользователя. Если введенные данные среды выполнения для производного класса от [класс CUserTool](../mfc/reference/cusertool-class.md) качестве четвертого параметра [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) будет создать экземпляр и вместо этого возвращать экземпляр этого класса.

1. Для каждого средства, установить его текстовую метку, задав `CUserTool::m_strLabel` и установить ее команды путем вызова `CUserTool::SetCommand`. Реализация по умолчанию [класс CUserTool](../mfc/reference/cusertool-class.md) автоматически извлекает доступных значков из программы, указанной в вызове `SetCommand`.

## <a name="see-also"></a>См. также

[Настройка для MFC](../mfc/customization-for-mfc.md)<br/>
[Класс CUserTool](../mfc/reference/cusertool-class.md)<br/>
[Класс CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md)<br/>
[Класс CWinAppEx](../mfc/reference/cwinappex-class.md)
