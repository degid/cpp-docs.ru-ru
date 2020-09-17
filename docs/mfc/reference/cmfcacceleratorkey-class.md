---
title: CMFCAcceleratorKey Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: a814618d3bda27d5b4ace12209dd93343ef2eef9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751782"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey Класс

Класс помощника, который реализует картирование и форматирование виртуальных ключей.

## <a name="syntax"></a>Синтаксис

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Формирует объект `CMFCAcceleratorKey`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCAcceleratorKey::Формат](#format)|Переводит структуру ACCEL на ее визуальное представление.|
|[CMFCAcceleratorKey:SetAccelerator](#setaccelerator)|Устанавливает ключ ярлыка `CMFCAcceleratorKey` для объекта.|

## <a name="remarks"></a>Примечания

Ключи от ускорителя также известны как клавиши ярлыка. Если вы хотите отобразить ярлыки клавиатуры, в которые входит пользователь, то на ключевые клавишные клавиши [CMFCAcceleratorKeyAssignCtrl Class,](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) такие как Alt-Shift-S, можно посмотреть на пользовательский текстовый формат, такой как "Alt и Shift s". Каждый `CMFCAcceleratorKey` объект отображает один ключ от короткого ключа к текстовому формату.

Для получения дополнительной информации о том, как использовать клавиши ярлыка и таблицы акселераторов, [см.](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="example"></a>Пример

В следующем примере показано, `CMFCAcceleratorKey` как построить `Format` объект и как использовать его метод.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Требования

**Заголовок:** afxacceleratorkey.h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey

Строит объект [CMFCAcceleratorKey.](../../mfc/reference/cmfcacceleratorkey-class.md)

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Параметры

*lpAccel*<br/>
(в) Указатель на клавишу ярлыка.

### <a name="remarks"></a>Примечания

Если при создании ключа краткивы `CMFCAccleratorKey`вы не предоставляете, используйте [метод CMFCAcceleratorKey::SetAccelerator](#setaccelerator) для ассоциировать ключ кратки с вашим `CMFCAcceleratorKey` объектом.

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a>CMFCAcceleratorKey::Формат

Преобразует структуру ACCEL в связанное с ней значение строки.

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
(ваут) Ссылка на `CString` объект, где метод пишет переведенный ключ ярлыка.

### <a name="remarks"></a>Примечания

Этот метод получает формат строки связанного ключа ярлыка. Вы можете установить формат строки объекта [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) с помощью либо конструктора, либо метода [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>CMFCAcceleratorKey:SetAccelerator

Устанавливает ключ кратки для объекта [CMFCAcceleratorKey.](../../mfc/reference/cmfcacceleratorkey-class.md)

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Параметры

*lpAccel*<br/>
(в) Указатель на клавишу ярлыка.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы установить ключ ярлыка для того, `CMFCAcceleratorKey` если `CMFCAcceleratorKey`вы не предоставили ключ ярлыка при создании .

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
