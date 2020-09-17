---
title: Класс CMFCPropertyGridProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 0ce3321968f0c29ce3b946f6127e4435b531c422
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360584"
---
# <a name="cmfcpropertygridfileproperty-class"></a>Класс CMFCPropertyGridProperty

Класс `CMFCPropertyGridFileProperty` поддерживает элемент управления списком свойств, который открывает диалоговую коробку выбора файлов.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertyGridFileНедвижимость::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Формирует объект `CMFCPropertyGridFileProperty`.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|`CMFCPropertyGridFileProperty::OnClickButton`|(Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a>CMFCPropertyGridFileНедвижимость::CMFCPropertyGridFileProperty

Формирует объект `CMFCPropertyGridFileProperty`.

```
CMFCPropertyGridFileProperty(
    const CString& strName,
    BOOL bOpenFileDialog,
    const CString& strFileName,
    LPCTSTR lpszDefExt=NULL,
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,
    LPCTSTR lpszFilter=NULL,
    LPCTSTR lpszDescr=NULL,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*strName*<br/>
[in] Имя свойства.

*bOpenFileДиалог*<br/>
(в) TRUE, чтобы открыть окно диалога **Open File;** FALSE, чтобы открыть диалоговый ящик **Save File.**

*strFileName*<br/>
(в) Начальное имя файла.

*lpszDefExt*<br/>
(в) Строка одного или нескольких расширений имени файла. Значение по умолчанию — NULL.

*dwFlags*<br/>
(в) Флаги коробки Dialog. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

*lpszFilter*<br/>
(в) Строка одного или нескольких фильтров файлов. Значение по умолчанию — NULL.

*lpszDescr*<br/>
(в) Описание элемента свойства. Значение по умолчанию — NULL.

*dwData*<br/>
(в) Данные, связанные с элементом свойства. Например, 32-разрядное целое число или указатель на другие данные. Значение по умолчанию — 0.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Полный список доступных флагов можно найти в [структуре OPENFILENAME.](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)

### <a name="example"></a>Пример

В этом примере демонстрируется создание объекта с помощью конструктора класса `CMFCPropertyGridFileProperty`. Этот пример является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
