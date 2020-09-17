---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 2ec4e90c8f0c1009cc47e9022a09b3b8f7dbb284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190005"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Блок, относящийся только к системам Microsoft**

Создает новый экземпляр объекта с заданным `CLSID` или `ProgID`.

## <a name="syntax"></a>Синтаксис

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>Параметры

*рклсид*<br/>
`CLSID` объекта.

*клсидстринг*<br/>
Строка в Юникоде, содержащая либо `CLSID` (начиная с " **{** "), либо `ProgID`.

*клсидстринга*<br/>
Многобайтовая строка, в которой используется кодовая страница ANSI, содержащая либо `CLSID` (начиная с " **{** "), либо `ProgID`.

*двклсконтекст*<br/>
Контекст для выполняющегося исполняемого кода.

*паутер*<br/>
Внешняя неизвестная для [агрегирования](../atl/aggregation.md).

## <a name="remarks"></a>Примечания

Эти функции-члены вызывают `CoCreateInstance` для создания нового COM-объект, а затем запрашивают тип интерфейса данного интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя. Эта подпрограммы возвращает значение HRESULT для обозначения успеха или неудачи.

- **CreateInstance (**  *рклсид* **,**  *двклсконтекст*  **)** Создает новый выполняющийся экземпляр объекта, заданный `CLSID`.

- **CreateInstance (**  *клсидстринг* **,**  *двклсконтекст*  **)** Создает новый запущенный экземпляр объекта, учитывая строку в Юникоде, содержащую `CLSID` (начиная с " **{** ") или `ProgID`.

- **CreateInstance (**  *клсидстринга* **,**  *двклсконтекст*  **)** Создает новый запущенный экземпляр объекта, используя многобайтовую строку символов, содержащую `CLSID` (начиная с " **{** ") или `ProgID`. Вызывает [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка находится в кодовой странице ANSI, а не на кодовой странице OEM.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
