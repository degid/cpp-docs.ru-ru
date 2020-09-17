---
title: Класс CDragListBox
ms.date: 11/04/2016
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: 0d1ae94948e1143a5bac17985423c4bd1bfbaf65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374035"
---
# <a name="cdraglistbox-class"></a>Класс CDragListBox

В дополнение к функциональности окна списка Windows, `CDragListBox` класс позволяет пользователю перемещать элементы списка поле, такие как имена файлов, в поле списка.

## <a name="syntax"></a>Синтаксис

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CdragListBox::CdragListBox](#cdraglistbox)|Формирует объект `CDragListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDragListBox::BeginDrag](#begindrag)|Вызывается по фреймворку при запуске операции перетаскивания.|
|[CDragListBox::CancelDrag](#canceldrag)|Вызывается системой при отмене операции перетаскивания.|
|[CDragListBox::D](#dragging)|Вызывается фреймворками во время операции перетаскивания.|
|[CDragListBox::Drawinsert](#drawinsert)|Рисует руководство по вставке в поле списка перетаскивания.|
|[CDragListBox::Dопроза](#dropped)|Вызывается рамкой после того, как элемент был удален.|
|[Cdraglistbox::ItemFromPt](#itemfrompt)|Возвращает координаты перетаскиваемого элемента.|

## <a name="remarks"></a>Примечания

Список ящиков с этой возможностью позволяет пользователям заказывать элементы в списке в любой способ является наиболее полезным для них. По умолчанию поле списка переместит элемент в новое место в списке. Тем `CDragListBox` не менее, объекты могут быть настроены для копирования элементов, а не их перемещения.

Управление полем списка, `CDragListBox` связанное с классом, не должно иметь LBS_SORT или LBS_MULTIPLESELECT стиле. Для описания стилей списка поле, см [List-Box стили](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Чтобы использовать поле списка перетаскивания в существующем диалоговом поле вашего приложения, добавьте управление полем списка в `Control` шаблон `CDragListBox`диалогового шаблона с помощью редактора диалогов, а затем назначьте переменную участника (категории и переменного типа), соответствующую управлению полем списка в шаблоне диалогов.

Для получения дополнительной информации о назначении [Shortcut for Defining Member Variables for Dialog Controls](../../windows/defining-member-variables-for-dialog-controls.md)элементов управления переменным членов см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a>CDragListBox::BeginDrag

Вызывается в фреймворке при возникновении события, которое может начать операцию перетаскивания, например нажатие кнопки левой мыши.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint,](../../atl-mfc-shared/reference/cpoint-class.md) содержащий координаты перетаскиваемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если перетаскивание разрешено, в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, если вы хотите контролировать то, что происходит при начале операции перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания до тех пор, пока пользователь не нажмет левую или правую кнопку мыши или не нажмет ESC, после чего операция перетаскивания отменяется.

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a>CDragListBox::CancelDrag

Вызывается системой при отмене операции перетаскивания.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint,](../../atl-mfc-shared/reference/cpoint-class.md) содержащий координаты перетаскиваемого элемента.

### <a name="remarks"></a>Примечания

Переопределить эту функцию для обработки любой специальной обработки для управления окном списка.

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a>CdragListBox::CdragListBox

Формирует объект `CDragListBox`.

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a>CDragListBox::D

Вызывается инфраструктурой при перетаскивании `CDragListBox` элемента полесписка в объекте.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint,](../../atl-mfc-shared/reference/cpoint-class.md) содержащий координаты экрана x и y курсора.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса курсора для отображения. Возможны следующие значения:

- DL_COPYCURSOR указывает, что элемент будет скопирован.

- DL_MOVECURSOR указывает на то, что элемент будет перемещен.

- DL_STOPCURSOR указывает на то, что текущая цель падения неприемлема.

### <a name="remarks"></a>Примечания

Поведение по умолчанию возвращает DL_MOVECURSOR. Переопределить эту функцию, если вы хотите предоставить дополнительную функциональность.

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a>CDragListBox::Drawinsert

Вызывается рамкой, чтобы нарисовать руководство по вставке перед пунктом с указанным индексом.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Нулевой индекс точки вставки.

### <a name="remarks"></a>Примечания

Значение - 1 очищает руководство вставки. Переизвейдите эту функцию, чтобы изменить внешний вид или поведение руководства по вставке.

## <a name="cdraglistboxdropped"></a><a name="dropped"></a>CDragListBox::Dопроза

Вызывается инфраструктурой при падении `CDragListBox` элемента внутри объекта.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Параметры

*nSrcIndex*<br/>
Определяет нулевой индекс упавной строки.

*пт*<br/>
Объект [CPoint,](../../atl-mfc-shared/reference/cpoint-class.md) содержащий координаты места падения.

### <a name="remarks"></a>Примечания

Поведение по умолчанию копирует элемент коробки списка и его данные в новое место, а затем удаляет исходный элемент. Переопределить эту функцию для настройки поведения по умолчанию, например, возможность перетасовки копий элементов списка в ашего листе.

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a>Cdraglistbox::ItemFromPt

Вызовите эту функцию, чтобы получить нулевой индекс элемента коробки списка, расположенного в *pt.*

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint,](../../atl-mfc-shared/reference/cpoint-class.md) содержащий координаты точки в поле списка.

*bAutoScroll*<br/>
Nonzero, если прокрутка разрешена, в противном случае 0.

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс элемента ящика списка перетаскивания.

## <a name="see-also"></a>См. также раздел

[MFC Образец TSTCON](../../overview/visual-cpp-samples.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)
