---
title: Инициализация OLE
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 13c267df492ab86606e893df4c13e5510e6e546a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843694"
---
# <a name="ole-initialization"></a>Инициализация OLE

Прежде чем приложение сможет использовать системные службы OLE, оно должно инициализировать системные библиотеки DLL OLE и убедиться, что библиотеки DLL имеют правильную версию. `AfxOleInit`Функция инициализирует системные DLL-библиотеки OLE.

### <a name="ole-initialization"></a>Инициализация OLE

|Имя|Описание|
|-|-|
|[AfxOleInit](#afxoleinit)|Инициализирует библиотеки OLE.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Вызовите эту функцию в функции объекта приложения `InitInstance` , чтобы обеспечить поддержку включения элементов управления OLE.|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a> афксенаблеконтролконтаинер

Вызовите эту функцию в функции объекта приложения `InitInstance` , чтобы обеспечить поддержку включения элементов управления OLE.

### <a name="syntax"></a>Синтаксис

```cpp
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения об элементах управления OLE (которые теперь называются элементами управления ActiveX) см. в [разделах элементы управления ActiveX](../mfc-activex-controls.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="afxoleinit"></a><a name="afxoleinit"></a> афксолеинит

Инициализирует поддержку OLE для приложения.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; 0, если инициализация не удалась, возможно, установлены неверные версии системных библиотек OLE.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы инициализировать поддержку OLE для приложения MFC. При вызове этой функции выполняются следующие действия.

- Инициализирует библиотеку COM в текущем апартаменте вызывающего приложения. Дополнительные сведения см. в разделе [олеинитиализе](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- Создает объект фильтра сообщений, реализуя интерфейс [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) . Доступ к этому фильтру сообщений можно получить с помощью вызова [афксолежетмессажефилтер](application-control.md#afxolegetmessagefilter).

> [!NOTE]
> Если **афксолеинит** вызывается из библиотеки DLL MFC, вызов завершится ошибкой. Сбой происходит из-за того, что функция предполагает, что, если она вызывается из библиотеки DLL, система OLE была ранее инициализирована вызывающим приложением.

> [!NOTE]
> Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в `InitInstance` переопределении укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
