---
title: Структура CMemoryState
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: 823d424620e205d14f247a147bbf7dcb40a626b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222918"
---
# <a name="cmemorystate-structure"></a>Структура CMemoryState

Предоставляет удобный способ обнаружения утечек памяти в программе.

## <a name="syntax"></a>Синтаксис

```
struct CMemoryState
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|Создает структуру, похожую на класс, которая управляет контрольными точками памяти.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|Получает моментальный снимок (контрольная точка) текущего состояния памяти.|
|[CMemoryState::D ифференце](#difference)|Вычисление разницы между двумя объектами типа `CMemoryState` .|
|[CMemoryState::D Умпаллобжектссинце](#dumpallobjectssince)|Выводит сводку всех объектов, выделенных в данный момент с момента создания предыдущей контрольной точки.|
|[CMemoryState::D Умпстатистикс](#dumpstatistics)|Печать статистики выделения памяти для `CMemoryState` объекта.|

## <a name="remarks"></a>Примечания

`CMemoryState`является структурой и не имеет базового класса.

«Утечка памяти» возникает, когда память для объекта выделяется в куче, но не освобождается, если она больше не нужна. Такие утечки памяти могут в конечном итоге привести к ошибкам нехватки памяти. Существует несколько способов выделения и освобождения памяти в программе.

- Использование `malloc` /  `free` семейства функций из библиотеки времени выполнения.

- С помощью функций управления памятью Windows API `LocalAlloc` /  `LocalFree` и `GlobalAlloc` /  `GlobalFree` .

- Использование операторов C++ **`new`** и **`delete`** .

`CMemoryState`Диагностика позволяет выявить утечки памяти, вызванные тем, что память, выделенная с помощью **`new`** оператора, не освобождается с помощью **`delete`** . Две другие группы функций управления памятью предназначены для программ, не относящихся к C + +, и их смешивание с **`new`** и **`delete`** в одной программе не рекомендуется. Дополнительный макрос, DEBUG_NEW, предоставляется для замены **`new`** оператора, если требуется отслеживание количества выделений памяти в файле и строке. DEBUG_NEW используется при обычном использовании **`new`** оператора.

Как и в случае с другими диагностическими данными, `CMemoryState` Диагностика доступна только в отладочных версиях программы. Для отладочной версии должна быть определена константа _DEBUG.

Если предполагается, что программа имеет утечку памяти, можно использовать `Checkpoint` функции, `Difference` и, `DumpStatistics` чтобы узнать разницу между состоянием памяти (выделенными объектами) в двух разных точках выполнения программы. Эти сведения могут быть полезны при определении того, очищается ли функция от всех объектов, которые она выделяет.

Если просто узнать, где происходит дисбаланс при выделении и освобождении, не предоставляет достаточно информации, можно использовать `DumpAllObjectsSince` функцию для дампа всех объектов, выделенных с момента предыдущего вызова `Checkpoint` . Этот дамп показывает порядок выделения, исходный файл и строку, в которой был выделен объект (если используется DEBUG_NEW для выделения) и наследование объекта, его адрес и размер. `DumpAllObjectsSince`также вызывает функцию каждого объекта `Dump` , чтобы предоставить сведения о его текущем состоянии.

Дополнительные сведения об использовании `CMemoryState` и других диагностических данных см. в разделе [Отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
> Объявления объектов типа `CMemoryState` и вызовов функций элементов должны быть заключены в квадратные `#if defined(_DEBUG)/#endif` директивы. Это приводит к тому, что диагностика памяти будет включена только в отладочных сборках программы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CMemoryState`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState:: Checkpoint

Создает сводку по снимкам памяти и сохраняет ее в этом `CMemoryState` объекте.

```cpp
void Checkpoint();
```

### <a name="remarks"></a>Примечания

`CMemoryState`Функции элементов [различаются](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использовать эти данные моментального снимка.

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState:: CMemoryState

Создает пустой `CMemoryState` объект, который должен быть заполнен с помощью функции члена [контрольной точки](#checkpoint) или [разности](#difference) .

```
CMemoryState();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>CMemoryState::D ифференце

Сравнивает два `CMemoryState` объекта, а затем сохраняет разность в этом `CMemoryState` объекте.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Параметры

*олдстате*<br/>
Начальное состояние памяти, определенное `CMemoryState` контрольной точкой.

*Новое_состояние*<br/>
Новое состояние памяти, определенное `CMemoryState` контрольной точкой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если два состояния памяти различаются; в противном случае — 0.

### <a name="remarks"></a>Примечания

Для каждого из двух параметров состояния памяти должна быть вызвана [контрольная точка](#checkpoint) .

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::D Умпаллобжектссинце

Вызывает `Dump` функцию для всех объектов типа, производных от класса `CObject` , которые были выделены (и по-прежнему выделены) с момента последнего вызова [контрольной точки](#checkpoint) для этого `CMemoryState` объекта.

```cpp
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Примечания

Вызов `DumpAllObjectsSince` с неинициализированным `CMemoryState` объектом приведет к дампу всех объектов, находящихся в памяти в данный момент.

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::D Умпстатистикс

Выводит отчет о краткой статистике памяти из `CMemoryState` объекта, который заполняется функцией-членом [разности](#difference) .

```cpp
void DumpStatistics() const;
```

### <a name="remarks"></a>Примечания

Отчет, который печатается на устройстве [афксдумп](diagnostic-services.md#afxdump) , содержит следующие сведения:

Образец отчета содержит сведения о количестве (или объеме):

- свободные блоки

- нормальные блоки

- Блоки CRT

- игнорировать блоки

- клиентские блоки

- максимальный объем памяти, используемый программой в любой момент времени (в байтах)

- Общий объем используемой программой памяти (в байтах)

Свободные блоки — число блоков, освобождение которых было отложено, если `afxMemDF` установлено значение `delayFreeMemDF` . Дополнительные сведения см. в статье [afxMemDF](diagnostic-services.md#afxmemdf)в разделе "макросы и глобальные библиотеки MFC".

### <a name="example"></a>Пример

  Следующий код следует поместить в приложение *ProjName*. cpp. Определите следующие глобальные переменные:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

В `InitInstance` функцию добавьте строку:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

Добавьте обработчик для `ExitInstance` функции и используйте следующий код:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Теперь можно запустить программу в режиме отладки, чтобы увидеть выходные данные `DumpStatistics` функции.

## <a name="see-also"></a>См. также статью

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
