---
title: Интерфейс ICommandTarget
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: be64f4e0367b9ecc1b24fa96f067f4acd45a9978
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751452"
---
# <a name="icommandtarget-interface"></a>Интерфейс ICommandTarget

Обеспечивает управление пользователем интерфейсом для получения команд от объекта исходного кода команды.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandTarget
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ICommandTarget::Инициализация](#initialize)|Инициализирует объект цели команды.|

## <a name="remarks"></a>Примечания

Когда вы размещаете управление пользователем в представлении MFC, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) направляет команды и обновляет сообщения пользовательского интерфейса для управления пользователем, чтобы он должен обрабатывать команды MFC (например, элементы меню кадра и кнопки панели инструментов). Реализуя, `ICommandTarget`вы даете пользователю управления ссылку на объект [ICommandSource.](../../mfc/reference/icommandsource-interface.md)

[Узнайте, как: Добавьте командную раминю](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) в управление `ICommandTarget`формами Windows для примера использования.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a>ICommandTarget::Инициализация

Инициализирует объект цели команды.

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Параметры

*cmdИсточник*<br/>
Ручка к объекту исходного кода команды.

### <a name="remarks"></a>Примечания

Когда вы размещаете управление пользователем в представлении MFC, CWinFormsView маршрутирует команды и обновляет сообщения пользовательского интерфейса для управления пользователем, чтобы позволить ему обрабатывать команды MFC.

Этот метод инициализирует объект цели команды и связывает его с указанным объектом источника команды cmdSource. Он должен быть вызван в реализации класса управления пользователем. При инициализации следует зарегистрировать обработчики команд с объектом исходного кода команды, позвонив в ICommandSource::AddCommandHandler в реализации Initialize. Узнайте, как: Добавьте командную раминю в систему управления windows, чтобы пример того, как использовать инициализацию для этого.

## <a name="see-also"></a>См. также раздел

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Интерфейс ICommandSource](../../mfc/reference/icommandsource-interface.md)
