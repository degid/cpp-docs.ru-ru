---
title: Использование CSpinButtonCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: 6f72601d3813f36e4a99b9ab04f2e9383c58df94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366485"
---
# <a name="using-cspinbuttonctrl"></a>Использование CSpinButtonCtrl

Управление *кнопкой вращения* (также известное как *вверх-вниз* управления) обеспечивает пару стрелок, которые пользователь может нажать, чтобы настроить значение. Это значение называется *текущим значением.* Положение остается в пределах диапазона кнопки вращения. Когда пользователь щелкает стрелкой вверх, положение перемещается к максимуму; и когда пользователь нажимает вниз стрелка, положение движется к минимуму.

Управление кнопками спина представлено в MFC классом [CSpinButtonCtrl.](../mfc/reference/cspinbuttonctrl-class.md)

> [!NOTE]
> По умолчанию диапазон для кнопки спина имеет максимальный набор до нуля (0) и минимальный набор до 100. Поскольку максимальное значение меньше минимального значения, нажатие на стрелку вверх уменьшает положение и нажатие вниз стрелка увеличивает его. Используйте [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) для корректировки этих значений.

Как правило, текущее положение отображается в управлении компаньона. Управление компаньоном известно как *окно приятеля.* Для иллюстрации управления кнопками спина, [см.](/windows/win32/Controls/up-down-controls)

Чтобы создать элемент управления спином и элементарное управление, в Visual Studio сначала перетащите элемент управления элементом управления в поле или окно диалогов, а затем перетащите элемент управления спином. Выберите спин-контроль и установите его **Auto Buddy** и **установить Бадди Integer** свойства **True.** Также установите свойство **выравнивания;** **Право ели нетипично.** С этими настройками элемент управления отсечения устанавливается как окно "приятель", поскольку оно непосредственно предшествует управлению отсеивательь в порядке вкладки. Управление элементаражаемого элемента отображает ряды, а контроль спина встроен в правую сторону управления правкой. Дополнительно можно установить допустимый диапазон спин-контроля с помощью метода [CSpinButtonCtrl::SetRange.](../mfc/reference/cspinbuttonctrl-class.md#setrange) Обработчики событий не обязаны связываться между управлением спином и окном приятеля, поскольку они обмениваются данными напрямую. Если вы используете элемент управления спином для какой-либо другой цели, например, для того, чтобы просмотреть последовательность окон или диалоговых коробок, добавьте обработчик для сообщения UDN_DELTAPOS и выполните там пользовательские действия.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Стили счетчика](../mfc/spin-button-styles.md)

- [Функции-члены счетчика](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>См. также раздел

[Элементы управления](../mfc/controls-mfc.md)
