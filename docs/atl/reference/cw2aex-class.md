---
title: Класс CW2AEX
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 849cbe5c26d7c7af7a8925a26057b5777554471d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330455"
---
# <a name="cw2aex-class"></a>Класс CW2AEX

Этот класс используется макросами преобразования строк и CT2AEX, CW2TEX, CW2CTEX и CT2CAEX, а также typedef CW2A.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Конструктор.|
|[CW2AEX::CW2AEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::оператор LPSTR](#operator_lpstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|
|[CW2AEX:::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованной строки.|

## <a name="remarks"></a>Примечания

Если не требуется дополнительная функциональность, используйте CT2AEX, CW2TEX, CW2CTEX, CT2CAEX или CW2A в коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик, чтобы поместиться в статический буфер, класс выделяет память с помощью **malloc,** освобождая память, когда объект выходит из области. Это гарантирует, что, в отличие от макросов преобразования текста, доступных в предыдущих версиях ATL, этот класс безопасен для использования в циклах и что он не будет переполнять стек.

Если класс пытается выделить память на кучу и не `AtlThrow` удается, он будет звонить с аргументом E_OUTOFMEMORY.

По умолчанию классы и макросы конверсии ATL используют для преобразования страницу кода ANSI текущего потока. Если требуется переопределить это поведение для определенного преобразования, укажите страницу кода в качестве второго параметра для конструктора для класса.

Следующие макросы основаны на этом классе:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Следующий тип основан на этом классе:

- CW2A

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="cw2aexcw2aex"></a><a name="cw2aex"></a>CW2AEX::CW2AEX

Конструктор.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Страница кода, используемая для выполнения преобразования. Более подробную информацию можно узнать о обсуждении параметров страницы кода для функции Windows SDK [MultiByteToWideChar.](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)

### <a name="remarks"></a>Примечания

Выделяет буфер, используемый в процессе перевода.

## <a name="cw2aexcw2aex"></a><a name="dtor"></a>CW2AEX::CW2AEX

Деструктор

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

## <a name="cw2aexm_psz"></a><a name="m_psz"></a>CW2AEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPSTR m_psz;
```

## <a name="cw2aexm_szbuffer"></a><a name="m_szbuffer"></a>CW2AEX:::m_szBuffer

Статический буфер, используемый для хранения преобразованной строки.

```
char m_szBuffer[t_nBufferLength];
```

## <a name="cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CW2AEX::оператор LPSTR

Оператор конверсии.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
