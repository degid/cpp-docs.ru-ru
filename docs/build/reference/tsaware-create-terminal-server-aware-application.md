---
title: /TSAWARE (создание приложения, поддерживающего сервер терминалов)
ms.date: 11/04/2016
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
ms.openlocfilehash: c2ec12b0b5fbe241d75acc4bb0d87837371a293e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845735"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (создание приложения, поддерживающего сервер терминалов)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Примечания

Параметр/TSAWARE устанавливает флаг в поле IMAGE_OPTIONAL_HEADER DllCharacteristics в необязательном заголовке образа программы. Если этот флаг установлен, сервер терминалов не будет вносить определенные изменения в приложение.

Если приложение не поддерживает сервер терминалов (также известное как устаревшее приложение), сервер терминалов вносит определенные изменения в устаревшее приложение, чтобы оно работало правильно в многопользовательской среде. Например, сервер терминалов создаст виртуальную папку Windows, так что каждый пользователь получает папку Windows, а не каталог Windows системы. Это дает пользователям доступ к своим файлам INI. Кроме того, сервер терминалов вносит некоторые изменения в реестр для устаревшего приложения. Эти изменения замедляют загрузку устаревшего приложения на сервере терминалов.

Если приложение поддерживает сервер терминалов, оно не должно полагаться на INI-файлы и записывать в реестр **HKEY_CURRENT_USER** во время установки.

Если вы используете параметр/TSAWARE и приложение по-прежнему использует файлы INI, эти файлы будут совместно использоваться всеми пользователями системы. Если это допустимо, вы по-прежнему можете связать приложение с параметром/TSAWARE; в противном случае необходимо использовать параметр/TSAWARE: NO.

Параметр/TSAWARE включен по умолчанию для Windows и консольных приложений. Сведения см. в разделе [/SUBSYSTEM](subsystem-specify-subsystem.md) и [/Version](version-version-information.md) .

Параметр/TSAWARE недопустим для драйверов и библиотек DLL.

Если приложение было связано с параметром/TSAWARE, [то в](headers.md) подмассиве DUMPBIN будет отображаться информация об этом результате.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Перейдите на страницу свойств **системы** .

1. Измените свойство **сервера терминалов** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[Хранение сведений, относящихся к пользователю](/windows/win32/TermServ/storing-user-specific-information)<br/>
[Устаревшие приложения в среде служб терминалов](/previous-versions/aa382957(v=vs.85))
