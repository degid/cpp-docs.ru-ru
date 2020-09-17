---
title: Класс CMFCColorDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 1d4bd31d5095f572ee80f0357a2d7526482f1caa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752542"
---
# <a name="cmfccolordialog-class"></a>Класс CMFCColorDialog

Класс `CMFCColorDialog` представляет собой диалоговую коробку выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorДиалог::CMFCColorДиалог](#cmfccolordialog)|Формирует объект `CMFCColorDialog`.|
|`CMFCColorDialog::~CMFCColorDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorДиалог::GetColor](#getcolor)|Возвращает выбранный цвет текущего.|
|[CMFCColorДиалог::GetPalette](#getpalette)|Возвращает цветовую палитру.|
|`CMFCColorDialog::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. Для синтаксиса и получения дополнительной информации см. [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CDialogEx::PreTranslateMessage`.)|
|[CMFCColorДиалог::RebuildPalette](#rebuildpalette)|Получает палитру из системной палитры.|
|[CMFCColorДиалог::SetCurrentColor](#setcurrentcolor)|Устанавливает текущий выбранный цвет.|
|[CMFCColorДиалог::SetNewColor](#setnewcolor)|Устанавливает цвет, наиболее эквивалентный указанному значению RGB.|
|[CMFCColorДиалог::SetPageOne](#setpageone)|Выберите значение RGB для первой страницы свойства.|
|[CMFCColorДиалог::SetPageTwo](#setpagetwo)|Выбирает значение RGB для второй страницы свойства.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|`m_bIsMyPalette`|ПРАВДА, если цвет выбор диалоговая коробка использует свою собственную цветовую палитру, `CMFCColorDialog` или FALSE, если диалоговая коробка использует палитру, которая указана в конструкторе.|
|`m_bPickerMode`|TRUE в то время как пользователь выбирает цвет из окна диалога выбора; в противном случае, FALSE.|
|`m_btnColorSelect`|Кнопка цвета, выбранная пользователем.|
|`m_CurrentColor`|Выбранный в настоящее время цвет.|
|`m_hcurPicker`|Курсор, который используется для выбора цвета.|
|`m_NewColor`|Перспективный выбранный цвет, который может быть постоянно выбран или возвращен к первоначальному цвету.|
|`m_pColourSheetOne`|Указатель на первую страницу свойств листа свойства выбора цвета.|
|`m_pColourSheetTwo`|Указатель на вторую страницу свойства листа свойства выбора цвета.|
|`m_pPalette`|Текущая логическая палитра.|
|`m_pPropSheet`|Указатель на лист свойств для окна диалога выбора цвета.|
|`m_wndColors`|Объект управления сборщиком цветов.|
|`m_wndStaticPlaceHolder`|Статический элемент управления, который является заполнителем для листа свойства сборщика цветов.|

## <a name="remarks"></a>Примечания

Коробка диалога выбора цвета отображается как лист свойств с двумя страницами. На первой странице вы выбираете стандартный цвет из системной палитры; на второй странице вы выбираете пользовательский цвет.

Вы можете `CMFCColorDialog` построить объект на `DoModal`стеке, а затем вызвать, передавая первоначальный цвет в качестве параметра конструктору. `CMFCColorDialog` Затем в диалоговом поле выбора цвета создается несколько объектов [класса CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md) для обработки каждой цветовой палитры.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Пример

Ниже приводится следующий пример, как настроить цветовой диалог `CMFCColorDialog` с помощью различных методов в классе. На примере показано, как установить ток и новые цвета диалога, а также как установить красные, зеленые и синие компоненты выбранного цвета на двух страницах свойств цветового диалога. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxcolordialog.h

## <a name="cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>CMFCColorДиалог::CMFCColorДиалог

Формирует объект `CMFCColorDialog`.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>Параметры

*clrInit*<br/>
(в) Выбор цвета по умолчанию. Если значение не указано, по умолчанию RGB (0,0,0) (черный).

*dwFlags*<br/>
[in] Зарезервировано.

*pParentWnd*<br/>
(в) Указатель на родительское или владельца окна диалогового окна.

*hPal*<br/>
(в) Ручка к цветовой палитре.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfccolordialoggetcolor"></a><a name="getcolor"></a>CMFCColorДиалог::GetColor

Извлекает цвет, выбранный пользователем из цветового диалога.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) содержащее информацию О РГБ для цвета, выбранного в цветном диалоговом поле.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова метода. `DoModal`

## <a name="cmfccolordialoggetpalette"></a><a name="getpalette"></a>CMFCColorДиалог::GetPalette

Получает цветовую палитру, которая доступна в текущем цветовом диалоге.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPalette` объект, указанный `CMFCColorDialog` в конструкторе.

### <a name="remarks"></a>Примечания

Цветовая палитра определяет цвета, которые пользователь может выбрать.

## <a name="cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorДиалог::RebuildPalette

Получает палитру из системной палитры.

```cpp
void RebuildPalette();
```

## <a name="cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CMFCColorДиалог::SetCurrentColor

Устанавливает текущий цвет диалогового окна.

```cpp
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>Параметры

*Rgb*<br/>
(в) Значение цвета RGB

### <a name="remarks"></a>Примечания

## <a name="cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>CMFCColorДиалог::SetNewColor

Устанавливает текущий цвет к цвету в текущей палитре, которая наиболее похожа.

```cpp
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>Параметры

*Rgb*<br/>
(в) [COLORREF,](/windows/win32/gdi/colorref) который определяет цвет RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolordialogsetpageone"></a><a name="setpageone"></a>CMFCColorДиалог::SetPageOne

Явно опознавательный цвет красный, зеленый и синий компоненты выбранного цвета на первой странице свойств цветового диалога.

```cpp
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

*R*<br/>
(в) Определяет красный компонент значения RGB.

*Г*<br/>
(в) Определяет зеленый компонент значения RGB.

*B*<br/>
(в) Определяет синий компонент значения RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>CMFCColorДиалог::SetPageTwo

Явно опознавательный цвет красный, зеленый и синий компоненты выбранного цвета на второй странице свойства цветового диалога.

```cpp
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

*R*<br/>
(в) Определяет красный компонент значения RGB

*Г*<br/>
(в) Определяет зеленый компонент значения RGB

*B*<br/>
(в) Определяет синий компонент значения RGB

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)
