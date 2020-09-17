---
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: b9eddca85d66f4978e1b33299ca655cd880cf45e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181152"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Блок, относящийся только к системам Microsoft**

Добавляет символы в конец объекта `_bstr_t` или объединяет две строки.

## <a name="syntax"></a>Синтаксис

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Параметры

*s1*<br/>
Объект `_bstr_t` .

*s2*<br/>
Многобайтовая строка.

*S3*<br/>
Строка Юникода.

## <a name="remarks"></a>Примечания

Эти операторы выполняют объединение строк:

- **operator + = (**  *S1*  **)** Добавляет символы в инкапсулированном `BSTR` *S1* в конец инкапсулированного `BSTR`объекта.

- **operator + (**  *S1*  **)** Возвращает новый `_bstr_t`, сформированный путем сцепления `BSTR` этого объекта с объектом *S1*.

- **operator + (**  *S2*  **&#124;**  *S1*  **)** Возвращает новый `_bstr_t`, сформированный путем сцепления многобайтовой строки *S2*, преобразованной в Юникод, с `BSTR`, инкапсулированным в *S1*.

- **оператор + (**  *S3* **,**  *S1*  **)** Возвращает новый `_bstr_t`, сформированный путем сцепления *строки в* юникоде с `BSTR`, инкапсулированным в *S1*.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)
