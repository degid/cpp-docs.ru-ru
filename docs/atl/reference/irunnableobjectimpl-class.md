---
title: IRunnableПредметImpl класс
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 2843c0c25a5c104ffbdff72255ac5d85cf53b1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329444"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableПредметImpl класс

Этот класс `IUnknown` реализует и обеспечивает реализацию интерфейса [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) по умолчанию.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IRunnableObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Возвращает CLSID управления. Реализация ATL устанавливает CLSID для GUID_NULL и возвращает E_UNEXPECTED.|
|[IRunnableObjectImpl::Исранж](#isrunning)|Определяет, работает ли элемент управления. Реализация ATL возвращает TRUE.|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Блокировка элемента управления в запущенное состояние. Реализация ATL возвращает S_OK.|
|[IRunnableObjectImpl::Run](#run)|Заставляет контроль бежать. Реализация ATL возвращает S_OK.|
|[IRunnableObjectImpl::SetContainedПредмет](#setcontainedobject)|Означает, что элемент управления встроен. Реализация ATL возвращает S_OK.|

## <a name="remarks"></a>Примечания

Интерфейс [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) позволяет контейнеру определить, работает ли элемент управления, заставить его запуститься или заблокировать его в запущенном состоянии. Класс `IRunnableObjectImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass

Возвращает CLSID управления.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL \* устанавливает *lpClsid* для GUID_NULL и возвращает E_UNEXPECTED.

### <a name="remarks"></a>Примечания

Смотрите [IRunnableObject::GetRunningClass](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) в Windows SDK.

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a>IRunnableObjectImpl::Исранж

Определяет, работает ли элемент управления.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL возвращает TRUE.

### <a name="remarks"></a>Примечания

Смотрите [IRunnableObject::Бег в](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) Windows SDK.

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>IRunnableObjectImpl::LockRunning

Блокировка элемента управления в запущенное состояние.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IRunnableObject::LockRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) в Windows SDK.

## <a name="irunnableobjectimplrun"></a><a name="run"></a>IRunnableObjectImpl::Run

Заставляет контроль бежать.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IRunnableObject::Запуск](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) в Windows SDK.

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedПредмет

Означает, что элемент управления встроен.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IRunnableObject::SetContainedПредмет](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
