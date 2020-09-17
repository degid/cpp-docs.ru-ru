---
title: Реализация диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 7866afd26c901181f2b4193a87daf5dca2b0c67f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226689"
---
# <a name="implementing-a-dialog-box"></a>Реализация диалогового окна

Существует два способа добавления диалогового окна в проект ATL: Используйте мастер диалогового окна ATL или добавьте его вручную.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Добавление диалогового окна с помощью мастера диалогового окна ATL

В [диалоговом окне Добавление класса](../ide/add-class-dialog-box.md)выберите объект диалогового окна ATL, чтобы добавить диалоговое окно в проект ATL. Заполните мастер диалоговых окон ATL соответствующим образом и нажмите кнопку **Готово**. Мастер добавляет класс, производный от [каксдиалогимпл](../atl/reference/caxdialogimpl-class.md) , к проекту. Откройте **представление ресурсов** в меню **вид** , выберите диалоговое окно и дважды щелкните его, чтобы открыть в редакторе ресурсов.

> [!NOTE]
> Если диалоговое окно является производным от `CAxDialogImpl` , в нем могут размещаться элементы управления ActiveX и Windows. Если вы не хотите издержки в поддержке элементов управления ActiveX в классе диалогового окна, используйте вместо него [ксимпледиалог](../atl/reference/csimpledialog-class.md) или [CDialogImpl](../atl/reference/cdialogimpl-class.md) .

Обработчики сообщений и событий можно добавлять в класс диалогового окна из представление классов. Дополнительные сведения см. в разделе [Добавление обработчика сообщений ATL](../atl/adding-an-atl-message-handler.md).

## <a name="adding-a-dialog-box-manually"></a>Добавление диалогового окна вручную

Реализация диалогового окна аналогична реализации окна. Класс является производным от [каксдиалогимпл](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md)или [ксимпледиалог](../atl/reference/csimpledialog-class.md) и объявляет [схему сообщений](../atl/message-maps-atl.md) для работы с сообщениями. Однако необходимо также указать идентификатор ресурса шаблона диалогового окна в производном классе. Для хранения этого значения классу должен быть вызван член данных `IDD` .

> [!NOTE]
> При создании диалогового окна с помощью мастера диалоговых окон ATL мастер автоматически добавляет член в `IDD` качестве **`enum`** типа.

`CDialogImpl`позволяет реализовать модальное или немодальное диалоговое окно, в котором размещаются элементы управления Windows. `CAxDialogImpl`позволяет реализовать модальное или немодальное диалоговое окно, в котором размещаются элементы управления ActiveX и Windows.

Чтобы создать модальное диалоговое окно, создайте экземпляр класса, `CDialogImpl` производного от (или `CAxDialogImpl` производного), а затем вызовите метод [DoModal](../atl/reference/cdialogimpl-class.md#domodal) . Чтобы закрыть модальное диалоговое окно, вызовите метод [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) из обработчика сообщений. Чтобы создать немодальное диалоговое окно, вызовите метод [CREATE](../atl/reference/cdialogimpl-class.md#create) вместо `DoModal` . Чтобы уничтожить немодальное диалоговое окно, вызовите [дестройвиндов](../atl/reference/cdialogimpl-class.md#destroywindow).

События-приемники автоматически выполняются в [каксдиалогимпл](../atl/reference/caxdialogimpl-class.md). Реализуйте обработчики сообщений диалогового окна, как и обработчики в `CWindowImpl` производном классе. При наличии возвращаемого значения, возвращающего сообщения, верните его как `LRESULT` . Возвращенные `LRESULT` значения сопоставляются с библиотекой ATL для правильной обработки с помощью диспетчера диалоговых окон Windows. Дополнительные сведения см. в исходном коде для [кдиалогимплбасет::D иалогпрок](../atl/reference/cdialogimpl-class.md#dialogproc) в atlwin.h.

## <a name="example"></a>Пример

В следующем классе реализуется диалоговое окно:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>См. также статью

[Классы окон](../atl/atl-window-classes.md)
