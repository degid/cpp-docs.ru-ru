---
title: Обновление WINVER и _WIN32_WINNT
description: Когда и как обновлять макросы WINVER и _WIN32_WINNT в обновленных проектах Visual Studio C++.
ms.date: 06/19/2020
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a0faed612517bf26cd89473e1aef248fb9e7b33e
ms.sourcegitcommit: 493fd8747f832e1facb9a76c437a25a5c9fb55f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141058"
---
# <a name="update-winver-and-_win32_winnt"></a>Обновление WINVER и _WIN32_WINNT

При использовании Windows SDK можно указать версии Windows, на которых может выполняться ваш код. Макросы препроцессора **WINVER** и **_WIN32_WINNT** указывают минимальную версию операционной системы, поддерживаемую кодом. Visual Studio и компилятор Microsoft C++ поддерживают для Windows 7 с пакетом обновления 1 (SP1) и более поздних версий. К старым наборам инструментов относятся поддержка Windows XP SP2, Windows Server 2003 с пакетом обновления 1 (SP1), Vista и Windows Server 2008. Windows 95, Windows 98, Windows ME, Windows NT и Windows 2000 не поддерживаются.

При обновлении более старого проекта может потребоваться обновить макросы **WINVER** или **_WIN32_WINNT** . Если им назначены значения для неподдерживаемой версии Windows, могут возникнуть ошибки компиляции, связанные с этими макросами.

## <a name="remarks"></a>Комментарии

Чтобы изменить макросы, в файле заголовка (например, в *targetver.h*, который включен в некоторые шаблоны проектов, предназначенные для Windows), добавьте следующие строки.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

Макросы в примере задаются для каждой версии операционной системы Windows 10. Возможные значения перечислены в файле заголовка Windows *sdkddkver.h*, который определяет макросы для каждой основной версии Windows. Чтобы создать приложение для поддержки предыдущей платформы Windows, включите *WinSDKVer.h*. Затем установите для макросов **WINVER** и **_WIN32_WINNT** самую старую поддерживаемую платформу перед включением *sdkddkver.h*. Ниже приведены строки из версии *sdkddkver.h* пакета SDK для Windows 10, которые записывают значения для каждой основной версии Windows:

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

Для более детального подхода к управлении версиями можно использовать константы версии НТДДИ в *sdkddkver.h*. Ниже приведены некоторые макросы, определенные в *sdkddkver.h* в пакете SDK для Windows 10 версии 10.0.18362.0.

```C
//
// NTDDI version constants
//
#define NTDDI_WIN7                          0x06010000
#define NTDDI_WIN8                          0x06020000
#define NTDDI_WINBLUE                       0x06030000
#define NTDDI_WINTHRESHOLD                  0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10                         0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10_TH2                     0x0A000001  /* ABRACADABRA_WIN10_TH2 */
#define NTDDI_WIN10_RS1                     0x0A000002  /* ABRACADABRA_WIN10_RS1 */
#define NTDDI_WIN10_RS2                     0x0A000003  /* ABRACADABRA_WIN10_RS2 */
#define NTDDI_WIN10_RS3                     0x0A000004  /* ABRACADABRA_WIN10_RS3 */
#define NTDDI_WIN10_RS4                     0x0A000005  /* ABRACADABRA_WIN10_RS4 */
#define NTDDI_WIN10_RS5                     0x0A000006  /* ABRACADABRA_WIN10_RS5 */
#define NTDDI_WIN10_19H1                    0x0A000007  /* ABRACADABRA_WIN10_19H1*/

#define WDK_NTDDI_VERSION                   NTDDI_WIN10_19H1 /* ABRACADABRA_WIN10_19H1 */

//
// masks for version macros
//
#define OSVERSION_MASK      0xFFFF0000
#define SPVERSION_MASK      0x0000FF00
#define SUBVERSION_MASK     0x000000FF

//
// macros to extract various version fields from the NTDDI version
//
#define OSVER(Version)  ((Version) & OSVERSION_MASK)
#define SPVER(Version)  (((Version) & SPVERSION_MASK) >> 8)
#define SUBVER(Version) (((Version) & SUBVERSION_MASK) )
```

В коде можно использовать макросы **освер**, **спвер**и **субвер** для управления условной компиляцией на различных уровнях поддержки API.

Возможно, вы не видите все эти версии Windows, перечисленные в *sdkddkver.h* , которые вы ищете. Это означает, что вы, вероятно, используете более старую версию Windows SDK. По умолчанию в новых проектах Windows в Visual Studio используется пакет SDK для Windows 10.

> [!NOTE]
> Значения могут не сработать, если включить в приложение внутренние заголовки MFC.

Также можно определить этот макрос с помощью параметра компилятора `/D`. Для получения дополнительной информации см. [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).

Дополнительные сведения о значении этих макросов см. в разделе [Использование заголовков Windows](/windows/win32/WinProg/using-the-windows-headers).

## <a name="see-also"></a>См. также

[Журнал изменений Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
