---
title: Класс CMenu
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: 5ec97d8cf039034078f29b38fb6a41d6ff9a5e53
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369984"
---
# <a name="cmenu-class"></a>Класс CMenu

Инкапсуляция `HMENU`Windows.

## <a name="syntax"></a>Синтаксис

```
class CMenu : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|Формирует объект `CMenu`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Приложения новый пункт в конце этого меню.|
|[CMenu::Attach](#attach)|Прикрепляет ручку меню `CMenu` Windows к объекту.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Разместите галочку рядом или удалите галочку из пункта меню во всплывающем меню.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Разместите кнопку радио рядом с пунктом меню и удалите кнопку радио из всех других пунктов меню в группе.|
|[CMenu::CreateMenu](#createmenu)|Создает пустое меню и прикрепляет его к объекту. `CMenu`|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Создает пустое всплывающее меню и прикрепляет его к объекту. `CMenu`|
|[CMenu::DeleteMenu](#deletemenu)|Удаляет указанный элемент из меню. Если элемент меню имеет связанное всплывающее меню, разрушает ручку всплывающее меню и освобождает память, используемую им.|
|[CMenu::DeleteTempMap](#deletetempmap)|Удаляет все `CMenu` временные объекты, созданные функцией `FromHandle` участника.|
|[CMenu::DestroyMenu](#destroymenu)|Разрушает меню, прикрепленное `CMenu` к объекту, и освобождает любую память, занятую в меню.|
|[CMenu::Detach](#detach)|Отсоединяет ручку меню Windows `CMenu` от объекта и возвращает ручку.|
|[CMenu::DrawItem](#drawitem)|Вызывается в рамках, когда визуальный аспект нарисованного владельцем меню изменяется.|
|[CMenu::EnableMenuItem](#enablemenuitem)|Включает, отменяет или тускнеет (серый) элемент меню.|
|[CMenu::FromHandle](#fromhandle)|Возвращает указатель объекту `CMenu` с ручкой меню Windows.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Определяет элемент меню по умолчанию в указанном меню.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Извлекает идентификатор контекста справки, связанный с меню.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Извлекает информацию в определенном меню.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Определяет количество элементов в всплывающем или верхнем меню.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Получает идентификатор меню-элемент аподням меню для элемента меню, расположенного в указанном положении.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Извлекает информацию о пункте меню.|
|[CMenu::GetMenuState](#getmenustate)|Возвращает состояние указанного элемента меню или количество элементов во всплывающем меню.|
|[CMenu::GetMenuString](#getmenustring)|Извлекает метку указанного элемента меню.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Возвращает `m_hMenu` завернутый `CMenu` этим объектом.|
|[CMenu::GetSubMenu](#getsubmenu)|Извлекает указатель на всплывающее меню.|
|[CMenu::InsertMenu](#insertmenu)|Вставляет новый элемент меню в указанном положении, перемещая другие элементы вниз по меню.|
|[CMenu::InsertMenuItem](#insertmenuitem)|Вставляет новый пункт меню в указанном положении в меню.|
|[CMenu::LoadMenu](#loadmenu)|Загружает ресурс меню из исполняемого файла `CMenu` и прикрепляет его к объекту.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Загружает меню из шаблона меню в `CMenu` памяти и прикрепляет его к объекту.|
|[CMenu::MeasureItem](#measureitem)|Вызывается в рамках, чтобы определить размеры меню при создании нарисованного владельцем меню.|
|[CMenu::ModifyMenu](#modifymenu)|Изменяет существующий элемент меню в указанном положении.|
|[CMenu::RemoveMenu](#removemenu)|Удаляет элемент меню с соответствующим всплывающее меню из указанного меню.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Устанавливает элемент меню по умолчанию для указанного меню.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Устанавливает идентификатор контекста справки, связанный с меню.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Устанавливает информацию в определенном меню.|
|[CMenu::SetMenuBitmaps](#setmenuitembitmaps)|Связывает указанные галочно-меткиные карты с пунктом меню.|
|[CMenu::SetMenu.](#setmenuiteminfo)|Изменяет информацию о пункте меню.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Отображает плавающее всплывающее меню в указанном месте и отслеживает выбор элементов в всплывающем меню.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Отображает плавающее всплывающее меню в указанном месте и отслеживает выбор элементов в всплывающем меню.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CMenu:оператор HMENU](#operator_hmenu)|Извлекает ручку объекта меню.|
|[CMenu::оператор !](#operator_neq)|Определяет, не равны ли двум объектам меню.|
|[CMenu::оператор](#operator_eq_eq)|Определяет, являются ли два объекта меню равными.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|Определяет ручку в меню Windows, прикрепленную `CMenu` к объекту.|

## <a name="remarks"></a>Примечания

Он предоставляет функции членов для создания, отслеживания, обновления и уничтожения меню.

Создайте `CMenu` объект на кадре стека в `CMenu`качестве локального, а затем вызовите функции члена,для управления новым меню по мере необходимости. Далее звоните [cWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) для установки меню в окно, `CMenu` а затем немедленно вызов в функцию члена элемента [отсеиваемости](#detach) объекта. Функция `CWnd::SetMenu` участника устанавливает меню окна в новое меню, приводит к перерисовке окна, чтобы отразить изменение меню, а также передает право собственности на меню в окно. Призыв `Detach` отсеять HMENU от `CMenu` объекта, так что, когда локальная `CMenu` `CMenu` переменная выходит за рамки, разрушаемый объект не пытается уничтожить меню, которым он больше не владеет. Само меню автоматически уничтожается при разрушении окна.

Функцию члена [LoadMenuIndirect](#loadmenuindirect) можно использовать для создания меню из шаблона в памяти, но меню, созданное из ресурса по вызову [в LoadMenu,](#loadmenu) легче поддерживаться, а сам ресурс меню может быть создан и изменен редактором меню.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmenuappendmenu"></a><a name="appendmenu"></a>CMenu::AppendMenu

Приложения к новому элементу к концу меню.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nФлаги*<br/>
При добавлении в меню указывается информация о состоянии нового пункта меню. Он состоит из одного или нескольких значений, перечисленных в разделе Замечания.

*nIDNewItem*<br/>
Упоняет либо идентификатор команды нового элемента меню, либо, `HMENU`если *nFlags* установлен на MF_POPUP, ручка меню () всплывающее меню. Параметр *nIDNewItem* игнорируется (не требуется), если *nFlags* установлен на MF_SEPARATOR.

*lpszNewItem*<br/>
Определяет содержание нового пункта меню. Параметр *nFlags* используется для интерпретации *lpszNewItem* следующим образом:

|nФлаги|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-битное значение, поставляемое приложением для поддержания дополнительных данных, связанных с пунктом меню. Это 32-битное значение доступно приложению при обработке WM_MEASUREITEM и WM_DRAWITEM сообщений. Значение хранится в `itemData` составе структуры, поставляемой с этими сообщениями.|
|MF_STRING|Содержит указатель на нулевую строку. Это интерпретация по умолчанию.|
|MF_SEPARATOR|Параметр *lpszNewItem* игнорируется (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение может указать состояние элемента меню, установив значения в *nFlags*. Когда *nIDNewItem* определяет всплывающее меню, оно становится частью меню, к которому оно приложено. Если это меню будет уничтожено, придативное меню также будет уничтожено. Придативное меню `CMenu` должно быть отделено от объекта, чтобы избежать конфликта. Обратите внимание, что MF_STRING и MF_OWNERDRAW не `AppendMenu`действительны для версии bitmap .

В следующем списке описаны флаги, которые могут быть установлены в *nFlags:*

- MF_CHECKED действует как переключатель с MF_UNCHECKED, чтобы разместить галочку по умолчанию рядом с пунктом. Когда приложение поставляет галочку bitmaps (см. функцию члена [SetMenuItemBitmaps),](#setmenuitembitmaps) отображается биткарта "проверка".

- MF_UNCHECKED действует как переключатель с MF_CHECKED, чтобы удалить контрольный знак рядом с пунктом. Когда приложение поставляет галочку bitmaps (см. `SetMenuItemBitmaps` функцию члена), отображается бит-карта "проверить отметку".

- MF_DISABLED отменяет элемент меню так, чтобы он не мог быть выбран, но не тускнеет его.

- MF_ENABLED включает элемент меню, чтобы он мог быть выбран, и восстанавливает его из затемненного состояния.

- MF_GRAYED отстраняет элемент меню так, что он не может быть выбран и затемняет его.

- MF_MENUBARBREAK помещает элемент в новую строку в статическое меню или в новую колонку во всплывающих меню. Новая всплывающая колонка меню будет отделена от старой колонки вертикальной разделительной линией.

- MF_MENUBREAK помещает элемент в новую строку в статическое меню или в новую колонку во всплывающих меню. Между колоннами не помещается разделительная линия.

- MF_OWNERDRAW указывает, что товар является элементом, нарисовав владельцем. Когда меню отображается в первый раз, окно, которому принадлежит меню, получает WM_MEASUREITEM сообщение, которое получает высоту и ширину элемента меню. Сообщение WM_DRAWITEM — это сообщение, отправленное всякий раз, когда владелец должен обновить внешний вид элемента меню. Эта опция не действительна для элемента меню верхнего уровня.

- MF_POPUP указывает, что элемент меню имеет всплывающее меню, связанное с ним. Параметр идентификатора определяет ручку к всплывающем меню, которое должно быть связано с элементом. Это используется для добавления либо всплывающее меню верхнего уровня, либо иерархического всплывающее меню к элементу всплывающих меню.

- MF_SEPARATOR рисует горизонтальную разделительную линию. Может быть использован только во всплывающем меню. Эта строка не может быть затемнена, отключена или выделена. Другие параметры игнорируются.

- MF_STRING указывает, что элемент меню является строкой символов.

Каждая из следующих групп перечисляет флаги, которые являются взаимоисключающими и не могут использоваться вместе:

- MF_DISABLED, MF_ENABLED и MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR и версия биткарта

- MF_MENUBARBREAK и MF_MENUBREAK

- MF_CHECKED и MF_UNCHECKED

Всякий раз, когда меню, которое находится в окне, изменяется (независимо от того, отображается окно или нет), приложение должно вызывать [CWnd::DrawMenuBar.](../../mfc/reference/cwnd-class.md#drawmenubar)

### <a name="example"></a>Пример

  Смотрите пример [cMenu::CreateMenu](#createmenu).

## <a name="cmenuattach"></a><a name="attach"></a>CMenu::Attach

Прикрепляет существующее меню `CMenu` Windows к объекту.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Упоняет ручку в меню Windows.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция не должна вызываться, если меню `CMenu` уже прикреплено к объекту. Ручка меню хранится `m_hMenu` в элементе данных.

Если меню, которым вы хотите манипулировать, уже связано с окном, вы можете использовать функцию [CWnd::GetMenu,](../../mfc/reference/cwnd-class.md#getmenu) чтобы получить ручку в меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenucheckmenuitem"></a><a name="checkmenuitem"></a>CMenu::CheckMenuItem

Добавляет контрольные отметки или удаляет контрольные отметки из пунктов меню во всплывающем меню.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Параметры

*nIDCheckItem*<br/>
Определяйте элемент меню, который должен быть проверен, как это определено *nCheck*.

*Nпроверьте*<br/>
Определите, как проверить элемент меню и как определить положение элемента в меню. Параметр *nCheck* может быть комбинацией MF_CHECKED или MF_UNCHECKED с MF_BYPOSITION или MF_BYCOMMAND флагами. Эти флаги могут быть объединены с помощью bitwise или оператора. Они имеют следующие значения:

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.

- MF_CHECKED действует как переключатель с MF_UNCHECKED, чтобы разместить галочку по умолчанию рядом с пунктом.

- MF_UNCHECKED действует как переключатель с MF_CHECKED, чтобы удалить контрольный знак рядом с пунктом.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние элемента: MF_CHECKED или MF_UNCHECKED, или 0xFFFFFF, если пункт меню не существует.

### <a name="remarks"></a>Примечания

Параметр *nIDCheckItem* определяет элемент, который будет изменен.

Параметр *nIDCheckItem* может определить всплывающий пункт меню, а также элемент меню. Для проверки всплывающем элемента меню не требуется никаких специальных шагов. Элементы меню верхнего уровня не могут быть проверены. Элемент всплывающих меню должен быть проверен по позициям, так как у него нет связанного с ним идентификатора меню-элемента.

### <a name="example"></a>Пример

  Смотрите пример [CMenu::GetMenuState](#getmenustate).

## <a name="cmenucheckmenuradioitem"></a><a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem

Проверяет указанный элемент меню и делает его элементом радио.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nIDПервый*<br/>
Определяет (в виде идентификатора или смещения, в зависимости от значения *nFlags)* первый пункт меню в группе радиокнопок.

*nIDLast*<br/>
Определяет (в виде идентификатора или смещения, в зависимости от значения *nFlags)* последний элемент меню в группе радиокнопок.

*nIDItem*<br/>
Определяет (в качестве идентификатора или смещения, в зависимости от значения *nFlags)* элемент в группе, который будет проверен с помощью кнопки радио.

*nФлаги*<br/>
Определяет интерпретацию *nIDFirst,* *nIDLast*и *nIDItem* следующим образом:

|nФлаги|Интерпретация|
|------------|--------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае 0

### <a name="remarks"></a>Примечания

В то же время функция отсеивает все остальные элементы меню в связанной группе и очищает флаг типа радиоэлемента для этих элементов. Проверенный элемент отображается с помощью радиокнопки (или пули) bitmap вместо битовой карты чековой отметки.

### <a name="example"></a>Пример

  Смотрите пример [для ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).

## <a name="cmenucmenu"></a><a name="cmenu"></a>CMenu::CMenu

Создает пустое меню и прикрепляет его к объекту. `CMenu`

```
CMenu();
```

### <a name="remarks"></a>Примечания

Меню не создается до тех пор, пока вы не позвоните в одну из функций члена создать или загрузить`CMenu:`

- [СоздатьМеню](#createmenu)

- [СоздатьПоппупМеню](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Attach](#attach)

## <a name="cmenucreatemenu"></a><a name="createmenu"></a>CMenu::CreateMenu

Создает меню и прикрепляет `CMenu` его к объекту.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если меню было создано успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню изначально пусто. Элементы меню могут быть `AppendMenu` `InsertMenu` добавлены с помощью функции или элемента.

Если меню присваивается окну, оно автоматически уничтожается при разрушении окна.

Перед выходом приложение должно освободить системные ресурсы, связанные с меню, если меню не назначено окну. Приложение освобождает меню, позвонив в функцию [участника DestroyMenu.](#destroymenu)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

## <a name="cmenucreatepopupmenu"></a><a name="createpopupmenu"></a>CMenu::CreatePopupMenu

Создает всплывающее меню и прикрепляет `CMenu` его к объекту.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если всплывающее меню было успешно создано; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню изначально пусто. Элементы меню могут быть `AppendMenu` `InsertMenu` добавлены с помощью функции или элемента. Приложение может добавить всплывающее меню в существующее или всплывающее меню. Функция `TrackPopupMenu` участника может использоваться для отображения этого меню в виде плавающего всплывающего меню и для отслеживания выделений в всплывающем меню.

Если меню присваивается окну, оно автоматически уничтожается при разрушении окна. Если меню добавлено в существующее меню, оно автоматически уничтожается при уничтожении этого меню.

Перед выходом приложение должно освободить системные ресурсы, связанные с всплывающим меню, если меню не назначено окну. Приложение освобождает меню, позвонив в функцию [участника DestroyMenu.](#destroymenu)

### <a name="example"></a>Пример

  Смотрите пример [cMenu::CreateMenu](#createmenu).

## <a name="cmenudeletemenu"></a><a name="deletemenu"></a>CMenu::DeleteMenu

Удаляет элемент из меню.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nПозиция*<br/>
Определяем элемент меню, который должен быть удален, как это определено *nFlags*.

*nФлаги*<br/>
Используется для интерпретации *nPosition* следующим образом:

|nФлаги|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если элемент меню имеет связанное всплывающее меню, `DeleteMenu` разрушает ручку всплывающее меню и освобождает память, используемую всплывающее меню.

Всякий раз, когда меню, которое находится в окне, изменяется (независимо от того, отображается окно или нет), приложение должно вызывать [CWnd::DrawMenuBar.](../../mfc/reference/cwnd-class.md#drawmenubar)

### <a name="example"></a>Пример

  Смотрите пример [для CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenudeletetempmap"></a><a name="deletetempmap"></a>CMenu::DeleteTempMap

Вызывается автоматически `CWinApp` обработчиком простоя, `CMenu` удаляет любые временные объекты, созданные функцией участника [FromHandle.](#fromhandle)

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Примечания

`DeleteTempMap`отсоединяет объект меню Windows, прикрепленный `CMenu` к временному объекту, `CMenu` перед удаляя объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

## <a name="cmenudestroymenu"></a><a name="destroymenu"></a>CMenu::DestroyMenu

Уничтожает меню и все используемые ресурсы Windows.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если меню уничтожено; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню отделяется `CMenu` от объекта до его уничтожения. Функция `DestroyMenu` Windows автоматически вызывается `CMenu` в деструкторе.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::CreateMenu](#createmenu).

## <a name="cmenudetach"></a><a name="detach"></a>CMenu::Detach

Отсоединяет меню Windows от `CMenu` объекта и возвращает ручку.

```
HMENU Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка, типа HMENU, в меню Windows, в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Член `m_hMenu` данных настроен на NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenudrawitem"></a><a name="drawitem"></a>CMenu::DrawItem

