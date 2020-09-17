---
title: Класс CMFCEditBrowseCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
ms.openlocfilehash: d542af4a87b6f0a33c0344d1d3da76980f8c1a91
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752377"
---
# <a name="cmfceditbrowsectrl-class"></a>Класс CMFCEditBrowseCtrl

Класс `CMFCEditBrowseCtrl` поддерживает управление просмотром редактирования, которое является редактирование текстового окна, которое дополнительно содержит кнопку просмотра. Когда пользователь нажимает кнопку обзора, элемент управления выполняет настраиваемое действие или отображает стандартное диалоговое окно, содержащее браузер файла или папки в браузере.

## <a name="syntax"></a>Синтаксис

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Конструктор по умолчанию.|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Включает или отсутсвий (скрывает) кнопку просмотра.|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Включает кнопку просмотра и помещает управление просмотром в режим *просмотра файлов.*|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Включает кнопку просмотра и помещает управление просмотром в режим *еде.*|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Возвращает текущий режим просмотра.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Вызывается инфраструктурой после элемента управления просмотром edit обновляется в результате действия просмотра.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Вызывается по системе после того, как пользователь нажимает кнопку просмотра.|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Перерисовывает текущий элемент управления просмотра реанивных веб-страниц.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Вызывается по рамке, чтобы нарисовать кнопку просмотра.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Вызывается в фреймворке, когда незаконное имя файла было внесено в элементуправления правки.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. Для синтаксиса и получения дополнительной информации см. [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Устанавливает пользовательское изображение для кнопки просмотра.|

## <a name="remarks"></a>Примечания

Используйте элемент управления просмотра, чтобы выбрать имя файла или папки. Дополнительно используйте элемент управления для выполнения пользовательских действий, таких как отображение диалогового окна. Вы можете отображать или не отображать кнопку просмотра, и вы можете применить пользовательские этикетки или изображения на кнопке.

*Режим просмотра* управления воспроизведением просматривать определяет, отображает ли он кнопку просмотра и какие действия происходят при нажатии кнопки. Для получения дополнительной [информации](#getmode) см.

Класс `CMFCEditBrowseCtrl` поддерживает следующие режимы.

- **пользовательский режим**

   Пользовательское действие выполняется, когда пользователь нажимает кнопку просмотра. Например, можно отобразить поле диалога, конкретное приложение.

- **файл режим**

   Стандартный диалоговый ящик выбора файлов отображается при нажатии кнопки просмотра.

- **режим папки**

   Стандартный диалоговый ящик выбора папки отображается при нажатии кнопки просмотра.

## <a name="how-to-specify-an-edit-browse-control"></a>Как-к: Укажите элемент управления просмотром edit

Выполните следующие шаги, чтобы включить элемент управления просмотром в приложении:

1. Если вы хотите реализовать пользовательский режим просмотра, `CMFCEditBrowseCtrl` получить свой собственный класс из класса, а затем переопределить [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) метод. В переиденном методе выполните пользовательское действие просмотра и обновите элемент управления просмотра с результатом.

1. Встраивайте `CMFCEditBrowseCtrl` объект или выведенное элементуправления просмотра в объект родительского окна.

1. Если вы используете **Класс Мастера** для создания диалогового `CEdit`окна, добавьте элемент управления () в форму диалогового окна. Кроме того, добавьте переменную для доступа к элементу управления в файле заголовка. В файле заголовка измените тип `CEdit` переменной с к `CMFCEditBrowseCtrl`. Управление просмотром веб-страниц будет создано автоматически. Если вы не используете **класс Мастера,** добавьте переменную `CMFCEditBrowseCtrl` в `Create` файл заголовка, а затем позвоните в его метод.

1. Если вы добавите элементарное управление просмотром в диалоговый ящик, используйте инструмент **ClassWizard** для настройки обмена данными.

1. Позвоните [enableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), или [EnableBrowseButton](#enablebrowsebutton) метод, чтобы установить режим просмотра и отобразить кнопку просмотра. Вызовите метод [GetMode,](#getmode) чтобы получить текущий режим просмотра.

1. Чтобы предоставить пользовательское изображение для кнопки просмотра, позвоните по методу [SetBrowseButtonImage](#setbrowsebuttonimage) или переопределить метод [OnDrawBrowseButton.](#ondrawbrowsebutton)

1. Чтобы удалить кнопку просмотра из управления просматривать, позвоните в метод [EnableBrowseButton](#enablebrowsebutton) с *параметраb bEnable,* установленным на FALSE.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Пример

Следующий пример показывает, как использовать два `CMFCEditBrowseCtrl` метода в классе: `EnableFolderBrowseButton` и `EnableFileBrowseButton`. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxeditbrowsectrl.h

## <a name="cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton

Отображает или не отображает кнопку просмотра на текущем элементе управления воспроизведением.

```cpp
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
TRUE для отображения кнопки просмотра; FALSE не отображать кнопку просмотра. Значение по умолчанию — TRUE.

*szLabel*<br/>
Метка, отображаемый на кнопке просмотра. Значение по умолчанию является **"...".**

### <a name="remarks"></a>Примечания

Если параметр *bEnable* является правдой, реализуйте специальное действие для выполнения при нажатии кнопки просмотра. Чтобы реализовать пользовательское действие, вычеркните класс из `CMFCEditBrowseCtrl` класса, а затем переизуйте его метод [OnBrowse.](#onbrowse)

Если параметр *bEnable* является правдой, режим `BrowseMode_Default`просмотра управления; в противном случае, режим просмотра `BrowseMode_None`. Для получения дополнительной информации о [GetMode](#getmode) режимах просмотра см.

## <a name="cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton

Отображает кнопку просмотра на текущем элементе управления просмотром и помещает элемент управления в режим *просмотра файлов.*

```cpp
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Параметры

*lpszDefExt*<br/>
Указывает расширение имени файла по умолчанию, используемое в диалоговом окне выбора файла. Значение по умолчанию — NULL.

*lpszFilter*<br/>
Указывает строку фильтра по умолчанию, используемую в диалоговом окне выбора файла. Значение по умолчанию — NULL.

*dwFlags*<br/>
Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

### <a name="remarks"></a>Примечания

Когда элемент управления "Обзор" находится в режиме поиска файлов, а пользователь нажимает кнопку обзора, элемент управления отображает стандартное диалоговое окно выбора файла.

Полный список доступных флагов можно найти в [структуре OPENFILENAME.](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)

## <a name="cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton

Отображает кнопку просмотра на текущем элементе управления воспроизведением и помещает управление в режим *просмотра папок.*

```cpp
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Примечания

Когда управление просмотром воспроизведения находится в режиме просмотра папок и пользователь нажимает кнопку просмотра, элемент управления отображает стандартный диалоговую будку выбора папки.

## <a name="cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>CMFCEditBrowseCtrl::GetMode

Извлекает режим просмотра текущего управления просмотром.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления, которое определяет текущий режим управления просмотром edit. Режим просмотра определяет, отображает ли фреймворк кнопку просмотра и какие действия происходят, когда пользователь нажимает на эту кнопку.

В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Описание|
|-----------|-----------------|
|`BrowseMode_Default`|**пользовательский режим**. Выполняется действие, определяемое программистом.|
|`BrowseMode_File`|**файл режиме**. Отображается стандартный диалоговый ящик файлового браузера.|
|`BrowseMode_Folder`|**режим папки**. Отображается стандартная папка браузера диалоговая коробка.|
|`BrowseMode_None`|Кнопка просмотра не отображается.|

### <a name="remarks"></a>Примечания

По умолчанию `CMFCEditBrowseCtrl` объект инициализирован в `BrowseMode_None` режиме. Измените режим просмотра с помощью методов [CMFCEditBrowseCtrl::EnableBrowseButton,](#enablebrowsebutton) [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)и [CMFCEditBrowseCtrl::EnableFolderBrowseButton.](#enablefolderbrowsebutton)

## <a name="cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate

Вызывается инфраструктурой после элемента управления просмотром edit обновляется в результате действия просмотра.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе для реализации пользовательского действия.

## <a name="cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse

Вызывается по системе после того, как пользователь нажимает кнопку просмотра управления просмотром.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Примечания

Используйте этот метод для выполнения пользовательского кода, когда пользователь нажимает кнопку просмотра управления воспроизведением. Вычеркните `CMFCEditBrowseCtrl` свой собственный `OnBrowse` класс из класса и переизуйте его метод. В этом методе реализуйте пользовательское действие просмотра и дополнительно обновите текстовое поле управления редактированием. В приложении используйте метод [EnableBrowseButton,](#enablebrowsebutton) чтобы поместить элемент управления просмотром в пользовательском режиме *просмотра.*

## <a name="cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout

Перерисовывает текущий элемент управления просмотра реанивных веб-страниц.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод при изменении элемента управления просмотром. Для получения дополнительной информации, [см CMFCEditBrowseCtrl::GetMode](#getmode).

## <a name="cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton

Вызывается рамкой, чтобы нарисовать кнопку просмотра на элементуправления просмотра.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства.

*Rect*<br/>
Ограничивающий прямоугольник кнопки просмотра.

*bIsButtonpressed*<br/>
TRUE, если кнопка нажата; в противном случае, FALSE.

*bIsButtonHot*<br/>
TRUE, если кнопка выделена; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Переопределить эту функцию в производном классе, чтобы настроить внешний вид кнопки просмотра.

## <a name="cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage

Устанавливает пользовательское изображение на кнопке просмотра управления просмотром.

```cpp
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Ручка иконы.

*hBitmap*<br/>
Ручка бит-карты.

*uiBmpResId*<br/>
Идентификатор ресурса битной карты.

*bAutoDestroy*<br/>
TRUE удалить указанную иконку или бит-карту, когда этот метод выходит; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы применить пользовательское изображение к кнопке просмотра. По умолчанию фреймворк получает стандартное изображение, когда элемент управления воспроизведения веб-страниц находится в режиме *просмотра файлов* или *папок.*

## <a name="cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName

Вызывается в фреймворке, когда незаконное имя файла было внесено в элементуправления правки.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Параметры

*strFileName*<br/>
Уточняется незаконное имя файла.

### <a name="return-value"></a>Возвращаемое значение

Если это имя файла не может быть передано далее в диалог файла. В этом случае фокус возвращается к управлению редактированием, и пользователь должен продолжить редактирование. Реализация по умолчанию отображает окно сообщений, сообщающее пользователю о незаконном имени файла, и возвращает FALSE. Вы можете переопределить этот метод, исправить имя файла и вернуть TRUE для дальнейшей обработки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
