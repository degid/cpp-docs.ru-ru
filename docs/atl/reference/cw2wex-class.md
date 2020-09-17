---
title: Класс CW2WEX
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: b116775a595f9fb3612d46e19526cf1396f85002
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330351"
---
# <a name="cw2wex-class"></a>Класс CW2WEX

Этот класс используется макросами преобразования строк cW2TEX и CT2WEX, а также typedef CW2W.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CW2WEX:CW2WEX](#cw2wex)|Конструктор.|
|[CW2WEX:::CW2WEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CW2WEX:Оператор LPWSTR](#operator_lpwstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CW2WEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|
|[CW2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованной строки.|

## <a name="remarks"></a>Примечания

Если не требуется дополнительная функциональность, используйте CW2TEX, CT2WEX или CW2W в коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик, чтобы поместиться в статический буфер, класс выделяет память с помощью **malloc,** освобождая память, когда объект выходит из области. Это гарантирует, что, в отличие от макросов преобразования текста, доступных в предыдущих версиях ATL, этот класс безопасен для использования в циклах и что он не будет переполнять стек.

Если класс пытается выделить память на кучу и не `AtlThrow` удается, он будет звонить с аргументом E_OUTOFMEMORY.

По умолчанию классы и макросы конверсии ATL используют для преобразования страницу кода ANSI текущего потока.

Следующие макросы основаны на этом классе:

- CW2TEX

- CT2WEX

Следующий тип основан на этом классе:

- CW2W

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX:CW2WEX

Конструктор.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Кодовая страница. Не используется в этом классе.

### <a name="remarks"></a>Примечания

Создает буфер, необходимый для перевода.

## <a name="cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX:::CW2WEX

Деструктор.

```
~CW2WEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

## <a name="cw2wexm_psz"></a><a name="m_psz"></a>CW2WEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a>CW2WEX::m_szBuffer

Статический буфер, используемый для хранения преобразованной строки.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX:Оператор LPWSTR

Оператор актерского состава.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPWSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
