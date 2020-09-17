---
title: Глобальные функции контекста устройства
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: d2d25660083f074683a3f42f878497ce14a008b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833469"
---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства

Эта функция создает контекст устройства для данного устройства.

|Имя|Описание|
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a> атлкреатетаржетдк

Создает контекст устройства для устройства, указанного в структуре [двтаржетдевице](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) .

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Параметры

*HDC*<br/>
окне Существующий обработчик контекста устройства или значение NULL.

*ptd*<br/>
окне Указатель на `DVTARGETDEVICE` структуру, содержащую сведения о целевом устройстве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер для контекста устройства для устройства, указанного в `DVTARGETDEVICE` . Если устройство не указано, возвращает маркер в устройство дисплея по умолчанию.

### <a name="remarks"></a>Примечания

Если структура имеет значение NULL и *HDC* имеет значение null, создает контекст устройства для устройства вывода по умолчанию.

Если параметр *HDC* не равен null и *ПТД* имеет значение null, функция возвращает существующий параметр *HDC*.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
