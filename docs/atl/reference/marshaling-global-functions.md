---
title: Маршалирование глобальных функций
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: 79b19b613fbae49c0f8338dcadd2225e092fb371
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835328"
---
# <a name="marshaling-global-functions"></a>Маршалирование глобальных функций

Эти функции обеспечивают поддержку упаковки и преобразования данных маршалирования в указатели интерфейса.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Освобождает данные маршалирования и `IStream` указатель.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Создает новый объект Stream и маршалирует указанный указатель интерфейса.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Преобразует данные маршалирования потока в указатель интерфейса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a> атлфримаршалстреам

Освобождает данные маршалинга в потоке, затем освобождает указатель потока.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на `IStream` интерфейс в потоке, используемый для маршалирования.

### <a name="example"></a>Пример

См. пример для [атлмаршалптринпрок](#atlmarshalptrinproc).

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a> атлмаршалптринпрок

Создает новый объект потока, записывает в поток CLSID прокси-сервера и маршалирует заданный указатель интерфейса, записывая в поток данные, необходимые для инициализации прокси-сервера.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на интерфейс, который необходимо маршалировать.

*IID*<br/>
окне Идентификатор GUID для упакованного интерфейса.

*ппстреам*<br/>
заполняет Указатель на `IStream` интерфейс нового объекта потока, используемого для маршалирования.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Флаг MSHLFLAGS_TABLESTRONG установлен таким образом, чтобы можно было маршалировать указатель на несколько потоков. Указатель также можно распаковать несколько раз.

Если упаковка завершается неудачей, указатель потока освобождается.

`AtlMarshalPtrInProc` может использоваться только для указателя на внутрипроцессный объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a> атлунмаршалптр

Преобразует данные маршалинга потока в указатель интерфейса, который может использоваться клиентом.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на неупакованный поток.

*IID*<br/>
окне Идентификатор GUID для неупакованного интерфейса.

*ппунк*<br/>
заполняет Указатель на неупакованный интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

См. пример для [атлмаршалптринпрок](#atlmarshalptrinproc).

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
