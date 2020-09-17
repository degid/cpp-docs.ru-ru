---
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
- cstdbool
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: ed780e059a5e456731fd6a4f651639e282016f5e
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341099"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

Включает заголовок \<стандартной библиотеки C stdbool.h > и добавляет связанные имена `std` в пространство имен.

> [!NOTE]
> Так как заголовок C++ stdbool.h>определяетмакросы,которыеявляютсяключевымисловамив,втомчисленеоказываетникакого\<влияния. В C++рекомендуется использовать заголовок stdbool.h\<>. Заголовок \<кстдбул > является устаревшим в c++ 17 и удаляется в черновом стандарте c++ 20.

## <a name="requirements"></a>Требования

**Заголовок:** \<кстдбул >

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C `std` , объявляются в пространстве имен.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[C++Общие сведения о стандартной библиотеке](cpp-standard-library-overview.md)\
[Безопасность потоков в C++ стандартной библиотеке](thread-safety-in-the-cpp-standard-library.md)
