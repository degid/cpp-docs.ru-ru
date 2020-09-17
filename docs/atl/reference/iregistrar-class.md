---
title: Интерфейс IRegistrar
ms.date: 02/01/2017
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 98943fe294322715723bd91207a6f3320ca1ffb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329464"
---
# <a name="iregistrar-interface"></a>Интерфейс IRegistrar

Этот интерфейс определяется в atliface.h и используется внутренне функциями членов CAtlModule, такими как [UpdateRegistryFromResourceD.](catlmodule-class.md#updateregistryfromresourced)

## <a name="syntax"></a>Синтаксис

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Примечания

Более подробная информация приводиткся в [теме «Использование сменных параметров » (Препроцессор регистратора).](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Регистрирует ресурс. |
|[IRegistrar::РесурсUnregisterSz](#resourceunregistersz)| Отменить регистрацию ресурса.|
|[IRegistrar::FileRegister](#fileregister)|Регистрирует файл.|
|[IRegistrar:FileUnregister](#fileunregister)|Отменить регистрацию файла.|
|[IRegistrar::StringRegister](#stringregister)|Регистрирует строку.|
|[IRegistrar::StringUnregister](#stringunregister)|Отменить регистрацию строки|
|[IRegistrar::Источник](#resourceregister)|Регистрирует ресурс.|
|[IRegistrar::РесурсНерегистр](#resourceunregister)|Отменить регистрацию ресурса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlifase.h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz

Регистрирует ресурс.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>IRegistrar::РесурсUnregisterSz

Отменить регистрацию ресурса.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a>IRegistrar::FileRegister

Регистрирует файл.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a>IRegistrar:FileUnregister

Отменить регистрацию файла.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a>IRegistrar::StringRegister

Регистрирует указанные строки данных.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a>IRegistrar::StringUnregister

Не регистрирует указанные строки данных.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a>IRegistrar::Источник

Регистрирует ресурс.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a>IRegistrar::РесурсНерегистр

Отменить регистрацию ресурса.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>См. также раздел

[Использование заменяемых параметров (Препроцессор регистратора)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)<br/>
[Компонент реестра (регистратор)](../../atl/atl-registry-component-registrar.md)
