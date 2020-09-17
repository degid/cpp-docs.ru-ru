---
title: CSnapInPropertyPageImpl класс
ms.date: 11/04/2016
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: 3f09e8500eadd36eec53db95f10261834d672101
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747578"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl класс

Этот класс предоставляет методы для реализации объекта страницы свойств оснастки.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CancelToclose](#canceltoclose)|Изменяет сяоположение кнопок **OK** и **Cancel.**|
|[CSnapInPropertyPageImpl::Создание](#create)|Инициализирует `CSnapInPropertyPageImpl` вновь созданный объект.|
|[CSnapInPropertyPageImpl::Onapply](#onapply)|Вызывается по системе, когда пользователь нажимает кнопку **Apply Now** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Вызывается по системе, когда пользователь нажимает кнопку **справки** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Вызывается инфраструктурой, когда текущая страница больше не активна.|
|[CSnapInPropertyPageImpl::OnqueryCancel](#onquerycancel)|Вызывается по системе, когда пользователь нажимает кнопку **Отмена** и до отмены имеет место.|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Вызывается по системе, когда пользователь нажимает кнопку **Сбросить** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Вызывается инфраструктурой, когда текущая страница становится активной.|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Вызывается по системе, когда пользователь нажимает кнопку **"Назад"** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Вызывается по фреймворку, когда пользователь нажимает кнопку **Finish** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Вызывается по системе, когда пользователь нажимает кнопку **Next** при использовании листа свойств типа мастера.|
|[CSnapInPropertyPageImpl::КвириВи](#querysiblings)|Перенаправляет текущее сообщение на все страницы листа свойств.|
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Позвоните, чтобы активировать или отключить кнопку **Apply Now.**|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Структура `PROPSHEETPAGE` Windows, используемая объектом. `CSnapInPropertyPageImpl`|

## <a name="remarks"></a>Примечания

`CSnapInPropertyPageImpl`обеспечивает базовую реализацию для объекта страницы свойств оснастки. Основные функции страницы свойств оснастки реализованы с использованием нескольких различных интерфейсов и типов карт.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

## <a name="csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToclose

Вызов ими функции после невосполнимого изменения данных на странице листа свойств модального значения.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>Примечания

Эта функция изменит кнопку **OK,** чтобы **закрыть** и отключить кнопку **Отмена.** Это изменение предупреждает пользователя о том, что изменение является постоянным и изменения не могут быть отменены.

Функция `CancelToClose` участника ничего не делает в листе бесрежимного свойства, потому что в листе безрежима свойства нет кнопки **«Отмена»** по умолчанию.

## <a name="csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl

Формирует объект `CSnapInPropertyPageImpl`.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Параметры

*lpszНазвание*<br/>
(в) Название страницы собственности.

### <a name="remarks"></a>Примечания

Чтобы инициализировать базовую структуру, позвоните [cSnapInPropertyPageImpl::Create](#create).

## <a name="csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Создание

Вызовите эту функцию, чтобы инициализировать базовую структуру страницы свойств.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к `PROPSHEETPAGE` структуре, содержащей атрибуты вновь созданного листа свойств.

### <a name="remarks"></a>Примечания

Вы должны сначала позвонить [CSnapInPropertyPageImpImpl::CSnapInPropertyPageImpImpl](#csnapinpropertypageimpl) перед вызовом этой функции.

## <a name="csnapinpropertypageimplm_psp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp

`m_psp`представляет собой структуру, члены которой хранят характеристики `PROPSHEETPAGE`.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Примечания

Используйте эту структуру для инициализации внешнего вида страницы свойств после ее построения.

Более подробную информацию об этой структуре, включая список ее членов, [можно](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3) узнать в SDK Windows.

## <a name="csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::Onapply

Эта функция участника вызывается, когда пользователь нажимает кнопку **OK** или **Кнопку Apply Now.**

```
BOOL OnApply();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если изменения будут приняты; в противном случае 0.

### <a name="remarks"></a>Примечания

Прежде `OnApply` чем можно назвать рамки, вы `SetModified` должны иметь призвал и установить его параметр, чтобы true. Это активирует кнопку **Apply Now,** как только пользователь вносит изменения на странице свойств.

Переуверьте эту функцию участника, чтобы указать, какие действия принимает программа, когда пользователь нажимает кнопку **Apply Now.** При переопределением функция должна вернутьСЯ true, чтобы принять изменения и FALSE, чтобы предотвратить вступления изменений в силу.

По умолчанию `OnApply` реализация возвращает TRUE.

## <a name="csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp

Эта функция участника вызывается, когда пользователь нажимает кнопку **справки** для страницы свойств.

```cpp
void OnHelp();
```

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника для отображения справки для страницы свойств.

## <a name="csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive

Эта функция участника вызывается, когда страница больше не является активной страницей.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если данные были успешно обновлены; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника для выполнения специальных задач проверки данных.

## <a name="csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnqueryCancel

Эта функция участника вызывается, когда пользователь нажимает кнопку **Отмена** и до того, как действие отмены произошло.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, чтобы позволить операцию отмены; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать действие, предпринимаетепрограмму программы, когда пользователь нажимает кнопку **«Отмена».**

По умолчанию `OnQueryCancel` реализация возвращает TRUE.

## <a name="csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset

Эта функция участника вызывается, когда пользователь нажимает кнопку **Отмена.**

```cpp
void OnReset();
```

### <a name="remarks"></a>Примечания

При вызове этой функции отбрасываются изменения на всех страницах свойств, внесенных пользователем, ранее нажимающим на кнопку **Apply Now,** и лист свойств сохраняет фокус.

Переувисляйте эту функцию участника, чтобы указать, какие действия принимает программа, когда пользователь нажимает кнопку **«Отмена».**

## <a name="csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive

Эта функция участника вызывается, когда страница выбрана пользователем и становится активной страницей.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если страница была успешно установлена активная; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника для выполнения задач при активации страницы. Переопределение этой функции участника должно вызвать версию по умолчанию до выполнения любой другой обработки.

Реализация по умолчанию возвращает TRUE.

## <a name="csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack

Эта функция участника вызывается, когда пользователь нажимает кнопку **«Назад»** в мастере.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Возвращаемое значение

- 0 для автоматического перейти на предыдущую страницу.

- -1, чтобы предотвратить изменение страницы.

Чтобы перейти на страницу, кроме следующей, верните отображаемый идентификатор диалогового окна.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать некоторые действия, которые пользователь должен предпринять при нажатии кнопки **"Назад".**

## <a name="csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish

Эта функция участника вызывается, когда пользователь нажимает кнопку **«Завершение»** в мастере.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лист свойства уничтожен, когда мастер заканчивает; в противном случае ноль.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать **Finish** некоторые действия, которые пользователь должен предпринять при нажатии кнопки "Завершение".

## <a name="csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext

Эта функция участника вызывается, когда пользователь нажимает кнопку **Next** в мастере.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Возвращаемое значение

- 0 для автоматического перейти на следующую страницу.

- -1, чтобы предотвратить изменение страницы.

Чтобы перейти на страницу, кроме следующей, верните отображаемый идентификатор диалогового окна.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать некоторые действия, которые пользователь должен предпринять при нажатии кнопки **Next.**

## <a name="csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::КвириВи

Вызов ими функции участника для переадресовывания сообщения на каждую страницу в листе свойств.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
(в) Определяет дополнительную информацию, зависящая от сообщений.

*lParam*<br/>
(в) Определяет дополнительную информацию, зависящая от сообщений.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение не должно быть перенаправлено на следующую страницу свойств; в противном случае ноль.

### <a name="remarks"></a>Примечания

Если страница возвращает ненулевое значение, лист свойств не отправляет сообщение на последующие страницы.

## <a name="csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified

Вызовите эту функцию участника, чтобы включить или отключить кнопку **Apply Now,** основываясь на том, следует ли применять настройки на странице свойств к соответствующему внешнему объекту.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Параметры

*bИзменено*<br/>
(в) TRUE, чтобы указать, что настройки страницы свойств были изменены с момента последнего применения; FALSE указать, что настройки страницы свойств были применены или должны быть проигнорированы.

### <a name="remarks"></a>Примечания

Лист свойств отслеживает, какие страницы являются "грязными", то есть `SetModified( TRUE )`страницы свойств, для которых вы позвонили. Кнопка **Apply Now** всегда будет `SetModified( TRUE )` включена, если вы позвоните на одну из страниц. Кнопка **Apply Now** будет отключена при вызове `SetModified( FALSE )` одной из страниц, но только в том случае, если ни одна из других страниц не является «грязной».

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