Вызывается в рамках, когда визуальный аспект нарисованного владельцем меню изменяется.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Примечания

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено. Переопределить эту функцию элемента для `CMenu` реализации чертежа для объекта владельца-рисования. Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста отображения, поставляемые в *lpDrawItemStruct* до прекращения этой функции участника.

Смотрите [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) для описания `DRAWITEMSTRUCT` структуры.

### <a name="example"></a>Пример

Следующий код из образца MFC [CTRLTEST:](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

## <a name="cmenuenablemenuitem"></a><a name="enablemenuitem"></a>CMenu::EnableMenuItem

Включает, отсваивает или затемняет элемент меню.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Параметры

*nIDEnableItem*<br/>
Определяем элемент меню, который будет включен, как это определено *nEnable*. Этот параметр может указывать всплывающие пункты меню, а также стандартные элементы меню.

*nEnable*<br/>
Определяет действия, которые необходимо предпринять. Это может быть сочетание MF_DISABLED, MF_ENABLED или MF_GRAYED, с MF_BYCOMMAND или MF_BYPOSITION. Эти значения можно комбинировать с помощью bitwise или оператора. Данные величины имеют следующие значения:

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.

- MF_DISABLED отменяет элемент меню так, чтобы он не мог быть выбран, но не тускнеет его.

- MF_ENABLED включает элемент меню, чтобы он мог быть выбран, и восстанавливает его из затемненного состояния.

- MF_GRAYED отстраняет элемент меню так, что он не может быть выбран и затемняет его.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние (MF_DISABLED, MF_ENABLED или MF_GRAYED) или -1, если не действует.

### <a name="remarks"></a>Примечания

[Функции члена CreateMenu,](#createmenu) [InsertMenu,](#insertmenu) [ModifyMenu](#modifymenu)и [LoadMenuIndirect](#loadmenuindirect) также могут установить состояние (включено, отключено или затемнено) элемента меню.

Использование MF_BYPOSITION значения требует, чтобы `CMenu`приложение использовало правильное. `CMenu` Если используется панель меню, то влияет элемент меню верхнего уровня (элемент в баре меню). Чтобы установить состояние элемента во всплывающем или вложенном всплывающем меню по `CMenu` позиции, приложение должно указать всплывающее меню.

Когда приложение указывает MF_BYCOMMAND флаг, Windows проверяет все всплывающие элементы меню, которые подчинены `CMenu`; поэтому, если не присутствуют дублирующиеся пункты меню, достаточно использовать `CMenu` панель меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

## <a name="cmenufromhandle"></a><a name="fromhandle"></a>CMenu::FromHandle

Возвращает указатель объекту, `CMenu` учитываемому ручку Windows, в меню.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Ручка Windows в меню.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMenu` который может быть временным или постоянным.

### <a name="remarks"></a>Примечания

Если `CMenu` объект еще не подключен к объекту меню `CMenu` Windows, создается и прикрепляется временный объект.

Этот `CMenu` временный объект действителен только до следующего времени, когда приложение будет проходить время простоя в цикле событий, после чего все временные объекты удаляются.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::CreateMenu](#createmenu).

## <a name="cmenugetdefaultitem"></a><a name="getdefaultitem"></a>CMenu::GetDefaultItem

Определяет элемент меню по умолчанию в указанном меню.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*gmdiFlags*<br/>
Значение, определяющее, как функция выполняет поиск элементов меню. Этот параметр не может быть ни одним, ни одним, или комбинацией следующих значений:

|Значение|Значение|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Уточняется, что, если элемент по умолчанию является элементом, открывающий подменю, функция заключается в повторном поиске в соответствующем подменю. Если в подмене нет элемента по умолчанию, значение возврата определяет элемент, открывающий подменю.<br /><br /> По умолчанию функция возвращает первый элемент по умолчанию в указанном меню, независимо от того, является ли это элементом, открывающий подменю.|
|GMDI_USEDISABLED|Уточняется, что функция заключается в возврате элемента по умолчанию, даже если он отключен.<br /><br /> По умолчанию функция пропускает отключенные или серые элементы.|

*fByPos*<br/>
Значение, определяющее, следует ли извлекать идентификатор элемента меню или его положение. Если этот параметр FALSE, идентификатор возвращается. В противном случае позиция возвращается.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата является идентификатором или положением элемента меню. Если функция выходит из строя, значение возврата - 1.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение функции Win32 [GetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem), как описано в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenugetmenucontexthelpid"></a><a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId

Извлекает идентификатор `CMenu`справки контекста, связанный с .

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор контекста, с помощью идентификатора, с которой он в настоящее время связан, `CMenu` если он имеет его; ноль в противном случае.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenugetmenuinfo"></a><a name="getmenuinfo"></a>CMenu::GetMenuInfo

Извлекает информацию для меню.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Параметры

*lpcmi*<br/>
Указатель на структуру [MENUINFO,](/windows/win32/api/winuser/ns-winuser-menuinfo) содержащую информацию для меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата неявляется; в противном случае значение возврата равно нулю.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы получить информацию о меню.

## <a name="cmenugetmenuitemcount"></a><a name="getmenuitemcount"></a>CMenu::GetMenuItemCount

Определяет количество элементов в всплывающем или верхнем меню.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в меню, если функция успешна; в противном случае -1.

### <a name="example"></a>Пример

  Смотрите пример [для CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenugetmenuitemid"></a><a name="getmenuitemid"></a>CMenu::GetMenuItemID

Получает идентификатор меню-элемента для элемента меню, расположенного в позиции, определенной *nPos.*

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Упоняет положение (нулевой) элемента меню, идентификатор которого извлекается.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор элемента для указанного элемента во всплывающем меню, если функция успешна. Если указанный элемент является всплывающее меню (в отличие от элемента в всплывающем меню), значение возврата -1. Если *nPos* соответствует пункту меню SEPARATOR, значение возврата составляет 0.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenugetmenuiteminfo"></a><a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo

Извлекает информацию о пункте меню.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Идентификация или положение пункта меню для получения информации. Значение этого параметра зависит от `ByPos`значения.

*lpMenuItemInfo*<br/>
Указатель на [MENUITEMINFO](/windows/win32/api/winuser/ns-winuser-menuiteminfow), как описано в Windows SDK, который содержит информацию о меню.

*fByPos*<br/>
Значение, определяющее `nIDItem`значение . По умолчанию, false, что указывает на то, `ByPos` что uItem является идентификатором элемента меню. Если `ByPos` false не установлен, он указывает положение элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата неявляется. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенную информацию об ошибках, используйте функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror), как описано в SDK Windows.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение функции Win32 [GetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow), как описано в Windows SDK. Обратите внимание, что в `GetMenuItemInfo`реализации MFC вы не используете ручку в меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

## <a name="cmenugetmenustate"></a><a name="getmenustate"></a>CMenu::GetMenuState

Возвращает состояние указанного элемента меню или количество элементов во всплывающем меню.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Установить идентификатор элемента меню, определяемый *nFlags*.

*nФлаги*<br/>
Определяет характер *nID*. Может иметь одно из следующих значений.

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.

### <a name="return-value"></a>Возвращаемое значение

Значение 0xFFFFFF если указанный элемент не существует. Если *nId* определяет всплывающее меню, байт высокого порядка содержит количество элементов в всплывающем меню, а байт с низким заказом содержит флаги меню, связанные с всплывающее меню. В противном случае значение возврата — это маска (Boolean OR) значений из следующего списка (эта маска описывает состояние элемента меню, который *идентифицирует nId):*

- MF_CHECKED действует как переключатель с MF_UNCHECKED, чтобы разместить галочку по умолчанию рядом с пунктом. Когда приложение поставляет галочку bitmaps (см. `SetMenuItemBitmaps` функцию члена), отображается биткарта "проверка".

- MF_DISABLED отменяет элемент меню так, чтобы он не мог быть выбран, но не тускнеет его.

- MF_ENABLED включает элемент меню, чтобы он мог быть выбран, и восстанавливает его из затемненного состояния. Обратите внимание, что значение этой константы составляет 0; приложение не должно тестировать против 0 на сбой при использовании этого значения.

- MF_GRAYED отстраняет элемент меню так, что он не может быть выбран и затемняет его.

- MF_MENUBARBREAK помещает элемент в новую строку в статическое меню или в новую колонку во всплывающих меню. Новая всплывающая колонка меню будет отделена от старой колонки вертикальной разделительной линией.

- MF_MENUBREAK помещает элемент в новую строку в статическое меню или в новую колонку во всплывающих меню. Между колоннами не помещается разделительная линия.

- MF_SEPARATOR рисует горизонтальную разделительную линию. Может быть использован только во всплывающем меню. Эта строка не может быть затемнена, отключена или выделена. Другие параметры игнорируются.

- MF_UNCHECKED действует как переключатель с MF_CHECKED, чтобы удалить контрольный знак рядом с пунктом. Когда приложение поставляет галочку bitmaps (см. `SetMenuItemBitmaps` функцию члена), отображается бит-карта "проверить отметку". Обратите внимание, что значение этой константы составляет 0; приложение не должно тестировать против 0 на сбой при использовании этого значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

## <a name="cmenugetmenustring"></a><a name="getmenustring"></a>CMenu::GetMenuString

Копирует метку указанного элемента меню в указанный буфер.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>Параметры

*nIDItem*<br/>
Упоняет идентификатор самого большого числа элемента меню или смещения элемента меню в меню, в зависимости от значения *nFlags.*

*lpString*<br/>
Указывает на буфер, который должен получить метку.

*rString*<br/>
Ссылка на `CString` объект, который должен получить скопированную строку меню.

*nMaxCount*<br/>
Упоняет максимальную длину (в символах) этикетки, которая будет скопирована. Если метка длиннее максимального, указанного в *nMaxCount,* дополнительные символы усечены.

*nФлаги*<br/>
Определяет интерпретацию параметра *nIDItem.* Может иметь одно из следующих значений.

|nФлаги|Интерпретация nIDItem|
|------------|-------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Определяет фактическое количество символов, скопированных в буфер, не включая нулевой терминатор.

### <a name="remarks"></a>Примечания

Параметр *nMaxCount* должен быть на один больше, чем количество символов на этикетке, чтобы разместить нулевой символ, который завершает строку.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenugetsafehmenu"></a><a name="getsafehmenu"></a>CMenu::GetSafeHmenu

Возвращает HMENU, завернутый этим `CMenu` объектом, или указатель NULL.`CMenu`

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Пример

  Смотрите пример [для CMenu:LoadMenu](#loadmenu).

## <a name="cmenugetsubmenu"></a><a name="getsubmenu"></a>CMenu::GetSubMenu

Извлекает `CMenu` объект всплывающее меню.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Определяет положение всплывающее меню, содержащееся в меню. Значения позиции начинаются с 0 для первого элемента меню. Идентификатор всплывающих меню не может быть использован в этой функции.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMenu` объект, `m_hMenu` член которого содержит ручку всплывающее меню, если всплывающее меню существует в данной позиции; в противном случае NULL. Если `CMenu` объекта не существует, создается временный. Возвращенный `CMenu` указатель не должен храниться.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::TrackPopupMenu](#trackpopupmenu).

## <a name="cmenuinsertmenu"></a><a name="insertmenu"></a>CMenu::InsertMenu

Вставляет новый элемент меню в позиции, указанной *nPosition,* и перемещает другие элементы вниз по меню.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nПозиция*<br/>
Определяет пункт меню, перед которым должен быть вставлен новый элемент меню. Параметр *nFlags* может быть использован для интерпретации *nPosition* следующим образом:

|nФлаги|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0. Если *nPosition* -1, новый элемент меню придумен к концу меню.|

*nФлаги*<br/>
Определяет, как интерпретируется *nPosition,* и определяет информацию о состоянии нового элемента меню при его добавлении в меню. Список флагов, которые могут быть [AppendMenu](#appendmenu) установлены, см. Чтобы указать несколько значений, используйте bitwise OR оператора, чтобы объединить их с MF_BYCOMMAND или MF_BYPOSITION флагом.

*nIDNewItem*<br/>
Упоняет либо идентификатор команды нового элемента меню, либо, если *nFlags* установлен на MF_POPUP, ручка меню ( HMENU) всплывающем меню. Параметр *nIDNewItem* игнорируется (не требуется), если *nFlags* установлен на MF_SEPARATOR.

*lpszNewItem*<br/>
Определяет содержание нового пункта меню. *nFlags* можно использовать для *интерпретации lpszNewItem* следующим образом:

|nФлаги|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-битное значение, поставляемое приложением для поддержания дополнительных данных, связанных с пунктом меню. Это 32-битное значение доступно `itemData` для приложения в члене структуры, поставляемой [WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem) и [WM_DRAWITEM](/windows/win32/Controls/wm-drawitem) сообщений. Эти сообщения отправляются при первоначальном отображении или изменении элемента меню.|
|MF_STRING|Содержит длинный указатель на нулевую строку. Это интерпретация по умолчанию.|
|MF_SEPARATOR|Параметр *lpszNewItem* игнорируется (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение может указать состояние элемента меню, установив значения в *nFlags*.

Всякий раз, когда меню, которое находится в окне, изменяется `CWnd::DrawMenuBar`(независимо от того, отображается окно или нет), приложение должно вызываться под номером.

Когда *nIDNewItem* определяет всплывающее меню, оно становится частью меню, в которое оно вставляется. Если это меню будет уничтожено, вставленное меню также будет уничтожено. Вставленное меню должно `CMenu` быть отделено от объекта, чтобы избежать конфликта.

Если окно ребенка с интерфейсом многоактивного нескольких документов (MDI) максимизировано и приложение вставляет всплывающее меню в меню приложения MDI, позвонив по этой функции и указав MF_BYPOSITION флаг, меню вставляется на одну позицию дальше влево, чем ожидалось. Это происходит потому, что меню управления активным окном ребенка MDI вставляется в первое положение панели меню окна mDI. Чтобы правильно расположить меню, приложение должно добавить 1 к значению позиции, которое в противном случае было бы использовано. Приложение может использовать WM_MDIGETACTIVE сообщение, чтобы определить, является ли в настоящее время активным окном ребенка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

## <a name="cmenuinsertmenuitem"></a><a name="insertmenuitem"></a>CMenu::InsertMenuItem

Вставляет новый пункт меню в указанном положении в меню.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Смотрите описание *uItem* в [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw) в Windows SDK.

*lpMenuItemInfo*<br/>
Смотрите описание *lpmii* в `InsertMenuItem` Windows SDK.

*fByPos*<br/>
Смотрите описание *fByPosition* в `InsertMenuItem` Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция обертывает [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw), описанные в Windows SDK.

## <a name="cmenuloadmenu"></a><a name="loadmenu"></a>CMenu::LoadMenu

Загружает ресурс меню из исполняемого файла приложения и `CMenu` прикрепляет его к объекту.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указывает на нулевую строку, содержащую название ресурса меню для загрузки.

*nIDResource*<br/>
Упоняет идентификатор меню ресурса меню для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если ресурс меню был загружен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Перед выходом приложение должно освободить системные ресурсы, связанные с меню, если меню не назначено окну. Приложение освобождает меню, позвонив в функцию [участника DestroyMenu.](#destroymenu)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

## <a name="cmenuloadmenuindirect"></a><a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect

Загружает ресурс из шаблона меню в `CMenu` памяти и прикрепляет его к объекту.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Параметры

*lpMenuTemplate*<br/>
Указывает на шаблон меню (который представляет собой единую структуру [MENUITEMTEMPLATEHEADHEADEDER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader) и коллекцию одной или нескольких структур [МЕНУНИТЕММЕКУТТЕР).](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) Для получения дополнительной информации об этих двух структурах, см.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если ресурс меню был загружен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Шаблон меню представляет собой заголовок, за которым следует коллекция из одной или нескольких структур [MENUITEMTEMPLATE,](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) каждая из которых может содержать один или несколько пунктов меню и всплывающих меню.

Номер версии должен быть 0.

Флаги `mtOption` должны включать MF_END для последнего элемента в всплывающем списке и для последнего элемента в основном списке. Просмотреть `AppendMenu` функцию участника для других флагов. Участник `mtId` должен быть исключен из структуры MENUITEMTEMPLATE, когда `mtOption`MF_POPUP указана в .

Пространство, выделенное для структуры MENUITEMTEMPLATE, должно быть достаточно большим, `mtString` чтобы содержать название элемента меню в виде строки с нулевым завершением.

Перед выходом приложение должно освободить системные ресурсы, связанные с меню, если меню не назначено окну. Приложение освобождает меню, позвонив в функцию [участника DestroyMenu.](#destroymenu)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

## <a name="cmenum_hmenu"></a><a name="m_hmenu"></a>CMenu::m_hMenu

Определяет ручку HMENU меню Windows, прикрепленную `CMenu` к объекту.

```
HMENU m_hMenu;
```

### <a name="example"></a>Пример

  Смотрите пример [для CMenu:LoadMenu](#loadmenu).

## <a name="cmenumeasureitem"></a><a name="measureitem"></a>CMenu::MeasureItem

Вызывается по фреймворку при создании меню со стилем владельца-рисования.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpИзмеренныйПункт*<br/>
Указатель на `MEASUREITEMSTRUCT` структуру.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переизобить эту функцию участника и заполнить структуру, `MEASUREITEMSTRUCT` чтобы сообщить Windows о размерах меню.

Смотрите [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) для описания `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

Следующий код из образца MFC [CTRLTEST:](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

## <a name="cmenumodifymenu"></a><a name="modifymenu"></a>CMenu::ModifyMenu

Изменяет существующий элемент меню в позиции, указанной *nPosition.*

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nПозиция*<br/>
Определяет элемент меню, который будет изменен. Параметр *nFlags* может быть использован для интерпретации *nPosition* следующим образом:

|nФлаги|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

*nФлаги*<br/>
Определяет, как интерпретируется *nPosition,* и дает информацию об изменениях, которые должны быть внесены в пункт меню. Список флагов, которые могут быть [AppendMenu](#appendmenu) установлены, см.

*nIDNewItem*<br/>
Упоняет либо идентификатор команды измененного элемента меню, либо, если *nFlags* установлен на MF_POPUP, ручка меню (HMENU) всплывающее меню. Параметр *nIDNewItem* игнорируется (не требуется), если *nFlags* установлен на MF_SEPARATOR.

*lpszNewItem*<br/>
Определяет содержание нового пункта меню. Параметр *nFlags* может быть использован для интерпретации *lpszNewItem* следующим образом:

|nФлаги|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-битное значение, поставляемое приложением для поддержания дополнительных данных, связанных с пунктом меню. Это 32-битное значение доступно для приложения, когда оно обрабатывает MF_MEASUREITEM и MF_DRAWITEM.|
|MF_STRING|Содержит длинный указатель на нулевую строку или на строку. `CString`|
|MF_SEPARATOR|Параметр *lpszNewItem* игнорируется (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение определяет новое состояние элемента меню, устанавливая значения в *nFlags.* Если эта функция заменяет всплывающее меню, связанное с пунктом меню, она разрушает старое всплывающее меню и освобождает память, используемую всплывающее меню.

Когда *nIDNewItem* определяет всплывающее меню, оно становится частью меню, в которое оно вставляется. Если это меню будет уничтожено, вставленное меню также будет уничтожено. Вставленное меню должно `CMenu` быть отделено от объекта, чтобы избежать конфликта.

Всякий раз, когда меню, которое находится в окне, изменяется `CWnd::DrawMenuBar`(независимо от того, отображается окно или нет), приложение должно вызываться под номером. Чтобы изменить атрибуты существующих элементов меню, гораздо `CheckMenuItem` `EnableMenuItem` быстрее использовать функции и функции участника.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenuoperator-hmenu"></a><a name="operator_hmenu"></a>CMenu:оператор HMENU

Используйте этот оператор для извлечения ручки `CMenu` объекта.

```
operator HMENU() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, `CMenu` ручка объекта; в противном случае, NULL.

### <a name="remarks"></a>Примечания

Ручку можно использовать для прямого вызова AA Windows.

## <a name="cmenuoperator-"></a><a name="operator_neq"></a>CMenu::оператор !

Определяет, если два меню логически не равны.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
Объект `CMenu` для сравнения.

### <a name="remarks"></a>Примечания

Тесты, если объект меню на левой стороне не равен объекту меню на правой стороне.

## <a name="cmenuoperator-"></a><a name="operator_eq_eq"></a>CMenu::оператор

Определяет, логически ли два меню равны.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
Объект `CMenu` для сравнения.

### <a name="remarks"></a>Примечания

Тесты, если объект меню на левой стороне равен (с точки зрения значения HMENU) с объектом меню на правой стороне.

## <a name="cmenuremovemenu"></a><a name="removemenu"></a>CMenu::RemoveMenu

Удаляет из меню элемент меню с сосвязанным всплывающее меню.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nПозиция*<br/>
Уотек элемента меню, который будет удален. Параметр *nFlags* может быть использован для интерпретации *nPosition* следующим образом:

|nФлаги|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

*nФлаги*<br/>
Определяет, как интерпретируется *nPosition.*

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Это не разрушает ручку для всплывающих меню, так что меню может быть повторно использовано. Перед вызовом этой функции `GetSubMenu` приложение может вызвать функцию `CMenu` участника для повторного использования всплывающих объектов.

Всякий раз, когда меню, находящееся в окне, изменяется `CWnd::DrawMenuBar`(независимо от того, отображается окно или нет), приложение должно вызвать вызов.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenusetdefaultitem"></a><a name="setdefaultitem"></a>CMenu::SetDefaultItem

Устанавливает элемент меню по умолчанию для указанного меню.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Идентификация или положение нового элемента меню по умолчанию или - 1 для элемента по умолчанию. Значение этого параметра зависит от значения *fByPos.*

*fByPos*<br/>
Значение, определяющее значение *uItem*. Если этот параметр FALSE, *uItem* является идентификатором элемента меню. В противном случае, это положение элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата неявляется. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенную информацию об ошибках, используйте функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror), как описано в SDK Windows.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение функции Win32 [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem), как описано в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenusetmenucontexthelpid"></a><a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId

Ассоциирует контекст, помогая ID с `CMenu`.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Параметры

*dwContextHelpId*<br/>
Контекст помогает ID `CMenu`связать с .

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае 0

### <a name="remarks"></a>Примечания

Все элементы меню разделяют этот идентификатор – к отдельным пунктам меню невозможно прикрепить идентификатор контекста справки.

### <a name="example"></a>Пример

  Смотрите пример [cMenu::InsertMenu](#insertmenu).

## <a name="cmenusetmenuinfo"></a><a name="setmenuinfo"></a>CMenu::SetMenuInfo

Устанавливает информацию для меню.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Параметры

*lpcmi*<br/>
Указатель на структуру [MENUINFO,](/windows/win32/api/winuser/ns-winuser-menuinfo) содержащую информацию для меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата неявляется; в противном случае значение возврата равно нулю.

### <a name="remarks"></a>Примечания

Позвоните в эту функцию, чтобы установить конкретную информацию о меню.

## <a name="cmenusetmenuitembitmaps"></a><a name="setmenuitembitmaps"></a>CMenu::SetMenuBitmaps

Связывает указанные биткарты с пунктом меню.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Параметры

*nПозиция*<br/>
Определяет элемент меню, который будет изменен. Параметр *nFlags* может быть использован для интерпретации *nPosition* следующим образом:

|nФлаги|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Упомянет, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если не установлены ни MF_BYCOMMAND, ни MF_BYPOSITION.|
|MF_BYPOSITION|Уточняется, что параметр дает положение существующего элемента меню. Первый элемент находится на позиции 0.|

*nФлаги*<br/>
Определяет, как интерпретируется *nPosition.*

*pBmpUnchecked*<br/>
Обращайте битную карту для использования для элементов меню, которые не проверены.

*pBmpChecked*<br/>
Обращайте в излишку для использования элементов меню, которые проверяются.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Независимо от того, проверен или бесконтрольно элемент меню, Windows отображает соответствующую бит-карту рядом с пунктом меню.

Если *pBmpUnChecked* или *pBmpChecked* null, то Windows не отображает ничего рядом с пунктом меню для соответствующего атрибута. Если оба параметра являются NULL, Windows использует чековую отметку по умолчанию при проверке элемента и удаляет контрольную отметку при бесконтрольном обнаружении элемента.

Когда меню уничтожено, эти бит-карты не разрушаются; приложение должно уничтожить их.

Функция `GetMenuCheckMarkDimensions` Windows извлекает размеры контрольной отметки по умолчанию, используемой для элементов меню. Приложение использует эти значения для определения соответствующего размера для бит-карт, поставляемых с этой функцией. Получить размер, создать свои bitmaps, а затем установить их.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

## <a name="cmenusetmenuiteminfo"></a><a name="setmenuiteminfo"></a>CMenu::SetMenu.

Изменяет информацию о пункте меню.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Смотрите описание *uItem* в [SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow) в Windows SDK.

*lpMenuItemInfo*<br/>
Смотрите описание *lpmii* в `SetMenuItemInfo` Windows SDK.

*fByPos*<br/>
Смотрите описание *fByPosition* в `SetMenuItemInfo` Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция обертывает [SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow), описанные в Windows SDK.

## <a name="cmenutrackpopupmenu"></a><a name="trackpopupmenu"></a>CMenu::TrackPopupMenu

Отображает плавающее всплывающее меню в указанном месте и отслеживает выбор элементов в всплывающем меню.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>Параметры

*nФлаги*<br/>
Определяет флаги положения экрана и мыши. Список доступных флагов можно найти в [TrackPopupMenu.](/windows/win32/api/winuser/nf-winuser-trackpopupmenu)

*x*<br/>
Определяет горизонтальное положение в координатах экрана всплывающее меню. В зависимости от значения параметра *nFlags* меню может быть лево-выровнено, правовы выровнено или по центру относительно этой позиции.

*Y*<br/>
Определяет вертикальное положение в координатах экрана верхней части меню на экране.

*pWnd*<br/>
Идентифицирует окно, которому принадлежит всплывающее меню. Этот параметр не может быть NULL, даже если указан TPM_NONOTIFY флаг. Это окно получает все WM_COMMAND сообщения из меню. В версиях Windows 3.1 и позже окно `TrackPopupMenu` не получает WM_COMMAND сообщений до возвращения. В Windows 3.0 окно получает `TrackPopupMenu` WM_COMMAND сообщений перед возвратом.

*lpRect*<br/>
Не обрабатывается.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает результат вызова [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) в Windows SDK.

### <a name="remarks"></a>Примечания

Плавающее всплывающее меню может появиться в любом месте экрана.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

## <a name="cmenutrackpopupmenuex"></a><a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx

Отображает плавающее всплывающее меню в указанном месте и отслеживает выбор элементов в всплывающем меню.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>Параметры

*fuFlags*<br/>
Определяет различные функции для расширенного меню. Для перечисления всех значений и их значения, [см.](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)

*x*<br/>
Определяет горизонтальное положение в координатах экрана всплывающее меню.

*Y*<br/>
Определяет вертикальное положение в координатах экрана верхней части меню на экране.

*pWnd*<br/>
Указатель на окно, владеющее всплывающим меню и получающий сообщения из созданного меню. Это окно может быть любым окном из текущего приложения, но не может быть NULL. Если вы укажете TPM_NONOTIFY *параметрfus fuFlags,* функция не отправляет никаких сообщений *pWnd.* Функция должна вернуться к окну, на которое указывает *pWnd* для получения WM_COMMAND сообщения.

*lptpm*<br/>
Указатель на структуру [TPMPARAMS,](/windows/win32/api/winuser/ns-winuser-tpmparams) которая определяет область экрана, меню не должно перекрываться. Этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Если указать TPM_RETURNCMD параметра *fuFlags,* значение возврата — это идентификатор элемента, выбранного пользователем. Если пользователь отменяет меню, не делая выбор, или если происходит ошибка, то значение возврата составляет 0.

Если вы не указали TPM_RETURNCMD параметра *fuFlags,* значение возврата неявляется, если функция успешно работает, и 0, если она не удается. Чтобы получить расширенную информацию об ошибке, позвоните [getLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

Плавающее всплывающее меню может появиться в любом месте экрана. Для получения дополнительной информации об ошибках обработки при создании всплывающего меню, [см.](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
