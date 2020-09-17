---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: 50c10eb4ff617f4bcdc69d2e1781a9920b9eb0e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233565"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Блок, относящийся только к системам Microsoft**

Формирует объект `_variant_t`.

## <a name="syntax"></a>Синтаксис

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект `VARIANT`, который необходимо скопировать в новый объект `_variant_t`.

*pVarSrc*<br/>
Указатель на `VARIANT` объект, который должен быть скопирован в новый `_variant_t` объект.

*var_t_Src*<br/>
Объект `_variant_t`, который необходимо скопировать в новый объект `_variant_t`.

*фкопи*<br/>
Если **`false`** задано значение, предоставленный `VARIANT` объект присоединяется к новому `_variant_t` объекту без создания новой копии с помощью `VariantCopy` .

*ISrc, sSrc*<br/>
Целочисленное значение, которое необходимо скопировать в новый объект `_variant_t`.

*втсрк*<br/>
`VARTYPE`Для нового `_variant_t` объекта.

*fltSrc, dblSrc*<br/>
Числовое значение, которое необходимо скопировать в новый объект `_variant_t`.

*цисрк*<br/>
Объект `CY`, который необходимо скопировать в новый объект `_variant_t`.

*бстрсрк*<br/>
Объект `_bstr_t`, который необходимо скопировать в новый объект `_variant_t`.

*strSrc, wstrSrc*<br/>
Строка, которую необходимо скопировать в новый объект `_variant_t`.

*бсрк*<br/>
**`bool`** Значение, которое должно быть скопировано в новый `_variant_t` объект.

*пиукновнсрк*<br/>
Указатель COM-интерфейса на объект VT_UNKNOWN, который должен быть инкапсулирован в новый `_variant_t` объект.

*пдиспсрк*<br/>
Указатель COM-интерфейса на объект VT_DISPATCH, который должен быть инкапсулирован в новый `_variant_t` объект.

*дексрк*<br/>
Значение `DECIMAL`, которое необходимо скопировать в новый объект `_variant_t`.

*бсрк*<br/>
Значение `BYTE`, которое необходимо скопировать в новый объект `_variant_t`.

*ксрк*<br/>
**`char`** Значение, которое должно быть скопировано в новый `_variant_t` объект.

*usSrc*<br/>
**`unsigned short`** Значение, которое должно быть скопировано в новый `_variant_t` объект.

*улсрк*<br/>
**`unsigned long`** Значение, которое должно быть скопировано в новый `_variant_t` объект.

*исрк*<br/>
**`int`** Значение, которое необходимо скопировать в новый `_variant_t` объект.

*uiSrc*<br/>
**`unsigned int`** Значение, которое необходимо скопировать в новый `_variant_t` объект.

*i8Src*<br/>
**`__int64`** Значение, которое необходимо скопировать в новый `_variant_t` объект.

*ui8Src*<br/>
Значение **__int64 без знака** , которое необходимо скопировать в новый `_variant_t` объект.

## <a name="remarks"></a>Примечания

- **_variant_t ()** Конструирует пустой `_variant_t` объект `VT_EMPTY` .

- **_variant_t (variant&** *варсрк***)** Конструирует `_variant_t` объект из копии `VARIANT` объекта.     Тип variant сохранен.

- **_variant_t (Variant** <strong>\*</strong> *пварсрк***)** конструирует `_variant_t` объект из копии `VARIANT` объекта.     Тип variant сохранен.

- **_variant_t (_variant_t&** *var_t_Src***)** Конструирует `_variant_t` объект из другого `_variant_t` объекта.     Тип variant сохранен.

- **_variant_t (Variant&** *варсрк* **, bool** `fCopy` **)** конструирует `_variant_t` объект из существующего `VARIANT` объекта.       Если *фкопи* имеет значение **`false`** , объект **Variant** присоединяется к новому объекту без создания копии.

- **_variant_t (Short***ССРК* **, VarType** `vtSrc` **= VT_I2)** конструирует `_variant_t` объект типа VT_I2 или VT_BOOL из **`short`** целочисленного значения.       Другие `VARTYPE` результаты в случае ошибки E_INVALIDARG.

- **_variant_t (Long** `lSrc` **, VarType** `vtSrc` **= VT_I4)** конструирует `_variant_t` объект типа VT_I4, VT_BOOL или VT_ERROR из **`long`** целочисленного значения.       Другие `VARTYPE` результаты в случае ошибки E_INVALIDARG.

- **_variant_t (float** `fltSrc` **)** конструирует `_variant_t` объект типа VT_R4 из **`float`** числового значения.    

- **_variant_t (Double** `dblSrc` **, VarType** `vtSrc` **= VT_R8)** конструирует `_variant_t` объект типа VT_R8 или VT_DATE из **`double`** числового значения.       Другие `VARTYPE` результаты в случае ошибки E_INVALIDARG.

- **_variant_t (CY&** `cySrc` **)** конструирует `_variant_t` объект типа VT_CY из `CY` объекта.    

- **_variant_t (_bstr_t&** `bstrSrc` **)** конструирует `_variant_t` объект типа VT_BSTR из `_bstr_t` объекта.     Выделяется новый параметр `BSTR`.

- **_variant_t (wchar_t** <strong>\*</strong> *встрсрк*  **)** конструирует `_variant_t` объект типа VT_BSTR из строки Юникода. Выделяется новый параметр `BSTR`.

- **_variant_t (char** <strong>\*</strong> `strSrc` **)** Конструирует `_variant_t` объект типа VT_BSTR из строки.     Выделяется новый параметр `BSTR`.

- **_variant_t (bool** `bSrc` **)** конструирует `_variant_t` объект типа VT_BOOL из **`bool`** значения.    

- **_variant_t (IUnknown** <strong>\*</strong> `pIUknownSrc` **, bool** `fAddRef` **= true)** Конструирует `_variant_t` объект типа VT_UNKNOWN из указателя COM-интерфейса.       Если `fAddRef` имеет значение **`true`** , то `AddRef` метод вызывается в указанном указателе интерфейса для сопоставления с вызовом `Release` , который будет происходить при `_variant_t` уничтожении объекта. Вам нужно вызвать `Release` по указанному указателю интерфейса. Если `fAddRef` имеет значение **`false`** , этот конструктор принимает владение переданным указателем интерфейса; не вызывайте `Release` указанный указатель интерфейса.

- **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc` **, bool** `fAddRef` **= true)** Конструирует `_variant_t` объект типа VT_DISPATCH из указателя COM-интерфейса.       Если `fAddRef` имеет значение **`true`** , то `AddRef` метод вызывается в указанном указателе интерфейса для сопоставления с вызовом `Release` , который будет происходить при `_variant_t` уничтожении объекта. Вам нужно вызвать `Release` по указанному указателю интерфейса. Если `fAddRef` имеет значение **`false`** , этот конструктор принимает владение переданным указателем интерфейса; не вызывайте `Release` указанный указатель интерфейса.

- **_variant_t (десятичное&** `decSrc` **)** конструирует `_variant_t` объект типа VT_DECIMAL из `DECIMAL` значения.    

- **_variant_t (Byte** `bSrc` **)** конструирует `_variant_t` объект типа `VT_UI1` из `BYTE` значения.    

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)
