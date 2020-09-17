---
title: Интерфейс ICommandUI
ms.date: 09/07/2019
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: b75509beb7287fad5e51dc9d15fc3e47cacf6854
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751306"
---
# <a name="icommandui-interface"></a>Интерфейс ICommandUI

Управляет командами пользовательского интерфейса.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandUI
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[icommandui__Check](#check)|Устанавливает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки.|
|[ICommandUI::Продолжение](#continuerouting)|Сообщает механизму командной расети продолжить движение текущего сообщения по цепочке обработчиков.|
|[ICommandUI::Включено](#enabled)|Позволяет или отсвапотребляет элемент пользовательского интерфейса для этой команды.|
|[ICommandUI:ID](#id)|Получает идентификатор объекта пользовательского `ICommandUI` интерфейса, представленного объектом.|
|[ICommandUI::Индекс](#index)|Получает индекс объекта пользовательского интерфейса, `ICommandUI` представленного объектом.|
|[ICommandUI::Радио](#radio)|Устанавливает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки.|
|[ICommandUI::Текст](#text)|Устанавливает текст элемента пользовательского интерфейса для этой команды.|

## <a name="remarks"></a>Примечания

Этот интерфейс предоставляет методы и свойства, которые управляют командами пользовательского интерфейса. `ICommandUI`похож на [CCmdUI класса](../../mfc/reference/ccmdui-class.md) `ICommandUI` , за исключением, что используется для приложений MFC, которые взаимодействуют с компонентами .NET.

`ICommandUI`используется в ON_UPDATE_COMMAND_UI обработчике в классе [ICommandTarget.](../../mfc/reference/icommandtarget-interface.md) Когда пользователь приложения активирует (выбирает или кликов) меню, каждый пункт меню отображается как включенный или отключенный. Цель каждой команды меню предоставляет эту информацию, реализуя ON_UPDATE_COMMAND_UI обработчик. Для каждого из объектов пользовательского интерфейса команды в приложении используйте [Класс Мастер](mfc-class-wizard.md) для создания входа и прототипа функции для каждого обработчика.

Для получения дополнительной `ICommandUI` информации о том, как интерфейс используется в командной реукторе, см. [Как: Добавьте командную равение в управление формами Windows.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

Для получения дополнительной информации о том, как [CCmdUI Class](../../mfc/reference/ccmdui-class.md)управлять командами пользовательского интерфейса в MFC, см.

## <a name="icommanduicheck"></a><a name="check"></a>ICommandUI::Проверить

Устанавливает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки.

```
property UICheckState Check;
```

## <a name="remarks"></a>Примечания

Это свойство настраивает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки. Установите проверить на следующие значения:

- 0 Uncheck
- 1 Проверка
- 2 Установить неопределенный

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a>ICommandUI::Продолжение

Сообщает механизму комнинета команды продолжить расшатывание текущего сообщения по цепочке обработчиков.

```cpp
void ContinueRouting();
```

## <a name="remarks"></a>Примечания

Это расширенная функция члена, которая должна использоваться в сочетании с обработчиком ON_COMMAND_EX, который возвращает FALSE. Для получения дополнительной информации см.

## <a name="icommanduienabled"></a><a name="enabled"></a>ICommandUI::Включено

Позволяет или отсвапотребляет элемент пользовательского интерфейса для этой команды.

```
property bool Enabled;
```

## <a name="remarks"></a>Примечания

Это свойство позволяет или отскакивает элемент пользовательского интерфейса для этой команды. Набор Включен в ИСТИНу, чтобы включить элемент, FALSE, чтобы отключить его.

## <a name="icommanduiid"></a><a name="id"></a>ICommandUI:ID

Получает идентификатор объекта пользовательского интерфейса, представленного объектом ICommandUI.

```
property unsigned int ID;
```

## <a name="remarks"></a>Примечания

Это свойство получает идентификатор (ручку) элемента меню, кнопки панели инструментов или другого объекта пользовательского интерфейса, представленного объектом ICommandUI.

## <a name="icommanduiindex"></a><a name="index"></a>ICommandUI::Индекс

Получает индекс объекта пользовательского интерфейса, представленного объектом ICommandUI.

```
property unsigned int Index;
```

## <a name="remarks"></a>Примечания

Это свойство получает индекс (ручку) элемента меню, кнопки панели инструментов или другого объекта пользовательского интерфейса, представленного объектом ICommandUI.

## <a name="icommanduiradio"></a><a name="radio"></a>ICommandUI::Радио

Устанавливает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки.

```
property bool Radio;
```

## <a name="remarks"></a>Примечания

Это свойство настраивает элемент пользовательского интерфейса для этой команды в соответствующее состояние проверки. Установите радио к TRUE, чтобы включить элемент; в противном случае FALSE.

## <a name="icommanduitext"></a><a name="text"></a>ICommandUI::Текст

Устанавливает текст элемента пользовательского интерфейса для этой команды.

```
property String^ Text;
```

## <a name="remarks"></a>Примечания

Это свойство устанавливает текст элемента пользовательского интерфейса для этой команды. Установите текст на ручку строки текста.

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="see-also"></a>См. также раздел

[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)
