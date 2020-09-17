---
title: Класс COleDBRecordView
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: de9c602cb747ee3d4449df479530e55ce907cb8a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366107"
---
# <a name="coledbrecordview-class"></a>Класс COleDBRecordView

Представление, которое отображает записи базы данных в элементах управления.

## <a name="syntax"></a>Синтаксис

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDBRecordView::ColeDBRecordView](#coledbrecordview)|Формирует объект `COleDBRecordView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Возвращает стандартное значение HRESULT.|
|[ColedbRecordView::Onmove](#onmove)|Обновляет текущую запись (если грязная) на источнике данных, а затем переходит к указанной записи (следующей, предыдущей, первой или последней).|

## <a name="remarks"></a>Примечания

Представление представляет собой представление формы, `CRowset` непосредственно связанное с объектом. Представление создается из ресурса шаблона диалогов и `CRowset` отображает поля объекта в элементах управления шаблона диалога. Объект `COleDBRecordView` использует диалоговые данные (DDX), а `CRowset`навигационная функциональность, встроенная в, для автоматизации перемещения данных между элементами управления по форме и полям строки. `COleDBRecordView`также поставляет реализацию по умолчанию для перехода к первой, следующей, предыдущей или последней записи и интерфейсу для обновления записи, наданных в настоящее время.

Функции DDX можно `COleDbRecordView` использовать для получения данных непосредственно из набора записей базы данных и отображения их в диалоговом управлении. Вы должны `DDX_*` использовать методы `DDX_Text`(например, не `DDX_FieldText`функции `COleDbRecordView` `DDX_Field*` (например, с ). `DDX_FieldText`не будет `COleDbRecordView` работать `DDX_FieldText` с, потому `CRecordset*` что `CRecordView`принимает `CDaoRecordset*` дополнительный аргумент типа (для ) или (для `CDaoRecordView`).

> [!NOTE]
> Если вы работаете с классами объектов доступа к данным (DAO), а не с классами ШАБЛОНов для потребителей OLE DB, используйте класс [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md) Для получения дополнительной информации смотрите статью [Обзор: Программирование базы данных](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView`отслеживает положение пользователя в строке, чтобы представление записи можно обновляло пользовательский интерфейс. Когда пользователь перемещается на любой конец строки, представление записи отводит объекты пользовательского интерфейса - такие как элементы меню или кнопки панели инструментов - для дальнейшего движения в том же направлении.

Для получения дополнительной информации о классах строк [см.](../../data/oledb/ole-db-consumer-templates-cpp.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>Требования

**Заголовок:** afxoledb.h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a>COleDBRecordView::ColeDBRecordView

Формирует объект `COleDBRecordView`.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Содержит строку с нулевым завершением, которая является названием ресурса диалог-шаблон.

*nIDTemplate*<br/>
Содержит идентификационный номер ресурса диалог-шаблон.

### <a name="remarks"></a>Примечания

При создании объекта типа, полученного `COleDBRecordView`из, вызвать один из конструкторов для создания объекта представления и идентификации ресурса диалога, на котором основано представление. Можно определить ресурс либо по имени (пройти строку в качестве аргумента к конструктору), либо по его идентификатору (пройти неподписанный целый ряд в качестве аргумента).

> [!NOTE]
> Ваш производный класс *должен* поставлять свой собственный конструктор. В конструкторе, вызвать конструктор, `COleDBRecordView::COleDBRecordView`с именем ресурса или id в качестве аргумента.

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a>COleDBRecordView::OnGetRowset

Возвращает ручку для **CRowset<>** объект, связанный с представлением записи.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Необходимо переопределить эту функцию участника, чтобы построить или получить объект с помощью строки и вернуть ручку к нему. Если вы объявляете свой класс представления записи с ClassWizard, мастер записывает переопределение по умолчанию для вас. Реализация ClassWizard по умолчанию возвращает ручку строки, хранящуюся в представлении записи, если она существует. Если нет, он строит объект строки типа, указанного с `Open` ClassWizard, и вызывает его функцию члена, чтобы открыть таблицу или запустить запрос, а затем возвращает ручку объекту.

> [!NOTE]
> До MFC 7.0, `OnGetRowset` вернулся `CRowset`указатель на . Если у вас `OnGetRowset`есть код, который вызывает, вам нужно изменить тип возврата на замялизнный класс **CRowset<>. **

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Для получения дополнительной информации [Record Views: Using a Record View](../../data/using-a-record-view-mfc-data-access.md)и примеров см.

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a>ColedbRecordView::Onmove

Перемещается на другую запись в строке и отображает свои поля в элементах управления представления записи.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Параметры

*nIDMoveCommand*<br/>
Одно из следующих стандартных значений идентификатора команды:

- ID_RECORD_FIRST - Перейдите к первому рекорду в рекорде.

- ID_RECORD_LAST - Перейти к последнему рекорду в рекорде.

- ID_RECORD_NEXT - Перейдите к следующему рекорду в рекорде.

- ID_RECORD_PREV - Перейдите к предыдущему рекорду в рекорде.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если ход был успешным; в противном случае 0, если запрос на перемещение был отклонен.

### <a name="remarks"></a>Примечания

Реализация по умолчанию `Move` вызывает соответствующую функцию члена `CRowset` объекта, связанную с представлением записи.

По умолчанию `OnMove` обновляется текущая запись источника данных, если пользователь изменил ее в представлении записи.

Волшебник приложения создает ресурс меню с элементами меню First Record, Last Record, Next Record и Previous Record. При выборе опции Dockable Toolbar Мастер приложения также создает панель инструментов с кнопками, соответствующими этим командам.

Если вы пройдите мимо последней записи в рекордном сете, представление записи продолжает отображать последнюю запись. При перемещении назад мимо первой записи представление записи продолжает отображать первую запись.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
