---
title: Макросы класса Window
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: ca19eba1632ef3754b704c82ad5a872160ae0c91
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834470"
---
# <a name="window-class-macros"></a>Макросы класса Window

Эти макросы определяют служебные программы класса Window.

|Имя|Описание|
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Позволяет указать имя нового класса окна.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Позволяет указать имя нового класса окна и включающий его класс, процедуру окна которого будет использовать новый класс.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Позволяет указать имя существующего класса окна, на котором будет основываться новый класс окна.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Позволяет указать параметры класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a> DECLARE_WND_CLASS

Позволяет указать имя нового класса окна. Поместите этот макрос в класс элемента управления ActiveX ATL.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Параметры

*вндкласснаме*<br/>
окне Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса Window.

### <a name="remarks"></a>Примечания

Если используется параметр компилятора/permissive-, то DECLARE_WND_CLASS вызовет ошибку компилятора; Вместо этого используйте DECLARE_WND_CLASS2.

DECLARE_WND_CLASS позволяет указать имя нового класса окон, данные которого будут управляться с помощью [квндклассинфо](cwndclassinfo-class.md). DECLARE_WND_CLASS определяет новый класс окна, реализуя следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS задает следующие стили для нового окна:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS также указывает цвет фона окна по умолчанию. Используйте макрос [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) для создания собственных стилей и цвета фона.

[Квиндовимпл](cwindowimpl-class.md) использует макрос DECLARE_WND_CLASS для создания окна на основе нового класса окна. Чтобы переопределить это поведение, используйте макрос [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) или предоставьте собственную реализацию функции [жетвндклассинфо](cwindowimpl-class.md#getwndclassinfo) .

Дополнительные сведения об использовании Windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a> DECLARE_WND_CLASS2

(Visual Studio 2017) Аналогичен DECLARE_WND_CLASS, но с дополнительным параметром, который позволяет избежать ошибки зависимого имени при компиляции с параметром/permissive-.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Параметры

*вндкласснаме*<br/>
окне Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса Window.

*енклосингкласс*<br/>
окне Имя класса окна, охватывающего новый класс окна. Не может быть NULL.

### <a name="remarks"></a>Примечания

Если используется параметр/permissive-, то DECLARE_WND_CLASS вызовет ошибку компиляции, так как она содержит зависимое имя. DECLARE_WND_CLASS2 требует явного указания имени класса, в котором используется этот макрос, и не вызывает ошибку в/permissive-флаге.
В противном случае этот макрос идентичен [DECLARE_WND_CLASS](#declare_wnd_class).

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a> DECLARE_WND_SUPERCLASS

Позволяет указать параметры класса. Поместите этот макрос в класс элемента управления ActiveX ATL.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Параметры

*вндкласснаме*<br/>
окне Имя класса окна, который будет суперклассом *оригвндкласснаме*. Если значение равно NULL, ATL создаст имя класса Window.

*оригвндкласснаме*<br/>
окне Имя существующего класса окна.

### <a name="remarks"></a>Примечания

Этот макрос позволяет указать имя класса окна, который будет суперклассом для существующего класса Window. [Квндклассинфо](cwndclassinfo-class.md) управляет сведениями о суперклассе.

DECLARE_WND_SUPERCLASS реализует следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

По умолчанию [квиндовимпл](cwindowimpl-class.md) использует макрос [DECLARE_WND_CLASS](#declare_wnd_class) для создания окна на основе нового класса окна. При указании макроса DECLARE_WND_SUPERCLASS в `CWindowImpl` производном классе класс Window будет основан на существующем классе, но будет использовать процедуру окна. Этот метод называется «подклассом».

Кроме использования макросов DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS, функцию [жетвндклассинфо](cwindowimpl-class.md#getwndclassinfo) можно переопределить собственной реализацией.

Дополнительные сведения об использовании Windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a> DECLARE_WND_CLASS_EX

Позволяет указать имя существующего класса окна, на котором будет основываться новый класс окна. Поместите этот макрос в класс элемента управления ActiveX ATL.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Параметры

*вндкласснаме*<br/>
окне Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса Window.

*style*<br/>
окне Стиль окна.

*Фоновая*<br/>
окне Цвет фона окна.

### <a name="remarks"></a>Примечания

Этот макрос позволяет указать параметры класса нового класса Window, сведения которого будут управляться с помощью [квндклассинфо](cwndclassinfo-class.md). DECLARE_WND_CLASS_EX определяет новый класс окна, реализуя следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Если вы хотите использовать стили и цвет фона по умолчанию, используйте макрос [DECLARE_WND_CLASS](#declare_wnd_class) . Дополнительные сведения об использовании Windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="see-also"></a>См. также раздел

[Макросы](atl-macros.md)
