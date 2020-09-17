---
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: 5b5383b1eca4fda72f5f9e3a78637373acbcf7ab
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341138"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

Включает заголовок C++ [ \<стандартной библиотеки Complex >](complex.md).

> [!NOTE]
> Заголовок с сложного \<h-> стандартной библиотеки C не \<включается в ccomplex >, поскольку он фактически заменяется C++ перегрузками \<в сложных > \<и cmath >. Это делает \<заголовок ccomplex > избыточным. Заголовок Complex.h > является устаревшим в C++ \< Заголовок \<ccomplex > является устаревшим в c++ 17 и удаляется в черновом стандарте c++ 20.

## <a name="requirements"></a>Требования

**Заголовок:** \<ccomplex >

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Имя `clog`, которое объявлено в \<сложном.h > `std` , не определено в пространстве имен из-за возможных конфликтов `clog` с, объявленных в [ \<iostream >](iostream.md).

## <a name="see-also"></a>См. также

[\<сложные >](complex.md)\
[\<cmath>](cmath.md)\
[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[C++Общие сведения о стандартной библиотеке](cpp-standard-library-overview.md)\
[Безопасность потоков в C++ стандартной библиотеке](thread-safety-in-the-cpp-standard-library.md)
