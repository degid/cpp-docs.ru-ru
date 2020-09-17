---
title: Структура CRuntimeClass
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: a58b9c97d5683423a0f81f6b5424f19f987943bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318553"
---
# <a name="cruntimeclass-structure"></a>Структура CRuntimeClass

Каждый класс, `CObject` полученный `CRuntimeClass` из связан с структурой, которую можно использовать для получения информации об объекте или его базовом классе во время выполнения.

## <a name="syntax"></a>Синтаксис

```
struct CRuntimeClass
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRuntimeClass::CreateObject](#createobject)|Создает объект во время выполнения.|
|[CRuntimeClass::От](#fromname)|Создает объект во время выполнения, используя знакомое имя класса.|
|[CRuntimeClass::IsDerived](#isderivedfrom)|Определяет, является ли класс выведен из указанного класса.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Имя класса.|
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Размер объекта в байтах.|
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Указатель на `CRuntimeClass` структуру базового класса.|
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Указатель на функцию, которая динамически создает объект.|
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Возвращает `CRuntimeClass` структуру (доступна только при динамическом подключении).|
|[CRuntimeClass::m_wSchema](#m_wschema)|Номер схемы класса.|

## <a name="remarks"></a>Примечания

`CRuntimeClass`является структурой и, следовательно, не имеет базового класса.

Возможность определения класса объекта во время выполнения полезна, когда требуется дополнительная проверка типа функциональных аргументов или когда необходимо написать специальный код на основе класса объекта. Информация о забеге не поддерживается непосредственно языком СЗ.

`CRuntimeClass`предоставляет информацию о связанном объекте КЗ, `CRuntimeClass` например указатель на базовый класс и название класса ASCII соответствующего класса. Эта структура также реализует различные функции, которые могут быть использованы для динамического создания объектов, с указанием типа объекта с помощью знакомого имени и определения того, является ли связанный класс выведен из определенного класса.

Для получения дополнительной `CRuntimeClass`информации об [использовании,](../../mfc/accessing-run-time-class-information.md)см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CRuntimeClass`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a>CRuntimeClass::CreateObject

Вызов ими функции динамического создания заданного класса во время выполнения.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Знакомое название создаваемого класса.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный объект или NULL, если имя класса не найдено или не хватает памяти для создания объекта.

### <a name="remarks"></a>Примечания

Полученные классы `CObject` могут поддерживать динамическое создание, то есть возможность создания объекта определенного класса во время выполнения. Например, классы документов, представления и кадра должны поддерживать динамическое создание. Для получения дополнительной информации `CreateObject` о создании динамического и участника см. [Класс CObject](../../mfc/using-cobject.md) и [Класс CObject: Определение уровней функциональности.](../../mfc/specifying-levels-of-functionality.md)

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassfromname"></a><a name="fromname"></a>CRuntimeClass::От

Вызовите эту функцию, чтобы получить структуру, связанную `CRuntimeClass` со знакомым именем.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Знакомое название класса происходит `CObject`от .

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CRuntimeClass` объект, соответствующий имени, передаваемому в *lpszClassName*. Функция возвращает NULL, если не найдено соответствующее имя класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a>CRuntimeClass::IsDerived

Вызовите эту функцию, чтобы определить, является ли класс вызовов выведен из класса, указанного в параметре *pBaseClass.*

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Параметры

*pBaseClass*<br/>
Знакомое название класса происходит `CObject`от .

### <a name="return-value"></a>Возвращаемое значение

TRUE, если `IsDerivedFrom` вызов класса происходит от `CRuntimeClass` базового класса, структура которого приведена в качестве параметра; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Отношения определяются "ходьба" от класса члена вверх по цепочке производных классов вплоть до вершины. Эта функция возвращает FALSE только в том случае, если для базового класса не найдено совпадений.

> [!NOTE]
> Чтобы использовать `CRuntimeClass` структуру, необходимо включить IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE или IMPLEMENT_SERIAL макрос в реализацию класса, для которого требуется получить информацию об объекте времени выполнения.

Для получения дополнительной `CRuntimeClass`информации об использовании, см. [CObject Class: Accessing Run-Time Class Information](../../mfc/accessing-run-time-class-information.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName

Строка с нулевым завершением, содержащая имя класса ASCII.

### <a name="remarks"></a>Примечания

Это имя может быть использовано для создания `FromName` экземпляра класса с использованием функции члена.

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize

Размер объекта, в байтах.

### <a name="remarks"></a>Примечания

Если у объекта есть члены данных, которые указывают на выделенную память, размер этой памяти не включен.

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass

Если приложение статично ссылается на MFC, этот участник `CRuntimeClass` данных содержит указатель на структуру базового класса.

### <a name="remarks"></a>Примечания

Если ваше приложение динамически ссылается на библиотеку MFC, см. [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject

Указатель функции на конструктор по умолчанию, который создает объект вашего класса.

### <a name="remarks"></a>Примечания

Этот указатель действителен только в том случае, если класс поддерживает создание динамического; в противном случае функция возвращает NULL.

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass

Если приложение использует библиотеку MFC в качестве общего DLL, этот `CRuntimeClass` участник данных указывает на функцию, которая возвращает структуру базового класса.

### <a name="remarks"></a>Примечания

Если приложение статично ссылается на библиотеку MFC, см. [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a>CRuntimeClass::m_wSchema

Число схем (-1 для несерийных классов).

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о цифрах схем см [IMPLEMENT_SERIAL.](run-time-object-model-services.md#implement_serial)

### <a name="example"></a>Пример

  Смотрите пример [isDerivedFrom](#isderivedfrom).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Объект::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[Объект::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
