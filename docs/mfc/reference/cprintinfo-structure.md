---
title: Структура CPrintInfo
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 3b081b0728514c0fca2eb31462e1bcd9e91a47aa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753014"
---
# <a name="cprintinfo-structure"></a>Структура CPrintInfo

Хранит информацию о работе при печати или предварительного просмотра.

## <a name="syntax"></a>Синтаксис

```
struct CPrintInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Возвращает номер печатной первой страницы.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Возвращает номер последней страницы документа.|
|[CPrintInfo::GetMinPage](#getminpage)|Возвращает номер первой страницы документа.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Возвращает количество страниц, предшествующих первой странице элемента DocObject, напечатанного в комбинированном заданиях печати DocObject.|
|[CPrintInfo:GetToPage](#gettopage)|Возвращает номер последней печатной страницы.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Устанавливается номер последней страницы документа.|
|[CPrintInfo::SetMinPage](#setminpage)|Устанавливается номер первой страницы документа.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Содержит флаг с указанием того, следует ли продолжить цикл печати.|
|[CPrintInfo::m_bDirect](#m_bdirect)|Содержит флаг, указывающий, печатается ли документ напрямую (без отображения диалогового окна печати).|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Содержит флаг, указывающий, является ли напечатанный документ DocObject.|
|[CPrintInfo::m_bPreview](#m_bpreview)|Содержит флаг с указанием, осуществляется ли предварительный просмотр документа.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|Специфика операций печати DocObject.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Содержит указатель на созданную пользователем структуру.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Определяет номер печатаемых страниц.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Упогоняет номер задания, присвоенный операционной системой для текущего задания печати|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Определяет количество страниц, отображаемых в окне предварительного просмотра; 1 или 2.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Осведывает смещение первой страницы конкретного DocObject в комбинированном заданиях печати DocObject.|
|[CPrintInfo::m_pPD](#m_ppd)|Содержит указатель на `CPrintDialog` объект, используемый для диалогового окна Печати.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Определяем прямоугольник, определяющий текущую область приговодляемой к удовечивой странице.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Содержит строку формата для отображения номеров страницы.|

## <a name="remarks"></a>Примечания

`CPrintInfo`является структурой и не имеет базового класса.

Фрейм создает `CPrintInfo` объект каждый раз, когда команда Print или Print Preview выбирается и уничтожает его при завершении команды.

`CPrintInfo`содержит информацию как о заданиях печати в целом, таких как диапазон страниц, которые должны быть напечатаны, так и о текущем состоянии задания печати, например, о печатаемых страницах. Некоторая информация хранится в связанном объекте [CPrintDialog;](../../mfc/reference/cprintdialog-class.md) этот объект содержит значения, введенные пользователем в поле диалога Print.

Объект `CPrintInfo` передается между фреймворкой и классом представления в процессе печати и используется для обмена информацией между ними. Например, фреймворк информирует класс представления, какую страницу `m_nCurPage` документа `CPrintInfo`распечатать, назначив значение члену; класс представления получает значение и выполняет фактическую печать указанной страницы.

Другим примером является случай, когда длина документа не известна до его печати. В этой ситуации класс представления тестирует конец документа каждый раз, когда страница печатается. Когда конец достигнут, класс представления `m_bContinuePrinting` устанавливает `CPrintInfo` член false; это информирует фреймворк, чтобы остановить цикл печати.

`CPrintInfo`используется функциями-членами, `CView` перечисленными в статье "Смотрите также". Для получения дополнительной информации об архитектуре печати, предоставленной [Document/View Architecture](../../mfc/document-view-architecture.md) библиотекой класса Microsoft [Printing](../../mfc/printing.md) Foundation, [см.](../../mfc/frame-windows.md) [Printing: Multipage Documents](../../mfc/multipage-documents.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPrintInfo`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a>CPrintInfo::GetFromPage

Вызовите эту функцию, чтобы получить номер первой страницы, которая будет напечатана.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер первой страницы, которая будет напечатана.

