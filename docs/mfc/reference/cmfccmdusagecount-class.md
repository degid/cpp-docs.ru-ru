---
title: Класс CMFCCmdUsageCount
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: 95dca548856510cd8b06914932cc46435c28399d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834281"
---
# <a name="cmfccmdusagecount-class"></a>Класс CMFCCmdUsageCount

Отслеживает количество использований сообщений Windows, например, когда пользователь выбирает элемент из меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[CMFCCmdUsageCount:: Аддкмд](#addcmd)|Увеличивает на один счетчик, связанный с заданной командой.|
|[CMFCCmdUsageCount:: NOCOUNT](#getcount)|Возвращает счетчик использования, связанный с заданным ИДЕНТИФИКАТОРом команды.|
|[CMFCCmdUsageCount:: Хасенаугхинформатион](#hasenoughinformation)|Определяет, собрал ли этот объект минимальный объем данных отслеживания.|
|[CMFCCmdUsageCount:: Исфрекеунтлюседкмд](#isfreqeuntlyusedcmd)|Определяет, используется ли данная команда часто.|
|[CMFCCmdUsageCount:: Reset](#reset)|Очищает счетчик использования всех команд.|
|[CMFCCmdUsageCount:: Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CMFCCmdUsageCount:: Сетоптионс](#setoptions)|Задает значения `CMFCCmdUsageCount` членов данных общего класса.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|-|-|
|`m_CmdUsage`|`CMap`Объект, который сопоставляет команды с их счетчиками использования.|
|`m_nMinUsagePercentage`|Минимальный процент использования для часто используемых команд.|
|`m_nStartCount`|Счетчик запуска, используемый для определения того, был ли этот объект собрал минимальный объем данных отслеживания.|
|`m_nTotalUsage`|Число всех отслеживаний команд.|

### <a name="remarks"></a>Примечания

`CMFCCmdUsageCount`Класс сопоставляет каждый числовой идентификатор сообщения Windows с счетчиком 32-разрядных целых чисел без знака. `CMFCToolBar` использует этот класс для вывода часто используемых элементов панели инструментов. Дополнительные сведения о см `CMFCToolBar` . в разделе [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).

`CMFCCmdUsageCount`Данные класса можно сохранять между запусками программы. Используйте метод [CMFCCmdUsageCount:: Serialize](#serialize) для сериализации данных элементов класса и метод [CMFCCmdUsageCount:: сетоптионс](#setoptions) , чтобы задать общие данные элемента.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкскмдусажекаунт.h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a> CMFCCmdUsageCount:: Аддкмд

Увеличивает на один счетчик, связанный с заданной командой.

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*уикмд*\
окне Указывает счетчик команд для увеличения.

### <a name="remarks"></a>Примечания

Этот метод добавляет новую запись в структуру Map счетчика команд, `m_CmdUsage` Если запись еще не существует.

Этот метод не выполняет никаких действий в следующих случаях:

- Платформа панели инструментов находится в режиме настройки (метод [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) возвращает ненулевое значение).

- Команда ссылается на подменю или разделитель меню ( *уикмд* равно 0 или-1).

- *уикмд* ссылается на стандартную команду (Глобальная `IsStandardCommand` функция возвращает ненулевое значение).

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a> CMFCCmdUsageCount:: NOCOUNT

Возвращает счетчик использования, связанный с заданным ИДЕНТИФИКАТОРом команды.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

*уикмд*\
окне ИДЕНТИФИКАТОР получаемого счетчика команды.

### <a name="return-value"></a>Возвращаемое значение

Счетчик использования, связанный с заданным ИДЕНТИФИКАТОРом команды.

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a> CMFCCmdUsageCount:: Хасенаугхинформатион

Определяет, получил ли этот объект минимальный объем данных отслеживания.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот объект получил минимальный объем данных отслеживания; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает ненулевое значение, если общее число `m_nTotalUsage` всех записанных команд равно значению начального счетчика или превышает его `m_nStartCount` . По умолчанию платформа устанавливает начальное значение счетчика 0. Это значение можно переопределить с помощью метода [CMFCCmdUsageCount:: сетоптионс](#setoptions) .

Этот метод используется функцией [CMFCMenuBar:: исшоваллкоммандс](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) , чтобы определить, следует ли отображать все доступные команды меню.

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a> CMFCCmdUsageCount:: Исфрекеунтлюседкмд

Определяет, используется ли данная команда часто.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

*уикмд*\
окне Указывает команду для проверки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда часто используется; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает 0, если общее использование команды `m_nTotalUsage` равно 0. В противном случае этот метод возвращает ненулевое значение, если процент, в котором используется указанная команда, больше, чем минимальный процент, `m_nMinUsagePercentage` . По умолчанию платформа устанавливает для минимального значения в процентах значение 5. Это значение можно переопределить с помощью метода [CMFCCmdUsageCount:: сетоптионс](#setoptions) . Если минимальный процент равен 0, этот метод возвращает ненулевое значение, если указанное число команд больше 0.

[CMFCToolBar:: искоммандрарелюсед](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) использует этот метод, чтобы определить, используется ли команда редко.

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a> CMFCCmdUsageCount:: Reset

Очищает счетчик использования всех команд.

```cpp
void Reset();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы очистить все записи из структуры карт для счетчика команд, `m_CmdUsage` и, чтобы сбросить общее использование команды, `m_nTotalUsage` , счетчик — 0.

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a> CMFCCmdUsageCount:: Serialize

Считывает этот объект из архива или записывает его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*\
окне `CArchive` Объект для сериализации из или в.

### <a name="remarks"></a>Примечания

Этот метод сериализует структуру отображения счетчиков команд, `m_CmdUsage` и общее использование команды, `m_nTotalUsage` , счетчик из или в указанный архив.

Примеры сериализации см. [в разделе Сериализация: сериализация объекта](../../mfc/serialization-serializing-an-object.md).

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a> CMFCCmdUsageCount:: Сетоптионс

Задает значения `CMFCCmdUsageCount` членов данных общего класса.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Параметры

*нстарткаунт*\
окне Новое начальное число всех отслеживаний команд.

*нминусажеперцентаже*\
окне Новый минимальный процент использования.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполняется, значение FALSE, если значение параметра *нминусажеперцентаже* больше или равно 100.

### <a name="remarks"></a>Примечания

Этот метод задает `CMFCCmdUsageCount` члены данных общего класса `m_nStartCount` , а `m_nMinUsagePercentage` также *нстарткаунт* и *нминусажеперцентаже*соответственно. `m_nStartCount` используется методом [CMFCCmdUsageCount:: хасенаугхинформатион](#hasenoughinformation) , чтобы определить, собрал ли этот объект минимальный объем данных отслеживания. `m_nMinUsagePercentage` используется методом [CMFCCmdUsageCount:: исфрекеунтлюседкмд](#isfreqeuntlyusedcmd) , чтобы определить, используется ли данная команда часто.

В отладочных сборках этот метод создает ошибку утверждения, если параметр *нминусажеперцентаже* больше или равен 100.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
