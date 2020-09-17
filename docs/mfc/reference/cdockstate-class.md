---
title: Класс CDockState
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 9850486407ee7550ee866a10e656d45ad18fc196
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753257"
---
# <a name="cdockstate-class"></a>Класс CDockState

Сериализуемый класс `CObject` для загрузки, выгрузки или очистки состояния одной или нескольких закрепляемых панелей элементов управления в постоянной памяти (файле).

## <a name="syntax"></a>Синтаксис

```
class CDockState : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDockState::Clear](#clear)|Очищает информацию о состоянии док-станции.|
|[CDockState::GetVersion](#getversion)|Извлекает номер версии состояния сохраненной панели.|
|[CDockState::LoadState](#loadstate)|Извлекает государственную информацию из реестра или . Файл INI.|
|[CDockState::SaveState](#savestate)|Сохраняет сведения о состоянии в реестре или файле INI.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Массив указателей на хранимые сведения о состоянии док-станции с одной записью для каждой панели управления.|

## <a name="remarks"></a>Примечания

Состояние дока включает размер и положение бара и то, состыкован ли он или нет. При извлечении сохраненного `CDockState` состояния доков проверяйте положение панели и, если панель `CDockState` не видна с текущими настройками экрана, масштабирует положение панели так, чтобы она была видна. Основная цель `CDockState` состоит в том, чтобы держать все состояние ряда баров управления и позволить, что состояние будет сохранено и загружено либо в реестр, приложение . Файл INI, или в двоичной форме как часть содержимого `CArchive` объекта.

Бар может быть любой док-бар управления, в том числе панели инструментов, статус бар, или диалог бар. `CDockState`объекты пишутся и читаются или `CArchive` из файла через объект.

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) получает информацию о состоянии всех `CControlBar` объектов окна `CDockState` кадра и помещает ее в объект. Затем можно написать содержимое `CDockState` объекта для хранения с [помощью Serialize](../../mfc/reference/cobject-class.md#serialize) или [CDockState::SaveState](#savestate). Если позже вы хотите восстановить состояние элементов управления в окне `Serialize` кадра, вы можете загрузить состояние с или [CDockState::LoadState](#loadstate), затем использовать [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) для применения сохраненного состояния к барам управления окна кадра.

Для получения дополнительной информации о стыковковых баров управления, [Toolbars: Docking and Floating](../../mfc/docking-and-floating-toolbars.md)см. [Control Bars](../../mfc/control-bars.md) [Frame Windows](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

## <a name="cdockstateclear"></a><a name="clear"></a>CDockState::Clear

Вызов ими функции для очистки `CDockState` всей стыковочного стыковки информации, хранящейся в объекте.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

Это включает в себя не только ли бар состыкован или нет, но размер бара и положение, и является ли он видимым.

## <a name="cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion

Вызов ими функции для получения номера версии состояния сохраненной панели.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Возвращаемое значение

1, если хранимые данные бара старше текущего состояния бара; 2, если сохраненная информация о барной панели такая же, как и текущее состояние бара.

### <a name="remarks"></a>Примечания

Поддержка версии позволяет пересмотренной панели добавлять новые стойкие свойства и по-прежнему быть в состоянии обнаружить и загрузить постоянное состояние, созданное более ранней версией бара.

## <a name="cdockstateloadstate"></a><a name="loadstate"></a>CDockState::LoadState

Вызов эту функцию для получения информации о состоянии из реестра или . Файл INI.

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Указывает на строку с нулевым именем, которая определяет название раздела в файле инициализации или ключ в реестре Windows, где хранится государственная информация.

### <a name="remarks"></a>Примечания

Название профиля — это раздел приложения. Файл INI или реестр, содержащий сведения о состоянии баров. Вы можете сохранить информацию о состоянии панели управления в реестр е или . InI файл `SaveState`с .

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo

Объект, `CPtrArray` являющиеся массивом указателей на сохраненную информацию панели управления для `CDockState` каждой панели управления, сохраненной информацией о состоянии объекта.

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a>CDockState::SaveState

Позвоните в эту функцию, чтобы сохранить государственную информацию в реестр или . Файл INI.

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Указывает на строку с нулевым именем, которая определяет название раздела в файле инициализации или ключ в реестре Windows, где хранится государственная информация.

### <a name="remarks"></a>Примечания

Название профиля — это раздел приложения. Файл INI или реестр, содержащий сведения о состоянии панели управления. `SaveState`также сохраняет текущий размер экрана. Вы можете получить информацию панели управления из реестра или . InI файл `LoadState`с .

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
