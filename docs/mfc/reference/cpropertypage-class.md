---
title: Класс CPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: f46566eb562f1515e98aedf938ca68b225ee1b67
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751106"
---
# <a name="cpropertypage-class"></a>Класс CPropertyPage

Представляет отдельные страницы вкладки свойств, также известные как диалоговое окно вкладки.

## <a name="syntax"></a>Синтаксис

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPropertyPage::CPropertyPage](#cpropertypage)|Формирует объект `CPropertyPage`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Страница имущества::CancelToclose](#canceltoclose)|Изменяет кнопку OK для чтения Close и отменяет кнопку «Отмена» после невосполнимого изменения на странице листа свойств модального значения.|
|[CPropertyPage::Конструкция](#construct)|Формирует объект `CPropertyPage`. Используйте, `Construct` если вы хотите указать параметры во время выполнения, или если вы используете массивы.|
|[CPropertyPage::GetPSP](#getpsp)|Извлекает структуру Windows [PROPSHEETPAGE,](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) связанную с объектом. `CPropertyPage`|
|[Страница недвижимости::OnApply](#onapply)|Вызывается по фреймворку при нажатии кнопки Apply Now.|
|[Страница недвижимости::Отмена](#oncancel)|Вызывается по фрейму при нажатии кнопки «Отмена».|
|[CPropertyPage::OnKillActive](#onkillactive)|Вызывается в рамках, когда текущая страница больше не является активной страницей. Выполните проверку данных здесь.|
|[Страница имущества::OnOK](#onok)|Вызывается по системе при нажатии кнопки OK, Apply Now или Close.|
|[CPropertyPage::On-cqueryCancel](#onquerycancel)|Вызывается по фрейму при нажатии кнопки Отмена и до отмены.|
|[CPropertyPage::OnReset](#onreset)|Вызывается по фрейму при нажатии кнопки «Отмена».|
|[Страница недвижимости::OnSetActive](#onsetactive)|Вызывается по системе, когда страница сделана активная страница.|
|[CPropertyPage::TheWizardBack](#onwizardback)|Вызывается по фреймворку при нажатии кнопки "Назад" при использовании листа свойств типа мастера.|
|[CPropertyPage::InWizardFinish](#onwizardfinish)|Вызывается по фреймворку при нажатии кнопки "Завершение" при использовании листа свойств типа мастера.|
|[CPropertyPage::WizardNext](#onwizardnext)|Вызывается по фреймворку при нажатии кнопки Next при использовании листа свойств типа мастера.|
|[CPropertyPage::Квиривы](#querysiblings)|Перенаправляет сообщение на каждую страницу листа свойств.|
|[CPropertyPage::SetModified](#setmodified)|Позвоните, чтобы активировать или отключить кнопку Apply Now.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPropertyPage:::m_psp](#m_psp)|Структура Windows [PROPSHEETPAGE.](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) Обеспечивает доступ к основным параметрам страницы свойств.|

## <a name="remarks"></a>Примечания

Как и в стандартных диалоговых `CPropertyPage` коробках, вы получаете класс для каждой страницы в листе недвижимости. Для `CPropertyPage`использования полученных объектов сначала создайте объект [CPropertySheet,](../../mfc/reference/cpropertysheet-class.md) а затем создайте объект для каждой страницы, которая входит в лист свойств. Вызов [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) для каждой страницы в листе, а затем отобразить лист свойств, позвонив [cPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) для листа модального свойства, или [CPropertySheet::Создать](../../mfc/reference/cpropertysheet-class.md#create) для листа безмерного свойства.

Можно создать тип диалогового окна вкладок, называемый мастером, который состоит из листа свойств с последовательностью страниц свойств, которые направляют пользователя через этапы операции, такие как настройка устройства или создание бюллетеня. В диалоговом окне вкладок типа мастер-класса страницы свойств не имеют вкладок, и одновременно отображается только одна страница свойств. Кроме того, вместо того, OK и Применить сейчас кнопки, мастер типа вкладки диалог оваки имеет кнопку "Назад", кнопку Next или Finish, и кнопку Отмена.

Для получения дополнительной информации об установлении листа свойств в качестве мастера, [см.](../../mfc/reference/cpropertysheet-class.md#setwizardmode) Для получения дополнительной `CPropertyPage` информации об [Property Sheets and Property Pages](../../mfc/property-sheets-and-property-pages-in-mfc.md)использовании объектов см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>Страница имущества::CancelToclose

Вызов ими функции после невосполнимого изменения данных на странице листа свойств модального значения.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>Примечания

Эта функция изменит кнопку OK, чтобы закрыть и отключить кнопку Отмена. Это изменение предупреждает пользователя о том, что изменение является постоянным и изменения не могут быть отменены.

Функция `CancelToClose` участника ничего не делает в листе бесрежимного свойства, потому что в листе безрежима свойства нет кнопки «Отмена» по умолчанию.

### <a name="example"></a>Пример

  Смотрите пример [cPropertyPage::Квири.)](#querysiblings)

## <a name="cpropertypageconstruct"></a><a name="construct"></a>CPropertyPage::Конструкция

Вызовите эту функцию участника для построения `CPropertyPage` объекта.

```cpp
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Идентификатор шаблона, используемого для этой страницы.

*nIDCaption*<br/>
Идентификатор имени, которое будет размещено на вкладке для этой страницы. Если 0, имя будет взято из шаблона диалога для этой страницы.

*lpszTemplateName*<br/>
Содержит строку с нулевым завершением, которая является именем ресурса шаблона.

*nIDHeaderTitle*<br/>
Идентификатор имени, которое будет размещено в месте заголовка страницы свойства. По умолчанию, 0.

*nIDHeaderSubTitle*<br/>
Идентификатор имени, которое будет размещено в месте расположения субтитров заголовка страницы свойства. По умолчанию, 0.

### <a name="remarks"></a>Примечания

Объект отображается после выполнения всех следующих условий:

- Страница была добавлена в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Функция [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [Create](../../mfc/reference/cpropertysheet-class.md#create) листа свойств была вызвана.

- Пользователь выбрал (подавив) эту страницу.

Звоните, `Construct` если один из других конструкторов класса не был вызван. Функция `Construct` члена является гибкой, поскольку вы можете оставить заявление параметра пустым, а затем указать несколько параметров и конструкцию в любой момент в коде.

Вы должны `Construct` использовать при работе с массивами, и вы должны вызвать `Construct` для каждого члена массива, чтобы членам данных были назначены правильные значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

## <a name="cpropertypagecpropertypage"></a><a name="cpropertypage"></a>CPropertyPage::CPropertyPage

Формирует объект `CPropertyPage`.

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Идентификатор шаблона, используемого для этой страницы.

*nIDCaption*<br/>
Идентификатор имени, которое будет размещено на вкладке для этой страницы. Если 0, имя будет взято из шаблона диалога для этой страницы.

*dwSize*<br/>
*lpszTemplateName* Уотчку строки, содержащей имя шаблона для этой страницы. Не может быть NULL.

*nIDHeaderTitle*<br/>
Идентификатор имени, которое будет размещено в месте заголовка страницы свойства.

*nIDHeaderSubTitle*<br/>
Идентификатор имени, которое будет размещено в месте расположения субтитров заголовка страницы свойства.

### <a name="remarks"></a>Примечания

Объект отображается после выполнения всех следующих условий:

- Страница была добавлена в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Функция [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [Create](../../mfc/reference/cpropertysheet-class.md#create) листа свойств была вызвана.

- Пользователь выбрал (подавив) эту страницу.

Если у вас есть несколько параметров (например, если вы используете `CPropertyPage`массив), используйте [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) вместо .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

## <a name="cpropertypagegetpsp"></a><a name="getpsp"></a>CPropertyPage::GetPSP

Извлекает структуру Windows [PROPSHEETPAGE,](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) связанную с объектом. `CPropertyPage`

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `PROPSHEETPAGE` структуру.

## <a name="cpropertypagem_psp"></a><a name="m_psp"></a>CPropertyPage:::m_psp

`m_psp`представляет собой структуру, члены которой хранят характеристики [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2).

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Примечания

Используйте эту структуру для инициализации внешнего вида страницы свойств после ее построения.

Более подробную информацию об этой структуре, `PROPSHEETPAGE` включая список ее членов, можно узнать в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

## <a name="cpropertypageonapply"></a><a name="onapply"></a>Страница недвижимости::OnApply

Эта функция участника вызывается инфраструктурой, когда пользователь выбирает кнопку OK или кнопку Apply Now.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если изменения будут приняты; в противном случае 0.

### <a name="remarks"></a>Примечания

Когда фреймворк вызывает эту функцию, изменения, внесенные на всех страницах `OnApply` свойств в листе свойств, принимаются, лист свойств сохраняет фокус и возвращает TRUE (значение 1). Прежде `OnApply` чем можно вызвать по фреймворку, вы должны вызвать [SetModified](#setmodified) и установить его параметр к TRUE. Это активирует кнопку Apply Now, как только пользователь вносит изменения на странице свойств.

Переуверьте эту функцию участника, чтобы указать, какие действия принимает программа, когда пользователь нажимает кнопку Apply Now. При переопределением функция должна вернутьСЯ true, чтобы принять изменения и FALSE, чтобы предотвратить вступления изменений в силу.

Реализация вызовов `OnApply` `OnOK`по умолчанию.

Для получения дополнительной информации об уведомлениях, отправляемых при нажатии на кнопку Apply Now или OK в листе свойств, с [PSN_APPLYм.](/windows/win32/Controls/psn-apply)

### <a name="example"></a>Пример

  Смотрите пример [cPropertyPage::OnOK](#onok).

## <a name="cpropertypageoncancel"></a><a name="oncancel"></a>Страница недвижимости::Отмена

Эта функция участника вызывается инфраструктурой при выборе кнопки «Отмена».

```
virtual void OnCancel();
```

### <a name="remarks"></a>Примечания

Переизбь эту функцию участника для выполнения действий кнопки «Отмена». По умолчанию отменяется все внесенные изменения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

## <a name="cpropertypageonkillactive"></a><a name="onkillactive"></a>CPropertyPage::OnKillActive

Эта функция участника вызывается инфраструктурой, когда страница больше не является активной страницей.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если данные были обновлены успешно, в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника для выполнения специальных задач проверки данных.

Реализация этой функции элемента по умолчанию копирует настройки от элементов управления на странице свойств к переменным элемента страницы свойств. Если данные не были успешно обновлены из-за ошибки проверки данных диалогов (DDV), страница сохраняет фокус.

После успешного возврата функции участника платформа вызовет функцию [OnOK](#onok) страницы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

## <a name="cpropertypageonok"></a><a name="onok"></a>Страница имущества::OnOK

Эта функция участника вызывается инфраструктурой, когда пользователь выбирает кнопку OK или Apply Now сразу после вызова [платформы OnKillActive.](#onkillactive)

```
virtual void OnOK();
```

### <a name="remarks"></a>Примечания

Когда пользователь выбирает кнопку OK или кнопку Apply Now, платформа получает [уведомление PSN_APPLY](/windows/win32/Controls/psn-apply) со страницы свойств. Вызов не `OnOK` будет сделан, если вы позвоните [CPropertySheet::PressButton,](../../mfc/reference/cpropertysheet-class.md#pressbutton) потому что страница свойств не отправляет уведомление в этом случае.

Переопределить эту функцию участника для реализации дополнительного поведения, характерного для активной страницы, когда пользователь увольняет весь лист свойств.

Реализация этой функции участника по умолчанию помечает страницу как `OnKillActive` «чистую», чтобы отразить, что данные были обновлены в функции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

## <a name="cpropertypageonquerycancel"></a><a name="onquerycancel"></a>CPropertyPage::On-cqueryCancel

Эта функция участника вызывается инфраструктурой, когда пользователь нажимает кнопку «Отмена» и до того, как действие отмены произошло.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE, чтобы предотвратить операцию отмены или TRUE, чтобы позволить это.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать действие, предпринимаетепрограмму программы, когда пользователь нажимает кнопку «Отмена».

По умолчанию `OnQueryCancel` реализация возвращает TRUE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

## <a name="cpropertypageonreset"></a><a name="onreset"></a>CPropertyPage::OnReset

Эта функция участника вызывается фректовой, когда пользователь выбирает кнопку Отмена.

```
virtual void OnReset();
```

### <a name="remarks"></a>Примечания

При вызове этой функции фреймворк удаляет изменения на всех страницах свойств, внесенных пользователем, ранее выбравимимом кнопку Apply Now, отбрасываются, а лист свойств сохраняет фокус.

Переувисляйте эту функцию участника, чтобы указать, какие действия принимает программа, когда пользователь нажимает кнопку «Отмена».

Реализация по `OnReset` умолчанию ничего не делает.

### <a name="example"></a>Пример

  Смотрите пример [cPropertyPage::OnCancel](#oncancel).

## <a name="cpropertypageonsetactive"></a><a name="onsetactive"></a>Страница недвижимости::OnSetActive

Эта функция участника вызывается инфраструктурой, когда страница выбрана пользователем и становится активной страницей.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если страница была успешно установлена активная; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника для выполнения задач при активации страницы. Переопределение этой функции участника обычно называется версией по умолчанию после обновления данных, чтобы позволить ей обновлять элементы управления страницой новыми данными.

Реализация по умолчанию создает окно для страницы, если она не была создана ранее, и делает ее активной страницей.

### <a name="example"></a>Пример

  Смотрите пример [для CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).

## <a name="cpropertypageonwizardback"></a><a name="onwizardback"></a>CPropertyPage::TheWizardBack

Эта функция участника вызывается инфраструктурой, когда пользователь нажимает на кнопку «Назад» в мастере.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Возвращаемое значение

0 для автоматического продвижения на следующую страницу; -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, кроме следующей, верните отображаемый идентификатор диалога.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать некоторые действия, которые пользователь должен предпринять при нажатии кнопки "Назад".

Для получения дополнительной информации о том, как сделать лист свойств типа мастера, [см.](../../mfc/reference/cpropertysheet-class.md#setwizardmode)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

## <a name="cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>CPropertyPage::InWizardFinish

Эта функция участника вызывается инфраструктурой, когда пользователь нажимает на кнопку «Завершение» в мастере.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лист свойства уничтожен, когда мастер заканчивает; в противном случае ноль.

### <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку **«Завершение»** в мастере, фреймворк вызывает эту функцию; когда `OnWizardFinish` возвращается TRUE (ненулевое значение), лист свойства может быть уничтожен (но на самом деле не уничтожен). Звоните, `DestroyWindow` чтобы уничтожить лист имущества. Не `DestroyWindow` звоните `OnWizardFinish`из; это приведет к куче коррупции или других ошибок.

Вы можете переопределить эту функцию участника, чтобы указать некоторые действия, которые пользователь должен предпринять при нажатии кнопки «Финиш». При перегоне этой функции верните FALSE, чтобы предотвратить уничтожение листа имущества.

Для получения дополнительной информации об уведомлениях, отправляемых при нажатии кнопки "Завершение" в листе свойств мастера, см. [PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish) в SDK Windows.

Для получения дополнительной информации о том, как сделать лист свойств типа мастера, [см.](../../mfc/reference/cpropertysheet-class.md#setwizardmode)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

## <a name="cpropertypageonwizardnext"></a><a name="onwizardnext"></a>CPropertyPage::WizardNext

Эта функция участника вызывается инфраструктурой, когда пользователь нажимает на кнопку Next в мастере.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Возвращаемое значение

0 для автоматического продвижения на следующую страницу; -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, кроме следующей, верните отображаемый идентификатор диалога.

### <a name="remarks"></a>Примечания

Переопределить эту функцию участника, чтобы указать некоторые действия, которые пользователь должен предпринять при нажатии кнопки Next.

Для получения дополнительной информации о том, как сделать лист свойств типа мастера, [см.](../../mfc/reference/cpropertysheet-class.md#setwizardmode)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

## <a name="cpropertypagequerysiblings"></a><a name="querysiblings"></a>CPropertyPage::Квиривы

Вызов ими функции участника для переадресовывания сообщения на каждую страницу в листе свойств.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
Определяет дополнительную информацию, зависящая от сообщений.

*lParam*<br/>
Определяет дополнительную информацию, зависящая от сообщений

### <a name="return-value"></a>Возвращаемое значение

Значение ненулевого со страницы в листе свойства или 0, если все страницы возвращают значение 0.

### <a name="remarks"></a>Примечания

Если страница возвращает ненулевое значение, лист свойств не отправляет сообщение на последующие страницы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

## <a name="cpropertypagesetmodified"></a><a name="setmodified"></a>CPropertyPage::SetModified

Вызовите эту функцию участника, чтобы включить или отключить кнопку Apply Now, основываясь на том, следует ли применять настройки на странице свойств к соответствующему внешнему объекту.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Параметры

*bИзменено*<br/>
TRUE, чтобы указать, что настройки страницы свойств были изменены с момента последнего применения; FALSE указать, что настройки страницы свойств были применены или должны быть проигнорированы.

### <a name="remarks"></a>Примечания

Платформа отслеживает, какие страницы являются «грязными», то есть страницами свойств, для которых вы вызвали `SetModified( TRUE )`. Кнопка Apply Now всегда будет `SetModified( TRUE )` включена, если вы позвоните на одну из страниц. Кнопка Apply Now будет отключена при вызове `SetModified( FALSE )` одной из страниц, но только в том случае, если ни одна из других страниц не является «грязной».

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