### <a name="remarks"></a>Примечания

Это значение, указанное пользователем в диалоговом поле Print, `CPrintDialog` и оно `m_pPD` хранится в объекте, на который ссылается участник. Если пользователь не указал значение, по умолчанию является первая страница документа.

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a>CPrintInfo::GetMaxPage

Вызовите эту функцию, чтобы получить номер последней страницы документа.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер последней страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится `CPrintDialog` в объекте, на который ссылается `m_pPD` участник.

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a>CPrintInfo::GetMinPage

Вызовите эту функцию, чтобы получить номер первой страницы документа.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер первой страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится `CPrintDialog` в объекте, на который ссылается `m_pPD` участник.

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage

Вызов исчерпнивите эту функцию, чтобы получить смещение при печати нескольких элементов DocObject от клиента DocObject.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество страниц, предшествующих первой странице элемента DocObject, печатаемых в комбинированном заданиях печати DocObject.

### <a name="remarks"></a>Примечания

Это значение ссылается `m_nOffsetPage` на участника. Первая страница документа будет пронумерована `m_nOffsetPage` значение1 при печати в виде DocObject с другими активными документами. Участник `m_nOffsetPage` действителен только `m_bDocObject` в том случае, если значение является правдой.

## <a name="cprintinfogettopage"></a><a name="gettopage"></a>CPrintInfo:GetToPage

Вызовите эту функцию, чтобы получить номер последней страницы, которая будет напечатана.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер последней страницы, которая будет напечатана.

### <a name="remarks"></a>Примечания

Это значение, указанное пользователем в диалоговом поле Print, `CPrintDialog` и оно `m_pPD` хранится в объекте, на который ссылается участник. Если пользователь не указал значение, по умолчанию является последней страницей документа.

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting

Содержит флаг с указанием того, следует ли продолжить цикл печати.

### <a name="remarks"></a>Примечания

Если вы занимаетесь pagination в печатное время, вы `CView::OnPrepareDC` можете установить этот элемент на FALSE в переопределение после того, как конец документа был достигнут. Вам не нужно изменять эту переменную, если вы указали длину документа `SetMaxPage` в начале задания печати с помощью функции члена. Участник `m_bContinuePrinting` является публичной переменной типа BOOL.

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a>CPrintInfo::m_bDirect

Рамочная платформа устанавливает этот член к TRUE, если диалоговый ящик Print будет обойдена для прямой печати; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Диалог печати обычно обходят стороной при печати из оболочки или при печати с помощью идентификатора команды ID_FILE_PRINT_DIRECT.

