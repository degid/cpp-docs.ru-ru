---
title: Структура _ATL_BASE_MODULE70
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 3893e4ce4fcd24f48d9e981ad24505f82dc98833
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168648"
---
# <a name="_atl_base_module70-structure"></a>Структура _ATL_BASE_MODULE70

Используется любым проектом, использующим ATL.

## <a name="syntax"></a>Синтаксис

```cpp
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```

## <a name="members"></a>Участники

`cbSize`<br/>
Размер структуры, используемый для управления версиями.

`m_hInst`<br/>
`hInstance` Для этого модуля (exe или DLL).

`m_hInstResource`<br/>
Обработчик ресурсов экземпляра по умолчанию.

`m_bNT5orWin98`<br/>
Сведения о версии операционной системы. Используется внутренне библиотекой ATL.

`dwAtlBuildVer`<br/>
Хранит версию ATL. В настоящее время 0x0700.

`pguidVer`<br/>
Внутренний идентификатор GUID ATL.

`m_csResource`<br/>
Используется для синхронизации доступа к `m_rgResourceInstance` массиву. Используется внутренне библиотекой ATL.

`m_rgResourceInstance`<br/>
Массив, используемый для поиска ресурсов во всех экземплярах ресурсов, в которых учитывается ATL. Используется внутренне библиотекой ATL.

## <a name="remarks"></a>Примечания

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) определяется как typedef _ATL_BASE_MODULE70.

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
