---
title: Структура CMFCTabToolTipInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: a507d1e69b3524074e50fde0e87fc5ebb6e5ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367344"
---
# <a name="cmfctabtooltipinfo-structure"></a>Структура CMFCTabToolTipInfo

Эта структура предоставляет информацию о вкладке MDI, над которым зависает пользователь.

## <a name="syntax"></a>Синтаксис

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Определяет индекс управления вкладками.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Указатель на элемент управления вкладки.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Текст подсказки.|

## <a name="remarks"></a>Примечания

Указатель на `CMFCTabToolTipInfo` структуру передается как параметр AFX_WM_ON_GET_TAB_TOOLTIP сообщения. Это сообщение генерируется при включении вкладок MDI и нависает над управлением вкладками.

## <a name="example"></a>Пример

Ниже приводится `CMFCTabToolTipInfo` следующий пример, как используется в [MDITabsDemo Образец: MFC Tabbed MDI приложение](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbasetabctrl.h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex

Определяет индекс управления вкладками.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Примечания

Индекс вкладки, над которой зависает пользователь.

### <a name="example"></a>Пример

Ниже приводится `m_nTabIndex` следующий пример, как используется в [MDITabsDemo Образец: MFC Tabbed MDI приложение](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd

Указатель на элемент управления вкладки.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Пример

Ниже приводится `m_pTabWnd` следующий пример, как используется в [MDITabsDemo Образец: MFC Tabbed MDI приложение](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText

Текст подсказки.

```
CString m_strText;
```

### <a name="remarks"></a>Примечания

Если строка пуста, набор инструментов не отображается.

### <a name="example"></a>Пример

Ниже приводится `m_strText` следующий пример, как используется в [MDITabsDemo Образец: MFC Tabbed MDI приложение](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
