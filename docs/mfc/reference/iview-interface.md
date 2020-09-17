---
title: Интерфейс IView
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: dfe77699a51ad2670c703d02e13e9062e76debcd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751284"
---
# <a name="iview-interface"></a>Интерфейс IView

Реализует несколько методов, используемых [CWinFormsView](../../mfc/reference/cwinformsview-class.md) для отправки уведомлений о представлении в управляемый элемент управления.

## <a name="syntax"></a>Синтаксис

```
interface class IView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Вызывается MFC при активации или отключении представления.|
|[IView::OninitialUpdate](#oninitialupdate)|Вызывается фреймворком после того, как представление сначала прикрепляется к документу, но до отображения представления.|
|[IView::OnUpdate](#onupdate)|Вызвано MFC после того, как документ представления был изменен; эта функция позволяет представлению обновлять свой дисплей, чтобы отразить изменения.|

## <a name="remarks"></a>Примечания

`IView`реализует несколько методов, используемых `CWinFormsView` для переадресовывательных уведомлений общего представления в управляемый элемент управления. Это [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) и [OnActivateView](#onactivateview).

`IView`похож на [CView,](../../mfc/reference/cview-class.md)но используется только с управляемыми представлениями и элементами управления.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="requirements"></a>Требования

Заголовок: afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a>IView::OnActivateView

Вызывается MFC при активации или отключении представления.

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Параметры

*Активировать*<br/>
Указывает, активируется или деактивируется представление.

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::OninitialUpdate

Вызывается фреймворком после того, как представление сначала прикрепляется к документу, но до отображения представления.

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a>IView::OnUpdate

Вызывается MFC после того, как документ представления был изменен.

```cpp
void OnUpdate();
```

## <a name="remarks"></a>Примечания

Эта функция позволяет представлению обновлять свой дисплей, чтобы отразить изменения.

## <a name="see-also"></a>См. также раздел

[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
