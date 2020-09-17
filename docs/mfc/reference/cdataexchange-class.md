---
title: Класс CDataExchange
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: fd1bce7de7ac323dc3099ab4938306768eb95a35
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754632"
---
# <a name="cdataexchange-class"></a>Класс CDataExchange

Поддерживает процедуры обмена данными диалогового окна (DDX) и проверки данных диалогового окна (DDV), используемые классами Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class CDataExchange
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|Формирует объект `CDataExchange`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDataExchange::Fail](#fail)|Вызывается при сбой проверки. Сбросфокус на предыдущий элемент управления и выбрасывает исключение.|
|[CDataExchange::PrepareCtrl](#preparectrl)|Подготавливает указанный элемент управления для обмена данными или проверки. Используется для элементов управления nonedit.|
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Подготавливает указанный элемент управления дейтом для обмена данными или проверки.|
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Подготавливает указанный элемент управления OLE для обмена данными или проверки. Используется для элементов управления nonedit.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Флаг для направления DDX и DDV.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Окно диалога или окно, где происходит обмен данными.|

## <a name="remarks"></a>Примечания

`CDataExchange`не имеет базового класса.

Используйте этот класс, если вы пишете процедуры обмена данными для пользовательских типов данных или элементов управления, или если вы пишете свои собственные процедуры проверки данных. Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV см. [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md) и [Dialog boxes](../../mfc/dialog-boxes.md).

Объект `CDataExchange` предоставляет контекстную информацию, необходимую для DDX и DDV. Флаг *m_bSaveAndValidate* FALSE, когда DDX используется для заполнения исходных значений элементов управления диалогом от членов данных. *M_bSaveAndValidate* флага является правдой, когда DDX используется для установки текущих значений элементов управления диалогом в элементы данных и когда DDV используется для проверки значений данных. Если проверка DDV не удается, процедура DDV будет отображать окно сообщения, объясняющее ошибку ввода. Процедура DDV затем `Fail` вызовет сбросить фокус на управление нарушителя и выбросить исключение, чтобы остановить процесс проверки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDataExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a>CDataExchange::CDataExchange

Вызовите эту функцию участника для построения `CDataExchange` объекта.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Параметры

*pDlgWnd*<br/>
Указатель на родительское окно, содержащее элемент управления. Обычно это [CDialog-производный](../../mfc/reference/cdialog-class.md)объект.

*bSaveAndValidate*<br/>
Если true, этот объект проверяет данные, а затем записывает данные из элементов управления для членов. Если FALSE, этот объект будет перемещать данные от элементов к элементам управления.

### <a name="remarks"></a>Примечания

Постройте `CDataExchange` объект самостоятельно для хранения дополнительной информации в объекте обмена данными для передачи функции [cWnd::DoDataExchange.](../../mfc/reference/cwnd-class.md#dodataexchange)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a>CDataExchange::Fail

Платформа вызывает эту функцию участника при сходе сбоя в проверке данных диалогов (DDV).

```cpp
void Fail();
```

### <a name="remarks"></a>Примечания

`Fail`восстанавливает фокус и выделение элемента управления, проверка которого не удалась (при наличии элемента управления для восстановления). `Fail`затем бросает исключение типа [CUserException,](../../mfc/reference/cuserexception-class.md) чтобы остановить процесс проверки. Исключение приводит к тому, что окно сообщений, объясняющее отображение ошибки, отображается. После сбоя проверки DDV пользователь может повторно ввести данные в управление правонарушения.

Исполнители пользовательских процедур DDV `Fail` могут звонить из своих процедур, когда проверка не удается.

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate

Этот флаг указывает направление операции обмена данными диалогов (DDX).

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Примечания

Флаг незерн, `CDataExchange` если объект используется для перемещения данных из элементов управления диалогом в члены данных диалогового класса после того, как пользователь отодвигает элементы управления. Флаг равен нулю, если объект используется для инициализации элементов управления диалогом от членов данных диалогового класса.

Флаг также является незеролевым во время проверки данных диалогов (DDV).

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd

Содержит указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) для которого происходит обмен диалоговыми данными (DDX) или проверка (DDV).

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Примечания

Этот объект обычно является объектом [CDialog.](../../mfc/reference/cdialog-class.md) Исполнители пользовательских процедур DDX или DDV могут использовать этот указатель для получения доступа к окну диалога, содержащей элементы управления, на которые они работают.

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a>CDataExchange::PrepareCtrl

Платформа вызывает эту функцию участника для подготовки указанного элемента управления для обмена диалоговыми данными (DDX) и проверки (DDV).

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Параметры

*nIDC*<br/>
Идентификатор элемента управления, который должен быть подготовлен для DDX или DDV.

### <a name="return-value"></a>Возвращаемое значение

HWND управления готовится к DDX или DDV.

### <a name="remarks"></a>Примечания

Вместо этого используйте [PrepareEditCtrl](#prepareeditctrl) для элементов управления; использовать эту функцию члена для всех других элементов управления.

Подготовка состоит из хранения HWND элемента `CDataExchange` управления в классе. Платформа использует эту ручку для восстановления фокусировки ранее сфокусированного элемента управления в случае сбоя DDX или DDV.

Исполнители пользовательских процедур DDX или DDV должны вызывать `PrepareCtrl` все элементы управления без изменений, для которых они обмениваются данными через DDX или проверки данных через DDV.

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl

Платформа вызывает эту функцию участника для подготовки указанного элемента управления дейтерами для обмена диалоговыми данными (DDX) и проверки (DDV).

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Параметры

*nIDC*<br/>
Идентификатор элемента управления правки, который будет подготовлен для DDX или DDV.

### <a name="return-value"></a>Возвращаемое значение

HWND элемента управления правки, готовящемся для DDX или DDV.

### <a name="remarks"></a>Примечания

Вместо этого используйте [PrepareCtrl](#preparectrl) для всех элементов управления без отсылки.

Подготовка состоит из двух вещей. Во-первых, `PrepareEditCtrl` хранит HWND управления `CDataExchange` в классе. Платформа использует эту ручку для восстановления фокусировки ранее сфокусированного элемента управления в случае сбоя DDX или DDV. Во-вторых, `PrepareEditCtrl` устанавливает `CDataExchange` флаг в классе, чтобы указать, что элемент управления, данные которого обмениваются или проверяются, является элементом управления отсеивания.

Исполнители пользовательских процедур DDX или DDV должны вызывать `PrepareEditCtrl` все элементы управления для элементов, для которых они обмениваются данными через DDX или проверки данных через DDV.

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl

Платформа вызывает эту функцию участника для подготовки указанного управления OLE для обмена диалоговыми данными (DDX) и проверки (DDV).

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Параметры

*nIDC*<br/>
Идентификатор управления OLE, который будет подготовлен для DDX или DDV.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сайт управления OLE.

### <a name="remarks"></a>Примечания

Вместо этого используйте [PrepareEditCtrl](#prepareeditctrl) для элементов управления или [prepareCtrl](#preparectrl) для всех других элементов управления, не относясь к OLE.

Исполнители пользовательских процедур DDX или DDV должны вызывать `PrepareOleCtrl` все элементы управления OLE, для которых они обмениваются данными через DDX или проверки данных через DDV.

Для получения дополнительной информации о написании собственных процедур DDX и DDV [см.](../../mfc/tn026-ddx-and-ddv-routines.md) Для обзора DDX и DDV [см.](../../mfc/dialog-data-exchange-and-validation.md) [Dialog Box Topics](../../mfc/dialog-boxes.md)

## <a name="see-also"></a>См. также раздел

[MFC Образец VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
