---
title: Дата и время
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 2a5e6977acfca51b8074399f6f9b3166c8a358bc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491301"
---
# <a name="date-and-time"></a>Дата и время

MFC поддерживает несколько различных способов работы с датами и временем:

- Поддержка [типа данных даты](../atl-mfc-shared/date-type.md)автоматизации. Дата поддерживает значения даты, времени и даты и времени. Классы [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) и [коледатетимеспан](../atl-mfc-shared/reference/coledatetimespan-class.md) инкапсулируют эту функциональность. Они работают с классом [COleVariant](../mfc/reference/colevariant-class.md) , используя поддержку автоматизации.

- Классы времени общего назначения. Классы [CTime](../atl-mfc-shared/reference/ctime-class.md) и [ктимеспан](../atl-mfc-shared/reference/ctimespan-class.md) инкапсулируют большую часть функциональных возможностей, связанных с библиотекой времени ANSI-Standard, которая объявлена по времени. Высоты.

- Поддержка системных часов. В MFC версии 3,0 добавлена `CTime` поддержка для Win32 `SYSTEMTIME` и `FILETIME` типов данных.

## <a name="date-and-time-automation-support"></a>Дата и время: Поддержка автоматизации

Класс [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) предоставляет способ представления сведений о дате и времени. Он обеспечивает большую детализацию и больший диапазон, чем класс [CTime](../atl-mfc-shared/reference/ctime-class.md) . Класс [коледатетимеспан](../atl-mfc-shared/reference/coledatetimespan-class.md) представляет прошедшее время, например разницу между двумя `COleDateTime` объектами.

Классы `COleDateTime` и `COleDateTimeSpan` предназначеныдляиспользования`COleVariant` с классом. `COleDateTime`и `COleDateTimeSpan` также полезны в программировании баз данных MFC, но их можно использовать при управлении значениями даты и времени. Несмотря на `COleDateTime` то, что класс имеет больший диапазон значений и более детально, `CTime` чем класс, он требует больше места для хранения `CTime`на объект, чем. При работе с базовым типом даты также необходимо учитывать некоторые особенности. Дополнительные сведения о реализации даты см. [в разделе Тип даты](../atl-mfc-shared/date-type.md).

`COleDateTime`объекты можно использовать для представления дат между 1 января 100 и 31 декабря 9999. `COleDateTime`объекты — это значения с плавающей запятой с приблизительной разрешающей точкой в 1 миллисекунде. `COleDateTime`основывается на типе данных DATE, определенном в документации MFC в разделе [COleDateTime::operator Date](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Фактическая реализация даты выходит за пределы этих границ. `COleDateTime` Реализация накладывает эти границы, чтобы облегчить работу с классом.

`COleDateTime`не поддерживает Юлианские даты. Предполагается, что григорианский календарь продлится обратно на 1 января 100 г.

`COleDateTime`игнорирует летнее время (DST). В следующем примере кода сравниваются два метода вычисления временного интервала, пересекающие дату переключения летнего времени: один с помощью CRT, а другой с помощью `COleDateTime`.

Первый метод устанавливает два `CTime` объекта, *time1* и *time2*, в 5 апреля и 6 апреля соответственно, используя стандартные структуры `tm` типов C и. `time_t` Код отображает *time1* и *time2* , а также интервал времени между ними.

Второй метод создает два `COleDateTime` объекта, `oletime1` и `oletime2`, и устанавливает их в те же даты, что и *time1* и *time2*. Он отображает `oletime1` и `oletime2` , а также промежуток времени между ними.

CRT правильно вычисляет разность в 23 часа. `COleDateTimeSpan`Вычисляет разность за 24 часа.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>Отображают текущее время

В следующей процедуре показано, как создать `COleDateTime` объект и инициализировать его с текущим временем.

#### <a name="to-get-the-current-time"></a>Получение текущего времени

1. Создание объекта `COleDateTime`.

1. Вызовите метод `GetCurrentTime`.

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>Вычисление затраченного времени

Эта процедура показывает, как вычислить разницу между `COleDateTime` двумя объектами и `COleDateTimeSpan` получить результат.

#### <a name="to-calculate-elapsed-time"></a>Вычисление истекшего времени

1. Создайте два `COleDateTime` объекта.

1. Задайте для одного из `COleDateTime` объектов текущее время.

1. Выполнение определенной длительной задачи.

1. Задайте для другого `COleDateTime` объекта текущее время.

1. Проведите разность между двумя значениями времени.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>Форматирование времени

#### <a name="to-format-a-time"></a>Форматирование времени

Используйте `Format` функцию- член либо [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md), либо [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md), чтобы создать символьную строку, представляющую время или истекшее время.

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

Дополнительные сведения см. в разделе Class [COleVariant](../mfc/reference/colevariant-class.md).

## <a name="date-and-time-database-support"></a>Дата и время: Поддержка баз данных

Начиная с версии 4,0, программирование базы данных MFC использует классы [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) и [коледатетимеспан](../atl-mfc-shared/reference/coledatetimespan-class.md) для представления данных даты и времени. Эти классы, также используемые в службе автоматизации, являются производными от класса [COleVariant](../mfc/reference/colevariant-class.md). Они предоставляют лучшую поддержку для управления данными даты и времени, чем [CTime](../atl-mfc-shared/reference/ctime-class.md) и [ктимеспан](../atl-mfc-shared/reference/ctimespan-class.md).

## <a name="date-and-time-systemtime-support"></a>Дата и время: Поддержка SYSTEMTIME

Класс [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) имеет конструкторы, принимающие время системы и файлов из Win32.

Структура Win32 `FILETIME` представляет время как 64-разрядное значение. Это более удобный формат для внутреннего хранения, чем `SYSTEMTIME` структура, и формат, используемый Win32 для представления времени создания файла. Сведения о структуре SYSTEMTIME см. в разделе [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). Дополнительные сведения о структуре FILETIME см. в разделе [fileTime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)\
[Общие разделы по MFC](../mfc/general-mfc-topics.md)
