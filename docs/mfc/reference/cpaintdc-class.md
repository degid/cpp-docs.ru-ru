---
title: Класс CPaintDC
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: 55342b03454a6dba07bc10ea5f0464c34e0e8db3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374779"
---
# <a name="cpaintdc-class"></a>Класс CPaintDC

Класс «устройство-контекст», полученный из [CDC.](../../mfc/reference/cdc-class.md)

## <a name="syntax"></a>Синтаксис

```
class CPaintDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPaintDC:CPaintDC](#cpaintdc)|Строит подключенный `CPaintDC` к указанному [CWnd.](../../mfc/reference/cwnd-class.md)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|Содержит [PAINTSTRUCT,](/windows/win32/api/winuser/ns-winuser-paintstruct) используемый для покраски клиентской области.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|HWND, к `CPaintDC` которому прилагается этот объект.|

## <a name="remarks"></a>Примечания

Он выполняет [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) во время строительства и [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) во время разрушения.

Объект `CPaintDC` может использоваться только при [WM_PAINT](/windows/win32/gdi/wm-paint) ответе на `OnPaint` WM_PAINT сообщение, как правило, в функции обработчика сообщений.

Для получения дополнительной `CPaintDC`информации об использовании см. [Device Contexts](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a>CPaintDC:CPaintDC

Строит `CPaintDC` объект, подготавливает окно приложения для покраски и хранит структуру [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) в переменной [m_ps](#m_ps) члена.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на `CWnd` объект, `CPaintDC` к которому принадлежит объект.

### <a name="remarks"></a>Примечания

Исключение (типа) `CResourceException`брошено, если вызов Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) не удается. Контекст устройства может быть недоступен, если Windows уже выделила все доступные контексты устройства. Ваше приложение конкурирует за пять общих контекстов отображения, доступных в любой момент времени под Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a>CPaintDC::m_hWnd

К `HWND` которому `CPaintDC` прилагается этот объект.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

*m_hWnd* является защищенной переменной типа HWND.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a>CPaintDC::m_ps

`m_ps`является общедоступной переменной типа [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct).

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Примечания

Это то, `PAINTSTRUCT` что передается и заполнены [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).

Содержит `PAINTSTRUCT` информацию, которую приложение использует для окраски `CPaintDC` клиентской области окна, связанной с объектом.

Обратите внимание, что вы можете получить `PAINTSTRUCT`доступ к устройству-контексту ручек через . Тем не менее, вы можете `m_hDC` получить доступ `CPaintDC` к ручке более непосредственно через переменную члена, которая наследует от CDC.

### <a name="example"></a>Пример

  Смотрите пример [CPaintDC::m_hWnd](#m_hwnd).

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
