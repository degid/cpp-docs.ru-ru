---
title: Доступ к библиотеке типов
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 55d6a56f566416bb25f3ee3ae508c86f17f0df99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840457"
---
# <a name="type-library-access"></a>Доступ к библиотеке типов

Библиотеки типов предоставляют интерфейсы элемента управления OLE другим приложениям, поддерживающим технологию OLE. Каждый элемент управления OLE должен иметь библиотеку типов, если требуется предоставить один или несколько интерфейсов.

Следующие макросы позволяют элементу управления OLE предоставлять доступ к собственной библиотеке типов:

### <a name="type-library-access"></a>Доступ к библиотеке типов

|Имя|Описание|
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет функцию- `GetTypeLib` член элемента управления OLE (должна использоваться в объявлении класса).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует `GetTypeLib` функцию-член элемента управления OLE (должна использоваться в реализации класса).|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a> DECLARE_OLETYPELIB

Объявляет `GetTypeLib` функцию члена класса Control.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, связанного с библиотекой типов.

### <a name="remarks"></a>Примечания

Используйте этот макрос в файле заголовка класса элемента управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a> IMPLEMENT_OLETYPELIB

Реализует `GetTypeLib` функцию элемента элемента управления.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, связанного с библиотекой типов.

*тлид*<br/>
ИДЕНТИФИКАЦИОНный номер библиотеки типов.

*ввермажор*<br/>
Основной номер версии библиотеки типов.

*вверминор*<br/>
Дополнительный номер версии библиотеки типов.

### <a name="remarks"></a>Примечания

Этот макрос должен присутствовать в файле реализации для любого класса элементов управления, использующего макрос DECLARE_OLETYPELIB.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
