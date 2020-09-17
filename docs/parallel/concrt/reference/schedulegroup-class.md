---
title: Класс ScheduleGroup
ms.date: 11/04/2016
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
ms.openlocfilehash: 8686b5ef0906e3188a1e683d1190bbe6124cd19e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424233"
---
# <a name="schedulegroup-class"></a>Класс ScheduleGroup

Представляет абстракцию для группы расписаний. Группы расписаний организуют набор связанных работ, которые выигрывают от планирования в непосредственной близости друг от друга: во времени (путем выполнения другой задачи в той же группе перед перемещением в другую группу) или в пространстве (путем выполнения нескольких элементов в той же группе в том же узле NUMA или физическом сокете).

## <a name="syntax"></a>Синтаксис

```cpp
class ScheduleGroup;
```

## <a name="members"></a>Члены

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[Деструктор ~ ScheduleGroup](#dtor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Id](#id)|Возвращает идентификатор для группы расписаний, уникальный в пределах планировщика, к которому принадлежит группа.|
|[Справочные материалы](#reference)|Увеличивает значение счетчика ссылок группы расписания.|
|[Выпуск](#release)|Уменьшает значение счетчика ссылок группы планировщика.|
|[ScheduleTask](#scheduletask)|Планирует облегченную задачу в группе расписаний.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ScheduleGroup`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="id"></a>Удостоверения

Возвращает идентификатор для группы расписаний, уникальный в пределах планировщика, к которому принадлежит группа.

```cpp
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор группы расписаний, уникальный в пределах планировщика, к которому принадлежит группа.

## <a name="operator_delete"></a>оператор DELETE

Объект `ScheduleGroup` внутренне уничтожается средой выполнения, когда все внешние ссылки на него освобождаются. Его невозможно удалить явно.

```cpp
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
const char *,
    int);
```

### <a name="parameters"></a>Параметры

*_PObject*<br/>
Указатель на удаляемый объект.

## <a name="reference"></a>IsReference

Увеличивает значение счетчика ссылок группы расписания.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Вновь увеличивающееся число ссылок.

### <a name="remarks"></a>Примечания

Обычно это используется для управления временем существования группы расписаний для композиции. Если количество ссылок группы расписаний становится равным нулю, Группа расписаний удаляется средой выполнения. Группа расписаний, созданная с помощью метода [CurrentScheduler:: CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) или метода [Scheduler:: CreateScheduleGroup](scheduler-class.md#createschedulegroup) , начинается со счетчика ссылок одного из них.

## <a name="release"></a>Отпускании

Уменьшает значение счетчика ссылок группы планировщика.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Вновь уменьшенное число ссылок.

### <a name="remarks"></a>Примечания

Обычно это используется для управления временем существования группы расписаний для композиции. Если количество ссылок группы расписаний становится равным нулю, Группа расписаний удаляется средой выполнения. После вызова метода `Release` определенное количество раз для удаления счетчика ссылок создания и любых дополнительных ссылок, помещенных с помощью метода `Reference`, вы не сможете использовать группу расписаний еще дальше. Это приведет к неопределенному поведению.

Группа расписаний связана с определенным экземпляром планировщика. Необходимо убедиться, что все ссылки на группу расписаний освобождены до выпуска всех ссылок на планировщик, так как Последнее может привести к уничтожению планировщика. В противном случае это приведет к неопределенному поведению.

## <a name="dtor"></a>~ ScheduleGroup

```cpp
virtual ~ScheduleGroup();
```

## <a name="scheduletask"></a>ScheduleTask

Планирует облегченную задачу в группе расписаний.

```cpp
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```

### <a name="parameters"></a>Параметры

*_Proc*<br/>
Указатель на функцию, которая должна быть выполнена, чтобы выполнить задачу неплотности.

*_Data*<br/>
Указатель типа void на данные, которые будут переданы в качестве параметра в текст задачи.

### <a name="remarks"></a>Примечания

Вызов метода `ScheduleTask` неявно помещает счетчик ссылок на группу расписаний, которая удаляется средой выполнения в соответствующее время после выполнения задачи.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс CurrentScheduler](currentscheduler-class.md)<br/>
[Класс Scheduler](scheduler-class.md)<br/>
[Планировщик заданий](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
