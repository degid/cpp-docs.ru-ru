---
title: Интерфейс Идочостуихандлердиспатч
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: 4d80934a5768eda917c90345ddeeff017edf0eae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835445"
---
# <a name="idochostuihandlerdispatch-interface"></a>Интерфейс Идочостуихандлердиспатч

Интерфейс для механизма анализа и подготовки отчетов в формате HTML (Майкрософт).

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

> [!NOTE]
> Ссылки в следующей таблице относятся к справочным разделам пакета SDK INet для членов интерфейса [идокуихоссандлер](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) . `IDocHostUIHandlerDispatch` функция имеет те же функциональные возможности, что и, в отличие от того, `IDocUIHostHandler` что является disp-интерфейсом, в `IDocHostUIHandlerDispatch` то время как `IDocUIHostHandler` является настраиваемым.

|Имя|Описание|
|-|-|
|[енаблемоделесс](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|Вызывается из MSHTML реализации [метода IOleInPlaceActiveObject:: енаблемоделесс](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Также вызывается, когда MSHTML отображает модальный пользовательский интерфейс.|
|[филтердатаобжект](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Вызывается на узле MSHTML для того, чтобы разрешить узлу заменить объект данных MSHTML.|
|[жетдроптаржет](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Вызывается MSHTML, когда используется в качестве цели перетаскивания, чтобы позволить узлу предоставить альтернативный [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget).|
|[Внешний](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Вызывается MSHTML для получения интерфейса IDispatch узла.|
|[жесостинфо](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|Получает возможности пользовательского интерфейса узла MSHTML.|
|[жетоптионкэйпас](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|Возвращает раздел реестра, в котором MSHTML хранит настройки пользователя.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|Вызывается, когда MSHTML удаляет свои меню и панели инструментов.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|Вызывается из MSHTML реализации [метода IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|Вызывается из MSHTML реализации [метода IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|Вызывается из MSHTML реализации [метода IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Вызывается из MSHTML для вывода контекстного меню.|
|[Параметра showUI задано](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Позволяет узлу заменять меню и панели инструментов MSHTML.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|Вызывается MSHTML при вызове [метода IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) или [IOleControlSite:: TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) .|
|[транслатеурл](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Вызывается MSHTML, чтобы разрешить узлу изменять URL-адрес для загрузки.|
|[упдатеуи](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Уведомляет основное приложение об изменении состояния команды.|

## <a name="remarks"></a>Примечания

Узел может заменить меню, панели инструментов и контекстные меню, используемые модулем синтаксического анализа и визуализации Microsoft HTML (MSHTML), путем реализации этого интерфейса.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|Описана. idl|
|C++|Описана.h (также входит в ATLBase.h)|

## <a name="see-also"></a>См. также раздел

[идокуихоссандлер](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
