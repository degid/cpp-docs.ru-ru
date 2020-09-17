---
title: Класс CSimpleДиалог
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 345372d71ad96a74bb0ae6dd7e89bdf0724cd822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330831"
---
# <a name="csimpledialog-class"></a>Класс CSimpleДиалог

Этот класс реализует базовый модульный диалоговый ящик.

## <a name="syntax"></a>Синтаксис

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>Параметры

*t_wDlgTemplateID*

Идентификатор ресурса ресурса шаблона диалога.

*t_bCenter*<br/>
TRUE, если объект диалога должен быть сосредоточен на окне владельца; в противном случае FALSE.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleДиалог::DoModal](#domodal)|Создает модальный диалоговый ящик.|

## <a name="remarks"></a>Примечания

Реализует модальный диалоговый ящик с основной функциональностью. `CSimpleDialog`обеспечивает поддержку только общих элементов управления Windows. Чтобы создать и отобразить модульное диалоговое окно, создайте экземпляр этого класса, предоставляющий название существующего шаблона ресурсов для диалогового окна. Объект поле диалога закрывается, когда пользователь нажимает на любой элемент управления с заранее определенным значением (например, IDOK или IDCANCEL).

`CSimpleDialog`позволяет создавать только модальные диалоговые ящики. `CSimpleDialog`обеспечивает процедуру диалогового окна, которая использует карту сообщений по умолчанию для направления сообщений соответствующим обработчикам.

Дополнительную информацию можно узнать о [приведении в ней dialog Box.](../../atl/implementing-a-dialog-box.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a>CSimpleДиалог::DoModal

Вызывает модульный диалоговый ящик и возвращает результат диалогового ящика при этом.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Ручка для родительского окна диалога. Если значение не предусмотрено, родительский должен быть установлен в текущее активное окно.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха значение возврата — это идентификатор ресурсов элемента управления, который отклонил диалоговую коробку.

Если функция выходит из строя, значение возврата -1. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

Этот метод обрабатывает все взаимодействие с пользователем в то время как диалоговые окна активны. Это то, что делает диалоговую коробку модальной; то есть пользователь не может взаимодействовать с другими окнами до тех пор, пока диалоговая шкатулка не будет закрыта.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
