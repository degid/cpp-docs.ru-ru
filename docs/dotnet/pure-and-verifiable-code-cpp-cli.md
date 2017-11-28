---
title: "Чистый и проверяемый код (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ec68a6179cd74020638aa895028942bc76e21f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>Чистый и проверяемый код (C++/CLI)
Для программирования .NET, Visual C++ поддерживает создание трех различных типов компонентов и приложений: смешанных, чистых и проверяемых. Все три доступны через [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о проверяемых сборках см. в разделе:  
  
-   [Сравнение смешанных, чистых и проверяемых компонентов (C++/CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Как: переход на/CLR: pure (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Практическое руководство. Создание проверяемых проектов на языке C++ (C++/CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Как: перенос в/CLR: safe (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [Использование проверяемых сборок вместе с SQL Server (C++/CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [Рекомендации по безопасности](../security/security-best-practices-for-cpp.md)  
  
-   [Преобразование проектов из смешанного режима в чистый промежуточный язык](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>Смешанный (/ clr)  
 Смешанные сборки (скомпилированные с **/CLR**), содержат как неуправляемые и управляемые части, что позволяет им использовать функции .NET, но по-прежнему содержать неуправляемый код. Это позволяет приложениям и компонентам обновляться для использования функций .NET без необходимости переписать всего проекта. С помощью Visual C++ смешивания управляемого и неуправляемого кода таким образом, называется взаимодействия C++. Дополнительные сведения см. в разделе [сборки смешанный (машинный и управляемый код)](../dotnet/mixed-native-and-managed-assemblies.md) и [машинного кода и .NET-взаимодействии](../dotnet/native-and-dotnet-interoperability.md).  
  
## <a name="pure-clrpure"></a>Чистые (/ clr: pure)  
 Чистые сборки (скомпилированные с **/CLR: pure**) может содержать оба данных машинного и управляемого типа, но только управляемых функций. Подобно смешанных сборок, чистые сборки обеспечивают взаимодействие со собственные библиотеки DLL с помощью P/Invoke (см. [с помощью явного вызова PInvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)), но не доступны возможности взаимодействия C++. Более того, чистые сборки не могут экспортировать функции, которые вызываются из функций машинного кода, поскольку точки входа в чистых сборках используют [__clrcall](../cpp/clrcall.md) соглашение о вызовах.  
  
### <a name="advantages-of-clrpure"></a>Преимущества/CLR: pure  
  
-   Более высокая производительность: Поскольку чистые сборки содержат только MSIL, нет собственного функций и таким образом, не управляемых и неуправляемых переходов необходимы. (Вызовы функций с помощью P/Invoke являются исключением из этого правила.)  
  
-   Информированность о домене приложения: Управляемые функции и типы данных CLR существуют внутри `Application Domains`, что влияет на их видимость и доступность. Чистые сборки осведомлены о домене (__declspec ([appdomain](../cpp/appdomain.md)) подразумевается для каждого типа), доступ к типам и функциональные возможности из других компонентов .NET проще и безопаснее. В результате чистые сборки проще взаимодействуют с другими компонентами .NET, чем смешанные сборки.  
  
-   Загрузка не диск: чистые сборки могут загружаться в памяти или даже передаваться потоком. Это важно при использовании сборок .NET как хранимых процедур. Это отличается от смешанных сборок, которые из-за зависимостей в ОС Windows для выполнения загрузки механизмы, должна существовать на диске.  
  
-   Отражение: Это не позволяет отражать смешанные исполняемые файлы, в то время как чистые сборки имеется полная поддержка отражения. Дополнительные сведения см. в разделе [отражения (C + +/ CLI)](../dotnet/reflection-cpp-cli.md).  
  
-   Управляемость ведущего приложения: Поскольку чистые сборки содержат только MSIL, их поведение более предсказуемое и более гибкое, чем смешанные сборки при использовании в приложениях, на которых размещены среды CLR и изменить его поведение по умолчанию.  
  
### <a name="limitations-of-clrpure"></a>Ограничения/CLR: pure  
 В этом разделе описываются функции, не поддерживаемых **/CLR: pure**.  
  
-   Чистые сборки не может быть вызван неуправляемые функции. Поэтому чистые сборки не может реализовывать интерфейсы COM или предоставлять собственные обратные вызовы. Чистые сборки не могут экспортировать функции через __declspec(dllexport) или. DEF-файлы. Кроме того, функций, объявленных с \__clrcall соглашению нельзя импортировать с помощью \__declspec(dllimport). Функции в модуль в машинном коде, которые могут быть вызваны из чистой сборки, но чистые сборки не может предоставлять собственный вызываемой функции, поэтому функции предоставления в чистые сборки должны осуществляться через управляемых функций в смешанной сборки. В разделе [как: переход на/CLR: pure (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) для получения дополнительной информации.  
  
-   Библиотеки ATL и MFC не поддерживаются при компиляции чистом режиме в Visual C++.  
  
-   Чистые NETMODULE не могут использоваться в качестве входных данных компоновщика Visual C++. Тем не менее чистые OBJ-файлы принимаются компоновщиком и содержат надмножество сведений, содержащихся в файлах NETMODULE. В разделе [.netmodule качестве входных файлов компоновщика](../build/reference/netmodule-files-as-linker-input.md) для получения дополнительной информации.  
  
-   Поддержка компилятора COM (#import) не поддерживается, как это стало бы причиной неуправляемые инструкции в чистую сборку.  
  
-   Число с плавающей запятой, что параметры выравнивания и обработки исключений не являются изменяемыми для чистые сборки. В результате __declspec(align) не может использоваться. Это делает некоторые файлы заголовков, такие как fpieee.h, несовместимые с параметром/clr: pure.  
  
-   Функция GetLastError PSDK может предоставить неопределенное поведение при компиляции с параметром **/CLR: pure**.  
  
## <a name="verifiable-clrsafe"></a>Проверяемый (/ CLR: safe)  
 **/CLR: safe** генерирует проверяемые сборки, как на языке Visual Basic и C#, удовлетворяющих требованиям, позволяющим общеязыковой среды выполнения (CLR), чтобы гарантировать, что код не нарушает текущего параметры безопасности. Например если компонент запрещено параметрами безопасности из записи на диск, среда CLR можно определить, если проверяемых компонент критериям перед выполнением какого-либо кода. Для проверяемых сборок не поддерживается CRT. (Поддержка CRT доступна для чистых сборок посредством чистого MSIL-версии библиотеки времени выполнения C).  
  
 Проверяемые сборки предоставляют следующие преимущества чистых и смешанных сборок:  
  
-   Повышение уровня безопасности.  
  
-   В некоторых ситуациях необходимо его (например, компоненты SQL).  
  
-   Будущие версии Windows все чаще будут требовать компонентов и приложений в проверяемые.  
  
 Один недостаток заключается в возможности взаимодействия C++ на недоступны. Проверяемые сборки не может содержать неуправляемые функции или собственные типы данных, даже если они указаны в управляемом коде.  
  
 Несмотря на использование слова «safe» компиляция приложений с **/CLR: safe** не означает без ошибок, что это означает, что среда CLR может проверить параметры безопасности во время выполнения.  
  
 Независимо от типа сборки вызовы, выполненные из управляемых сборок в собственные библиотеки DLL с помощью вызова P/Invoke будет скомпилирован, но может завершиться ошибкой во время выполнения в зависимости от параметров безопасности.  
  
> [!NOTE]
>  Имеется один сценарий кодирования, будет пропущен компилятором, но приведет сборку непроверяемый: вызов виртуальной функции через экземпляр объекта с помощью оператора разрешения области действия.  Например, `MyObj -> A::VirtualFunction();`.  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)