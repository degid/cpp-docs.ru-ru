---
title: Класс CClientDC
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: abe8a3220fd37a0375fcf37504c715edf4c6962e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352297"
---
# <a name="cclientdc-class"></a>Класс CClientDC

Заботится о вызове функций Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) во время строительства и [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) во время разрушения.

## <a name="syntax"></a>Синтаксис

```
class CClientDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|Строит объект, `CClientDC` подключенный `CWnd`к .|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|HWND окна, для которого это `CClientDC` действительно.|

## <a name="remarks"></a>Примечания

Это означает, что контекст `CClientDC` устройства, связанный с объектом, является областью клиента окна.

Для получения `CClientDC`дополнительной [информации](../../mfc/device-contexts.md)о, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a>CClientDC::CClientDC

Строит `CClientDC` объект, который получает доступ к клиентской области [CWnd,](../../mfc/reference/cwnd-class.md) на который указывает *pWnd.*

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Окно, к которой будет доступ клиентский объект контекста устройства.

### <a name="remarks"></a>Примечания

Конструктор вызывает функцию Windows [GetDC.](/windows/win32/api/winuser/nf-winuser-getdc)

Исключение (типа) `CResourceException`брошено, если `GetDC` вызов Windows не удается. Контекст устройства может быть недоступен, если Windows уже выделила все доступные контексты устройства. Ваше приложение конкурирует за пять общих контекстов отображения, доступных в любой момент времени под Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a>CClientDC::m_hWnd

`HWND` Указатель, `CWnd` используемый для `CClientDC` построения объекта.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

*m_hWnd* является защищенной переменной.

### <a name="example"></a>Пример

  Смотрите пример [cClientDC::CClientDC](#cclientdc).

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
