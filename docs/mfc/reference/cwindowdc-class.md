---
title: Класс CWindowDC
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 89a822280ddebca942016f9a3a334a7128d8456a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371984"
---
# <a name="cwindowdc-class"></a>Класс CWindowDC

Производное от `CDC`.

## <a name="syntax"></a>Синтаксис

```
class CWindowDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|Формирует объект `CWindowDC`.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|HWND, к `CWindowDC` которому это прилагается.|

## <a name="remarks"></a>Примечания

Вызывает функцию Windows [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)во время строительства и [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) во время разрушения. Это означает, `CWindowDC` что объект получает доступ ко всей площади экрана [CWnd](../../mfc/reference/cwnd-class.md) (как клиент, так и неклиентобласти).

Для получения дополнительной `CWindowDC`информации об использовании см. [Device Contexts](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Требования

Заголовок: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a>CWindowDC::CWindowDC

Строит `CWindowDC` объект, который получает доступ ко всей области экрана `CWnd` (как клиента, так и неклиента) объекта, на который указывает *pWnd.*

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Окно, к которой будет доступ клиент, к объекту-контексту устройства будет.

### <a name="remarks"></a>Примечания

Конструктор вызывает функцию Windows [GetWindowDC.](/windows/win32/api/winuser/nf-winuser-getwindowdc)

Исключение (типа) `CResourceException`брошено, если `GetWindowDC` вызов Windows не удается. Контекст устройства может быть недоступен, если Windows уже выделила все доступные контексты устройства. Ваше приложение конкурирует за пять общих контекстов отображения, доступных в любой момент времени под Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a>CWindowDC::m_hWnd

HWND указателя `CWnd` используется для построения `CWindowDC` объекта.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

`m_hWnd`защищенная переменная типа HWND.

### <a name="example"></a>Пример

  Смотрите пример [CWindowDC::CWindowDC](#cwindowdc).

## <a name="see-also"></a>См. также раздел

[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
