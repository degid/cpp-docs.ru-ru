---
title: Макросы обмена данными в реестре
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 507db77b525c526fe1cd47c7d75c34e15a6a0628
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834548"
---
# <a name="registry-data-exchange-macros"></a>Макросы обмена данными в реестре

Эти макросы выполняют операции обмена данными в реестре.

|Имя|Описание|
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Помечает начало схемы обмена данными реестра.|
|[END_RDX_MAP](#end_rdx_map)|Отмечает конец схемы обмена данными реестра.|
|[RDX_BINARY](#rdx_binary)|Связывает указанную запись реестра с заданной переменной-членом типа BYTE.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанную запись реестра с указанной переменной-членом типа CString.|
|[RDX_DWORD](#rdx_dword)|Связывает указанную запись реестра с указанной переменной-членом типа DWORD.|
|[RDX_TEXT](#rdx_text)|Связывает указанную запись реестра с указанной переменной-членом типа TCHAR.|

## <a name="requirements"></a>Требования

**Заголовок:** атлплус.h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a> BEGIN_RDX_MAP

Помечает начало схемы обмена данными реестра.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Примечания

Следующие макросы используются в схеме обмена данными реестра для чтения и записи записей в системном реестре:

|Макрос|Описание|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Связывает указанную запись реестра с заданной переменной-членом типа BYTE.|
|[RDX_DWORD](#rdx_dword)|Связывает указанную запись реестра с указанной переменной-членом типа DWORD.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанную запись реестра с указанной переменной-членом типа CString.|
|[RDX_TEXT](#rdx_text)|Связывает указанную запись реестра с указанной переменной-членом типа TCHAR.|

Глобальная функция [регистридатаексчанже](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)или функция с тем же именем, создаваемая макросами BEGIN_RDX_MAP и END_RDX_MAP, следует использовать всякий раз, когда код должен обмениваться данными между системным реестром и переменными, указанными в сопоставлении RDX.

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a> END_RDX_MAP

Отмечает конец схемы обмена данными реестра.

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a> RDX_BINARY

Связывает указанную запись реестра с заданной переменной-членом типа BYTE.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*руткэй*<br/>
Корневой раздел реестра.

*вложен*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*участниками*<br/>
Переменная члена, связываемая с указанной записью реестра.

*member_size*<br/>
Размер переменной члена в байтах.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP, чтобы связать переменную-член с заданной записью реестра. Глобальная функция [регистридатаексчанже](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)или функция члена с тем же именем, созданная с помощью макросов BEGIN_RDX_MAP и END_RDX_MAP, должны использоваться для обмена данными между системным реестром и переменными членов в сопоставлении RDX.

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a> RDX_CSTRING_TEXT

Связывает указанную запись реестра с указанной переменной-членом типа CString.

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*руткэй*<br/>
Корневой раздел реестра.

*вложен*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*участниками*<br/>
Переменная члена, связываемая с указанной записью реестра.

*member_size*<br/>
Размер переменной члена в байтах.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP, чтобы связать переменную-член с заданной записью реестра. Глобальная функция [регистридатаексчанже](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)или функция члена с тем же именем, созданная с помощью макросов BEGIN_RDX_MAP и END_RDX_MAP, должны использоваться для обмена данными между системным реестром и переменными членов в сопоставлении RDX.

## <a name="rdx_dword"></a><a name="rdx_dword"></a> RDX_DWORD

Связывает указанную запись реестра с указанной переменной-членом типа DWORD.

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*руткэй*<br/>
Корневой раздел реестра.

*вложен*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*участниками*<br/>
Переменная члена, связываемая с указанной записью реестра.

*member_size*<br/>
Размер переменной члена в байтах.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP, чтобы связать переменную-член с заданной записью реестра. Глобальная функция [регистридатаексчанже](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)или функция члена с тем же именем, созданная с помощью макросов BEGIN_RDX_MAP и END_RDX_MAP, должны использоваться для обмена данными между системным реестром и переменными членов в сопоставлении RDX.

## <a name="rdx_text"></a><a name="rdx_text"></a> RDX_TEXT

Связывает указанную запись реестра с указанной переменной-членом типа TCHAR.

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*руткэй*<br/>
Корневой раздел реестра.

*вложен*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*участниками*<br/>
Переменная члена, связываемая с указанной записью реестра.

*member_size*<br/>
Размер переменной члена в байтах.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP, чтобы связать переменную-член с заданной записью реестра. Глобальная функция [регистридатаексчанже](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)или функция члена с тем же именем, созданная с помощью макросов BEGIN_RDX_MAP и END_RDX_MAP, должны использоваться для обмена данными между системным реестром и переменными членов в сопоставлении RDX.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
