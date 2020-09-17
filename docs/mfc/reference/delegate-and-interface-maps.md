---
title: Макросы с картами делегата и интерфейса (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 01f5cbfb1f751823d218761410bc9091b73cb0a3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837454"
---
# <a name="delegate-and-interface-map-macros"></a>Макросы схем делегата и интерфейса

MFC поддерживает следующие макросы для сопоставлений делегатов и интерфейсов:

|Имя|Описание|
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Начинает карту делегата.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Начинает определение взаимосвязанной схемы.|
|[Делегат CommandHandler](#commandhandler)|Регистрирует методы обратного вызова с источником команды.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Завершает карту делегата.|
|[END_INTERFACE_MAP](#end_interface_map)|Завершает карту интерфейса в файле реализации. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Создает запись в сопоставлении делегата.|
|[INTERFACE_PART](#interface_part)|Используется между макросом BEGIN_INTERFACE_MAP и макросом END_INTERFACE_MAP для каждого интерфейса, который будет поддерживаться объектом.|
|[MAKE_DELEGATE](#make_delegate)|Присоединяет обработчик событий к управляемому элементу управления.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

Начинает карту делегата.

### <a name="syntax"></a>Синтаксис

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Параметры

*СМ*<br/>
Класс, в котором размещается управляемый элемент управления.

### <a name="remarks"></a>Примечания

Этот макрос отмечает начало списка записей делегатов, образующих карту делегатов. Пример использования этого макроса см. в разделе [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Требования

**Заголовок:** мсклр\евент.х

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a> BEGIN_INTERFACE_MAP

Начинает определение взаимосвязанной схемы при использовании в файле реализации.

### <a name="syntax"></a>Синтаксис

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Класс, в котором определяется схема интерфейсов.

*baseClass*<br/>
Класс, от которого наследуется *секласс* .

### <a name="remarks"></a>Примечания

Для каждого реализуемого интерфейса существует один или несколько INTERFACE_PART вызовов макросов. Для каждого статистического выражения, используемого классом, существует один INTERFACE_AGGREGATE вызов макроса.

Дополнительные сведения о картах интерфейсов см. в [техническом примечании 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a> Делегат Коммандхандлер

Регистрирует методы обратного вызова с источником команды.

### <a name="syntax"></a>Синтаксис

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот делегат регистрирует методы обратного вызова с источником команды. При добавлении делегата в исходный объект команды метод обратного вызова превращается в обработчик команд, поступающих из указанного источника.

Дополнительные сведения см. в разделе [инструкции. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Требования

**Заголовок:** афксвинформс.h (определяется в atlmfc\lib\mfcmifc80.dll сборки)

## <a name="commanduihandler"></a><a name="commanduihandler"></a> коммандуихандлер

Регистрирует методы обратного вызова в сообщении командной строки для обновления пользовательского интерфейса.

### <a name="syntax"></a>Синтаксис

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

*кмдуи*<br/>
Идентификатор сообщения команды.

### <a name="remarks"></a>Примечания

Этот делегат регистрирует методы обратного вызова с помощью сообщения команды обновления пользовательского интерфейса. `CommandUIHandler` аналогичен [коммандхандлер](#commandhandler) , за исключением того, что этот делегат используется с командами обновления объекта пользовательского интерфейса. Команды обновления пользовательского интерфейса должны сопоставляться один к одному с помощью методов обработчика сообщений.

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Требования

**Заголовок:** афксвинформс.h (определяется в atlmfc\lib\mfcmifc80.dll сборки)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a> END_DELEGATE_MAP

Завершает карту делегата.

### <a name="syntax"></a>Синтаксис

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Примечания

Этот макрос отмечает конец списка записей делегатов, образующих карту делегатов. Пример использования этого макроса см. в разделе [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Требования

**Заголовок:** мсклр\евент.х

## <a name="end_interface_map"></a><a name="end_interface_map"></a> END_INTERFACE_MAP

Завершает карту интерфейса в файле реализации.

### <a name="syntax"></a>Синтаксис

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о картах интерфейсов см. в [техническом примечании 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a> EVENT_DELEGATE_ENTRY

Создает запись в сопоставлении делегата.

### <a name="syntax"></a>Синтаксис

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Параметры

*УЧАСТНИКАМИ*<br/>
Метод обработчика событий, который должен быть присоединен к элементу управления.

*ARG0*<br/>
Первый аргумент метода обработчика управляемых событий, например `Object^` .

*ARG1*<br/>
Второй аргумент метода обработчика управляемых событий, например `EventArgs^` .

### <a name="remarks"></a>Примечания

Каждая запись в сопоставлении делегата соответствует делегату управляемого обработчика событий, созданному [MAKE_DELEGATE](#make_delegate).

### <a name="example"></a>Пример

В следующем примере кода показано, как использовать EVENT_DELEGATE_ENTRY для создания записи в сопоставлении делегата для `OnClick` обработчика событий. также см. пример кода в MAKE_DELEGATE. Дополнительные сведения см. [в разделе как передавать Windows Forms события из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** мсклр\евент.х

## <a name="interface_part"></a><a name="interface_part"></a> INTERFACE_PART

Используется между макросом BEGIN_INTERFACE_MAP и макросом END_INTERFACE_MAP для каждого интерфейса, который будет поддерживаться объектом.

### <a name="syntax"></a>Синтаксис

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса, содержащего схему интерфейсов.
*IID*<br/>
IID, который должен быть сопоставлен с внедренным классом.
*локалкласс*<br/>
Имя локального класса.

### <a name="remarks"></a>Примечания

Он позволяет сопоставлять IID с членом класса, указанного в *секласс* и *локалкласс*.

Дополнительные сведения о картах интерфейсов см. в [техническом примечании 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a> MAKE_DELEGATE

Присоединяет обработчик событий к управляемому элементу управления.

### <a name="syntax"></a>Синтаксис

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Параметры

*ПОЛУЧИТЬ*<br/>
Тип делегата управляемого обработчика событий, например [EventHandler](/dotnet/api/system.eventhandler).

*УЧАСТНИКАМИ*<br/>
Имя метода обработчика событий, который должен быть присоединен к элементу управления.

### <a name="remarks"></a>Примечания

Этот макрос создает управляемый делегат обработчика событий типа *Delegate* и *члена*Name. Делегат управляемого обработчика событий позволяет собственному классу управлять управляемыми событиями.

### <a name="example"></a>Пример

В следующем примере кода показано, как вызвать метод `MAKE_DELEGATE` , чтобы присоединить `OnClick` обработчик событий к элементу управления MFC `MyControl` . Более подробное описание работы этого макроса в приложении MFC см. в разделе [как передавать Windows Forms события из машинных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** мсклр\евент.х

## <a name="see-also"></a>См. также раздел

[Как приемник Windows Forms событий из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Как добавить маршрутизацию команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