Обычно вы не меняете этот член, но если вы измените его, измените его перед вызовом [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) в [переопределениеc CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a>CPrintInfo::m_bDocObject

Содержит флаг, указывающий, является ли напечатанный документ DocObject.

### <a name="remarks"></a>Примечания

Члены `m_dwFlags` `m_nOffsetPage` данных и являются недействительными, если этот флаг не является правдой.

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a>CPrintInfo::m_bPreview

Содержит флаг с указанием, осуществляется ли предварительный просмотр документа.

### <a name="remarks"></a>Примечания

Это устанавливается фреймворком в зависимости от того, какую команду выполняет пользователь. Поле диалога Print не отображается для выполнения задания для предварительного просмотра печати. Участник `m_bPreview` является публичной переменной типа BOOL.

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a>CPrintInfo::m_dwFlags

Содержит комбинацию флагов, указывающих на операции печати DocObject.

### <a name="remarks"></a>Примечания

Действителен только `m_bDocObject` в том случае, если данные соответствуют действительности.

Флаги могут быть одним или более из следующих значений:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData

Содержит указатель на созданную пользователем структуру.

### <a name="remarks"></a>Примечания

Это можно использовать для хранения данных, относясь к печати, которые не хотите хранить в классе представлений. Участник `m_lpUserData` является публичной переменной типа LPVOID.

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a>CPrintInfo::m_nCurPage

Содержит номер текущей страницы.

### <a name="remarks"></a>Примечания

Платформа вызывает `CView::OnPrepareDC` `CView::OnPrint` и один раз для каждой страницы документа, каждый раз определяя различное значение для этого участника; его значения варьируются от `GetFromPage` значения, возвращенного к возвращенному. `GetToPage` Используйте этот член в `CView::OnPrepareDC` `CView::OnPrint` переопределениях и печати указанной страницы документа.

При первом вызове режима предварительного просмотра фреймворк считывает значение этого элемента, чтобы определить, какая страница документа должна быть предварительно просмотрена на начальном этапе. Значение этого участника можно установить в `CView::OnPreparePrinting` переопределение для поддержания текущего положения пользователя в документе при вводе режима предварительного просмотра. Участник `m_nCurPage` является публичной переменной типа UINT.

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber

Указывает номер задания, присвоенный операционной системой для текущего задания печати.

### <a name="remarks"></a>Примечания

Это значение может быть SP_ERROR, если задание еще не `CPrintInfo` напечатано (т.е. если объект построен и еще не используется для печати), или если была ошибка при запуске задания.

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages

Содержит количество страниц, отображаемых в режиме предварительного просмотра; это может быть 1 или 2.

### <a name="remarks"></a>Примечания

Участник `m_nNumPreviewPages` является публичной переменной типа UINT.

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage

Содержит количество страниц, предшествующих первой странице конкретной DocObject в комбинированном заданияпечати печати DocObject.

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a>CPrintInfo::m_pPD

Содержит указатель на `CPrintDialog` объект, используемый для отображения диалогового окна печати для выполнения задания печати.

### <a name="remarks"></a>Примечания

Член `m_pPD` является общедоступной переменной, `CPrintDialog`объявленной указателем на .

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a>CPrintInfo::m_rectDraw

Уотек области рисунка страницы в логических координатах.

### <a name="remarks"></a>Примечания

Вы можете сослаться на это в `CView::OnPrint`переопределение . Вы можете использовать этот член, чтобы отслеживать, какая область остается пригодной для использования после печати заголовки, колонтитулы, и так далее. Участник `m_rectDraw` является публичной переменной типа. `CRect`

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc

Содержит строку формата, используемую для отображения номеров страниц во время предварительного просмотра печати; эта строка состоит из двух подстрок, одна для одностраничного дисплея и одна для двухстраничного дисплея, каждая из которых завершается символом 'n'.

### <a name="remarks"></a>Примечания

В качестве значения по умолчанию в фреймворке используется значение "Page % u'nPages% u-% u'n". Если требуется другой формат для номеров страниц, укажите `CView::OnPreparePrinting`строку формата в переопределении. Участник `m_strPageDesc` является публичной переменной типа. `CString`

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a>CPrintInfo::SetMaxPage

Позвоните в эту функцию, чтобы указать номер последней страницы документа.

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Параметры

*nMaxPage*<br/>
Номер последней страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится `CPrintDialog` в объекте, на который ссылается `m_pPD` участник. Если длина документа известна до его печати, позвоните по `CView::OnPreparePrinting`этой функции из переопределения . Если длина документа зависит от параметра, указанного пользователем в диалоговом поле `CView::OnBeginPrinting`Print, позвоните по этой функции из переопределения . Если длина документа не известна до его печати, используйте `m_bContinuePrinting` элемент для управления циклом печати.

### <a name="example"></a>Пример

  Смотрите пример [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a>CPrintInfo::SetMinPage

Позвоните в эту функцию, чтобы указать номер первой страницы документа.

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Параметры

*nMinPage*<br/>
Номер первой страницы документа.

### <a name="remarks"></a>Примечания

Номера страниц обычно начинаются с 1. Это значение хранится `CPrintDialog` в объекте, на который ссылается `m_pPD` участник.

## <a name="see-also"></a>См. также раздел

[MFC Образец DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView:OnendPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnendPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::OnPrint](../../mfc/reference/cview-class.md#onprint)
