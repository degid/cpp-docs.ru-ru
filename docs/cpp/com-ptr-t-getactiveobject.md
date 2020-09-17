---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: ea8059a039b77811dd54d4a4937ad746b7ca0937
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170805"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Блок, относящийся только к системам Microsoft**

Присоединяется к существующему экземпляру объекта, заданному `CLSID` или `ProgID`.

## <a name="syntax"></a>Синтаксис

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>Параметры

*рклсид*<br/>
`CLSID` объекта.

*клсидстринг*<br/>
Строка в Юникоде, содержащая либо `CLSID` (начиная с " **{** "), либо `ProgID`.

*клсидстринга*<br/>
Многобайтовая строка, в которой используется кодовая страница ANSI, содержащая либо `CLSID` (начиная с " **{** "), либо `ProgID`.

## <a name="remarks"></a>Примечания

Эти функции-члены вызывают **жетактивеобжект** , чтобы получить указатель на запущенный объект, зарегистрированный в OLE, а затем запрашивает тип интерфейса этого интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя. Эта подпрограммы возвращает значение HRESULT для обозначения успеха или неудачи.

- **Жетактивеобжект (** `rclsid` **)** Присоединяет к существующему экземпляру объекта при наличии `CLSID`.

- **Жетактивеобжект (** `clsidString` **)** Присоединяет к существующему экземпляру объекта при наличии строки в Юникоде, содержащей `CLSID` (начиная с " **{** ") или `ProgID`.

- **Жетактивеобжект (** `clsidStringA` **)** Присоединяет к существующему экземпляру объекта при наличии строки многобайтовых символов, содержащей либо `CLSID` (начиная с " **{** "), либо `ProgID`. Вызывает [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка находится в кодовой странице ANSI, а не на кодовой странице OEM.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
