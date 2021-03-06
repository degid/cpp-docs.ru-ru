---
title: Распространение файлов Visual C++
description: Visual Studio включает распространяемые библиотеки и компоненты, которые можно развернуть с помощью приложения.
ms.date: 07/16/2020
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 7a639f7ad7deb76cade47b0162012dcb70cb0d69
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446757"
---
# <a name="redistributing-visual-c-files"></a>Распространение файлов Visual C++

> [!NOTE]
> Вы находитесь здесь, потому что ищете загрузку одного из файлов среды выполнения Visual C++? Перейдите на [веб-сайт Майкрософт](https://www.microsoft.com/) и введите **Visual C++ распространяемый пакет** в поле поиска. Скачайте и установите распространяемый пакет для архитектуры своего компьютера (например, x64, если у вас 64-разрядная версия Windows) и нужную версию Visual C++ (например, 2015).

## <a name="redistributable-files-and-licensing"></a>Распространяемые файлы и лицензирование

При развертывании приложения необходимо также развернуть файлы, поддерживающие это приложение. Если какие – либо из этих файлов предоставляются корпорацией Майкрософт, проверьте, разрешено ли их распространение. Ссылка на условия лицензии Visual Studio находится в интегрированной среде разработки. Используйте ссылку условия лицензии в диалоговом окне о Microsoft Visual Studio. Или загрузите соответствующие лицензионные соглашения и лицензии из [каталога лицензий](https://visualstudio.microsoft.com/license-terms/)Visual Studio.

::: moniker range="vs-2019"

Чтобы просмотреть список Redist, указанный в разделе "распространяемый код" условий лицензионного соглашения на использование программного обеспечения Microsoft Visual Studio 2019, ознакомьтесь с разделом [файлы распространяемого кода для Microsoft Visual Studio 2019](/visualstudio/releases/2019/redistribution#-distributable-code-files-for-visual-studio-2019)

::: moniker-end

::: moniker range="vs-2017"

Чтобы просмотреть список Redist, указанный в разделе "распространяемый код" условий лицензионного соглашения на использование программного обеспечения Microsoft Visual Studio 2017, ознакомьтесь с разделом [файлы распространяемого кода для Microsoft Visual Studio 2017](/visualstudio/productinfo/2017-redistribution-vs#-distributable-code-files-for-visual-studio-2017).

::: moniker-end

::: moniker range="vs-2015"

Чтобы просмотреть список Redist, указанный в разделе "распространяемый код" условий лицензионного соглашения на использование программного обеспечения Microsoft Visual Studio 2015, ознакомьтесь с разделом [файлы распространяемого кода для Microsoft Visual Studio 2015](/visualstudio/productinfo/2015-redistribution-vs#-distributable-code-files-for-visual-studio-2015).

::: moniker-end

Дополнительные сведения о распространяемых файлах см. [в разделе Определение библиотек DLL для](determining-which-dlls-to-redistribute.md) повторного распространения и [примеров развертывания](deployment-examples.md).

## <a name="locate-the-redistributable-files"></a>Размещение распространяемых файлов

Для развертывания распространяемых файлов можно использовать распространяемые пакеты, установленные Visual Studio. В версиях Visual Studio, начиная с 2017, эти файлы называются *`vc_redist.arm64.exe`* , *`vc_redist.x64.exe`* и *`vc_redist.x86.exe`* . В Visual Studio 2015, Visual Studio 2017 и Visual Studio 2019 они также доступны под именами *`vcredist_x86.exe`* , *`vcredist_x64.exe`* и *`vcredist_arm.exe`* (только для 2015).

Самый простой способ размещения распространяемых файлов — использовать переменные среды, заданные в командной строке разработчика. В последней версии Visual Studio 2019 вы найдете распространяемые файлы в *`%VCINSTALLDIR%Redist\MSVC\v142`* папке. В Visual Studio 2017 и Visual Studio 2019 они также находятся в *`%VCToolsRedistDir%`* . В Visual Studio 2015 эти файлы можно найти в *`%VCINSTALLDIR%redist\<locale>`* , где *`<locale>`* — это языковой стандарт распространяемых пакетов.

Другой вариант развертывания — использовать распространяемые модули слияния ( *`.msm`* файлы). В Visual Studio 2019 эти файлы являются частью необязательного устанавливаемого компонента с именем " **распространяемый компонент C++ 2019 МСМС** " в Visual Studio Installer. Модули слияния устанавливаются по умолчанию в рамках установки C++ в Visual Studio 2017 и Visual Studio 2015. При установке в последней версии Visual Studio 2019 можно найти распространяемые модули слияния в *`%VCINSTALLDIR%Redist\MSVC\v142\MergeModules`* . В Visual Studio 2019 и Visual Studio 2017 они также находятся в *`%VCToolsRedistDir%MergeModules`* . В Visual Studio 2015 они находятся в *`Program Files [(x86)]\Common Files\Merge Modules`* .

## <a name="install-the-redistributable-packages"></a>Установка распространяемых пакетов

Распространяемые пакеты Visual C++ позволяют устанавливать и регистрировать все библиотеки Visual C++. Если вы используете его, запустите его в качестве необходимого компонента в целевой системе, прежде чем устанавливать приложение. Рекомендуется использовать эти пакеты для развертываний, поскольку они включают функцию автоматического обновления библиотек Visual C++. Пример использования этих пакетов см. в разделе [Пошаговое руководство. Развертывание приложения Visual C++ с помощью распространяемого пакета Visual C++](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

Каждый распространяемый пакет Visual C++ проверяет наличие более новой версии на компьютере. Если обнаружена более поздняя версия, пакет не будет установлен. Начиная с Visual Studio 2015, в распространяемых пакетах отображается сообщение о сбое установки. Если пакет выполняется с помощью **`/quiet`** флага, сообщение об ошибке не отображается. В любом случае ошибка записывается установщиком Майкрософт, а результат ошибки возвращается вызывающему объекту. Начиная с пакетов Visual Studio 2015 вы можете избежать этой ошибки, проверив реестр, чтобы узнать, установлена ли более новая версия. Текущий номер установленной версии хранится в `HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\Microsoft\VisualStudio\14.0\VC\Runtimes\{x86|x64|ARM}` ключе. Номер версии — 14,0 для Visual Studio 2015, Visual Studio 2017 и Visual Studio 2019, так как последний распространяемый пакет совместим с версией 2015. Ключ — `ARM` , `x86` или, в `x64` зависимости от установленных версий Vcredist для платформы. ( `Wow6432Node` Если вы используете Regedit для просмотра версии установленного пакета x86 на платформе x64, необходимо проверить подраздел.) Номер версии хранится в REG_SZ строковом значении **`Version`** , а также в наборе **`Major`** значений, **`Minor`** , **`Bld`** и **`Rbld`** `REG_DWORD` . Чтобы избежать ошибки во время установки, нужно пропустить установку распространяемого пакета, если только что установленная версия является более новой.

## <a name="install-the-redistributable-merge-modules"></a>Установка распространяемых модулей слияния

Распространяемые модули слияния должны быть добавлены в пакет установщик Windows (или аналогичный пакет установки), который используется для развертывания приложения. Дополнительные сведения см. в разделе [Распространение с использованием модулей слияния](redistributing-components-by-using-merge-modules.md). Пример см. в разделе [Пошаговое руководство. развертывание Visual C++ приложения с помощью проекта установки](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

## <a name="install-individual-redistributable-files"></a>Установка отдельных распространяемых файлов

Также можно напрямую установить распространяемые DLL-файлы в *локальную папку приложения*. Это папка, содержащая файл исполняемого приложения. В целях обслуживания мы не рекомендуем использовать это расположение установки.

## <a name="potential-run-time-errors"></a>Потенциальные ошибки времени выполнения

Если Windows не удается найти одну из распространяемых библиотек DLL, необходимых для приложения, может отобразиться сообщение следующего вида: "не удалось запустить приложение, так как *Библиотека*DLL не найдена. Переустановка приложения может устранить эту проблему. "

Чтобы устранить эту ошибку, убедитесь, что установщик приложения построен правильно. Убедитесь, что распространяемые библиотеки правильно развернуты в целевой системе. Дополнительные сведения см. в разделе [Основные сведения о зависимостях приложения Visual C++](understanding-the-dependencies-of-a-visual-cpp-application.md).

## <a name="related-articles"></a>Похожие статьи

[Распространение с помощью модулей слияния](redistributing-components-by-using-merge-modules.md)\
Описывает использование Visual C++ распространяемых модулей слияния для установки библиотек среды выполнения Visual C++ в качестве общих библиотек DLL в *`%windir%\system32\`* папке.

[Распространение Visual C++ элементов управления ActiveX](redistributing-visual-cpp-activex-controls.md)\
Описание процедуры повторного распространения приложения, которое использует элементы управления ActiveX.

[Распространение библиотеки MFC](redistributing-the-mfc-library.md)\
Описание процедуры повторного распространения приложения, которое использует MFC.

[Распространение приложения ATL](redistributing-an-atl-application.md)\
Описание способа распространения приложения, которое использует ATL. Начиная с Visual Studio 2012, распространяемая библиотека для ATL не требуется.

[Примеры развертывания](deployment-examples.md)\
Ссылки на примеры, демонстрирующие развертывание приложений Visual C++.

[Развертывание классических приложений](deploying-native-desktop-applications-visual-cpp.md)\
Представлены технологии развертывания Visual C++ и связанные понятия.
