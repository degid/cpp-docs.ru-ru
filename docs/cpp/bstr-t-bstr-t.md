---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 843d6aa0e04595143d7da585e95d58e97fe80db0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221839"
---
# <a name="_bstr_t_bstr_t"></a>_bstr_t::_bstr_t

**Блок, относящийся только к системам Microsoft**

Формирует объект `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t( ) throw( );
_bstr_t(
   const _bstr_t& s1
) throw( );
_bstr_t(
   const char* s2
);
_bstr_t(
   const wchar_t* s3
);
_bstr_t(
   const _variant_t& var
);
_bstr_t(
   BSTR bstr,
   bool fCopy
);
```

#### <a name="parameters"></a>Параметры

*S1*<br/>
Копируемый объект `_bstr_t`.

*S2*<br/>
Многобайтовая строка.

*S3*<br/>
Строка Юникода.

*var*<br/>
Объект [_variant_t](../cpp/variant-t-class.md) .

*bstr*<br/>
Существующий объект `BSTR`.

*фкопи*<br/>
Если **`false`** значение равно, аргумент *BSTR* присоединяется к новому объекту без создания копии путем вызова метода `SysAllocString` .

## <a name="remarks"></a>Примечания

В следующей таблице описываются конструкторы объекта `_bstr_t`.

|Конструктор|Описание|
|-----------------|-----------------|
|`_bstr_t( )`|Конструирует объект по умолчанию `_bstr_t` , инкапсулирующий `BSTR` объект null.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Создает объект `_bstr_t` как копию другого объекта.<br /><br /> Это *неполная* копия, которая увеличивает счетчик ссылок инкапсулированного `BSTR` объекта, а не создает новый.|
|`_bstr_t( char*`  `s2`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.<br /><br /> Этот конструктор конструктор сначала преобразует многобайтовую строку в строку Юникода.|
|`_bstr_t( wchar_t*`  `s3`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.|
|`_bstr_t( _variant_t&`  `var`  `)`|Создает объект `_bstr_t` из объекта `_variant_t`, предварительно получив объект `BSTR` из инкапсулированного объекта VARIANT.|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Создает объект `_bstr_t` из существующего объекта `BSTR` (а не из строки `wchar_t*`). Если *фкопи* имеет значение false, указанный `BSTR` объект присоединяется к новому объекту без создания новой копии с помощью `SysAllocString` .<br /><br /> С помощью этого конструктора функции-оболочки в заголовках библиотек типов инкапсулируют и получают право владения объектом `BSTR`, который был возвращен методом интерфейса.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _bstr_t](../cpp/bstr-t-class.md)<br/>
[Класс _variant_t](../cpp/variant-t-class.md)
