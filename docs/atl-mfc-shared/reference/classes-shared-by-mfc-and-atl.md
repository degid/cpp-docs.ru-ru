---
title: Общие классы MFC и ATL
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: e3e4b35721e84e289aed586c4d010a6986dcc61c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491459"
---
# <a name="classes-shared-by-mfc-and-atl"></a>Общие классы MFC и ATL

В следующей таблице перечислены классы, общие для MFC и ATL.

|Класс|Описание|Заголовочный файл|
|-----------|-----------------|-----------------|
|[кфилетиме](../../atl-mfc-shared/reference/cfiletime-class.md)|Предоставляет методы для управления значениями даты и времени, связанными с файлом.|атлтиме.h|
|[кфилетимеспан](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Предоставляет методы для управления относительными значениями даты и времени, связанными с файлом.|атлтиме.h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Представляет строковый объект с фиксированным буфером символов.|CStringT.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Обеспечивает улучшенную поддержку точечных рисунков, включая возможность загрузки и сохранения изображений в форматах JPEG, GIF, BMP и PNG.|атлимаже.h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Инкапсулирует тип данных DATE, используемый в OLE Automation.|atlcomtime.h|
|[коледатетимеспан](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Представляет относительное время, интервал времени.|atlcomtime.h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Класс, похожий на структуру [точек](/windows/win32/api/windef/ns-windef-point) Windows, который также включает функции-члены `CPoint` для `POINT` работы со структурами и.|атлтипес.h|
|[крект](../../atl-mfc-shared/reference/crect-class.md)|Класс, аналогичный структуре [прямоугольника](/windows/win32/api/windef/ns-windef-rect) Windows, который также включает функции-члены `CRect` для работы с `RECT` объектами и структурами Windows.|атлтипес.h|
|[ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md)|`CSimpleStringT` Представляет объект.|атлсимпстр.h|
|[ксизе](../../atl-mfc-shared/reference/csize-class.md)|Класс, аналогичный структуре [размера](/windows/win32/api/windef/ns-windef-size) Windows, которая реализует относительную координату или положение.|атлтипес.h|
|[кстрбуфт](../../atl-mfc-shared/reference/cstrbuft-class.md)|Обеспечивает автоматическую очистку ресурсов `GetBuffer` для `ReleaseBuffer` и вызовов для существующего `CStringT` объекта.|атлсимпстр.h|
|[кстрингдата](../../atl-mfc-shared/reference/cstringdata-class.md)|Представляет данные строкового объекта.|атлсимпстр.h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|`CStringT` Представляет объект.|CStringT.h (зависит от MFC) atlstr.h (независимо от MFC)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Представляет абсолютное время и дату.|атлтиме.h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Количество времени, которое внутренне хранится как количество секунд в интервале времени.|атлтиме.h|
|[иатлстрингмгр](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Представляет интерфейс для `CStringT` диспетчера памяти.|атлсимпстр.h|

## <a name="see-also"></a>См. также

[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
