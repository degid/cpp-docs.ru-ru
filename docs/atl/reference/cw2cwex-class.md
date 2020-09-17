---
title: Класс CW2CWEX
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 07dd0319586054403d8ed0c8efc813b4061e355a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330436"
---
# <a name="cw2cwex-class"></a>Класс CW2CWEX

Этот класс используется макросами преобразования строкc CW2CTEX и CT2CWEX, а также typedef CW2W.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|Конструктор.|
|[CW2CWEX:: »CW2CWEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CW2CWEX:Оператор LPCWSTR](#operator_lpcwstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|

## <a name="remarks"></a>Примечания

Если не требуется дополнительная функциональность, используйте CW2CTEX, CT2CWEX или CW2W в коде.

Этот класс безопасен для использования в циклах и не будет переполнять стек. По умолчанию классы и макросы конверсии ATL используют для преобразования страницу кода ANSI текущего потока.

Следующие макросы основаны на этом классе:

- CW2CTEX

- CT2CWEX

Следующий тип основан на этом классе:

- CW2W

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX

Конструктор.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Кодовая страница. Не используется в этом классе.

### <a name="remarks"></a>Примечания

Выделяет буфер, используемый в процессе перевода.

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX:: »CW2CWEX

Деструктор

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a>CW2CWEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX:Оператор LPCWSTR

Оператор конверсии.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPCWSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
