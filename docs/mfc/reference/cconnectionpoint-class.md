---
title: Класс Кконнектионпоинт
ms.date: 11/04/2016
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
ms.openlocfilehash: f428ec597e0e4a56788fae2455eff80b286fda39
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87183088"
---
# <a name="cconnectionpoint-class"></a>Класс Кконнектионпоинт

Определяет особый тип интерфейса, используемый для взаимодействия с другими объектами OLE и называемый "точкой подключения".

## <a name="syntax"></a>Синтаксис

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кконнектионпоинт:: Кконнектионпоинт](#cconnectionpoint)|Формирует объект `CConnectionPoint`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кконнектионпоинт:: соединений](#getconnections)|Извлекает все точки подключения в схеме соединения.|
|[Кконнектионпоинт:: Contain](#getcontainer)|Извлекает контейнер элемента управления, которому принадлежит схема соединения.|
|[Кконнектионпоинт:: Жетиид](#getiid)|Возвращает идентификатор интерфейса точки подключения.|
|[Кконнектионпоинт:: GetMaxConnections](#getmaxconnections)|Возвращает максимальное число точек соединения, поддерживаемое элементом управления.|
|[Кконнектионпоинт:: Жетнекстконнектион](#getnextconnection)|Извлекает указатель на элемент Connection в *торговом терминале*.|
|[Кконнектионпоинт:: Жетстартпоситион](#getstartposition)|Запускает итерацию Map, возвращая значение ПОЗИЦИЕЙ, которое можно передать в `GetNextConnection` вызов.|
|[Кконнектионпоинт:: onadvise](#onadvise)|Вызывается платформой при установке или разрыве соединений.|
|[Кконнектионпоинт:: Куерисинкинтерфаце](#querysinkinterface)|Извлекает указатель на запрошенный интерфейс приемника.|

## <a name="remarks"></a>Примечания

В отличие от обычных интерфейсов OLE, которые используются для реализации и предоставления функциональных возможностей элемента управления OLE, точка соединения реализует исходящий интерфейс, который может инициировать действия с другими объектами, такими как срабатывание событий и уведомления об изменениях.

Соединение состоит из двух частей: объекта, вызывающего интерфейс, называемого «источником», и объекта, реализующего интерфейс, называемого «приемником». Предоставляя точку подключения, источник позволяет приемникам устанавливать соединения с самим собой. С помощью механизма точки подключения исходный объект получает указатель на реализацию набора функций-членов приемника. Например, чтобы запустить событие, реализованное приемником, источник может вызвать соответствующий метод реализации приемника.

По умолчанию `COleControl` производный класс реализует две точки соединения: одну для событий и одну для уведомлений об изменении свойств. Эти соединения используются соответственно для срабатывания событий и для уведомления приемника (например, контейнера элемента управления) при изменении значения свойства. Кроме того, предоставляется поддержка элементов управления OLE для реализации дополнительных точек подключения. Для каждой дополнительной точки подключения, реализованной в классе элемента управления, необходимо объявить часть соединения, которая реализует точку подключения. При реализации одной или нескольких точек подключения необходимо также объявить одну «карту соединения» в классе элемента управления.

В следующем примере показана простая схема соединения и одна точка подключения для `Sample` элемента управления OLE, состоящая из двух фрагментов кода: первая часть объявляет карту соединения и точку, а вторая реализует эту карту и точку. Первый фрагмент вставляется в объявление класса элемента управления в **`protected`** разделе:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

Макросы BEGIN_CONNECTION_PART и END_CONNECTION_PART объявляют внедренный класс `XSampleConnPt` (производный от `CConnectionPoint` ), который реализует эту конкретную точку подключения. Если вы хотите переопределить `CConnectionPoint` функции элементов или добавить собственные функции, объявите их между этими двумя макросами. Например, CONNECTION_IID макрос переопределяет `CConnectionPoint::GetIID` функцию члена при помещении между этими двумя макросами.

Второй фрагмент кода вставляется в файл реализации (. CPP) класса элемента управления. Этот код реализует карту подключения, которая включает дополнительную точку подключения `SampleConnPt` :

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

После вставки этих фрагментов кода образец элемента управления OLE предоставляет точку подключения для `ISampleSink` интерфейса.

Как правило, точки подключения поддерживают "многоадресную рассылку", которая является возможностью вещания в несколько приемников, подключенных к одному интерфейсу. В следующем фрагменте кода показано, как выполнять многоадресную рассылку путем прохода по каждому приемнику в точке подключения:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

В этом примере извлекается текущий набор соединений в `SampleConnPt` точке соединения с вызовом `CConnectionPoint::GetConnections` . Затем он проходит через соединения и вызывает `ISampleSink::SinkFunc` для каждого активного соединения.

Дополнительные сведения об использовании см `CConnectionPoint` . в статье [точки подключения](../../mfc/connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>Кконнектионпоинт:: Кконнектионпоинт

Формирует объект `CConnectionPoint`.

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a>Кконнектионпоинт:: соединений

Вызовите эту функцию, чтобы получить все активные соединения для точки подключения.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив активных соединений (приемников). Некоторые указатели в массиве могут иметь значение NULL. Каждый непустой указатель в этом массиве можно безопасно преобразовать в указатель на интерфейс приемника с помощью оператора приведения.

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a>Кконнектионпоинт:: Contain

Вызывается платформой для получения `IConnectionPointContainer` точки подключения.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на контейнер; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Эта функция обычно реализуется с помощью макроса BEGIN_CONNECTION_PART.

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a>Кконнектионпоинт:: Жетиид

Вызывается платформой для получения идентификатора интерфейса точки подключения.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор интерфейса точки подключения.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы вернуть идентификатор интерфейса для этой точки подключения.

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>Кконнектионпоинт:: GetMaxConnections

Вызывается платформой для получения максимального числа соединений, поддерживаемых точкой подключения.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число подключений, поддерживаемое элементом управления, или значение-1, если ограничение отсутствует.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает значение-1, что означает отсутствие ограничения.

Переопределите эту функцию, если требуется ограничить количество приемников, которые могут подключаться к элементу управления.

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>Кконнектионпоинт:: Жетнекстконнектион

Извлекает указатель на элемент Connection в *торговом терминале*.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Задает ссылку на значение, возвращенное предыдущим `GetNextConnection` или [жетстартпоситион](#getstartposition) вызовом.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент Connection, указанный в *POS*, или значение null.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для прохода по всем элементам в схеме соединения. При итерации пропустите все значения NULL, возвращенные этой функцией.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a>Кконнектионпоинт:: Жетстартпоситион

Запускает итерацию Map, возвращая значение расположения, которое может быть передано в вызов [жетнекстконнектион](#getnextconnection) .

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение положения, указывающее начальную точку для прохода по карте; или значение NULL, если схема пуста.

### <a name="remarks"></a>Примечания

Последовательность итераций не является прогнозируемой. Таким образом, «первый элемент на карте» не имеет особой значимости.

### <a name="example"></a>Пример

  См. пример для [кконнектионпоинт:: жетнекстконнектион](#getnextconnection).

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a>Кконнектионпоинт:: onadvise

Вызывается платформой при установке или разрыве соединения.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Параметры

*бадвисе*<br/>
Значение TRUE, если соединение устанавливается. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий.

Переопределите эту функцию, если требуется уведомление, когда приемники подключаются к точке подключения или отключаются от нее.

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>Кконнектионпоинт:: Куерисинкинтерфаце

Извлекает указатель на запрошенный интерфейс приемника.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Параметры

*пунксинк*<br/>
Идентификатор запрашиваемого интерфейса приемника.

*ппинтерфаце*<br/>
Указатель на указатель интерфейса, идентифицируемый *пунксинк*. Если объект не поддерживает этот интерфейс, \* *ппинтерфаце* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[Класс от CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
