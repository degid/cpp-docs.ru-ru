---
title: CObject, класс
ms.date: 11/04/2016
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
ms.openlocfilehash: ce745e0717e36a3c9acb5323d04545c59750add7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222905"
---
# <a name="cobject-class"></a>CObject, класс

Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CObject:: CObject](#cobject)|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|Проверяет целостность этого объекта.|
|[CObject::D УМП](#dump)|Создает диагностический дамп этого объекта.|
|[CObject:: Жетрунтимекласс](#getruntimeclass)|Возвращает `CRuntimeClass` структуру, соответствующую классу данного объекта.|
|[CObject:: IsKindOf](#iskindof)|Проверяет связь этого объекта с заданным классом.|
|[CObject:: Serializable](#isserializable)|Проверяет, можно ли сериализовать этот объект.|
|[CObject:: Serialize](#serialize)|Загружает или сохраняет объект из или в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Удаление CObject::operator](#operator_delete)|Специальный **`delete`** оператор.|
|[CObject:: оператор New](#operator_new)|Специальный **`new`** оператор.|

## <a name="remarks"></a>Примечания

Он выступает в качестве корня не только для классов библиотек, таких как `CFile` и `CObList` , но также и для классов, которые вы пишете. `CObject`предоставляет базовые службы, включая

- Поддержка сериализации

- Сведения о классе времени выполнения

- Вывод диагностики объектов

- Совместимость с классами коллекций

Обратите внимание, что не `CObject` поддерживает множественное наследование. Производные классы могут иметь только один `CObject` базовый класс, который `CObject` должен быть левым в иерархии. Однако допускается наличие структур и классов, не являющихся `CObject` производными, в правой части ветвей с множественным наследованием.

При `CObject` использовании некоторых необязательных макросов в реализации и объявлениях класса вы получите значительные преимущества от наследования.

Макросы первого уровня, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), допускают доступ во время выполнения к имени класса и его положению в иерархии. Это, в свою очередь, допускает осмысленную диагностическую копию.

Макросы второго уровня, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), включают все функциональные возможности макросов первого уровня, и они позволяют «сериализовать» объект в «архив» и «из него».

Дополнительные сведения о наследовании классов Microsoft Foundation и классов C++ в целом и использовании см `CObject` . в разделе [Использование CObject](../../mfc/using-cobject.md) и [Serialization](../../mfc/serialization-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CObject`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>CObject:: AssertValid

Проверяет целостность этого объекта.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Примечания

`AssertValid`выполняет проверку достоверности этого объекта, проверяя его внутреннее состояние. В отладочной версии библиотеки `AssertValid` может утверждать и, таким же, завершать программу сообщением, в котором отображается номер строки и имя файла, в котором произошел сбой утверждения.

При написании собственного класса следует переопределить `AssertValid` функцию, чтобы предоставить службы диагностики для себя и других пользователей класса. Переопределение `AssertValid` обычно вызывает `AssertValid` функцию своего базового класса перед проверкой элементов данных, уникальных для производного класса.

Поскольку `AssertValid` является **`const`** функцией, вы не имеете права изменять состояние объекта во время теста. Собственные функции производного класса `AssertValid` не должны вызывать исключения, а должны утверждать, обнаруживают ли они недопустимые данные объекта.

Определение "допустимости" зависит от класса объекта. Как правило, функция должна выполнить «полную проверку». То есть, если объект содержит указатели на другие объекты, он должен проверить, не имеет ли указатель значение null, но не должен выполнять проверку на наличие объектов, на которые ссылаются указатели.

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Другой пример см. в разделе [афксдофораллобжектс](diagnostic-services.md#afxdoforallobjects).

## <a name="cobjectcobject"></a><a name="cobject"></a>CObject:: CObject

Эти функции являются стандартными `CObject` конструкторами.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Параметры

*обжектсрк*<br/>
Ссылка на другую`CObject`

### <a name="remarks"></a>Примечания

Версия по умолчанию автоматически вызывается конструктором производного класса.

Если класс является сериализуемым (он включает в себя IMPLEMENT_SERIAL макрос), то в объявлении класса должен быть конструктор по умолчанию (конструктор без аргументов). Если конструктор по умолчанию не нужен, объявите закрытый или защищенный конструктор "Empty". Дополнительные сведения см. [в разделе Использование CObject](../../mfc/using-cobject.md).

Стандартный конструктор копирования класса по умолчанию C++ выполняет копирование по элементу. Наличие закрытого `CObject` конструктора копий гарантирует, что если конструктор копии класса необходим, но недоступен, появится сообщение об ошибке компилятора. Поэтому необходимо предоставить конструктор копии, если класс требует этой возможности.

### <a name="example"></a>Пример

Список классов, используемых в примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>CObject::D УМП

Выводит содержимое объекта в объект [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Параметры

*Постоянный*<br/>
Контекст диагностического дампа для дампа обычно `afxDump` .

### <a name="remarks"></a>Примечания

При написании собственного класса следует переопределить `Dump` функцию, чтобы предоставить службы диагностики для себя и других пользователей класса. `Dump` `Dump` Перед печатью элементов данных, уникальных для производного класса, переопределение обычно вызывает функцию своего базового класса. `CObject::Dump`Выводит имя класса, если в классе используется `IMPLEMENT_DYNAMIC` макрос или IMPLEMENT_SERIAL.

> [!NOTE]
> `Dump`Функция не должна печатать символ новой строки в конце выходных данных.

`Dump`вызовы имеют смысл только в отладочной версии библиотека Microsoft Foundation Class. Для условной компиляции следует заключать в скобки вызовы, объявления функций и реализации функций с помощью **#ifdef _DEBUGных** /  `#endif` инструкций.

Поскольку `Dump` является **`const`** функцией, вы не имеете права изменять состояние объекта во время создания дампа.

[Оператор вставки CDumpContext (<<)](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызывает `Dump` при `CObject` вставке указателя.

`Dump`разрешает только "ациклический" дамп объектов. Можно создать дамп списка объектов, например, но если один из объектов является самим списком, то в конечном итоге стек будет переполнен.

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>CObject:: Жетрунтимекласс

Возвращает `CRuntimeClass` структуру, соответствующую классу данного объекта.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , соответствующую классу данного объекта; никогда не **имеет значения NULL**.

### <a name="remarks"></a>Примечания

`CRuntimeClass`Для каждого `CObject` производного класса существует одна структура. Члены структуры выглядят следующим образом:

- **LPCSTR m_lpszClassName** Строка, заканчивающаяся нулем и содержащая имя класса ASCII.

- **m_nObjectSize int** Размер объекта в байтах. Если объект содержит элементы данных, указывающие на выделенную память, размер этой памяти не включается.

- **M_wSchema uint** Номер схемы (-1 для несериализуемых классов). Описание номера схемы см. в макросе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

- **CObject \* (Pascal \* m_pfnCreateObject) ()** указатель функции на конструктор по умолчанию, создающий объект класса (действителен, только если класс поддерживает динамическое создание; в противном случае возвращает **значение NULL**).

- **Крунтимекласс \* (Pascal \* m_pfn_GetBaseClass) ()** если приложение динамически СВЯЗАНО с версией AFXDLL MFC, то указатель на функцию, возвращающую `CRuntimeClass` структуру базового класса.

- **Крунтимекласс \* m_pBaseClass** , если приложение СТАТИЧЕСКИ связано с MFC, указатель на `CRuntimeClass` структуру базового класса.

Эта функция требует использования макроса [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) в реализации класса. В противном случае будут получены неверные результаты.

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>CObject:: IsKindOf

Проверяет связь этого объекта с заданным классом.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Параметры

*пкласс*<br/>
Указатель на структуру [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанную с `CObject` классом, производным от класса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект соответствует классу; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция проверяет *пкласс* , чтобы определить, является ли он объектом указанного класса или (2) является объектом класса, производного от указанного класса. Эта функция работает только для классов, объявленных с помощью макроса [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) .

Не используйте эту функцию широко, так как она нарушает функцию полиморфизма C++. Вместо этого используйте виртуальные функции.

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>CObject:: Serializable

Проверяет, подходит ли этот объект для сериализации.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот объект можно сериализовать; в противном случае — 0.

### <a name="remarks"></a>Примечания

Чтобы класс был сериализуемым, его объявление должно содержать макрос [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) , а реализация должна содержать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

> [!NOTE]
> Не переопределяйте эту функцию.

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>Удаление CObject::operator

Для версии выпуска библиотеки оператор **`delete`** освобождает память, выделенную оператором **`new`** .

```cpp
void PASCAL operator delete(void* p);

void PASCAL operator delete(
    void* p,
    void* pPlace);

void PASCAL operator delete(
    void* p,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Примечания

В отладочной версии оператор **`delete`** участвует в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из реализаций в. CPP, будет использоваться третья версия, в которой **`delete`** будут храниться имя файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении дополнительных параметров. за вас позаботится макрос.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете возможность обнаружения утечек, но без описанных выше отчетов с исходными файлами.

Если вы переопределяете операторы **`new`** и **`delete`** , вы лишаете этой диагностической возможности.

### <a name="example"></a>Пример

Список классов, используемых в примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>CObject:: оператор New

Для окончательной версии библиотеки оператор **`new`** выполняет оптимальное выделение памяти подобным образом `malloc` .

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Примечания

В отладочной версии оператор **`new`** участвует в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из реализаций в. CPP, используется вторая версия **`new`** , которая сохраняет имя файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении дополнительных параметров. за вас позаботится макрос.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете возможность обнаружения утечек, но без описанных выше отчетов с исходными файлами.

> [!NOTE]
> При переопределении этого оператора необходимо также переопределить **`delete`** . Не используйте стандартную функцию библиотеки `_new_handler` .

### <a name="example"></a>Пример

Список классов, используемых в примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>CObject:: Serialize

Считывает этот объект из архива или записывает в него.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
`CArchive`Объект для сериализации в или из.

### <a name="remarks"></a>Примечания

Необходимо переопределить `Serialize` для каждого класса, который предполагается сериализовать. Переопределенный `Serialize` метод должен сначала вызвать `Serialize` функцию своего базового класса.

Необходимо также использовать макрос [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) в объявлении класса, и в реализации необходимо использовать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

Используйте [CArchive:: Load](../../mfc/reference/carchive-class.md#isloading) или [CArchive::](../../mfc/reference/carchive-class.md#isstoring) , чтобы определить, загружается ли архив или сохраняется.

`Serialize`вызывается методами [CArchive:: вызове ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связаны с `CArchive` оператором вставки ( **<\<**) and extraction operator ( **>>** ).

Примеры сериализации см. в статье [сериализация объекта](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Пример

Список классов, используемых во всех примерах, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>См. также статью

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
